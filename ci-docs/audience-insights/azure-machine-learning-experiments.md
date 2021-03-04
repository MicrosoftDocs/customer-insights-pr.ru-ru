---
title: Эксперименты в машинном обучении Azure
description: Используйте модели на основе машинного обучения Azure в Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: c166015b92596da0c6097e3d25e89579a5186ce0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267922"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="24df9-103">Использование моделей на основе машинного обучения Azure</span><span class="sxs-lookup"><span data-stu-id="24df9-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="24df9-104">Единые данные в Dynamics 365 Customer Insights являются источником для построения моделей машинного обучения, которые могут дать дополнительную бизнес-аналитику.</span><span class="sxs-lookup"><span data-stu-id="24df9-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="24df9-105">Customer Insights интегрируется со студией машинного обучения (классической) и машинным обучением Azure для использования ваших собственных настраиваемых моделей.</span><span class="sxs-lookup"><span data-stu-id="24df9-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="24df9-106">Примеры экспериментов, проведенных в студии машинного обучения (классической) см. в [Эксперименты в студии машинного обучения (классической)](machine-learning-studio-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="24df9-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="24df9-107">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="24df9-107">Prerequisites</span></span>

- <span data-ttu-id="24df9-108">Доступ к Customer Insights</span><span class="sxs-lookup"><span data-stu-id="24df9-108">Access to Customer Insights</span></span>
- <span data-ttu-id="24df9-109">Активная подписка Azure Enterprise</span><span class="sxs-lookup"><span data-stu-id="24df9-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="24df9-110">Объединенные профили клиента</span><span class="sxs-lookup"><span data-stu-id="24df9-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="24df9-111">[Экспорт объекта в хранилище BLOB-объектов Azure](export-azure-blob-storage.md) настроен</span><span class="sxs-lookup"><span data-stu-id="24df9-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="24df9-112">Настройка рабочей области машинного обучения Azure</span><span class="sxs-lookup"><span data-stu-id="24df9-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="24df9-113">Разные варианты создания рабочей области см. в разделе [Создание рабочей области машинного обучения Azure](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace).</span><span class="sxs-lookup"><span data-stu-id="24df9-113">See [create a Azure Machine Learning workspace](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="24df9-114">Для обеспечения максимальной производительности создайте рабочую область в регионе Azure, который географически ближе всего к вашей среде Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="24df9-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="24df9-115">Получите доступ к своей рабочей области через [студию машинного обучения Azure](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="24df9-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="24df9-116">Есть несколько [способов взаимодействия](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) с вашей рабочей областью.</span><span class="sxs-lookup"><span data-stu-id="24df9-116">There are several [ways to interact](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="24df9-117">Работа с конструктором машинного обучения Azure</span><span class="sxs-lookup"><span data-stu-id="24df9-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="24df9-118">Конструктор машинного обучения Azure предоставляет собой визуальный холст, на котором можно перетаскивать наборы данных и модули как в студии машинного обучения (классической).</span><span class="sxs-lookup"><span data-stu-id="24df9-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="24df9-119">Пакетный конвейер, созданный конструктором, может быть интегрирован в Customer Insights, если он настроен соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="24df9-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="24df9-120">Работа с пакетом SDK машинного обучения Azure</span><span class="sxs-lookup"><span data-stu-id="24df9-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="24df9-121">Специалисты по обработке данных и разработчики ИИ используют [пакет SDK машинного обучения SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) для создания рабочих процессов машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="24df9-121">Data scientists and AI developers use the [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) to build machine learning workflows.</span></span> <span data-ttu-id="24df9-122">В настоящее время модели, обученные с помощью пакета SDK, нельзя напрямую интегрировать в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="24df9-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="24df9-123">Конвейер пакетного вывода, который использует эту модель, необходим для интеграции с Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="24df9-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="24df9-124">Требования к конвейеру пакетной обработки для интеграции с Customer Insights</span><span class="sxs-lookup"><span data-stu-id="24df9-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="24df9-125">Конфигурация набора данных</span><span class="sxs-lookup"><span data-stu-id="24df9-125">Dataset Configuration</span></span>

<span data-ttu-id="24df9-126">Вам необходимо создать наборы данных, чтобы использовать данные сущности из Customer Insights в конвейере пакетного вывода.</span><span class="sxs-lookup"><span data-stu-id="24df9-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="24df9-127">Эти наборы данных необходимо зарегистрировать в рабочей области.</span><span class="sxs-lookup"><span data-stu-id="24df9-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="24df9-128">В настоящее время мы поддерживаем только [табличные наборы данных](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) в формате CSV.</span><span class="sxs-lookup"><span data-stu-id="24df9-128">Currently, we only support [tabular datasets](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="24df9-129">Наборы данных, соответствующие данным сущности, необходимо параметризовать как параметр конвейера.</span><span class="sxs-lookup"><span data-stu-id="24df9-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="24df9-130">Параметры набора данных в конструкторе</span><span class="sxs-lookup"><span data-stu-id="24df9-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="24df9-131">В конструкторе откройте **Выбрать столбцы в наборе данных** и выберите **Задать как параметр конвейера**, где вы указываете имя параметра.</span><span class="sxs-lookup"><span data-stu-id="24df9-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="24df9-132">![Параметризация набора данных в конструкторе](media/intelligence-designer-dataset-parameters.png "Параметризация набора данных в конструкторе")</span><span class="sxs-lookup"><span data-stu-id="24df9-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="24df9-133">Параметр набора данных в SDK (Python)</span><span class="sxs-lookup"><span data-stu-id="24df9-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="24df9-134">Конвейер пакетного вывода</span><span class="sxs-lookup"><span data-stu-id="24df9-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="24df9-135">В конструкторе конвейер обучения можно использовать для создания или обновления конвейера вывода.</span><span class="sxs-lookup"><span data-stu-id="24df9-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="24df9-136">В настоящее время поддерживаются только конвейеры пакетного вывода.</span><span class="sxs-lookup"><span data-stu-id="24df9-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="24df9-137">Используя SDK, вы можете опубликовать конвейер в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="24df9-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="24df9-138">В настоящее время Customer Insights интегрируется с конвейером по умолчанию в конечной точке конвейера пакетной обработки в рабочей области машинного обучения.</span><span class="sxs-lookup"><span data-stu-id="24df9-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="24df9-139">Импорт данных конвейера в Customer Insights</span><span class="sxs-lookup"><span data-stu-id="24df9-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="24df9-140">Конструктор содержит [Модуль экспорта данных](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data), который позволяет экспортировать выходные данные конвейера в хранилище Azure.</span><span class="sxs-lookup"><span data-stu-id="24df9-140">The designer provides the [Export Data module](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="24df9-141">В настоящее время модуль должен использовать тип хранилища данных **Хранилище BLOB-объектов Azure** и параметризовать **Хранилище данных** и относительный **Путь**.</span><span class="sxs-lookup"><span data-stu-id="24df9-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="24df9-142">Customer Insights переопределяет оба этих параметра во время выполнения конвейера с помощью хранилища данных и пути, доступного для продукта.</span><span class="sxs-lookup"><span data-stu-id="24df9-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="24df9-143">![Экспорт конфигурации модуля данных](media/intelligence-designer-importdata.png "Экспорт конфигурации модуля данных")</span><span class="sxs-lookup"><span data-stu-id="24df9-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="24df9-144">При создании выходных данных с использованием кода вы можете отправить выходные данные по пути в пределах *зарегистрированного хранилища данных* в рабочей области.</span><span class="sxs-lookup"><span data-stu-id="24df9-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="24df9-145">Если путь и хранилище данных параметризованы в конвейере, Customer Insights сможет считывать и импортировать выходные данные вывода.</span><span class="sxs-lookup"><span data-stu-id="24df9-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="24df9-146">В настоящее время поддерживается единый табличный вывод в формате CSV.</span><span class="sxs-lookup"><span data-stu-id="24df9-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="24df9-147">Путь должен включать каталог и имя файла.</span><span class="sxs-lookup"><span data-stu-id="24df9-147">The path must include the directory and filename.</span></span>

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]