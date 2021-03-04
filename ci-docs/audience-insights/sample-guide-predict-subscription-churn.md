---
title: Пример руководства по прогнозу оттока подписок
description: Используйте этот пример руководства, чтобы попробовать готовую модель прогноза оттока подписок.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3f1019ace424f89320c5a0d5058e928f4cbc7e62
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269857"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="08f1d-103">Пример руководства по прогнозу оттока подписок (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="08f1d-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="08f1d-104">Мы покажем вам комплексный пример прогноза оттока подписок, используя примеры данных, представленные ниже.</span><span class="sxs-lookup"><span data-stu-id="08f1d-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="08f1d-105">Сценарий</span><span class="sxs-lookup"><span data-stu-id="08f1d-105">Scenario</span></span>

<span data-ttu-id="08f1d-106">Contoso — компания, производящая кофе и кофемашины высокого качества, которые они продают через свой веб-сайт Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="08f1d-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="08f1d-107">Недавно они открыли бизнес по подписке, чтобы клиенты могли получать кофе на регулярной основе.</span><span class="sxs-lookup"><span data-stu-id="08f1d-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="08f1d-108">Их цель — понять, какие клиенты с подпиской могут отменить свою подписку в ближайшие несколько месяцев.</span><span class="sxs-lookup"><span data-stu-id="08f1d-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="08f1d-109">Зная, кто из их клиентов **вероятно уйдет**, они могут сэкономить на маркетинговых усилиях, сосредоточив внимание на их удержании как клиентов.</span><span class="sxs-lookup"><span data-stu-id="08f1d-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="08f1d-110">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="08f1d-110">Prerequisites</span></span>

- <span data-ttu-id="08f1d-111">По крайней мере [разрешения участника](permissions.md) в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="08f1d-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="08f1d-112">Мы рекомендуем вам выполнить следующие шаги [в новой среде](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="08f1d-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="08f1d-113">Задача 1. Прием данных</span><span class="sxs-lookup"><span data-stu-id="08f1d-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="08f1d-114">Просмотрите статьи [о приеме данных](data-sources.md) и [импорте источников данных с помощью соединителей Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="08f1d-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="08f1d-115">Следующая информация предполагает, что вы в целом ознакомились с приемом данных.</span><span class="sxs-lookup"><span data-stu-id="08f1d-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="08f1d-116">Получение данных о клиентах с платформы eCommerce</span><span class="sxs-lookup"><span data-stu-id="08f1d-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="08f1d-117">Создайте источник данных с именем **eCommerce**, выберите вариант импорта и выберите соединитель **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="08f1d-118">Введите URL-адрес для контактов eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="08f1d-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="08f1d-119">При редактировании данных выберите **Преобразовать**, затем **Использовать первую строку в качестве заголовков**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="08f1d-120">Обновите тип данных для столбцов, перечисленных ниже:</span><span class="sxs-lookup"><span data-stu-id="08f1d-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="08f1d-121">**DateOfBirth**: дата</span><span class="sxs-lookup"><span data-stu-id="08f1d-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="08f1d-122">**CreatedOn**: дата/время/часовой пояс</span><span class="sxs-lookup"><span data-stu-id="08f1d-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Преобразовать дату рождения в дату.":::

1. <span data-ttu-id="08f1d-124">В поле **Имя** на правой панели переименуйте свой источник данных с **Query** на **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="08f1d-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="08f1d-125">Сохраните источник данных.</span><span class="sxs-lookup"><span data-stu-id="08f1d-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="08f1d-126">Получение данных о клиентах из схемы лояльности</span><span class="sxs-lookup"><span data-stu-id="08f1d-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="08f1d-127">Создайте источник данных с именем **LoyaltyScheme**, выберите вариант импорта и выберите соединитель **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="08f1d-128">Введите URL-адрес для контактов eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="08f1d-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="08f1d-129">При редактировании данных выберите **Преобразовать**, затем **Использовать первую строку в качестве заголовков**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="08f1d-130">Обновите тип данных для столбцов, перечисленных ниже:</span><span class="sxs-lookup"><span data-stu-id="08f1d-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="08f1d-131">**DateOfBirth**: дата</span><span class="sxs-lookup"><span data-stu-id="08f1d-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="08f1d-132">**RewardsPoints**: целое число</span><span class="sxs-lookup"><span data-stu-id="08f1d-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="08f1d-133">**CreatedOn**: дата/время</span><span class="sxs-lookup"><span data-stu-id="08f1d-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="08f1d-134">В поле **Имя** на правой панели переименуйте свой источник данных с **Query** на **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="08f1d-135">Сохраните источник данных.</span><span class="sxs-lookup"><span data-stu-id="08f1d-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="08f1d-136">Прием информации о подписке</span><span class="sxs-lookup"><span data-stu-id="08f1d-136">Ingest subscription information</span></span>

1. <span data-ttu-id="08f1d-137">Создайте источник данных с именем **SubscriptionHistory**, выберите вариант импорта и выберите соединитель **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="08f1d-138">Введите URL-адрес для контактов eCommerce https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="08f1d-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="08f1d-139">При редактировании данных выберите **Преобразовать**, затем **Использовать первую строку в качестве заголовков**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="08f1d-140">Обновите тип данных для столбцов, перечисленных ниже:</span><span class="sxs-lookup"><span data-stu-id="08f1d-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="08f1d-141">**SubscriptioID**: целое число</span><span class="sxs-lookup"><span data-stu-id="08f1d-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="08f1d-142">**SubscriptionAmount**: валюта</span><span class="sxs-lookup"><span data-stu-id="08f1d-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="08f1d-143">**SubscriptionEndDate**: дата/время</span><span class="sxs-lookup"><span data-stu-id="08f1d-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="08f1d-144">**SubscriptionStartDate**: дата/время</span><span class="sxs-lookup"><span data-stu-id="08f1d-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="08f1d-145">**TransactionDate**: дата/время</span><span class="sxs-lookup"><span data-stu-id="08f1d-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="08f1d-146">**IsRecurring**: True/False</span><span class="sxs-lookup"><span data-stu-id="08f1d-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="08f1d-147">**Is_auto_renew**: True/False</span><span class="sxs-lookup"><span data-stu-id="08f1d-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="08f1d-148">**RecurringFrequencyInMonths**: целое число</span><span class="sxs-lookup"><span data-stu-id="08f1d-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="08f1d-149">В поле **Имя** на правой панели переименуйте свой источник данных с **Query** на **SubscriptionHistory**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="08f1d-150">Сохраните источник данных.</span><span class="sxs-lookup"><span data-stu-id="08f1d-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="08f1d-151">Получение данных о клиентах из отзывов веб-сайтов</span><span class="sxs-lookup"><span data-stu-id="08f1d-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="08f1d-152">Создайте источник данных с именем **Website**, выберите вариант импорта и выберите соединитель **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="08f1d-153">Введите URL-адрес для контактов eCommerce https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="08f1d-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="08f1d-154">При редактировании данных выберите **Преобразовать**, затем **Использовать первую строку в качестве заголовков**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="08f1d-155">Обновите тип данных для столбцов, перечисленных ниже:</span><span class="sxs-lookup"><span data-stu-id="08f1d-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="08f1d-156">**ReviewRating**: целое число</span><span class="sxs-lookup"><span data-stu-id="08f1d-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="08f1d-157">**ReviewDate**: дата</span><span class="sxs-lookup"><span data-stu-id="08f1d-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="08f1d-158">В поле "Имя" на правой панели переименуйте свой источник данных с **Query** на **webReviews**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="08f1d-159">Задача 2. Унификация данных</span><span class="sxs-lookup"><span data-stu-id="08f1d-159">Task 2 - Data unification</span></span>

<span data-ttu-id="08f1d-160">После приема данных мы запускаем процесс **Сопоставление, совпадение, объединение** для создания унифицированного профиля клиента.</span><span class="sxs-lookup"><span data-stu-id="08f1d-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="08f1d-161">Дополнительные сведения см. в разделе [Унификация данных](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="08f1d-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="08f1d-162">Сопоставление</span><span class="sxs-lookup"><span data-stu-id="08f1d-162">Map</span></span>

1. <span data-ttu-id="08f1d-163">После приема данных сопоставьте контакты из данных eCommerce и лояльности с общими типами данных.</span><span class="sxs-lookup"><span data-stu-id="08f1d-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="08f1d-164">Перейдите **Данные** > **Унификация** > **Сопоставление**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="08f1d-165">Выберите сущности, которые представляют профиль клиента — **eCommerceContacts** и **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="унифицировать источники данных ecommerce и лояльности.":::

1. <span data-ttu-id="08f1d-167">Выберите **ContactId** как первичный ключ для **eCommerceContacts**, а **LoyaltyID** как первичный ключ для **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Унифицируйте LoyaltyId как первичный ключ.":::

### <a name="match"></a><span data-ttu-id="08f1d-169">Совпадение найдено</span><span class="sxs-lookup"><span data-stu-id="08f1d-169">Match</span></span>

1. <span data-ttu-id="08f1d-170">Перейдите на вкладку **Совпадение** и выберите **Задать порядок**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="08f1d-171">В раскрывающемся списке **Первичный** выберите **eCommerceContacts : eCommerce** в качестве первичного источника и включите все записи.</span><span class="sxs-lookup"><span data-stu-id="08f1d-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="08f1d-172">В раскрывающемся списке **Сущность 2** выберите **loyCustomers: LoyaltyScheme** и включите все записи.</span><span class="sxs-lookup"><span data-stu-id="08f1d-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Унифицировать совпадение eCommerce и лояльности.":::

1. <span data-ttu-id="08f1d-174">Выберите **Создать правило**</span><span class="sxs-lookup"><span data-stu-id="08f1d-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="08f1d-175">Добавьте свое первое условие, используя FullName.</span><span class="sxs-lookup"><span data-stu-id="08f1d-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="08f1d-176">Для eCommerceContacts выберите **FullName** в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="08f1d-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="08f1d-177">Для loyCustomers выберите **FullName** в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="08f1d-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="08f1d-178">Выберите раскрывающийся список **Нормализовать** и выберите **Тип (телефон, имя, адрес, ...)**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="08f1d-179">Задайте **Уровень точности**: **Базовый** и **Значение**: **Высоко**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="08f1d-180">Введите имя **FullName, Email** для нового правила.</span><span class="sxs-lookup"><span data-stu-id="08f1d-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="08f1d-181">Добавьте второе условие для адреса электронной почты, выбрав **Добавить условие**</span><span class="sxs-lookup"><span data-stu-id="08f1d-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="08f1d-182">Для сущности eCommerceContacts выберите **EMail** в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="08f1d-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="08f1d-183">Для сущности loyCustomers выберите **EMail** в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="08f1d-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="08f1d-184">Оставьте поле "Нормализация" пустым.</span><span class="sxs-lookup"><span data-stu-id="08f1d-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="08f1d-185">Задайте **Уровень точности**: **Базовый** и **Значение**: **Высоко**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Унифицировать правило совпадения для имени и электронной почты.":::

7. <span data-ttu-id="08f1d-187">Выберите **Сохранить** и **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="08f1d-188">Объединение</span><span class="sxs-lookup"><span data-stu-id="08f1d-188">Merge</span></span>

1. <span data-ttu-id="08f1d-189">Перейдите на вкладку **Объединение**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="08f1d-190">В **ContactId** для сущности **loyCustomers** измените отображаемое имя на **ContactIdLOYALTY**, чтобы отличить его от других полученных идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="08f1d-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="Переименовать contactid из идентификатора лояльности.":::

1. <span data-ttu-id="08f1d-192">Выберите **Сохранить** и **Выполнить**, чтобы начать процесс объединения.</span><span class="sxs-lookup"><span data-stu-id="08f1d-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="08f1d-193">Задача 3. Настройте прогноз оттока подписок</span><span class="sxs-lookup"><span data-stu-id="08f1d-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="08f1d-194">С унифицированными профилями клиентов теперь мы можем запустить прогноз оттока подписок.</span><span class="sxs-lookup"><span data-stu-id="08f1d-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="08f1d-195">Подробные инструкции см. в статье [Прогноз оттока подписок (предварительная версия)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="08f1d-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="08f1d-196">Перейдите **Аналитика** > **Обнаружить** и выберите **Модель оттока клиентов**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="08f1d-197">Выберите вариант **Подписка** и выберите **Начать**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="08f1d-198">Назовите модель **OOB Subscription Churn Prediction** и выходную сущность **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="08f1d-199">Определите два условия для модели оттока:</span><span class="sxs-lookup"><span data-stu-id="08f1d-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="08f1d-200">**Дней с момента окончания подписки**: **не менее 60 дней**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="08f1d-201">Если клиент не продлил свою подписку в течение этого периода после окончания срока ее действия, он считается ушедшим.</span><span class="sxs-lookup"><span data-stu-id="08f1d-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="08f1d-202">**Определение оттока**: **не менее 93 дней**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="08f1d-203">Модель предсказывает продолжительность оттока клиентов.</span><span class="sxs-lookup"><span data-stu-id="08f1d-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="08f1d-204">Чем дальше в будущее, тем менее точны результаты.</span><span class="sxs-lookup"><span data-stu-id="08f1d-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Выберите для модели Окно прогноза и Определение оттока.":::

1. <span data-ttu-id="08f1d-206">Выберите **Добавление необходимых данных** и выберите **Добавить данные** для истории подписок.</span><span class="sxs-lookup"><span data-stu-id="08f1d-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="08f1d-207">Добавьте сущность **Subscription : SubscriptionHistory** и сопоставьте поля из eCommerce с соответствующими полями, необходимыми для модели.</span><span class="sxs-lookup"><span data-stu-id="08f1d-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="08f1d-208">Присоедините сущность **Subscription : SubscriptionHistory** к **eCommerceContacts : eCommerce**, назовите отношение **eCommerceSubscription**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Присоедините сущности eCommerce.":::

1. <span data-ttu-id="08f1d-210">В разделе действия клиентов добавьте сущность **webReviews : Website** и сопоставьте поля из webReviews с соответствующими полями, необходимыми для модели.</span><span class="sxs-lookup"><span data-stu-id="08f1d-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="08f1d-211">Первичный ключ: ReviewId</span><span class="sxs-lookup"><span data-stu-id="08f1d-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="08f1d-212">Метка времени: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="08f1d-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="08f1d-213">Событие: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="08f1d-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="08f1d-214">Настройте действие для обзоров веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="08f1d-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="08f1d-215">Выберите действие **Обзор** и присоедините сущность **webReviews : Website** к **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="08f1d-216">Выберите **Далее**, чтобы задать расписание модели.</span><span class="sxs-lookup"><span data-stu-id="08f1d-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="08f1d-217">Модель должна регулярно обучаться, чтобы изучать новые закономерности при поступлении новых данных.</span><span class="sxs-lookup"><span data-stu-id="08f1d-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="08f1d-218">В данном примере выберите **Ежемесячно**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="08f1d-219">Изучив все сведения, выберите **Сохранить и выполнить**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="08f1d-220">Задача 4. Обзор результатов модели и объяснения</span><span class="sxs-lookup"><span data-stu-id="08f1d-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="08f1d-221">Дайте модели завершить обучение и оценку данных.</span><span class="sxs-lookup"><span data-stu-id="08f1d-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="08f1d-222">Теперь вы можете просмотреть объяснения модели оттока подписок.</span><span class="sxs-lookup"><span data-stu-id="08f1d-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="08f1d-223">Для получения дополнительной информации см. [Просмотр статуса прогноза и результатов](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="08f1d-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="08f1d-224">Задача 5. Создайте сегмент клиентов с высоким риском оттока</span><span class="sxs-lookup"><span data-stu-id="08f1d-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="08f1d-225">Выполнение производственной модели создает новую сущность, которую вы можете увидеть в **Данные** > **Сущности**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="08f1d-226">Вы можете создать новый сегмент на основе сущности, созданной моделью.</span><span class="sxs-lookup"><span data-stu-id="08f1d-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="08f1d-227">Перейдите **Сегменты**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-227">Go to **Segments**.</span></span> <span data-ttu-id="08f1d-228">Выберите **Создать** и выберите **Создать из** > **Аналитика**.</span><span class="sxs-lookup"><span data-stu-id="08f1d-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Создание сегмента с выходом модели.":::

1. <span data-ttu-id="08f1d-230">Выберите конечную точку **OOBSubscriptionChurnPrediction** и определите сегмент:</span><span class="sxs-lookup"><span data-stu-id="08f1d-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="08f1d-231">Поле: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="08f1d-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="08f1d-232">Оператор: больше</span><span class="sxs-lookup"><span data-stu-id="08f1d-232">Operator: greater than</span></span>
   - <span data-ttu-id="08f1d-233">Значение: 0,6</span><span class="sxs-lookup"><span data-stu-id="08f1d-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Настройте сегмент оттока подписок.":::

<span data-ttu-id="08f1d-235">Теперь у вас есть динамически обновляемый сегмент, который определяет клиентов с высоким риском оттока для этого бизнеса по подписке.</span><span class="sxs-lookup"><span data-stu-id="08f1d-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="08f1d-236">Дополнительные сведения см. в разделе [Создание сегментов и управление ими](segments.md).</span><span class="sxs-lookup"><span data-stu-id="08f1d-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]