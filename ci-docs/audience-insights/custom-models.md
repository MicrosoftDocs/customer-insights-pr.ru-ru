---
title: Пользовательские модели машинного обучения | Документация Майкрософт
description: Работа с пользовательскими моделями из машинного обучения Azure в Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668919"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="6c9ba-103">Пользовательские модели машинного обучения</span><span class="sxs-lookup"><span data-stu-id="6c9ba-103">Custom machine learning models</span></span>

<span data-ttu-id="6c9ba-104">**Аналитика** > **Пользовательские Модели** позволяет управлять бизнес-процессами на основе моделей машинного обучения Azure.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="6c9ba-105">Бизнес-процессы помогают выбрать данные, на основе которых вы хотите получать информацию, и сопоставить результаты с вашими объединенными данными о клиентах.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="6c9ba-106">Для получения дополнительной информации о создании пользовательских моделей машинного обучения см. [Использование моделей на основе машинного обучения Azure](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="6c9ba-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="6c9ba-107">Ответственный ИИ</span><span class="sxs-lookup"><span data-stu-id="6c9ba-107">Responsible AI</span></span>

<span data-ttu-id="6c9ba-108">Прогнозы предлагают возможности для повышения качества обслуживания клиентов, улучшения бизнес-возможностей и потоков доходов.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="6c9ba-109">Мы настоятельно рекомендуем вам сбалансировать ценность вашего прогноза с учетом влияния, которое он оказывает, и отклонениями, которые могут быть внесены этическим образом.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="6c9ba-110">Узнайте больше о том, как Microsoft [работает с ответственным ИИ](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="6c9ba-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="6c9ba-111">Вы также можете узнать о [методах и процессах для ответственного машинного обучения](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml), относящегося к машинному обучению Azure.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6c9ba-112">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="6c9ba-112">Prerequisites</span></span>

- <span data-ttu-id="6c9ba-113">В настоящее время эта функция поддерживает веб-службы, опубликованные через [студию машинного обучения (классическую)](https://studio.azureml.net) и [пакетные конвейеры машинного обучения Azure](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="6c9ba-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="6c9ba-114">Для использования этой функции вам потребуется учетная запись хранения Azure Data Lake Gen2, связанная с экземпляром Azure Studio.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="6c9ba-115">Для получения дополнительной информации см. раздел [Создание учетной записи хранения Azure Data Lake Storage 2-го поколения](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="6c9ba-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="6c9ba-116">Добавление нового рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="6c9ba-116">Add a new workflow</span></span>

1. <span data-ttu-id="6c9ba-117">Перейти к **Аналитика** > **Пользовательские модели** и выберите **Создать бизнес-процесс**.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="6c9ba-118">Дайте вашей пользовательской модели узнаваемое имя в поле **Имя**.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6c9ba-119">![Снимок экрана: область "Новый бизнес-процесс"](media/new-workflowv2.png "Снимок экрана: область "Новый бизнес-процесс"")</span><span class="sxs-lookup"><span data-stu-id="6c9ba-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="6c9ba-120">Выберите организацию, которая содержит веб-сервис в **Клиенте, содержащий ваш веб-сервис**.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="6c9ba-121">Если ваша подписка Azure Machine Learning находится в другом клиенте, нежели Customer Insights, выберите **Войти** с вашими учетными данными для выбранной организации.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="6c9ba-122">Выберите **Рабочие области**, связанные с вашей веб-службой.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="6c9ba-123">В списке есть два раздела: один для машинного обучения Azure v1 (студия машинного обучения (классическая)) и машинного обучения Azure v2 (машинное обучение Azure).</span><span class="sxs-lookup"><span data-stu-id="6c9ba-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="6c9ba-124">Если вы не уверены, какая рабочая область подходит для вашей веб-службы студии машинного обучения (классической), выберите **Любая**.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="6c9ba-125">Выберите веб-службу студии машинного обучения (классической) или конвейер машинного обучения Azure в раскрывающемся списке **Веб-служба, содержащая вашу модель**.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="6c9ba-126">Затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="6c9ba-127">Узнать больше о [публикации веб-службы в студии машинного обучения (классической)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="6c9ba-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="6c9ba-128">Узнать больше о [публикации конвейера в машинном обучении Azure с помощью конструктора](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) или [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="6c9ba-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> 
     > [!NOTE]
     > <span data-ttu-id="6c9ba-129">Ваш конвейер должен быть опубликован в [конечной точке конвейера](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="6c9ba-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="6c9ba-130">Для каждого пункта **Входные данные веб-службы** выберите соответствующую **Сущность** из аналитики аудитории и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6c9ba-131">![Настройка рабочего процесса](media/intelligence-screen2-updated.png "Настройка рабочего процесса")</span><span class="sxs-lookup"><span data-stu-id="6c9ba-131">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="6c9ba-132">На этапе **Параметры выходных данных модели** задайте следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="6c9ba-132">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="6c9ba-133">Студия машинного обучения (классическая версия)</span><span class="sxs-lookup"><span data-stu-id="6c9ba-133">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="6c9ba-134">Введите выходные данные **Имя сущности**, куда должны направляться выходные результаты веб-службы.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-134">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="6c9ba-135">Машинное обучение Azure</span><span class="sxs-lookup"><span data-stu-id="6c9ba-135">Azure Machine Learning</span></span>
      1. <span data-ttu-id="6c9ba-136">Введите выходные данные **Имя сущности**, куда должны направляться выходные результаты конвейера.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-136">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="6c9ba-137">Выберите **Имя параметра хранилища выходных данных** для вашего пакетного конвейера в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-137">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="6c9ba-138">Выберите **Имя параметра пути выходных данных** для вашего пакетного конвейера в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-138">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="6c9ba-139">![Панель параметров выходных данных модели](media/intelligence-screen3-outputparameters.png "Панель параметров выходных данных модели")</span><span class="sxs-lookup"><span data-stu-id="6c9ba-139">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="6c9ba-140">Выберите соответствующий атрибут из раскрывающегося списка **Идентификатор клиента в результатах**, который определяет клиентов и выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-140">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6c9ba-141">![Связь результатов с областью данных клиентов](media/intelligence-screen4-relatetocustomer.png "Связь результатов с областью данных клиентов")</span><span class="sxs-lookup"><span data-stu-id="6c9ba-141">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="6c9ba-142">Вы увидите экран **бизнес-процесс сохранен** с подробной информацией о бизнес-процессе.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-142">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="6c9ba-143">Если вы настроили бизнес-процесс для конвейера машинного обучения Azure, аналитика аудитории будет прикреплена к рабочей области, содержащей конвейер.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-143">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="6c9ba-144">Аналитика аудитории получит роль **Участник** в рабочей области Azure.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-144">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="6c9ba-145">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-145">Select **Done**.</span></span>

1. <span data-ttu-id="6c9ba-146">Теперь вы можете запустить бизнес-процесс на странице **Пользовательские модели**.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-146">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="6c9ba-147">Изменение рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="6c9ba-147">Edit a workflow</span></span>

1. <span data-ttu-id="6c9ba-148">На странице **Пользовательские модели** выберите вертикальное многоточие в столбце **Действия** рядом с ранее созданным рабочим процессом и выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-148">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="6c9ba-149">Вы можете обновить узнаваемое имя бизнес-процесса в поле **Отображаемое имя**, но вы не можете изменить настроенную веб-службу или конвейер.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-149">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="6c9ba-150">Выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-150">Select **Next**.</span></span>

1. <span data-ttu-id="6c9ba-151">Для каждого пункта **Входные данные веб-службы** можно обновить соответствующую **Сущность** из аналитики аудитории.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-151">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="6c9ba-152">Затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-152">Then, select **Next**.</span></span>

1. <span data-ttu-id="6c9ba-153">На этапе **Параметры выходных данных модели** задайте следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="6c9ba-153">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="6c9ba-154">Студия машинного обучения (классическая версия)</span><span class="sxs-lookup"><span data-stu-id="6c9ba-154">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="6c9ba-155">Введите выходные данные **Имя сущности**, куда должны направляться выходные результаты веб-службы.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-155">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="6c9ba-156">Машинное обучение Azure</span><span class="sxs-lookup"><span data-stu-id="6c9ba-156">Azure Machine Learning</span></span>
      1. <span data-ttu-id="6c9ba-157">Введите выходные данные **Имя сущности**, куда должны направляться выходные результаты конвейера.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-157">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="6c9ba-158">Выберите **Имя параметра хранилища выходных данных** для вашего тестового конвейера.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-158">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="6c9ba-159">Выберите **Имя параметра пути выходных данных** для вашего тестового конвейера.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-159">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="6c9ba-160">Выберите соответствующий атрибут из раскрывающегося списка **Идентификатор клиента в результатах**, который определяет клиентов и выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-160">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="6c9ba-161">Вам необходимо выбрать атрибут из выходных данных со значениями, аналогичными столбцу "Идентификатор клиента" сущности "Клиент".</span><span class="sxs-lookup"><span data-stu-id="6c9ba-161">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="6c9ba-162">Если в вашем наборе данных нет такого столбца, выберите атрибут, который однозначно идентифицирует строку.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-162">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="6c9ba-163">Запуск бизнес-процесса</span><span class="sxs-lookup"><span data-stu-id="6c9ba-163">Run a workflow</span></span>

1. <span data-ttu-id="6c9ba-164">На странице **Пользовательские модели** выберите вертикальное многоточие в столбце **Действия** рядом с ранее созданным рабочим процессом.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-164">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="6c9ba-165">Выберите **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-165">Select **Run**.</span></span>

<span data-ttu-id="6c9ba-166">Ваш бизнес-процесс также запускается автоматически при каждом запланированном обновлении.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-166">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="6c9ba-167">Дополнительные сведения о [настройке запланированных обновлений](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6c9ba-167">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="6c9ba-168">Удаление рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="6c9ba-168">Delete a workflow</span></span>

1. <span data-ttu-id="6c9ba-169">На странице **Пользовательские модели** выберите вертикальное многоточие в столбце **Действия** рядом с ранее созданным рабочим процессом.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="6c9ba-170">Выберите **Удалить** и подтвердите удаление.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-170">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="6c9ba-171">Ваш рабочий процесс будет удален.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-171">Your workflow will be deleted.</span></span> <span data-ttu-id="6c9ba-172">[Сущность](entities.md), созданная при создании рабочего процесса, сохраняется, и ее можно просмотреть на странице **Сущности**.</span><span class="sxs-lookup"><span data-stu-id="6c9ba-172">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>
