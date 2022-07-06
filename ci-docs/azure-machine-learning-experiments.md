---
title: Использование моделей на основе машинного обучения Azure
description: Используйте модели на основе машинного обучения Azure в Dynamics 365 Customer Insights.
ms.date: 12/02/2021
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a1efad2887a02a92ee2960b07b066edc331f3665
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081321"
---
# <a name="use-azure-machine-learning-based-models"></a>Использование моделей на основе машинного обучения Azure

Единые данные в Dynamics 365 Customer Insights являются источником для построения моделей машинного обучения, которые могут дать дополнительную бизнес-аналитику. Customer Insights интегрируется с машинным обучением Azure для использования ваших собственных моделей.

## <a name="prerequisites"></a>Предварительные условия

- Доступ к Customer Insights
- Активная подписка Azure Enterprise
- [Объединенные профили клиента](data-unification.md)
- [Экспорт объекта в хранилище BLOB-объектов Azure](export-azure-blob-storage.md) настроен

## <a name="set-up-azure-machine-learning-workspace"></a>Настройка рабочей области машинного обучения Azure

1. Разные варианты создания рабочей области см. в разделе [Создание рабочей области машинного обучения Azure](/azure/machine-learning/concept-workspace#-create-a-workspace). Для обеспечения максимальной производительности создайте рабочую область в регионе Azure, который географически ближе всего к вашей среде Customer Insights.

1. Получите доступ к своей рабочей области через [студию машинного обучения Azure](https://ml.azure.com/). Есть несколько [способов взаимодействия](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) с вашей рабочей областью.

## <a name="work-with-azure-machine-learning-designer"></a>Работа с конструктором машинного обучения Azure

Конструктор Машинного обучения Azure — это визуальный холст, на который можно перетаскивать наборы данных и модули. Пакетный конвейер, созданный конструктором, может быть интегрирован в Customer Insights, если он настроен соответствующим образом. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Работа с пакетом SDK машинного обучения Azure

Специалисты по обработке данных и разработчики ИИ используют [пакет SDK машинного обучения SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) для создания рабочих процессов машинного обучения. В настоящее время модели, обученные с помощью пакета SDK, нельзя напрямую интегрировать в Customer Insights. Конвейер пакетного вывода, который использует эту модель, необходим для интеграции с Customer Insights.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Требования к конвейеру пакетной обработки для интеграции с Customer Insights

### <a name="dataset-configuration"></a>Конфигурация набора данных

Вам необходимо создать наборы данных, чтобы использовать данные сущности из Customer Insights в конвейере пакетного вывода. Эти наборы данных необходимо зарегистрировать в рабочей области. В настоящее время мы поддерживаем только [табличные наборы данных](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) в формате CSV. Наборы данных, соответствующие данным сущности, необходимо параметризовать как параметр конвейера.
   
* Параметры набора данных в конструкторе
   
     В конструкторе откройте **Выбрать столбцы в наборе данных** и выберите **Задать как параметр конвейера**, где вы указываете имя параметра.

     > [!div class="mx-imgBorder"]
     > ![Параметризация набора данных в конструкторе.](media/intelligence-designer-dataset-parameters.png "Параметризация набора данных в конструкторе")
   
* Параметр набора данных в SDK (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Конвейер пакетного вывода
  
* В конструкторе конвейер обучения можно использовать для создания или обновления конвейера вывода. В настоящее время поддерживаются только конвейеры пакетного вывода.

* Используя SDK, вы можете опубликовать конвейер в конечной точке. В настоящее время Customer Insights интегрируется с конвейером по умолчанию в конечной точке конвейера пакетной обработки в рабочей области машинного обучения.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Импорт данных конвейера в Customer Insights

* Конструктор содержит [Модуль экспорта данных](/azure/machine-learning/algorithm-module-reference/export-data), который позволяет экспортировать выходные данные конвейера в хранилище Azure. В настоящее время модуль должен использовать тип хранилища данных **Хранилище BLOB-объектов Azure** и параметризовать **Хранилище данных** и относительный **Путь**. Customer Insights переопределяет оба этих параметра во время выполнения конвейера с помощью хранилища данных и пути, доступного для продукта.
   > [!div class="mx-imgBorder"]
   > ![Экспорт конфигурации модуля данных.](media/intelligence-designer-importdata.png "Экспорт конфигурации модуля данных")
   
* При создании выходных данных с использованием кода вы можете отправить выходные данные по пути в пределах *зарегистрированного хранилища данных* в рабочей области. Если путь и хранилище данных параметризованы в конвейере, Customer Insights сможет считывать и импортировать выходные данные вывода. В настоящее время поддерживается единый табличный вывод в формате CSV. Путь должен включать каталог и имя файла.

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE [footer-include](includes/footer-banner.md)]