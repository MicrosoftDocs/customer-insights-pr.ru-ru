---
title: Руководство по прогнозу рекомендаций продуктов
description: Используйте этот пример руководства, чтобы попробовать готовую модель прогноза рекомендаций продуктов.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b136084316da5ae17a8428236381f69e5c21f9ea
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129915"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="97cc3-103">Руководство по прогнозу рекомендаций продуктов (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="97cc3-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="97cc3-104">Мы покажем вам комплексный пример прогноза рекомендаций продуктов, используя примеры данных, представленные ниже.</span><span class="sxs-lookup"><span data-stu-id="97cc3-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="97cc3-105">Сценарий</span><span class="sxs-lookup"><span data-stu-id="97cc3-105">Scenario</span></span>

<span data-ttu-id="97cc3-106">Contoso компания, производящая кофе и кофемашины высокого качества, которые они продают через свой веб-сайт Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="97cc3-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="97cc3-107">Их цель — понять, какие продукты они должны рекомендовать своим постоянным клиентам.</span><span class="sxs-lookup"><span data-stu-id="97cc3-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="97cc3-108">Знание того, какие клиенты, **скорее всего, совершат покупку**, может помочь им сэкономить маркетинговые ресурсы, сосредоточив внимание на конкретных товарах.</span><span class="sxs-lookup"><span data-stu-id="97cc3-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="97cc3-109">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="97cc3-109">Prerequisites</span></span>

- <span data-ttu-id="97cc3-110">По крайней мере [разрешения участника](permissions.md) в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="97cc3-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="97cc3-111">Мы рекомендуем вам выполнить следующие шаги [в новой среде](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="97cc3-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="97cc3-112">Задача 1. Прием данных</span><span class="sxs-lookup"><span data-stu-id="97cc3-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="97cc3-113">Просмотрите статьи [о приеме данных](data-sources.md) и [импорте источников данных с помощью соединителей Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="97cc3-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="97cc3-114">Следующая информация предполагает, что вы в целом ознакомились с приемом данных.</span><span class="sxs-lookup"><span data-stu-id="97cc3-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="97cc3-115">Получение данных о клиентах с платформы eCommerce</span><span class="sxs-lookup"><span data-stu-id="97cc3-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="97cc3-116">Создайте источник данных с именем **eCommerce**, выберите вариант импорта и выберите соединитель **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="97cc3-117">Введите URL-адрес для контактов eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="97cc3-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="97cc3-118">При редактировании данных выберите **Преобразовать**, затем **Использовать первую строку в качестве заголовков**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="97cc3-119">Обновите тип данных для столбцов, перечисленных ниже:</span><span class="sxs-lookup"><span data-stu-id="97cc3-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="97cc3-120">**DateOfBirth**: дата</span><span class="sxs-lookup"><span data-stu-id="97cc3-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="97cc3-121">**CreatedOn**: дата/время/часовой пояс</span><span class="sxs-lookup"><span data-stu-id="97cc3-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Преобразовать дату рождения в дату.":::

5. <span data-ttu-id="97cc3-123">В поле "Имя" на правой панели переименуйте свой источник данных с **Query** на **eCommerceContacts**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="97cc3-124">**Сохраните** источник данных.</span><span class="sxs-lookup"><span data-stu-id="97cc3-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="97cc3-125">Получение данных о покупках в Интернете</span><span class="sxs-lookup"><span data-stu-id="97cc3-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="97cc3-126">Добавьте другой набор данных к тому же источнику данных **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="97cc3-127">Снова выберите соединитель **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="97cc3-128">Введите URL-адрес для данных **Интернет-покупки** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="97cc3-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="97cc3-129">При редактировании данных выберите **Преобразовать**, затем **Использовать первую строку в качестве заголовков**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="97cc3-130">Обновите тип данных для столбцов, перечисленных ниже:</span><span class="sxs-lookup"><span data-stu-id="97cc3-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="97cc3-131">**PurchasedOn**: дата/время</span><span class="sxs-lookup"><span data-stu-id="97cc3-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="97cc3-132">**TotalPrice**: валюта</span><span class="sxs-lookup"><span data-stu-id="97cc3-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="97cc3-133">В поле **Имя** на боковой панели переименуйте свой источник данных с **Query** на **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="97cc3-134">**Сохраните** источник данных.</span><span class="sxs-lookup"><span data-stu-id="97cc3-134">**Save** the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="97cc3-135">Получение данных о клиентах из схемы лояльности</span><span class="sxs-lookup"><span data-stu-id="97cc3-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="97cc3-136">Создайте источник данных с именем **LoyaltyScheme**, выберите вариант импорта и выберите соединитель **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="97cc3-137">Введите URL-адрес для контактов eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="97cc3-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="97cc3-138">При редактировании данных выберите **Преобразовать**, затем **Использовать первую строку в качестве заголовков**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="97cc3-139">Обновите тип данных для столбцов, перечисленных ниже:</span><span class="sxs-lookup"><span data-stu-id="97cc3-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="97cc3-140">**DateOfBirth**: дата</span><span class="sxs-lookup"><span data-stu-id="97cc3-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="97cc3-141">**RewardsPoints**: целое число</span><span class="sxs-lookup"><span data-stu-id="97cc3-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="97cc3-142">**CreatedOn**: дата/время</span><span class="sxs-lookup"><span data-stu-id="97cc3-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="97cc3-143">В поле **Имя** на правой панели переименуйте свой источник данных с **Query** на **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="97cc3-144">**Сохраните** источник данных.</span><span class="sxs-lookup"><span data-stu-id="97cc3-144">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="97cc3-145">Задача 2. Унификация данных</span><span class="sxs-lookup"><span data-stu-id="97cc3-145">Task 2 - Data unification</span></span>

<span data-ttu-id="97cc3-146">После приема данных мы начинаем процесс объединения данных для создания единого профиля клиента.</span><span class="sxs-lookup"><span data-stu-id="97cc3-146">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="97cc3-147">Дополнительные сведения см. в разделе [Унификация данных](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="97cc3-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="97cc3-148">Сопоставление</span><span class="sxs-lookup"><span data-stu-id="97cc3-148">Map</span></span>

1. <span data-ttu-id="97cc3-149">После приема данных сопоставьте контакты из данных eCommerce и лояльности с общими типами данных.</span><span class="sxs-lookup"><span data-stu-id="97cc3-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="97cc3-150">Перейдите **Данные** > **Унификация** > **Сопоставление**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="97cc3-151">Выберите сущности, которые представляют профиль клиента — **eCommerceContacts** и **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![унифицировать источники данных ecommerce и лояльности.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="97cc3-153">Выберите **ContactId** как первичный ключ для **eCommerceContacts**, а **LoyaltyID** как первичный ключ для **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Унифицируйте LoyaltyId как первичный ключ.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="97cc3-155">Совпадение найдено</span><span class="sxs-lookup"><span data-stu-id="97cc3-155">Match</span></span>

1. <span data-ttu-id="97cc3-156">Перейдите на вкладку **Совпадение** и выберите **Задать порядок**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="97cc3-157">В раскрывающемся списке **Первичный** выберите **eCommerceContacts : eCommerce** в качестве первичного источника и включите все записи.</span><span class="sxs-lookup"><span data-stu-id="97cc3-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="97cc3-158">В раскрывающемся списке **Сущность 2** выберите **loyCustomers: LoyaltyScheme** и включите все записи.</span><span class="sxs-lookup"><span data-stu-id="97cc3-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Унифицировать совпадение eCommerce и лояльности.](media/unify-match-order.png)

4. <span data-ttu-id="97cc3-160">Выберите **Создать правило**</span><span class="sxs-lookup"><span data-stu-id="97cc3-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="97cc3-161">Добавьте свое первое условие, используя FullName.</span><span class="sxs-lookup"><span data-stu-id="97cc3-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="97cc3-162">Для eCommerceContacts выберите **FullName** в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="97cc3-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="97cc3-163">Для loyCustomers выберите **FullName** в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="97cc3-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="97cc3-164">Выберите раскрывающийся список **Нормализовать** и выберите **Тип (телефон, имя, адрес, ...)**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="97cc3-165">Задайте **Уровень точности**: **Базовый** и **Значение**: **Высоко**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="97cc3-166">Введите имя **FullName, Email** для нового правила.</span><span class="sxs-lookup"><span data-stu-id="97cc3-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="97cc3-167">Добавьте второе условие для адреса электронной почты, выбрав **Добавить условие**</span><span class="sxs-lookup"><span data-stu-id="97cc3-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="97cc3-168">Для сущности eCommerceContacts выберите **EMail** в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="97cc3-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="97cc3-169">Для сущности loyCustomers выберите **EMail** в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="97cc3-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="97cc3-170">Оставьте поле "Нормализация" пустым.</span><span class="sxs-lookup"><span data-stu-id="97cc3-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="97cc3-171">Задайте **Уровень точности**: **Базовый** и **Значение**: **Высоко**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Унифицировать правило совпадения для имени и электронной почты.](media/unify-match-rule.png)

7. <span data-ttu-id="97cc3-173">Выберите **Сохранить** и **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="97cc3-174">Объединение</span><span class="sxs-lookup"><span data-stu-id="97cc3-174">Merge</span></span>

1. <span data-ttu-id="97cc3-175">Перейдите на вкладку **Объединение**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="97cc3-176">В **ContactId** для сущности **loyCustomers** измените отображаемое имя на **ContactIdLOYALTY**, чтобы отличить его от других полученных идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="97cc3-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![Переименовать contactid из идентификатора лояльности.](media/unify-merge-contactid.png)

1. <span data-ttu-id="97cc3-178">Выберите **Сохранить** и **Выполнить**, чтобы начать процесс объединения.</span><span class="sxs-lookup"><span data-stu-id="97cc3-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="97cc3-179">Задача 3. Настройка прогноза рекомендаций продуктов</span><span class="sxs-lookup"><span data-stu-id="97cc3-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="97cc3-180">С унифицированными профилями клиентов теперь мы можем запустить прогноз оттока подписок.</span><span class="sxs-lookup"><span data-stu-id="97cc3-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="97cc3-181">Перейдите **Аналитика** > **Прогноз**, выберите **Рекомендация продукта**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="97cc3-182">Выберите **Приступая к работе**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-182">Select **Get started**.</span></span>

1. <span data-ttu-id="97cc3-183">Назовите модель **Прогноз модели рекомендации продуктов OOB** и сущность выходных данных **OOBProductRecommendationModelPrediction**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="97cc3-184">Определите три условия для модели:</span><span class="sxs-lookup"><span data-stu-id="97cc3-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="97cc3-185">**Количество продуктов**: установите это значение как **5**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="97cc3-186">Этот параметр определяет, сколько продуктов вы хотите рекомендовать своим клиентам.</span><span class="sxs-lookup"><span data-stu-id="97cc3-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="97cc3-187">**Ожидаются повторные покупки**: выберите **Да**, чтобы указать, что вы хотите включить в рекомендацию продукты, которые ваши клиенты покупали ранее.</span><span class="sxs-lookup"><span data-stu-id="97cc3-187">**Repeat purchases expected**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="97cc3-188">**Окно ретроспективного обзора:** выберите не менее **365 дней**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="97cc3-189">Этот параметр определяет, как далеко модель будет анализировать действия клиента, чтобы использовать их в качестве исходных данных для своих рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="97cc3-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Настройки модели для модели рекомендаций по продукту.":::

1. <span data-ttu-id="97cc3-191">Выберите **Необходимые данные** и выберите **Добавить данные** для истории покупок.</span><span class="sxs-lookup"><span data-stu-id="97cc3-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="97cc3-192">Добавьте сущность **eCommercePurchases : eCommerce** и сопоставьте поля из eCommerce с соответствующими полями, необходимыми для модели.</span><span class="sxs-lookup"><span data-stu-id="97cc3-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="97cc3-193">Присоедините сущность **eCommercePurchases : eCommerce** к **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Присоедините сущности eCommerce.](media/model-purchase-join.png)

1. <span data-ttu-id="97cc3-195">Выберите **Далее**, чтобы задать расписание модели.</span><span class="sxs-lookup"><span data-stu-id="97cc3-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="97cc3-196">Модель должна регулярно обучаться, чтобы изучать новые закономерности при поступлении новых данных.</span><span class="sxs-lookup"><span data-stu-id="97cc3-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="97cc3-197">В данном примере выберите **Ежемесячно**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="97cc3-198">Изучив все сведения, выберите **Сохранить и выполнить**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="97cc3-199">Задача 4. Обзор результатов модели и объяснения</span><span class="sxs-lookup"><span data-stu-id="97cc3-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="97cc3-200">Дайте модели завершить обучение и оценку данных.</span><span class="sxs-lookup"><span data-stu-id="97cc3-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="97cc3-201">Теперь вы можете просмотреть объяснения модели рекомендаций продуктов.</span><span class="sxs-lookup"><span data-stu-id="97cc3-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="97cc3-202">Для получения дополнительной информации см. [Просмотр статуса прогноза и результатов](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="97cc3-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="97cc3-203">Задача 5. Создание сегмента часто покупаемых товаров</span><span class="sxs-lookup"><span data-stu-id="97cc3-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="97cc3-204">Выполнение производственной модели создает новую сущность, которую вы можете увидеть в **Данные** > **Сущности**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="97cc3-205">Вы можете создать новый сегмент на основе сущности, созданной моделью.</span><span class="sxs-lookup"><span data-stu-id="97cc3-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="97cc3-206">Перейдите **Сегменты**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-206">Go to **Segments**.</span></span> <span data-ttu-id="97cc3-207">Выберите **Создать** и выберите **Создать из** > **Аналитика**.</span><span class="sxs-lookup"><span data-stu-id="97cc3-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Создание сегмента с выходом модели.](media/segment-intelligence.png)

1. <span data-ttu-id="97cc3-209">Выберите конечную точку **OOBProductRecommendationModelPrediction** и определите сегмент:</span><span class="sxs-lookup"><span data-stu-id="97cc3-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="97cc3-210">Поле: ProductID</span><span class="sxs-lookup"><span data-stu-id="97cc3-210">Field: ProductID</span></span>
   - <span data-ttu-id="97cc3-211">Оператор: Значение</span><span class="sxs-lookup"><span data-stu-id="97cc3-211">Operator: Value</span></span>
   - <span data-ttu-id="97cc3-212">Значение: выберите три первых кода продукта.</span><span class="sxs-lookup"><span data-stu-id="97cc3-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Создайте сегмент из результатов модели.":::

<span data-ttu-id="97cc3-214">Теперь у вас есть динамически обновляемый сегмент, который определяет клиентов, которые более охотно покупают три наиболее рекомендуемых продукта.</span><span class="sxs-lookup"><span data-stu-id="97cc3-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="97cc3-215">Дополнительные сведения см. в разделе [Создание сегментов и управление ими](segments.md).</span><span class="sxs-lookup"><span data-stu-id="97cc3-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
