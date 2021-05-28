---
title: Обогащение профилей клиентов данными из Microsoft
description: Используйте собственные данные Microsoft, чтобы обогатить данные о клиентах с учетом общности с брендом и интересов.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: be042dd139607849b795c903fa58da2edb9ff589
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064907"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="bc2ee-103">Обогащение профилей клиентов общностью с брендами и интересами (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="bc2ee-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="bc2ee-104">Используйте собственные данные Microsoft, чтобы обогатить данные о клиентах с учетом общности с брендом и интересов.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="bc2ee-105">Эти общности определяются на основе данных от людей с демографическими характеристиками, аналогичными вашим клиентам.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="bc2ee-106">Эта информация поможет вам лучше понять и сегментировать ваших клиентов на основе их привязанности к конкретным брендам и интересам.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="bc2ee-107">В аналитике аудитории перейдите **Данные** > **Обогащение**, чтобы [настраивать и просматривать обогащения](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="bc2ee-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="bc2ee-108">Чтобы настроить обогащение общностей с торговыми марками, перейдите к вкладке **Обнаружить** и выберите **Обогатить мои данные** на плитке **Торговые марки**.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="bc2ee-109">Чтобы настроить обогащение общностей интересов, перейдите к вкладке **Обнаружить** и выберите **Обогатить мои данные** на плитке **Интересы**.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bc2ee-110">![Плитки торговых марок и интересов](media/BrandsInterest-tile-Hub.png "Плитки торговых марок и интереса")</span><span class="sxs-lookup"><span data-stu-id="bc2ee-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="bc2ee-111">Как мы определяем общность</span><span class="sxs-lookup"><span data-stu-id="bc2ee-111">How we determine affinities</span></span>

<span data-ttu-id="bc2ee-112">Мы используем данные интернет-поиска Microsoft, чтобы найти общность с брендами и интересами в различных демографических сегментах (в зависимости от возраста, пола или местоположения).</span><span class="sxs-lookup"><span data-stu-id="bc2ee-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="bc2ee-113">Объем онлайн-поиска по бренду или интересу определяет, насколько много общности демографический сегмент по сравнению с другими сегментами имеет к данному бренду или интересу.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="bc2ee-114">Уровень сходства и оценка</span><span class="sxs-lookup"><span data-stu-id="bc2ee-114">Affinity level and score</span></span>

<span data-ttu-id="bc2ee-115">В каждом обогащенном профиле клиента мы указываем два связанных значения: уровень сходства и оценка сходства.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-115">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="bc2ee-116">Эти значения помогают определить, насколько сильно сходство для демографического сегмента этого профиля, для бренда или интереса, по сравнению с другими демографическими сегментами.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="bc2ee-117">*Уровень сходства* состоит из четырех уровней, а *оценка сходства* рассчитывается по 100-балльной шкале, соответствующей уровням сходства.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="bc2ee-118">Уровень сходства</span><span class="sxs-lookup"><span data-stu-id="bc2ee-118">Affinity level</span></span> |<span data-ttu-id="bc2ee-119">Показатель близости</span><span class="sxs-lookup"><span data-stu-id="bc2ee-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="bc2ee-120">Очень высокий</span><span class="sxs-lookup"><span data-stu-id="bc2ee-120">Very high</span></span>     | <span data-ttu-id="bc2ee-121">85–100</span><span class="sxs-lookup"><span data-stu-id="bc2ee-121">85-100</span></span>       |
|<span data-ttu-id="bc2ee-122">Высокое</span><span class="sxs-lookup"><span data-stu-id="bc2ee-122">High</span></span>     | <span data-ttu-id="bc2ee-123">70–84</span><span class="sxs-lookup"><span data-stu-id="bc2ee-123">70-84</span></span>        |
|<span data-ttu-id="bc2ee-124">Средний</span><span class="sxs-lookup"><span data-stu-id="bc2ee-124">Medium</span></span>     | <span data-ttu-id="bc2ee-125">35–69</span><span class="sxs-lookup"><span data-stu-id="bc2ee-125">35-69</span></span>        |
|<span data-ttu-id="bc2ee-126">Низкое</span><span class="sxs-lookup"><span data-stu-id="bc2ee-126">Low</span></span>     | <span data-ttu-id="bc2ee-127">1–34</span><span class="sxs-lookup"><span data-stu-id="bc2ee-127">1-34</span></span>        |

<span data-ttu-id="bc2ee-128">В зависимости от степени детализации, по которой вы хотите измерять сходство, вы можете использовать либо уровень сходства, либо оценку.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="bc2ee-129">Оценка сходства дает вам более точный контроль.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="bc2ee-130">Поддерживаемые страны/регионы</span><span class="sxs-lookup"><span data-stu-id="bc2ee-130">Supported countries/regions</span></span>

<span data-ttu-id="bc2ee-131">В настоящее время мы поддерживаем следующие страны/регионы: Австралия, Канада (английский), Франция, Германия, Соединенное Королевство или США (английский).</span><span class="sxs-lookup"><span data-stu-id="bc2ee-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="bc2ee-132">Чтобы выбрать страну, откройте **Обогащение брендов** или **Обогащение интересов** и выберите **Изменить** рядом с пунктом **Страна/регион**.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-132">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="bc2ee-133">На панели **Параметры страны/региона** выберите вариант и выберите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="bc2ee-134">Последствия, связанные с выбором страны</span><span class="sxs-lookup"><span data-stu-id="bc2ee-134">Implications related to country selection</span></span>

- <span data-ttu-id="bc2ee-135">При [выборе собственных брендов](#define-your-brands-or-interests) система предлагает варианты для выбранной страны или региона.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="bc2ee-136">При [выборе отрасли](#define-your-brands-or-interests) вы получите наиболее подходящие бренды или интересы в зависимости от выбранной страны или региона.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="bc2ee-137">При [обогащении профилей](#refresh-enrichment) мы обогатим все профили клиентов, для которых мы получаем данные по выбранным брендам и интересам.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="bc2ee-138">Включая профили, не относящиеся к выбранной стране или региону.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-138">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="bc2ee-139">Например, если вы выбрали Германию, мы обогатим профили, расположенные в США, если у нас есть данные для выбранных брендов и интересов в США.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-139">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="bc2ee-140">Настройка обогащения</span><span class="sxs-lookup"><span data-stu-id="bc2ee-140">Configure Enrichment</span></span>

<span data-ttu-id="bc2ee-141">Управляемый опыт поможет вам настроить обогащения.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-141">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="bc2ee-142">Определение торговых марок или интересов</span><span class="sxs-lookup"><span data-stu-id="bc2ee-142">Define your brands or interests</span></span>

<span data-ttu-id="bc2ee-143">Выберите один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-143">Select one of the following options:</span></span>

- <span data-ttu-id="bc2ee-144">**Отрасль**: система определяет лучшие бренды или интересы, относящиеся к вашей отрасли, и обогащает ими данные ваших клиентов.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-144">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="bc2ee-145">**Указать собственные**: выберите до пяти наименований из списка брендов или интересов, которые наиболее актуальны для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-145">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="bc2ee-146">Чтобы добавить бренд или интерес, введите его в область ввода, чтобы получить предложения на основе соответствующих терминов.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-146">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="bc2ee-147">Если мы не указываем интересующий вас бренд или интерес, отправьте нам отзыв, используя ссылку **Предложить**.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-147">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="bc2ee-148">Обзор предпочтений обогащения</span><span class="sxs-lookup"><span data-stu-id="bc2ee-148">Review enrichment preferences</span></span>

<span data-ttu-id="bc2ee-149">Изучите настройки обогащения по умолчанию и обновите их по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-149">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Снимок экрана окна настроек обогащения.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="bc2ee-151">Выберите сущность для обогащения</span><span class="sxs-lookup"><span data-stu-id="bc2ee-151">Select entity to enrich</span></span>

<span data-ttu-id="bc2ee-152">Выберите **Обогащенная сущность** и выберите набор данных, который вы хотите обогатить данными компании из Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-152">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="bc2ee-153">Вы можете выбрать сущность "Клиент", чтобы обогатить все ваши профили клиентов, или выбрать сущность сегмента, чтобы обогатить только профили клиентов, содержащиеся в этом сегменте.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-153">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="bc2ee-154">Сопоставление полей</span><span class="sxs-lookup"><span data-stu-id="bc2ee-154">Map your fields</span></span>

<span data-ttu-id="bc2ee-155">Сопоставьте поля из вашей объединенной сущности клиента, чтобы определить демографический сегмент, который система должна использовать для пополнения данных о клиентах.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-155">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="bc2ee-156">Укажите страну/регион и по крайней мере атрибуты «Дата рождения» или «Пол».</span><span class="sxs-lookup"><span data-stu-id="bc2ee-156">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="bc2ee-157">Кроме того, необходимо сопоставить минимум один атрибут: город (и область, республика, край, округ) или почтовый индекс.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-157">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="bc2ee-158">Выберите **Изменить**, чтобы определить сопоставление полей, и выберите **Применять**, когда вы закончите.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-158">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="bc2ee-159">Выберите **Сохранить**, чтобы завершить отображение полей.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-159">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="bc2ee-160">Поддерживаются следующие форматы и значения, значения не чувствительны к регистру:</span><span class="sxs-lookup"><span data-stu-id="bc2ee-160">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="bc2ee-161">**Дата рождения**: мы рекомендуем преобразовывать дату рождения в тип DateTime во время приема данных.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-161">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="bc2ee-162">Как вариант, это может быть строка в формате [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "гггг-ММ-дд" или "гггг-ММ-ддTЧЧ:мм:ссZ".</span><span class="sxs-lookup"><span data-stu-id="bc2ee-162">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="bc2ee-163">**Пол**: Мужской, Женский, Неизвестный</span><span class="sxs-lookup"><span data-stu-id="bc2ee-163">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="bc2ee-164">**Почтовый индекс**: пятизначные почтовые индексы для США, стандартный почтовый индекс во всех остальных странах/регионах</span><span class="sxs-lookup"><span data-stu-id="bc2ee-164">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="bc2ee-165">**Город**: название города на английском языке</span><span class="sxs-lookup"><span data-stu-id="bc2ee-165">**City**: City name in English</span></span>
- <span data-ttu-id="bc2ee-166">**Штат/провинция**: двухбуквенное сокращение для США и Канады.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-166">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="bc2ee-167">Аббревиатура из двух или трех букв для Австралии.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-167">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="bc2ee-168">Неприменимо для Франции, Германии или Соединенного Королевства.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-168">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="bc2ee-169">**Страна или регион**:</span><span class="sxs-lookup"><span data-stu-id="bc2ee-169">**Country/Region**:</span></span>

  - <span data-ttu-id="bc2ee-170">US: Соединенные Штаты Америки, Соединенные Штаты, США, US, Америка</span><span class="sxs-lookup"><span data-stu-id="bc2ee-170">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="bc2ee-171">CA: Канада, CA</span><span class="sxs-lookup"><span data-stu-id="bc2ee-171">CA: Canada, CA</span></span>
  - <span data-ttu-id="bc2ee-172">GB: Соединенное Королевство, UK, GB, Соединенное Королевство Великобритании и Северной Ирландии, Соединенное Королевство Великобритании</span><span class="sxs-lookup"><span data-stu-id="bc2ee-172">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="bc2ee-173">AU: Австралия, AU, Содружество Австралии</span><span class="sxs-lookup"><span data-stu-id="bc2ee-173">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="bc2ee-174">FR: Франция, FR, Французская Республика</span><span class="sxs-lookup"><span data-stu-id="bc2ee-174">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="bc2ee-175">DE: Германия, Deutschland, Allemagne, DE, Федеративная Республика Германия, Республика Германия</span><span class="sxs-lookup"><span data-stu-id="bc2ee-175">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="bc2ee-176">Просмотр и задание имени обогащения</span><span class="sxs-lookup"><span data-stu-id="bc2ee-176">Review and name the enrichment</span></span>

<span data-ttu-id="bc2ee-177">Наконец, вы можете просмотреть информацию и указать имя для обогащения.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-177">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Страница обзора интересов и задания имени.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="bc2ee-179">Обновление обогащения</span><span class="sxs-lookup"><span data-stu-id="bc2ee-179">Refresh enrichment</span></span>

<span data-ttu-id="bc2ee-180">Запустите обогащение после настройки брендов, интересов и сопоставления полей для демографии.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-180">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="bc2ee-181">Чтобы начать процесс, выберите **Выполнить** на странице конфигурации торговой марки или интереса.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-181">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="bc2ee-182">Кроме того, вы можете позволить системе автоматически выполнять обогащение как часть запланированного обновления.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-182">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="bc2ee-183">В зависимости от размера данных о клиентах, выполнение процесса обогащения может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-183">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="bc2ee-184">Есть [шесть типов статусов](system.md#status-types) для задач/процессов.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-184">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="bc2ee-185">Кроме того, большинство процессов [зависит от других последующих процессов](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="bc2ee-185">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="bc2ee-186">Вы можете выбрать статус процесса, чтобы увидеть детали выполнения всего задания.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-186">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="bc2ee-187">После выбора **См. сведения** для одной из задач задания вы найдете дополнительную информацию: время обработки, дату последней обработки, а также все ошибки и предупреждения, связанные с задачей.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-187">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="bc2ee-188">Результаты обогащения</span><span class="sxs-lookup"><span data-stu-id="bc2ee-188">Enrichment results</span></span>

<span data-ttu-id="bc2ee-189">После запуска процесса обогащения перейдите к **Мои обогащения**, чтобы просмотреть общее количество обогащенных клиентов и разбивку брендов и интересов в обогащенных профилях клиентов.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-189">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Предварительный просмотр результатов после выполнения процесса обогащения":::

<span data-ttu-id="bc2ee-191">Просмотрите обогащенные данные, выбрав **Просмотр обогащенных данных** на диаграмме.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-191">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="bc2ee-192">Обогащенные данные для брендов направляются в сущность **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-192">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="bc2ee-193">Данные для интересов находятся в сущности **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-193">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="bc2ee-194">Вы также найдете эти сущности в списке в группе **Обогащение** в области **Данные** > **Сущности**.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-194">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="bc2ee-195">Просмотр данных обогащения на карточке клиента</span><span class="sxs-lookup"><span data-stu-id="bc2ee-195">See enrichment data on the customer card</span></span>

<span data-ttu-id="bc2ee-196">Сродство с брендом и интересом также можно посмотреть на отдельных карточках клиентов.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-196">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="bc2ee-197">Перейдите в раздел **Клиенты** и выберите профиль клиента.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-197">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="bc2ee-198">В карточке клиента вы найдете диаграммы для торговых марок или интересов, к которым имеют отношение люди из демографического профиля этого клиента.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-198">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Карточка клиента с обогащенными данными":::

## <a name="next-steps"></a><span data-ttu-id="bc2ee-200">Дальнейшие шаги</span><span class="sxs-lookup"><span data-stu-id="bc2ee-200">Next steps</span></span>

<span data-ttu-id="bc2ee-201">Основывайтесь на ваших обогащенных данных клиентов.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-201">Build on top of your enriched customer data.</span></span> <span data-ttu-id="bc2ee-202">Создайте [Сегменты](segments.md), [меры](measures.md) и даже [экспортируйте данные](export-destinations.md), чтобы предоставлять персонализированное взаимодействие вашим клиентам.</span><span class="sxs-lookup"><span data-stu-id="bc2ee-202">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
