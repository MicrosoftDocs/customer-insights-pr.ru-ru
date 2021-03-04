---
title: Заполнение частичных данных с помощью прогнозов
description: Используйте прогнозы, чтобы заполнить неполные данные о клиентах.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 577232c7e901dfd54a195c3e9cfac5d1f0f866e6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268288"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="ac88d-103">Дополните частичные данные прогнозами</span><span class="sxs-lookup"><span data-stu-id="ac88d-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ac88d-104">Прогнозы позволяют вам легко создавать прогнозируемые значения, которые могут улучшить ваше понимание клиента.</span><span class="sxs-lookup"><span data-stu-id="ac88d-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="ac88d-105">На странице **Аналитика** > **Прогнозы** вы можете выбрать **Мои прогнозы**, чтобы увидеть прогнозы, которые вы настроили в других частях аналитики аудитории, и дополнительно настроить их.</span><span class="sxs-lookup"><span data-stu-id="ac88d-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="ac88d-106">Эту функцию нельзя использовать, если в вашей среде используется хранилище Azure Data Lake 2-го поколения.</span><span class="sxs-lookup"><span data-stu-id="ac88d-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="ac88d-107">Функция прогнозирования использует автоматизированные средства для оценки данных и прогнозирования на основе этих данных и, следовательно, может использоваться в качестве метода профилирования, как этот термин определяется "Общим регламентом по защите данных" ("GDPR").</span><span class="sxs-lookup"><span data-stu-id="ac88d-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="ac88d-108">Использование клиентом этой функции для обработки данных может регулироваться GDPR или другими законами или правилами.</span><span class="sxs-lookup"><span data-stu-id="ac88d-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="ac88d-109">Вы несете ответственность за то, что использование Dynamics 365 Customer Insights, включая прогнозы, соответствует всем применимым законам и требованиям, включая законы, касающиеся конфиденциальности, личных данных, биометрических данных, защиты данных и конфиденциальности сообщений.</span><span class="sxs-lookup"><span data-stu-id="ac88d-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ac88d-110">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="ac88d-110">Prerequisites</span></span>

<span data-ttu-id="ac88d-111">Прежде чем ваша организация сможет использовать функцию прогнозирования, должны быть выполнены следующие предварительные условия:</span><span class="sxs-lookup"><span data-stu-id="ac88d-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="ac88d-112">В вашей организации есть экземпляр, [созданный в Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites), и он находится в той же организации, что и Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ac88d-112">Your organization has an instance [set up in the Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="ac88d-113">Ваша среда привязана к вашему экземпляру Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ac88d-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="ac88d-114">Если вы [создаете новую среду](manage-environments.md), настройте ее в диалоге **Создание среды** и выберите **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="ac88d-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="ac88d-115">Если вы уже создали среду, перейдите в ее настройки и выберите **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="ac88d-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="ac88d-116">В любом случае, в разделе **Используйте прогнозы** введите URL-адрес экземпляра Common Data Service, к которому вы хотите присоединить свою среду.</span><span class="sxs-lookup"><span data-stu-id="ac88d-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="ac88d-117">Создание прогноза в сущности клиента</span><span class="sxs-lookup"><span data-stu-id="ac88d-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="ac88d-118">В аналитике аудитории перейдите **Данные** > **Сущности**.</span><span class="sxs-lookup"><span data-stu-id="ac88d-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="ac88d-119">Выберите сущность **Клиент**.</span><span class="sxs-lookup"><span data-stu-id="ac88d-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="ac88d-120">В сущности **Клиент: CustomerInsights** выберите вкладку **Поля**.</span><span class="sxs-lookup"><span data-stu-id="ac88d-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="ac88d-121">Найдите имя атрибута, для которого вы хотите прогнозировать значения, затем выберите значок **Обзор** в столбце **Сводка**.</span><span class="sxs-lookup"><span data-stu-id="ac88d-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ac88d-122">![Значок обзора](media/intelligence-overviewicon.png "Значок обзора")</span><span class="sxs-lookup"><span data-stu-id="ac88d-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="ac88d-123">Если для вашего атрибута велика доля пропущенных значений, выберите **Предсказать недостающие значения**, чтобы продолжить с прогнозом.</span><span class="sxs-lookup"><span data-stu-id="ac88d-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ac88d-124">![Состояние обзора с показанной кнопкой предсказания пропущенных значений](media/intelligence-overviewpredictmissingvalues.png "Состояние обзора с показанной кнопкой предсказания пропущенных значений")</span><span class="sxs-lookup"><span data-stu-id="ac88d-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="ac88d-125">Укажите **Отображаемое имя** и **Имя выходной сущности** для результатов прогноза.</span><span class="sxs-lookup"><span data-stu-id="ac88d-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="ac88d-126">Предварительно заполненный список параметров покажет, где можно сопоставить значения с прогнозируемой категорией.</span><span class="sxs-lookup"><span data-stu-id="ac88d-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="ac88d-127">В этом случае ваши единственные параметры категории будут 0 или 1, поскольку они соответствуют значению истина/ложь или двоичному характеру прогноза.</span><span class="sxs-lookup"><span data-stu-id="ac88d-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="ac88d-128">В столбце "Категория" сопоставьте значения полей, которые вы хотите классифицировать как "0" в окончательном прогнозе, со значением "0", а элементы, которые вы хотели бы классифицировать как "1" в окончательном прогнозе, со значением "1".</span><span class="sxs-lookup"><span data-stu-id="ac88d-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ac88d-129">![Пример, показывающий значения полей, сопоставленные категориям](media/intelligence-categorymapping.png "Пример, показывающий значения полей, сопоставленные категориям")</span><span class="sxs-lookup"><span data-stu-id="ac88d-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="ac88d-130">Выберите **Готово**, и прогноз будет обработан.</span><span class="sxs-lookup"><span data-stu-id="ac88d-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="ac88d-131">Обработка займет некоторое время, в зависимости от размера и сложности данных.</span><span class="sxs-lookup"><span data-stu-id="ac88d-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="ac88d-132">Результаты будут доступны в новой сущности на основе значения **Имя выходной сущности** созданного прогноза.</span><span class="sxs-lookup"><span data-stu-id="ac88d-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="ac88d-133">Создание прогноза при создании сегмента</span><span class="sxs-lookup"><span data-stu-id="ac88d-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="ac88d-134">Прогнозирование отсутствующих значений для конкретного выбранного атрибута также возможно при создании сегмента.</span><span class="sxs-lookup"><span data-stu-id="ac88d-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="ac88d-135">В частности, когда вы быстро создаете сегмент на основе единой сущности клиента или сущности меры клиентов.</span><span class="sxs-lookup"><span data-stu-id="ac88d-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="ac88d-136">В рамках этого потока вы выбираете определенный атрибут, на котором будет основываться сегмент, например, удовлетворенность клиентов или сумма покупки.</span><span class="sxs-lookup"><span data-stu-id="ac88d-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="ac88d-137">После создания сегмента система предложит метод прогнозирования любых отсутствующих значений для этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="ac88d-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="ac88d-138">В аналитике аудитории перейдите в **Сегменты** и выберите плитку **Профили**.</span><span class="sxs-lookup"><span data-stu-id="ac88d-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="ac88d-139">Выберите **Поле**, на основе которого создать сегмент, и выберите **Оператор**, затем выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="ac88d-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="ac88d-140">Укажите **Имя** и **Отображаемое имя** для сегмента.</span><span class="sxs-lookup"><span data-stu-id="ac88d-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="ac88d-141">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ac88d-141">Select **Save**.</span></span>

5. <span data-ttu-id="ac88d-142">Если в созданном сегменте есть неполные данные в исходном поле, вы можете выбрать прогнозирование недостающих значений.</span><span class="sxs-lookup"><span data-stu-id="ac88d-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ac88d-143">![Кнопка прогнозирования](media/segments-predictoption.png "Кнопка прогнозирования")</span><span class="sxs-lookup"><span data-stu-id="ac88d-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="ac88d-144">Укажите **Отображаемое имя** и **Имя выходной сущности** для результатов прогноза.</span><span class="sxs-lookup"><span data-stu-id="ac88d-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="ac88d-145">Выберите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="ac88d-145">Select **Done**.</span></span> <span data-ttu-id="ac88d-146">Ваш прогноз будет создан в ближайшее время в новой сущности с именем, которое вы указали в поле **Имя выходной сущности**.</span><span class="sxs-lookup"><span data-stu-id="ac88d-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="ac88d-147">Просмотр прогноза</span><span class="sxs-lookup"><span data-stu-id="ac88d-147">View a prediction</span></span>

1. <span data-ttu-id="ac88d-148">В аналитике аудитории перейдите **Аналитика** > **Прогнозы** > **Мои прогнозы**.</span><span class="sxs-lookup"><span data-stu-id="ac88d-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="ac88d-149">Выберите прогноз, который нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="ac88d-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="ac88d-150">Выберите многоточие в столбце **Действия** и выберите **Посмотреть**.</span><span class="sxs-lookup"><span data-stu-id="ac88d-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="ac88d-151">Вы увидите несколько точек данных в представлении вашего прогноза.</span><span class="sxs-lookup"><span data-stu-id="ac88d-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ac88d-152">![Страница прогнозов](media/intelligence-predictionsviewpage.png "Страница прогнозов")</span><span class="sxs-lookup"><span data-stu-id="ac88d-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="ac88d-153">**Прогнозируемые значения** показывают сопоставление, созданное вами на этапе сопоставления значения поля с категорией.</span><span class="sxs-lookup"><span data-stu-id="ac88d-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="ac88d-154">Это значения в вашем набор данных, которые были сопоставлены с определенной категорией.</span><span class="sxs-lookup"><span data-stu-id="ac88d-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="ac88d-155">-**Главные факторы влияния** — это факторы внутри вашего набор данных, которые, скорее всего, повлияли на достоверность прогноза при сопоставлении значения вашего поля с определенной категорией.</span><span class="sxs-lookup"><span data-stu-id="ac88d-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="ac88d-156">**Производительность** показывает эффективность прогнозов.</span><span class="sxs-lookup"><span data-stu-id="ac88d-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="ac88d-157">Нажмите на ссылку, чтобы узнать больше.</span><span class="sxs-lookup"><span data-stu-id="ac88d-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="ac88d-158">**Предварительный просмотр** показывает образцы выходного набора данных из вашего прогноза, а также вероятность или достоверность прогнозируемого значения, где 0 — неуверенно, а 1 — достоверно.</span><span class="sxs-lookup"><span data-stu-id="ac88d-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="ac88d-159">Обновление прогноза</span><span class="sxs-lookup"><span data-stu-id="ac88d-159">Update a prediction</span></span>

1. <span data-ttu-id="ac88d-160">В аналитике аудитории перейдите **Аналитика** > **Прогнозы** > **Мои прогнозы**.</span><span class="sxs-lookup"><span data-stu-id="ac88d-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="ac88d-161">Выберите прогноз, который вы хотите обновить, и выберите значок **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="ac88d-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="ac88d-162">Прогноз будет запланирован для обработки.</span><span class="sxs-lookup"><span data-stu-id="ac88d-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="ac88d-163">Вы можете увидеть время последнего обновления в столбце **Обновлено** на странице **Прогнозы**.</span><span class="sxs-lookup"><span data-stu-id="ac88d-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="ac88d-164">Изменение прогноза</span><span class="sxs-lookup"><span data-stu-id="ac88d-164">Edit a prediction</span></span>

<span data-ttu-id="ac88d-165">После того как вы создали прогноз, вы можете настроить модель в AI Builder, чтобы повысить эффективность вашей модели.</span><span class="sxs-lookup"><span data-stu-id="ac88d-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="ac88d-166">В аналитике аудитории перейдите **Аналитика** > **Прогнозы** > **Мои прогнозы**.</span><span class="sxs-lookup"><span data-stu-id="ac88d-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="ac88d-167">Выберите прогноз, который нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="ac88d-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="ac88d-168">Выберите многоточие в столбце **Действия** и выберите **Посмотреть**.</span><span class="sxs-lookup"><span data-stu-id="ac88d-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="ac88d-169">Выберите **Настроить в AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="ac88d-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="ac88d-170">Обновите вашу модель в AI Builder.</span><span class="sxs-lookup"><span data-stu-id="ac88d-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="ac88d-171">[Подробнее об управлении моделями в AI Builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="ac88d-171">[Learn more about managing models in the AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="ac88d-172">Следующий прогон вашего прогноза будет использовать обновленную модель, которую вы создали.</span><span class="sxs-lookup"><span data-stu-id="ac88d-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="ac88d-173">Новые модели, созданные в AI Builder, не будут отображаться в аналитике аудитории, если модель не была создана на основе перечисленных выше возможностей.</span><span class="sxs-lookup"><span data-stu-id="ac88d-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="ac88d-174">Удаление прогноза</span><span class="sxs-lookup"><span data-stu-id="ac88d-174">Remove a prediction</span></span>

1. <span data-ttu-id="ac88d-175">В аналитике аудитории перейдите **Аналитика** > **Прогнозы** > **Мои прогнозы**.</span><span class="sxs-lookup"><span data-stu-id="ac88d-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="ac88d-176">Выберите прогноз, который нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="ac88d-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="ac88d-177">Выберите многоточие в столбце **Действия** и выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="ac88d-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="ac88d-178">Подтвердите удаление.</span><span class="sxs-lookup"><span data-stu-id="ac88d-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="ac88d-179">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="ac88d-179">Troubleshooting</span></span>

<span data-ttu-id="ac88d-180">Если вы не можете завершить процесс прикрепления Common Data Service из-за ошибки, вы можете попробовать завершить процесс вручную.</span><span class="sxs-lookup"><span data-stu-id="ac88d-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="ac88d-181">В процессе присоединения могут возникнуть две известные проблемы:</span><span class="sxs-lookup"><span data-stu-id="ac88d-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="ac88d-182">Решение с надстройкой карточки клиента не установлено.</span><span class="sxs-lookup"><span data-stu-id="ac88d-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="ac88d-183">Завершите инструкции, чтобы [установить и настроить решение](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="ac88d-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="ac88d-184">Разрешения приложения не предоставлены.</span><span class="sxs-lookup"><span data-stu-id="ac88d-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="ac88d-185">Перейдите к [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="ac88d-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="ac88d-186">Выберите **Среды**.</span><span class="sxs-lookup"><span data-stu-id="ac88d-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="ac88d-187">Выберите многоточие рядом со средой, для которой вы хотите добавить разрешение, и выберите **Настройки**.</span><span class="sxs-lookup"><span data-stu-id="ac88d-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="ac88d-188">Разверните **Пользователи + разрешения** и выберите **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="ac88d-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="ac88d-189">Выберите **+ Создать** и выберите **Пользователь**.</span><span class="sxs-lookup"><span data-stu-id="ac88d-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="ac88d-190">Выберите **Пользователь приложения**, если он еще не выбран, и введите следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="ac88d-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="ac88d-191">**Имя пользователя:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ac88d-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="ac88d-192">**ИД приложения:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="ac88d-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="ac88d-193">**Имя клиента:** Customer</span><span class="sxs-lookup"><span data-stu-id="ac88d-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="ac88d-194">**Фамилия:** Insights</span><span class="sxs-lookup"><span data-stu-id="ac88d-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="ac88d-195">**Основной адрес электронной почты:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ac88d-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="ac88d-196">Выберите **Сохранить и закрыть**.</span><span class="sxs-lookup"><span data-stu-id="ac88d-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="ac88d-197">Выберите только что созданного пользователя.</span><span class="sxs-lookup"><span data-stu-id="ac88d-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="ac88d-198">Выберите **Управление ролями** в верхней строке меню.</span><span class="sxs-lookup"><span data-stu-id="ac88d-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="ac88d-199">Выберите **Системный администратор**, затем выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ac88d-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]