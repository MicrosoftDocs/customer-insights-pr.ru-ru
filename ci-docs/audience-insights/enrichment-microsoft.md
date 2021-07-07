---
title: Обогащение профилей клиентов данными из Microsoft
description: Используйте собственные данные Microsoft, чтобы обогатить данные о клиентах с учетом общности с брендом и интересов.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 1b11c325649b91ebb47cde924227eacedae64b7a
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305172"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="6fc43-103">Обогащение профилей клиентов общностью с брендами и интересами (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="6fc43-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="6fc43-104">Используйте собственные данные Microsoft, чтобы обогатить данные о клиентах с учетом общности с брендом и интересов.</span><span class="sxs-lookup"><span data-stu-id="6fc43-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="6fc43-105">Эти торговые марки основаны на данных от людей, демографические характеристики которых схожи с демографическими характеристиками ваших клиентов.</span><span class="sxs-lookup"><span data-stu-id="6fc43-105">These affinities are based on data from people with demographics similar to your customers.</span></span> <span data-ttu-id="6fc43-106">Эта информация поможет вам лучше понять и сегментировать ваших клиентов на основе их привязанности к конкретным брендам и интересам.</span><span class="sxs-lookup"><span data-stu-id="6fc43-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="6fc43-107">В аналитике аудитории перейдите **Данные** > **Обогащение**, чтобы [настраивать и просматривать обогащения](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="6fc43-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="6fc43-108">Чтобы настроить обогащение общностей с торговыми марками, перейдите к вкладке **Обнаружить** и выберите **Обогатить мои данные** на плитке **Торговые марки**.</span><span class="sxs-lookup"><span data-stu-id="6fc43-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="6fc43-109">Чтобы настроить обогащение общностей интересов, перейдите к вкладке **Обнаружить** и выберите **Обогатить мои данные** на плитке **Интересы**.</span><span class="sxs-lookup"><span data-stu-id="6fc43-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6fc43-110">![Плитки торговых марок и интересов](media/BrandsInterest-tile-Hub.png "Плитки торговых марок и интересов")</span><span class="sxs-lookup"><span data-stu-id="6fc43-110">![Brands and Interests tiles](media/BrandsInterest-tile-Hub.png "Brands and Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="6fc43-111">Как мы определяем общность</span><span class="sxs-lookup"><span data-stu-id="6fc43-111">How we determine affinities</span></span>

<span data-ttu-id="6fc43-112">Мы используем данные интернет-поиска Microsoft, чтобы найти общность с брендами и интересами в различных демографических сегментах (в зависимости от возраста, пола или местоположения).</span><span class="sxs-lookup"><span data-stu-id="6fc43-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="6fc43-113">Объем онлайн-поиска по бренду или интересу определяет, насколько много общности демографический сегмент по сравнению с другими сегментами имеет к данному бренду или интересу.</span><span class="sxs-lookup"><span data-stu-id="6fc43-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="6fc43-114">Уровень сходства и оценка</span><span class="sxs-lookup"><span data-stu-id="6fc43-114">Affinity level and score</span></span>

<span data-ttu-id="6fc43-115">В каждом обогащенном профиле клиента мы указываем два связанных значения: уровень сходства и оценка сходства.</span><span class="sxs-lookup"><span data-stu-id="6fc43-115">On every enriched customer profile, we provide two related values: affinity level and affinity score.</span></span> <span data-ttu-id="6fc43-116">Эти значения помогают определить, насколько сильно сходство для демографического сегмента этого профиля, для бренда или интереса, по сравнению с другими демографическими сегментами.</span><span class="sxs-lookup"><span data-stu-id="6fc43-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="6fc43-117">*Уровень сходства* состоит из четырех уровней, а *оценка сходства* рассчитывается по 100-балльной шкале, соответствующей уровням сходства.</span><span class="sxs-lookup"><span data-stu-id="6fc43-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="6fc43-118">Уровень сходства</span><span class="sxs-lookup"><span data-stu-id="6fc43-118">Affinity level</span></span> |<span data-ttu-id="6fc43-119">Показатель близости</span><span class="sxs-lookup"><span data-stu-id="6fc43-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="6fc43-120">Очень высокий</span><span class="sxs-lookup"><span data-stu-id="6fc43-120">Very high</span></span>     | <span data-ttu-id="6fc43-121">85–100</span><span class="sxs-lookup"><span data-stu-id="6fc43-121">85-100</span></span>       |
|<span data-ttu-id="6fc43-122">Высокое</span><span class="sxs-lookup"><span data-stu-id="6fc43-122">High</span></span>     | <span data-ttu-id="6fc43-123">70–84</span><span class="sxs-lookup"><span data-stu-id="6fc43-123">70-84</span></span>        |
|<span data-ttu-id="6fc43-124">Средний</span><span class="sxs-lookup"><span data-stu-id="6fc43-124">Medium</span></span>     | <span data-ttu-id="6fc43-125">35–69</span><span class="sxs-lookup"><span data-stu-id="6fc43-125">35-69</span></span>        |
|<span data-ttu-id="6fc43-126">Низкое</span><span class="sxs-lookup"><span data-stu-id="6fc43-126">Low</span></span>     | <span data-ttu-id="6fc43-127">1–34</span><span class="sxs-lookup"><span data-stu-id="6fc43-127">1-34</span></span>        |

<span data-ttu-id="6fc43-128">В зависимости от степени детализации, по которой вы хотите измерять сходство, вы можете использовать либо уровень сходства, либо оценку.</span><span class="sxs-lookup"><span data-stu-id="6fc43-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="6fc43-129">Оценка сходства дает вам более точный контроль.</span><span class="sxs-lookup"><span data-stu-id="6fc43-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="6fc43-130">Поддерживаемые страны/регионы</span><span class="sxs-lookup"><span data-stu-id="6fc43-130">Supported countries/regions</span></span>

<span data-ttu-id="6fc43-131">В настоящее время мы поддерживаем следующие страны/регионы: Австралия, Канада (английский), Франция, Германия, Соединенное Королевство или США (английский).</span><span class="sxs-lookup"><span data-stu-id="6fc43-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="6fc43-132">Чтобы выбрать страну или регион, откройте **Обогащение торговыми маркам** или **Обогащение интересами** и выберите **Изменить** рядом с **Страна/регион**.</span><span class="sxs-lookup"><span data-stu-id="6fc43-132">To select a country or region, open **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="6fc43-133">На панели **Параметры страны/региона** выберите вариант и выберите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="6fc43-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="6fc43-134">Последствия, связанные с выбором страны</span><span class="sxs-lookup"><span data-stu-id="6fc43-134">Implications related to country selection</span></span>

- <span data-ttu-id="6fc43-135">При [выборе собственных брендов](#define-your-brands-or-interests) система предлагает варианты для выбранной страны или региона.</span><span class="sxs-lookup"><span data-stu-id="6fc43-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="6fc43-136">При [выборе отрасли](#define-your-brands-or-interests) вы получите наиболее подходящие бренды или интересы в зависимости от выбранной страны или региона.</span><span class="sxs-lookup"><span data-stu-id="6fc43-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="6fc43-137">Во время [обогащения профилей](#refresh-enrichment) мы обогащаем все профили клиентов, для которых мы получаем данные по выбранным торговым маркам и интересам, включая профили, не относящиеся к выбранной стране или региону.</span><span class="sxs-lookup"><span data-stu-id="6fc43-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests, including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="6fc43-138">Например, если вы выбрали Германию, мы обогатим профили, расположенные в США, если у нас есть данные для выбранных брендов и интересов в США.</span><span class="sxs-lookup"><span data-stu-id="6fc43-138">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="6fc43-139">Настройка обогащения</span><span class="sxs-lookup"><span data-stu-id="6fc43-139">Configure enrichment</span></span>

<span data-ttu-id="6fc43-140">Управляемый опыт поможет вам настроить обогащения.</span><span class="sxs-lookup"><span data-stu-id="6fc43-140">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="6fc43-141">Определение торговых марок или интересов</span><span class="sxs-lookup"><span data-stu-id="6fc43-141">Define your brands or interests</span></span>

<span data-ttu-id="6fc43-142">Выберите до пяти брендов или интересов, используя один или оба из этих вариантов:</span><span class="sxs-lookup"><span data-stu-id="6fc43-142">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="6fc43-143">**Промышленность**: выберите свою отрасль из раскрывающегося списка, а затем выберите одну из ведущих торговых марок или интересов для этой отрасли.</span><span class="sxs-lookup"><span data-stu-id="6fc43-143">**Industry**: Select your industry from the dropdown list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="6fc43-144">**Свой выбор**: введите бренд или интерес, который имеет отношение к вашей организации, а затем выберите из подходящих предложений.</span><span class="sxs-lookup"><span data-stu-id="6fc43-144">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="6fc43-145">Если мы не указываем интересующий вас бренд или интерес, отправьте нам отзыв, используя ссылку **Предложить**.</span><span class="sxs-lookup"><span data-stu-id="6fc43-145">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="6fc43-146">Обзор предпочтений обогащения</span><span class="sxs-lookup"><span data-stu-id="6fc43-146">Review enrichment preferences</span></span>

<span data-ttu-id="6fc43-147">Изучите настройки обогащения по умолчанию и обновите их по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="6fc43-147">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Снимок экрана окна настроек обогащения.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="6fc43-149">Выберите сущность для обогащения</span><span class="sxs-lookup"><span data-stu-id="6fc43-149">Select entity to enrich</span></span>

<span data-ttu-id="6fc43-150">Выберите **Обогащенная сущность** и выберите набор данных, который вы хотите обогатить данными компании из Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6fc43-150">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="6fc43-151">Вы можете выбрать сущность "Клиент", чтобы обогатить все ваши профили клиентов, или выбрать сущность сегмента, чтобы обогатить только профили клиентов, содержащиеся в этом сегменте.</span><span class="sxs-lookup"><span data-stu-id="6fc43-151">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="6fc43-152">Сопоставление полей</span><span class="sxs-lookup"><span data-stu-id="6fc43-152">Map your fields</span></span>

<span data-ttu-id="6fc43-153">Сопоставьте поля из вашей объединенной сущности клиента, чтобы определить демографический сегмент, который система должна использовать для пополнения данных о клиентах.</span><span class="sxs-lookup"><span data-stu-id="6fc43-153">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="6fc43-154">Укажите страну/регион и по крайней мере атрибуты «Дата рождения» или «Пол».</span><span class="sxs-lookup"><span data-stu-id="6fc43-154">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="6fc43-155">Кроме того, необходимо сопоставить минимум один атрибут: город (и область, республика, край, округ) или почтовый индекс.</span><span class="sxs-lookup"><span data-stu-id="6fc43-155">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="6fc43-156">Выберите **Изменить**, чтобы определить сопоставление полей, и выберите **Применять**, когда вы закончите.</span><span class="sxs-lookup"><span data-stu-id="6fc43-156">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="6fc43-157">Выберите **Сохранить**, чтобы завершить отображение полей.</span><span class="sxs-lookup"><span data-stu-id="6fc43-157">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="6fc43-158">Поддерживаются следующие форматы и значения (значения не чувствительны к регистру):</span><span class="sxs-lookup"><span data-stu-id="6fc43-158">The following formats and values are supported (values are not case-sensitive):</span></span>

- <span data-ttu-id="6fc43-159">**Дата рождения**: мы рекомендуем преобразовывать дату рождения в тип DateTime во время приема данных.</span><span class="sxs-lookup"><span data-stu-id="6fc43-159">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="6fc43-160">В качестве альтернативы это может быть строка в [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) формат "гггг-ММ-дд" или "гггг-ММ-ддTЧЧ:мм:сс".</span><span class="sxs-lookup"><span data-stu-id="6fc43-160">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ss".</span></span>
- <span data-ttu-id="6fc43-161">**Пол**: Мужской, Женский, Неизвестный.</span><span class="sxs-lookup"><span data-stu-id="6fc43-161">**Gender**: Male, Female, Unknown.</span></span>
- <span data-ttu-id="6fc43-162">**Почтовый индекс**: пятизначные почтовые индексы для США, стандартный почтовый индекс для всех остальных.</span><span class="sxs-lookup"><span data-stu-id="6fc43-162">**Postal code**: Five-digit ZIP codes for United States, standard postal code everywhere else.</span></span>
- <span data-ttu-id="6fc43-163">**Город**: название города на английском языке.</span><span class="sxs-lookup"><span data-stu-id="6fc43-163">**City**: City name in English.</span></span>
- <span data-ttu-id="6fc43-164">**Штат/провинция**: двухбуквенное сокращение для США и Канады.</span><span class="sxs-lookup"><span data-stu-id="6fc43-164">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="6fc43-165">Аббревиатура из двух или трех букв для Австралии.</span><span class="sxs-lookup"><span data-stu-id="6fc43-165">Two- or three-letter abbreviation for Australia.</span></span> <span data-ttu-id="6fc43-166">Неприменимо для Франции, Германии или Соединенного Королевства.</span><span class="sxs-lookup"><span data-stu-id="6fc43-166">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="6fc43-167">**Страна или регион**:</span><span class="sxs-lookup"><span data-stu-id="6fc43-167">**Country/Region**:</span></span>

  - <span data-ttu-id="6fc43-168">US: Соединенные Штаты Америки, Соединенные Штаты, США, US, Америка</span><span class="sxs-lookup"><span data-stu-id="6fc43-168">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="6fc43-169">CA: Канада, CA</span><span class="sxs-lookup"><span data-stu-id="6fc43-169">CA: Canada, CA</span></span>
  - <span data-ttu-id="6fc43-170">GB: Соединенное Королевство, UK, GB, Соединенное Королевство Великобритании и Северной Ирландии, Соединенное Королевство Великобритании</span><span class="sxs-lookup"><span data-stu-id="6fc43-170">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="6fc43-171">AU: Австралия, AU, Австралийский союз</span><span class="sxs-lookup"><span data-stu-id="6fc43-171">AU: Australia, AU, Commonwealth of Australia</span></span>
  - <span data-ttu-id="6fc43-172">FR: Франция, FR, Французская Республика</span><span class="sxs-lookup"><span data-stu-id="6fc43-172">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="6fc43-173">DE: Германия, Deutschland, Allemagne, DE, Федеративная Республика Германия, Республика Германия</span><span class="sxs-lookup"><span data-stu-id="6fc43-173">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="6fc43-174">Просмотр и задание имени обогащения</span><span class="sxs-lookup"><span data-stu-id="6fc43-174">Review and name the enrichment</span></span>

<span data-ttu-id="6fc43-175">Наконец, вы можете просмотреть информацию и указать имя для обогащения.</span><span class="sxs-lookup"><span data-stu-id="6fc43-175">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Страница обзора интересов и задания имени.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="6fc43-177">Обновление обогащения</span><span class="sxs-lookup"><span data-stu-id="6fc43-177">Refresh enrichment</span></span>

<span data-ttu-id="6fc43-178">Запустите обогащение после настройки брендов, интересов и сопоставления полей для демографии.</span><span class="sxs-lookup"><span data-stu-id="6fc43-178">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="6fc43-179">Чтобы начать процесс, выберите **Выполнить** на странице конфигурации торговой марки или интереса.</span><span class="sxs-lookup"><span data-stu-id="6fc43-179">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="6fc43-180">Кроме того, вы можете позволить системе автоматически выполнять обогащение как часть запланированного обновления.</span><span class="sxs-lookup"><span data-stu-id="6fc43-180">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>

<span data-ttu-id="6fc43-181">В зависимости от размера данных о клиентах, выполнение процесса обогащения может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="6fc43-181">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="6fc43-182">Есть [шесть типов статусов](system.md#status-types) для задач/процессов.</span><span class="sxs-lookup"><span data-stu-id="6fc43-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="6fc43-183">Кроме того, большинство процессов [зависит от других последующих процессов](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="6fc43-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="6fc43-184">Вы можете выбрать статус процесса, чтобы увидеть детали выполнения всего задания.</span><span class="sxs-lookup"><span data-stu-id="6fc43-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="6fc43-185">После выбора **Показать подробности** для одной из задач задания вы найдете дополнительную информацию: время обработки, дату последней обработки, а также все ошибки и предупреждения, связанные с задачей.</span><span class="sxs-lookup"><span data-stu-id="6fc43-185">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="6fc43-186">Результаты обогащения</span><span class="sxs-lookup"><span data-stu-id="6fc43-186">Enrichment results</span></span>

<span data-ttu-id="6fc43-187">После запуска процесса обогащения перейдите к **Мои обогащения**, чтобы просмотреть общее количество обогащенных клиентов и разбивку брендов и интересов в обогащенных профилях клиентов.</span><span class="sxs-lookup"><span data-stu-id="6fc43-187">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Предварительный просмотр результатов после выполнения процесса обогащения":::

<span data-ttu-id="6fc43-189">Просмотрите обогащенные данные, выбрав **Просмотр обогащенных данных** на диаграмме.</span><span class="sxs-lookup"><span data-stu-id="6fc43-189">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="6fc43-190">Обогащенные данные для брендов направляются в сущность **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="6fc43-190">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="6fc43-191">Данные для интересов находятся в сущности **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="6fc43-191">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="6fc43-192">Вы также найдете эти сущности в списке в группе **Обогащение** в области **Данные** > **Сущности**.</span><span class="sxs-lookup"><span data-stu-id="6fc43-192">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="6fc43-193">Просмотр данных обогащения на карточке клиента</span><span class="sxs-lookup"><span data-stu-id="6fc43-193">See enrichment data on the customer card</span></span>

<span data-ttu-id="6fc43-194">Сродство с брендом и интересом также можно посмотреть на отдельных карточках клиентов.</span><span class="sxs-lookup"><span data-stu-id="6fc43-194">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="6fc43-195">Перейдите в раздел **Клиенты** и выберите профиль клиента.</span><span class="sxs-lookup"><span data-stu-id="6fc43-195">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="6fc43-196">В карточке клиента вы найдете диаграммы для торговых марок или интересов, к которым имеют отношение люди из демографического профиля этого клиента.</span><span class="sxs-lookup"><span data-stu-id="6fc43-196">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Карточка клиента с обогащенными данными":::

## <a name="next-steps"></a><span data-ttu-id="6fc43-198">Дальнейшие шаги</span><span class="sxs-lookup"><span data-stu-id="6fc43-198">Next steps</span></span>

<span data-ttu-id="6fc43-199">Основывайтесь на ваших обогащенных данных клиентов.</span><span class="sxs-lookup"><span data-stu-id="6fc43-199">Build on top of your enriched customer data.</span></span> <span data-ttu-id="6fc43-200">Создайте [Сегменты](segments.md) и [Меры](measures.md), и даже [экспортируйте данные](export-destinations.md), чтобы предоставить вашим клиентам индивидуальный подход.</span><span class="sxs-lookup"><span data-stu-id="6fc43-200">Create [Segments](segments.md) and [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
