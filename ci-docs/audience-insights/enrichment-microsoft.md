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
ms.openlocfilehash: 6f19033236190547f68d2b91ec6b32074bf7912a
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896618"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="db80e-103">Обогащение профилей клиентов общностью с брендами и интересами (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="db80e-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="db80e-104">Используйте собственные данные Microsoft, чтобы обогатить данные о клиентах с учетом общности с брендом и интересов.</span><span class="sxs-lookup"><span data-stu-id="db80e-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="db80e-105">Эти общности определяются на основе данных от людей с демографическими характеристиками, аналогичными вашим клиентам.</span><span class="sxs-lookup"><span data-stu-id="db80e-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="db80e-106">Эта информация поможет вам лучше понять и сегментировать ваших клиентов на основе их привязанности к конкретным брендам и интересам.</span><span class="sxs-lookup"><span data-stu-id="db80e-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="db80e-107">В аналитике аудитории перейдите **Данные** > **Обогащение**, чтобы [настраивать и просматривать обогащения](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="db80e-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="db80e-108">Чтобы настроить обогащение общностей с торговыми марками, перейдите к вкладке **Обнаружить** и выберите **Обогатить мои данные** на плитке **Торговые марки**.</span><span class="sxs-lookup"><span data-stu-id="db80e-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="db80e-109">Чтобы настроить обогащение общностей интересов, перейдите к вкладке **Обнаружить** и выберите **Обогатить мои данные** на плитке **Интересы**.</span><span class="sxs-lookup"><span data-stu-id="db80e-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="db80e-110">![Плитки торговых марок и интересов](media/BrandsInterest-tile-Hub.png "Плитки торговых марок и интереса")</span><span class="sxs-lookup"><span data-stu-id="db80e-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="db80e-111">Как мы определяем общность</span><span class="sxs-lookup"><span data-stu-id="db80e-111">How we determine affinities</span></span>

<span data-ttu-id="db80e-112">Мы используем данные интернет-поиска Microsoft, чтобы найти общность с брендами и интересами в различных демографических сегментах (в зависимости от возраста, пола или местоположения).</span><span class="sxs-lookup"><span data-stu-id="db80e-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="db80e-113">Объем онлайн-поиска по бренду или интересу определяет, насколько много общности демографический сегмент по сравнению с другими сегментами имеет к данному бренду или интересу.</span><span class="sxs-lookup"><span data-stu-id="db80e-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span> <span data-ttu-id="db80e-114">бренд или интерес.</span><span class="sxs-lookup"><span data-stu-id="db80e-114">brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="db80e-115">Уровень сходства и оценка</span><span class="sxs-lookup"><span data-stu-id="db80e-115">Affinity level and score</span></span>

<span data-ttu-id="db80e-116">В каждом обогащенном профиле клиента мы указываем два связанных значения: уровень сходства и оценка сходства.</span><span class="sxs-lookup"><span data-stu-id="db80e-116">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="db80e-117">Эти значения помогают определить, насколько сильно сходство для демографического сегмента этого профиля, для бренда или интереса, по сравнению с другими демографическими сегментами.</span><span class="sxs-lookup"><span data-stu-id="db80e-117">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="db80e-118">*Уровень сходства* состоит из четырех уровней, а *оценка сходства* рассчитывается по 100-балльной шкале, соответствующей уровням сходства.</span><span class="sxs-lookup"><span data-stu-id="db80e-118">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="db80e-119">Уровень сходства</span><span class="sxs-lookup"><span data-stu-id="db80e-119">Affinity level</span></span> |<span data-ttu-id="db80e-120">Показатель близости</span><span class="sxs-lookup"><span data-stu-id="db80e-120">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="db80e-121">Очень высокий</span><span class="sxs-lookup"><span data-stu-id="db80e-121">Very high</span></span>     | <span data-ttu-id="db80e-122">85–100</span><span class="sxs-lookup"><span data-stu-id="db80e-122">85-100</span></span>       |
|<span data-ttu-id="db80e-123">Высокое</span><span class="sxs-lookup"><span data-stu-id="db80e-123">High</span></span>     | <span data-ttu-id="db80e-124">70–84</span><span class="sxs-lookup"><span data-stu-id="db80e-124">70-84</span></span>        |
|<span data-ttu-id="db80e-125">Средний</span><span class="sxs-lookup"><span data-stu-id="db80e-125">Medium</span></span>     | <span data-ttu-id="db80e-126">35–69</span><span class="sxs-lookup"><span data-stu-id="db80e-126">35-69</span></span>        |
|<span data-ttu-id="db80e-127">Низкое</span><span class="sxs-lookup"><span data-stu-id="db80e-127">Low</span></span>     | <span data-ttu-id="db80e-128">1–34</span><span class="sxs-lookup"><span data-stu-id="db80e-128">1-34</span></span>        |

<span data-ttu-id="db80e-129">В зависимости от степени детализации, по которой вы хотите измерять сходство, вы можете использовать либо уровень сходства, либо оценку.</span><span class="sxs-lookup"><span data-stu-id="db80e-129">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="db80e-130">Оценка сходства дает вам более точный контроль.</span><span class="sxs-lookup"><span data-stu-id="db80e-130">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="db80e-131">Поддерживаемые страны/регионы</span><span class="sxs-lookup"><span data-stu-id="db80e-131">Supported countries/regions</span></span>

<span data-ttu-id="db80e-132">В настоящее время мы поддерживаем следующие страны/регионы: Австралия, Канада (английский), Франция, Германия, Соединенное Королевство или США (английский).</span><span class="sxs-lookup"><span data-stu-id="db80e-132">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="db80e-133">Чтобы выбрать страну, откройте **Обогащение брендов** или **Обогащение интересов** и выберите **Изменить** рядом с пунктом **Страна/регион**.</span><span class="sxs-lookup"><span data-stu-id="db80e-133">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="db80e-134">На панели **Параметры страны/региона** выберите вариант и выберите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="db80e-134">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="db80e-135">Последствия, связанные с выбором страны</span><span class="sxs-lookup"><span data-stu-id="db80e-135">Implications related to country selection</span></span>

- <span data-ttu-id="db80e-136">При [выборе собственных брендов](#define-your-brands-or-interests) система предлагает варианты для выбранной страны или региона.</span><span class="sxs-lookup"><span data-stu-id="db80e-136">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="db80e-137">При [выборе отрасли](#define-your-brands-or-interests) вы получите наиболее подходящие бренды или интересы в зависимости от выбранной страны или региона.</span><span class="sxs-lookup"><span data-stu-id="db80e-137">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="db80e-138">При [обогащении профилей](#refresh-enrichment) мы обогатим все профили клиентов, для которых мы получаем данные по выбранным брендам и интересам.</span><span class="sxs-lookup"><span data-stu-id="db80e-138">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="db80e-139">Включая профили, не относящиеся к выбранной стране или региону.</span><span class="sxs-lookup"><span data-stu-id="db80e-139">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="db80e-140">Например, если вы выбрали Германию, мы обогатим профили, расположенные в США, если у нас есть данные для выбранных брендов и интересов в США.</span><span class="sxs-lookup"><span data-stu-id="db80e-140">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="db80e-141">Настройка обогащения</span><span class="sxs-lookup"><span data-stu-id="db80e-141">Configure Enrichment</span></span>

<span data-ttu-id="db80e-142">Управляемый опыт поможет вам настроить обогащения.</span><span class="sxs-lookup"><span data-stu-id="db80e-142">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="db80e-143">Определение торговых марок или интересов</span><span class="sxs-lookup"><span data-stu-id="db80e-143">Define your brands or interests</span></span>

<span data-ttu-id="db80e-144">Выберите один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="db80e-144">Select one of the following options:</span></span>

- <span data-ttu-id="db80e-145">**Отрасль**: система определяет лучшие бренды или интересы, относящиеся к вашей отрасли, и обогащает ими данные ваших клиентов.</span><span class="sxs-lookup"><span data-stu-id="db80e-145">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="db80e-146">**Указать собственные**: выберите до пяти наименований из списка брендов или интересов, которые наиболее актуальны для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="db80e-146">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="db80e-147">Чтобы добавить бренд или интерес, введите его в область ввода, чтобы получить предложения на основе соответствующих терминов.</span><span class="sxs-lookup"><span data-stu-id="db80e-147">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="db80e-148">Если мы не указываем интересующий вас бренд или интерес, отправьте нам отзыв, используя ссылку **Предложить**.</span><span class="sxs-lookup"><span data-stu-id="db80e-148">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="db80e-149">Обзор предпочтений обогащения</span><span class="sxs-lookup"><span data-stu-id="db80e-149">Review enrichment preferences</span></span>

<span data-ttu-id="db80e-150">Изучите настройки обогащения по умолчанию и обновите их по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="db80e-150">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Снимок экрана окна настроек обогащения.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="db80e-152">Выберите сущность для обогащения</span><span class="sxs-lookup"><span data-stu-id="db80e-152">Select entity to enrich</span></span>

<span data-ttu-id="db80e-153">Выберите **Обогащенная сущность** и выберите набор данных, который вы хотите обогатить данными компании из Microsoft.</span><span class="sxs-lookup"><span data-stu-id="db80e-153">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="db80e-154">Вы можете выбрать сущность "Клиент", чтобы обогатить все ваши профили клиентов, или выбрать сущность сегмента, чтобы обогатить только профили клиентов, содержащиеся в этом сегменте.</span><span class="sxs-lookup"><span data-stu-id="db80e-154">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="db80e-155">Сопоставление полей</span><span class="sxs-lookup"><span data-stu-id="db80e-155">Map your fields</span></span>

<span data-ttu-id="db80e-156">Сопоставьте поля из вашей объединенной сущности клиента, чтобы определить демографический сегмент, который система должна использовать для пополнения данных о клиентах.</span><span class="sxs-lookup"><span data-stu-id="db80e-156">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="db80e-157">Укажите страну/регион и по крайней мере атрибуты «Дата рождения» или «Пол».</span><span class="sxs-lookup"><span data-stu-id="db80e-157">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="db80e-158">Кроме того, необходимо сопоставить минимум один атрибут: город (и область, республика, край, округ) или почтовый индекс.</span><span class="sxs-lookup"><span data-stu-id="db80e-158">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="db80e-159">Выберите **Изменить**, чтобы определить сопоставление полей, и выберите **Применять**, когда вы закончите.</span><span class="sxs-lookup"><span data-stu-id="db80e-159">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="db80e-160">Выберите **Сохранить**, чтобы завершить отображение полей.</span><span class="sxs-lookup"><span data-stu-id="db80e-160">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="db80e-161">Поддерживаются следующие форматы и значения, значения не чувствительны к регистру:</span><span class="sxs-lookup"><span data-stu-id="db80e-161">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="db80e-162">**Дата рождения**: мы рекомендуем преобразовывать дату рождения в тип DateTime во время приема данных.</span><span class="sxs-lookup"><span data-stu-id="db80e-162">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="db80e-163">Как вариант, это может быть строка в формате [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "гггг-ММ-дд" или "гггг-ММ-ддTЧЧ:мм:ссZ".</span><span class="sxs-lookup"><span data-stu-id="db80e-163">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="db80e-164">**Пол**: Мужской, Женский, Неизвестный</span><span class="sxs-lookup"><span data-stu-id="db80e-164">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="db80e-165">**Почтовый индекс**: пятизначные почтовые индексы для США, стандартный почтовый индекс во всех остальных странах/регионах</span><span class="sxs-lookup"><span data-stu-id="db80e-165">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="db80e-166">**Город**: название города на английском языке</span><span class="sxs-lookup"><span data-stu-id="db80e-166">**City**: City name in English</span></span>
- <span data-ttu-id="db80e-167">**Штат/провинция**: двухбуквенное сокращение для США и Канады.</span><span class="sxs-lookup"><span data-stu-id="db80e-167">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="db80e-168">Аббревиатура из двух или трех букв для Австралии.</span><span class="sxs-lookup"><span data-stu-id="db80e-168">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="db80e-169">Неприменимо для Франции, Германии или Соединенного Королевства.</span><span class="sxs-lookup"><span data-stu-id="db80e-169">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="db80e-170">**Страна или регион**:</span><span class="sxs-lookup"><span data-stu-id="db80e-170">**Country/Region**:</span></span>

  - <span data-ttu-id="db80e-171">US: Соединенные Штаты Америки, Соединенные Штаты, США, US, Америка</span><span class="sxs-lookup"><span data-stu-id="db80e-171">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="db80e-172">CA: Канада, CA</span><span class="sxs-lookup"><span data-stu-id="db80e-172">CA: Canada, CA</span></span>
  - <span data-ttu-id="db80e-173">GB: Соединенное Королевство, UK, GB, Соединенное Королевство Великобритании и Северной Ирландии, Соединенное Королевство Великобритании</span><span class="sxs-lookup"><span data-stu-id="db80e-173">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="db80e-174">AU: Австралия, AU, Содружество Австралии</span><span class="sxs-lookup"><span data-stu-id="db80e-174">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="db80e-175">FR: Франция, FR, Французская Республика</span><span class="sxs-lookup"><span data-stu-id="db80e-175">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="db80e-176">DE: Германия, Deutschland, Allemagne, DE, Федеративная Республика Германия, Республика Германия</span><span class="sxs-lookup"><span data-stu-id="db80e-176">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="db80e-177">Просмотр и задание имени обогащения</span><span class="sxs-lookup"><span data-stu-id="db80e-177">Review and name the enrichment</span></span>

<span data-ttu-id="db80e-178">Наконец, вы можете просмотреть информацию и указать имя для обогащения.</span><span class="sxs-lookup"><span data-stu-id="db80e-178">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Страница обзора интересов и задания имени.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="db80e-180">Обновление обогащения</span><span class="sxs-lookup"><span data-stu-id="db80e-180">Refresh enrichment</span></span>

<span data-ttu-id="db80e-181">Запустите обогащение после настройки брендов, интересов и сопоставления полей для демографии.</span><span class="sxs-lookup"><span data-stu-id="db80e-181">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="db80e-182">Чтобы начать процесс, выберите **Выполнить** на странице конфигурации торговой марки или интереса.</span><span class="sxs-lookup"><span data-stu-id="db80e-182">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="db80e-183">Кроме того, вы можете позволить системе автоматически выполнять обогащение как часть запланированного обновления.</span><span class="sxs-lookup"><span data-stu-id="db80e-183">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="db80e-184">В зависимости от размера данных о клиентах, выполнение процесса обогащения может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="db80e-184">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="db80e-185">Есть [шесть типов статусов](system.md#status-types) для задач/процессов.</span><span class="sxs-lookup"><span data-stu-id="db80e-185">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="db80e-186">Кроме того, большинство процессов [зависит от других последующих процессов](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="db80e-186">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="db80e-187">Вы можете выбрать статус процесса, чтобы увидеть детали выполнения всего задания.</span><span class="sxs-lookup"><span data-stu-id="db80e-187">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="db80e-188">После выбора **См. сведения** для одной из задач задания вы найдете дополнительную информацию: время обработки, дату последней обработки, а также все ошибки и предупреждения, связанные с задачей.</span><span class="sxs-lookup"><span data-stu-id="db80e-188">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="db80e-189">Результаты обогащения</span><span class="sxs-lookup"><span data-stu-id="db80e-189">Enrichment results</span></span>

<span data-ttu-id="db80e-190">После запуска процесса обогащения перейдите к **Мои обогащения**, чтобы просмотреть общее количество обогащенных клиентов и разбивку брендов и интересов в обогащенных профилях клиентов.</span><span class="sxs-lookup"><span data-stu-id="db80e-190">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Предварительный просмотр результатов после выполнения процесса обогащения":::

<span data-ttu-id="db80e-192">Просмотрите обогащенные данные, выбрав **Просмотр обогащенных данных** на диаграмме.</span><span class="sxs-lookup"><span data-stu-id="db80e-192">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="db80e-193">Обогащенные данные для брендов направляются в сущность **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="db80e-193">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="db80e-194">Данные для интересов находятся в сущности **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="db80e-194">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="db80e-195">Вы также найдете эти сущности в списке в группе **Обогащение** в области **Данные** > **Сущности**.</span><span class="sxs-lookup"><span data-stu-id="db80e-195">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="db80e-196">Просмотр данных обогащения на карточке клиента</span><span class="sxs-lookup"><span data-stu-id="db80e-196">See enrichment data on the customer card</span></span>

<span data-ttu-id="db80e-197">Сродство с брендом и интересом также можно посмотреть на отдельных карточках клиентов.</span><span class="sxs-lookup"><span data-stu-id="db80e-197">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="db80e-198">Перейдите в раздел **Клиенты** и выберите профиль клиента.</span><span class="sxs-lookup"><span data-stu-id="db80e-198">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="db80e-199">В карточке клиента вы найдете диаграммы для торговых марок или интересов, к которым имеют отношение люди из демографического профиля этого клиента.</span><span class="sxs-lookup"><span data-stu-id="db80e-199">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Карточка клиента с обогащенными данными":::

## <a name="next-steps"></a><span data-ttu-id="db80e-201">Дальнейшие шаги</span><span class="sxs-lookup"><span data-stu-id="db80e-201">Next steps</span></span>

<span data-ttu-id="db80e-202">Основывайтесь на ваших обогащенных данных клиентов.</span><span class="sxs-lookup"><span data-stu-id="db80e-202">Build on top of your enriched customer data.</span></span> <span data-ttu-id="db80e-203">Создайте [Сегменты](segments.md), [меры](measures.md) и даже [экспортируйте данные](export-destinations.md), чтобы предоставлять персонализированное взаимодействие вашим клиентам.</span><span class="sxs-lookup"><span data-stu-id="db80e-203">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
