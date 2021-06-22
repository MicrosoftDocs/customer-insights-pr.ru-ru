---
title: Пример руководства прогноза ценности клиента на протяжении жизненного цикла
description: Воспользуйтесь этим руководством, чтобы опробовать модель прогноза ценности клиента на протяжении жизненного цикла.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129961"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="76e98-103">Пример руководства прогноза ценности клиента на протяжении жизненного цикла (CLV)</span><span class="sxs-lookup"><span data-stu-id="76e98-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="76e98-104">Это руководство объяснит вам от начала до конца пример прогноза ценности клиента на протяжении жизненного цикла (CLV) в Customer Insights с использованием примеров данных.</span><span class="sxs-lookup"><span data-stu-id="76e98-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="76e98-105">Сценарий</span><span class="sxs-lookup"><span data-stu-id="76e98-105">Scenario</span></span>

<span data-ttu-id="76e98-106">Contoso — компания, производящая качественный кофе и кофемашины.</span><span class="sxs-lookup"><span data-stu-id="76e98-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="76e98-107">Они продают товары через свой веб-сайт Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="76e98-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="76e98-108">Компания хочет понять ценность (доход), которую их клиенты могут создать в следующие 12 месяцев.</span><span class="sxs-lookup"><span data-stu-id="76e98-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="76e98-109">Знание ожидаемой ценности своих клиентов в следующие 12 месяцев поможет им направить свои маркетинговые усилия на высокоценных клиентов.</span><span class="sxs-lookup"><span data-stu-id="76e98-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="76e98-110">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="76e98-110">Prerequisites</span></span>

- <span data-ttu-id="76e98-111">По меньшей мере [разрешения участника](permissions.md) в аналитике аудитории.</span><span class="sxs-lookup"><span data-stu-id="76e98-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="76e98-112">Мы рекомендуем вам выполнить следующие шаги [в новой среде](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="76e98-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="76e98-113">Задача 1. Прием данных</span><span class="sxs-lookup"><span data-stu-id="76e98-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="76e98-114">Просмотрите статьи [о приеме данных](data-sources.md) и [импорту источников данных с помощью соединителей Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="76e98-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="76e98-115">Следующая информация предполагает, что вы в целом ознакомились с приемом данных.</span><span class="sxs-lookup"><span data-stu-id="76e98-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="76e98-116">Получение данных о клиентах с платформы eCommerce</span><span class="sxs-lookup"><span data-stu-id="76e98-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="76e98-117">Создайте источник данных с именем **eCommerce**, выберите вариант импорта и выберите соединитель **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="76e98-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="76e98-118">Введите URL-адрес для контактов eCommerce [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="76e98-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="76e98-119">При редактировании данных выберите **Преобразовать**, затем **Использовать первую строку в качестве заголовков**.</span><span class="sxs-lookup"><span data-stu-id="76e98-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="76e98-120">Обновите тип данных для столбцов, перечисленных ниже:</span><span class="sxs-lookup"><span data-stu-id="76e98-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="76e98-121">**DateOfBirth**: дата</span><span class="sxs-lookup"><span data-stu-id="76e98-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="76e98-122">**CreatedOn**: дата/время/часовой пояс</span><span class="sxs-lookup"><span data-stu-id="76e98-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Преобразовать дату рождения в дату.":::

1. <span data-ttu-id="76e98-124">В поле "Имя" на правой панели переименуйте свой источник данных с **Query** на **eCommerceContacts**.</span><span class="sxs-lookup"><span data-stu-id="76e98-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="76e98-125">**Сохраните** источник данных.</span><span class="sxs-lookup"><span data-stu-id="76e98-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="76e98-126">Получение данных о покупках в Интернете</span><span class="sxs-lookup"><span data-stu-id="76e98-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="76e98-127">Добавьте другой набор данных к тому же источнику данных **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="76e98-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="76e98-128">Снова выберите соединитель **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="76e98-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="76e98-129">Введите URL-адрес для данных **Интернет-покупки** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="76e98-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="76e98-130">При редактировании данных выберите **Преобразовать**, затем **Использовать первую строку в качестве заголовков**.</span><span class="sxs-lookup"><span data-stu-id="76e98-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="76e98-131">Обновите тип данных для столбцов, перечисленных ниже:</span><span class="sxs-lookup"><span data-stu-id="76e98-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="76e98-132">**PurchasedOn**: дата/время</span><span class="sxs-lookup"><span data-stu-id="76e98-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="76e98-133">**TotalPrice**: валюта</span><span class="sxs-lookup"><span data-stu-id="76e98-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="76e98-134">В поле **Имя** на боковой панели переименуйте свой источник данных с **Query** на **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="76e98-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="76e98-135">**Сохраните** источник данных.</span><span class="sxs-lookup"><span data-stu-id="76e98-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="76e98-136">Получение данных о клиентах из схемы лояльности</span><span class="sxs-lookup"><span data-stu-id="76e98-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="76e98-137">Создайте источник данных с именем **LoyaltyScheme**, выберите вариант импорта и выберите соединитель **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="76e98-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="76e98-138">Введите URL-адрес для контактов eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="76e98-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="76e98-139">При редактировании данных выберите **Преобразовать**, затем **Использовать первую строку в качестве заголовков**.</span><span class="sxs-lookup"><span data-stu-id="76e98-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="76e98-140">Обновите тип данных для столбцов, перечисленных ниже:</span><span class="sxs-lookup"><span data-stu-id="76e98-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="76e98-141">**DateOfBirth**: дата</span><span class="sxs-lookup"><span data-stu-id="76e98-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="76e98-142">**RewardsPoints**: целое число</span><span class="sxs-lookup"><span data-stu-id="76e98-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="76e98-143">**CreatedOn**: дата/время</span><span class="sxs-lookup"><span data-stu-id="76e98-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="76e98-144">В поле **Имя** на правой панели переименуйте свой источник данных с **Query** на **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="76e98-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="76e98-145">**Сохраните** источник данных.</span><span class="sxs-lookup"><span data-stu-id="76e98-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="76e98-146">Получение данных о клиентах из отзывов веб-сайтов</span><span class="sxs-lookup"><span data-stu-id="76e98-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="76e98-147">Создайте источник данных с именем **Website**, выберите вариант импорта и выберите соединитель **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="76e98-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="76e98-148">Введите URL-адрес для контактов eCommerce https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="76e98-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="76e98-149">При редактировании данных выберите **Преобразовать**, затем **Использовать первую строку в качестве заголовков**.</span><span class="sxs-lookup"><span data-stu-id="76e98-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="76e98-150">Обновите тип данных для столбцов, перечисленных ниже:</span><span class="sxs-lookup"><span data-stu-id="76e98-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="76e98-151">**ReviewRating**: десятичное число</span><span class="sxs-lookup"><span data-stu-id="76e98-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="76e98-152">**ReviewDate**: дата</span><span class="sxs-lookup"><span data-stu-id="76e98-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="76e98-153">В поле "Имя" на правой панели переименуйте свой источник данных из **Запроса** на **Отзывы**.</span><span class="sxs-lookup"><span data-stu-id="76e98-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="76e98-154">**Сохраните** источник данных.</span><span class="sxs-lookup"><span data-stu-id="76e98-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="76e98-155">Задача 2. Унификация данных</span><span class="sxs-lookup"><span data-stu-id="76e98-155">Task 2 - Data unification</span></span>

<span data-ttu-id="76e98-156">После приема данных мы начинаем процесс объединения данных для создания единого профиля клиента.</span><span class="sxs-lookup"><span data-stu-id="76e98-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="76e98-157">Дополнительные сведения см. в разделе [Унификация данных](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="76e98-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="76e98-158">Сопоставление</span><span class="sxs-lookup"><span data-stu-id="76e98-158">Map</span></span>

1. <span data-ttu-id="76e98-159">После приема данных сопоставьте контакты из данных eCommerce и лояльности с общими типами данных.</span><span class="sxs-lookup"><span data-stu-id="76e98-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="76e98-160">Перейдите **Данные** > **Унификация** > **Сопоставление**.</span><span class="sxs-lookup"><span data-stu-id="76e98-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="76e98-161">Выберите сущности, которые представляют профиль клиента — **eCommerceContacts** и **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="76e98-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="76e98-162">Затем выберите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="76e98-162">Then, select **Apply**.</span></span>

   ![унифицировать источники данных ecommerce и лояльности.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="76e98-164">Выберите **ContactId** как первичный ключ для **eCommerceContacts**, а **LoyaltyID** как первичный ключ для **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="76e98-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Унифицируйте LoyaltyId как первичный ключ.](media/unify-loyaltyid.png)

1. <span data-ttu-id="76e98-166">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="76e98-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="76e98-167">Соответствие</span><span class="sxs-lookup"><span data-stu-id="76e98-167">Match</span></span>

1. <span data-ttu-id="76e98-168">Перейдите на вкладку **Совпадение** и выберите **Задать порядок**.</span><span class="sxs-lookup"><span data-stu-id="76e98-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="76e98-169">В раскрывающемся списке **Первичный** выберите **eCommerceContacts : eCommerce** в качестве первичного источника и включите все записи.</span><span class="sxs-lookup"><span data-stu-id="76e98-169">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="76e98-170">В раскрывающемся списке **Сущность 2** выберите **loyCustomers: LoyaltyScheme** и включите все записи.</span><span class="sxs-lookup"><span data-stu-id="76e98-170">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Унифицировать совпадение eCommerce и лояльности.](media/unify-match-order.png)

1. <span data-ttu-id="76e98-172">Выберите **Добавить правило**.</span><span class="sxs-lookup"><span data-stu-id="76e98-172">Select **Add rule**</span></span>

1. <span data-ttu-id="76e98-173">Добавьте свое первое условие, используя FullName.</span><span class="sxs-lookup"><span data-stu-id="76e98-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="76e98-174">Для eCommerceContacts выберите **FullName** в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="76e98-174">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="76e98-175">Для loyCustomers выберите **FullName** в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="76e98-175">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="76e98-176">Выберите раскрывающийся список **Нормализовать** и выберите **Тип (телефон, имя, адрес, ...)**.</span><span class="sxs-lookup"><span data-stu-id="76e98-176">Select the **Normalize** drop-down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="76e98-177">Задайте **Уровень точности**: **Базовый** и **Значение**: **Высоко**.</span><span class="sxs-lookup"><span data-stu-id="76e98-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="76e98-178">Введите имя **FullName, Email** для нового правила.</span><span class="sxs-lookup"><span data-stu-id="76e98-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="76e98-179">Добавьте второе условие для адреса электронной почты, выбрав **Добавить условие**</span><span class="sxs-lookup"><span data-stu-id="76e98-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="76e98-180">Для сущности eCommerceContacts выберите **EMail** в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="76e98-180">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="76e98-181">Для сущности loyCustomers выберите **EMail** в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="76e98-181">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="76e98-182">Оставьте поле "Нормализация" пустым.</span><span class="sxs-lookup"><span data-stu-id="76e98-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="76e98-183">Задайте **Уровень точности**: **Базовый** и **Значение**: **Высоко**.</span><span class="sxs-lookup"><span data-stu-id="76e98-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Унифицировать правило совпадения для имени и электронной почты.](media/unify-match-rule.png)

1. <span data-ttu-id="76e98-185">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="76e98-185">Select **Done**.</span></span>

1. <span data-ttu-id="76e98-186">Выберите **Сохранить** и **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="76e98-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="76e98-187">Объединение</span><span class="sxs-lookup"><span data-stu-id="76e98-187">Merge</span></span>

1. <span data-ttu-id="76e98-188">Перейдите на вкладку **Объединение**.</span><span class="sxs-lookup"><span data-stu-id="76e98-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="76e98-189">В **ContactId** для сущности **loyCustomers** измените отображаемое имя на **ContactIdLOYALTY**, чтобы отличить его от других полученных идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="76e98-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![Переименовать contactid из идентификатора лояльности.](media/unify-merge-contactid.png)

1. <span data-ttu-id="76e98-191">Выберите **Сохранить** и **Выполнить объединение и нисходящие процессы**.</span><span class="sxs-lookup"><span data-stu-id="76e98-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="76e98-192">Задача 3. Настройка прогноза ценности клиента на протяжении жизненного цикла</span><span class="sxs-lookup"><span data-stu-id="76e98-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="76e98-193">Имея единые профили клиентов, теперь мы можем определять прогноз ценности клиента на протяжении жизненного цикла.</span><span class="sxs-lookup"><span data-stu-id="76e98-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="76e98-194">Подробные инструкции см. в [Прогноз ценности клиента на протяжении жизненного цикла (предварительная версия)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="76e98-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="76e98-195">Перейдите **Аналитика**  > **Прогнозы** и выберите **Модель ценности клиента на протяжении жизненного цикла**.</span><span class="sxs-lookup"><span data-stu-id="76e98-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="76e98-196">Просмотрите информацию на боковой панели и выберите **Начать**.</span><span class="sxs-lookup"><span data-stu-id="76e98-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="76e98-197">Назовите модель **Прогноз OOB eCommerce CLV** и выходную сущность **OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="76e98-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="76e98-198">Определите параметры модели для модели CLV:</span><span class="sxs-lookup"><span data-stu-id="76e98-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="76e98-199">**Период прогнозирования**: **12 месяцев или 1 год**.</span><span class="sxs-lookup"><span data-stu-id="76e98-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="76e98-200">Этот параметр определяет, насколько далеко в будущем можно прогнозировать ценность клиента на протяжении жизненного цикла.</span><span class="sxs-lookup"><span data-stu-id="76e98-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="76e98-201">**Активные клиенты**: укажите, что активные клиенты значат для вашего бизнеса.</span><span class="sxs-lookup"><span data-stu-id="76e98-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="76e98-202">Установите исторический интервал времени, в котором у клиента должна быть хотя бы одна транзакция, чтобы считаться активным.</span><span class="sxs-lookup"><span data-stu-id="76e98-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="76e98-203">Модель будет прогнозировать CLV только для активных клиентов.</span><span class="sxs-lookup"><span data-stu-id="76e98-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="76e98-204">Выберите между разрешением модели рассчитывать период времени на основе исторических данных транзакций или укажите конкретный интервал времени.</span><span class="sxs-lookup"><span data-stu-id="76e98-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="76e98-205">В этом руководстве мы **позволим модели рассчитать интервал покупки**, который используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="76e98-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="76e98-206">**Ценные клиенты**: определите ценных клиентов как процентиль самых платящих клиентов.</span><span class="sxs-lookup"><span data-stu-id="76e98-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="76e98-207">Модель использует эти входные данные для получения результатов, которые соответствуют вашему бизнес-определению ценных клиентов.</span><span class="sxs-lookup"><span data-stu-id="76e98-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="76e98-208">Можно разрешить модели определять ценных клиентов.</span><span class="sxs-lookup"><span data-stu-id="76e98-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="76e98-209">Она использует эвристическое правило, которое вычисляет процентиль.</span><span class="sxs-lookup"><span data-stu-id="76e98-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="76e98-210">Также можно задать ценных клиентов как процентиль будущих самых платящих клиентов.</span><span class="sxs-lookup"><span data-stu-id="76e98-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="76e98-211">В этом руководстве мы вручную определяем ценных клиентов как **первые 30% активных платящих клиентов** и выбираем **Далее**.</span><span class="sxs-lookup"><span data-stu-id="76e98-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Шаг настроек в управляемом взаимодействии для модели CLV.":::

1. <span data-ttu-id="76e98-213">На шаге **Необходимые данные** шаг, выберите **Добавить данные** для предоставления данных истории транзакций.</span><span class="sxs-lookup"><span data-stu-id="76e98-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="76e98-214">Добавьте сущность **eCommercePurchases: eCommerce** и сопоставьте атрибуты, которые требуются модели:</span><span class="sxs-lookup"><span data-stu-id="76e98-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="76e98-215">Идентификатор транзакции: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="76e98-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="76e98-216">Дата транзакции: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="76e98-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="76e98-217">Сумма транзакции: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="76e98-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="76e98-218">Идентификатор продукта: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="76e98-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="76e98-219">Выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="76e98-219">Select **Next**.</span></span>

1. <span data-ttu-id="76e98-220">Установите связь между сущностью **eCommercePurchases: eCommerce** и **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="76e98-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="76e98-221">На шаге **Дополнительные данные (необязательно)** можно добавить дополнительные данные о действиях клиентов.</span><span class="sxs-lookup"><span data-stu-id="76e98-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="76e98-222">Эти данные могут помочь получить больше информации о взаимодействии клиентов с вашим бизнесом, что может способствовать CLV.</span><span class="sxs-lookup"><span data-stu-id="76e98-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="76e98-223">Добавление ключевых взаимодействий с клиентами, таких как веб-журналы, журналы обслуживания клиентов или история программы вознаграждений, может повысить точность прогнозов.</span><span class="sxs-lookup"><span data-stu-id="76e98-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="76e98-224">Выберите **Добавить данные**, чтобы включить больше данных о действиях клиентов.</span><span class="sxs-lookup"><span data-stu-id="76e98-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="76e98-225">Добавьте сущность действий клиента и сопоставьте имена ее полей с соответствующими полями, необходимыми для модели:</span><span class="sxs-lookup"><span data-stu-id="76e98-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="76e98-226">Сущность действий клиентов: Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="76e98-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="76e98-227">Первичный ключ: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="76e98-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="76e98-228">Отметка времени: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="76e98-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="76e98-229">Событие (название действия): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="76e98-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="76e98-230">Сведения (сумма или значение): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="76e98-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="76e98-231">Выберите **Далее** и настройте действие и взаимосвязь между данными транзакции и данными клиента:</span><span class="sxs-lookup"><span data-stu-id="76e98-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="76e98-232">Тип действия: Choose existing</span><span class="sxs-lookup"><span data-stu-id="76e98-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="76e98-233">Метка действия: Review</span><span class="sxs-lookup"><span data-stu-id="76e98-233">Activity label: Review</span></span>
   - <span data-ttu-id="76e98-234">Соответствующая метка: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="76e98-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="76e98-235">Сущность клиента: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="76e98-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="76e98-236">Отношение: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="76e98-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="76e98-237">Выберите **Далее**, чтобы задать расписание модели.</span><span class="sxs-lookup"><span data-stu-id="76e98-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="76e98-238">Модель должна регулярно обучаться, чтобы изучать новые закономерности при поступлении новых данных.</span><span class="sxs-lookup"><span data-stu-id="76e98-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="76e98-239">В этом примере выберите **Ежемесячно**.</span><span class="sxs-lookup"><span data-stu-id="76e98-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="76e98-240">Изучив все сведения, выберите **Сохранить и выполнить**.</span><span class="sxs-lookup"><span data-stu-id="76e98-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="76e98-241">Задача 4. Обзор результатов модели и объяснения</span><span class="sxs-lookup"><span data-stu-id="76e98-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="76e98-242">Дайте модели завершить обучение и оценку данных.</span><span class="sxs-lookup"><span data-stu-id="76e98-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="76e98-243">Затем вы можете просмотреть результаты и объяснения модели CLV.</span><span class="sxs-lookup"><span data-stu-id="76e98-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="76e98-244">Для получения дополнительной информации см. [Просмотр статуса прогноза и результатов](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="76e98-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="76e98-245">Задача 5. Создание сегмента ценных клиентов</span><span class="sxs-lookup"><span data-stu-id="76e98-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="76e98-246">Запуск модели создает новую сущность, которая указана в **Данные** > **Сущности**.</span><span class="sxs-lookup"><span data-stu-id="76e98-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="76e98-247">Вы можете создать новый сегмент клиентов на основе сущности, созданной моделью.</span><span class="sxs-lookup"><span data-stu-id="76e98-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="76e98-248">Перейдите **Сегменты**.</span><span class="sxs-lookup"><span data-stu-id="76e98-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="76e98-249">Выберите **Создать** и выберите **Создать из** > **Аналитика**.</span><span class="sxs-lookup"><span data-stu-id="76e98-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Создание сегмента с выходом модели.](media/segment-intelligence.png)

1. <span data-ttu-id="76e98-251">Выберите сущность **OOBeCommerceCLVPrediction** и определите сегмент:</span><span class="sxs-lookup"><span data-stu-id="76e98-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="76e98-252">Поле: CLVScore</span><span class="sxs-lookup"><span data-stu-id="76e98-252">Field: CLVScore</span></span>
  - <span data-ttu-id="76e98-253">Оператор: больше</span><span class="sxs-lookup"><span data-stu-id="76e98-253">Operator: greater than</span></span>
  - <span data-ttu-id="76e98-254">Значение: 1500</span><span class="sxs-lookup"><span data-stu-id="76e98-254">Value: 1500</span></span>

1. <span data-ttu-id="76e98-255">Выберите **Проверить** и **Сохранить** сегмент.</span><span class="sxs-lookup"><span data-stu-id="76e98-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="76e98-256">Теперь у вас есть сегмент, который определяет клиентов, которые, по прогнозам, принесут более 1500 долларов США дохода в следующие 12 месяцев.</span><span class="sxs-lookup"><span data-stu-id="76e98-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="76e98-257">Этот сегмент обновляется динамически, если загружается больше данных.</span><span class="sxs-lookup"><span data-stu-id="76e98-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="76e98-258">Дополнительные сведения см. в разделе [Создание сегментов и управление ими](segments.md).</span><span class="sxs-lookup"><span data-stu-id="76e98-258">For more information, see [Create and manage segments](segments.md).</span></span>
