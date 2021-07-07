---
title: Обогащение расширения адресов
description: Обогащайте и нормализируйте адресную информацию в профилях клиентов с помощью моделей Microsoft.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e0ca731f944da9a7eaae7c2dc2d7568b6386089f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305448"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="74c08-103">Пополнение профилей клиентов расширенными адресами</span><span class="sxs-lookup"><span data-stu-id="74c08-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="74c08-104">Адреса в ваших данных могут быть неструктурированными, неполными или неправильными.</span><span class="sxs-lookup"><span data-stu-id="74c08-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="74c08-105">Используйте модели Microsoft для нормализации и обогащения ваших адресов в [формате Common Data Model](/common-data-model/schema/core/applicationcommon/address) для большей точности и понимания.</span><span class="sxs-lookup"><span data-stu-id="74c08-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="74c08-106">Как мы улучшаем адреса</span><span class="sxs-lookup"><span data-stu-id="74c08-106">How we enhance addresses</span></span>

<span data-ttu-id="74c08-107">Наша модель проходит через двухэтапный процесс улучшения адреса.</span><span class="sxs-lookup"><span data-stu-id="74c08-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="74c08-108">Во-первых, она анализирует адрес для идентификации его компонентов и помещает их в структурированный формат.</span><span class="sxs-lookup"><span data-stu-id="74c08-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="74c08-109">Затем мы используем ИИ для исправления, заполнения и стандартизации значений в адресе.</span><span class="sxs-lookup"><span data-stu-id="74c08-109">Then, we use AI to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="74c08-110">Пример</span><span class="sxs-lookup"><span data-stu-id="74c08-110">Example</span></span>

<span data-ttu-id="74c08-111">Информация адреса может быть в нестандартном формате и содержать орфографические ошибки.</span><span class="sxs-lookup"><span data-stu-id="74c08-111">Address information might be in a nonstandard format and contain spelling errors.</span></span> <span data-ttu-id="74c08-112">Модель может исправить эти проблемы и создать согласованные адреса в унифицированных профилях клиентов.</span><span class="sxs-lookup"><span data-stu-id="74c08-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="74c08-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="74c08-113">Limitations</span></span>

<span data-ttu-id="74c08-114">Улучшенные адреса работают только со значениями, которые уже существуют в ваших принятых адресных данных.</span><span class="sxs-lookup"><span data-stu-id="74c08-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="74c08-115">Модель не выполняет следующих действий:</span><span class="sxs-lookup"><span data-stu-id="74c08-115">The model doesn't:</span></span> 

1. <span data-ttu-id="74c08-116">Не проверяет, что адрес действительный.</span><span class="sxs-lookup"><span data-stu-id="74c08-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="74c08-117">Не проверяет действительность любых значений, таких как почтовые индексы или названия улиц.</span><span class="sxs-lookup"><span data-stu-id="74c08-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="74c08-118">Не изменяет значения, которые она не распознает.</span><span class="sxs-lookup"><span data-stu-id="74c08-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="74c08-119">Модель использует методы машинного обучения для улучшения адресов.</span><span class="sxs-lookup"><span data-stu-id="74c08-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="74c08-120">Хотя мы применяем высокий порог достоверности, когда модель изменяет входное значение, как и в случае с любой моделью на основе машинного обучения, 100-процентная точность не гарантируется.</span><span class="sxs-lookup"><span data-stu-id="74c08-120">While we apply a high confidence threshold for when the model changes an input value, as with any machine learning-based model, 100 percent accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="74c08-121">Поддерживаемые страны или регионы</span><span class="sxs-lookup"><span data-stu-id="74c08-121">Supported countries or regions</span></span>

<span data-ttu-id="74c08-122">В настоящее время мы поддерживаем обогащение адресов в следующих странах или регионах:</span><span class="sxs-lookup"><span data-stu-id="74c08-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="74c08-123">Австралия</span><span class="sxs-lookup"><span data-stu-id="74c08-123">Australia</span></span>
- <span data-ttu-id="74c08-124">Канада</span><span class="sxs-lookup"><span data-stu-id="74c08-124">Canada</span></span>
- <span data-ttu-id="74c08-125">Соединенное Королевство</span><span class="sxs-lookup"><span data-stu-id="74c08-125">United Kingdom</span></span>
- <span data-ttu-id="74c08-126">Соединенные Штаты</span><span class="sxs-lookup"><span data-stu-id="74c08-126">United States</span></span>

<span data-ttu-id="74c08-127">Адреса должны содержать значение страны/региона.</span><span class="sxs-lookup"><span data-stu-id="74c08-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="74c08-128">Мы не обрабатываем адреса для стран или регионов, которые не поддерживаются, и адреса, для которых не указана страна или регион.</span><span class="sxs-lookup"><span data-stu-id="74c08-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="74c08-129">Настройка обогащения</span><span class="sxs-lookup"><span data-stu-id="74c08-129">Configure the enrichment</span></span>

1. <span data-ttu-id="74c08-130">Перейти к **Данные** > **Обогащение**.</span><span class="sxs-lookup"><span data-stu-id="74c08-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="74c08-131">Выберите **Обогатить мои данные** на плитке **Расширенные адреса**.</span><span class="sxs-lookup"><span data-stu-id="74c08-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Снимок экрана плитки расширенных адресов.":::

1. <span data-ttu-id="74c08-133">Выберите **Набор данных клиента** и выберите сущность, содержащую адреса, которые вы хотите обогатить.</span><span class="sxs-lookup"><span data-stu-id="74c08-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="74c08-134">Вы можете выбрать сущность *Клиент* для обогащения адресов во всех ваших профилях клиентов или выбрать сущность сегмента для обогащения адресов только в профилях клиентов, содержащихся в этом сегменте.</span><span class="sxs-lookup"><span data-stu-id="74c08-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="74c08-135">Выберите формат адресов в вашем наборе данных.</span><span class="sxs-lookup"><span data-stu-id="74c08-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="74c08-136">Выберите **Адрес, состоящий из одного атрибута**, если адреса в ваших данных используют одно поле.</span><span class="sxs-lookup"><span data-stu-id="74c08-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="74c08-137">Выберите **Адрес с несколькими атрибутами**, если адреса в ваших данных используют более одного поля данных.</span><span class="sxs-lookup"><span data-stu-id="74c08-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="74c08-138">Страна или регион является обязательным в адресах как с одним, так и с несколькими атрибутами.</span><span class="sxs-lookup"><span data-stu-id="74c08-138">Country/Region is mandatory in both single-attribute and multiple-attribute addresses.</span></span> <span data-ttu-id="74c08-139">Адреса, которые не содержат действительных или поддерживаемых значений страны/региона, не будут обогащаться.</span><span class="sxs-lookup"><span data-stu-id="74c08-139">Addresses that don't contain valid or supported country/region values won't be enriched.</span></span>

1.  <span data-ttu-id="74c08-140">Сопоставьте поля адреса из вашей единой сущности клиента.</span><span class="sxs-lookup"><span data-stu-id="74c08-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Страница сопоставления полей улучшенного адреса.":::

1. <span data-ttu-id="74c08-142">Выберите **Далее**, чтобы завершить сопоставление полей.</span><span class="sxs-lookup"><span data-stu-id="74c08-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="74c08-143">Укажите имя для обогащения и выходную сущность.</span><span class="sxs-lookup"><span data-stu-id="74c08-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="74c08-144">Выберите **Сохранить обогащение** после просмотра вашего выбора.</span><span class="sxs-lookup"><span data-stu-id="74c08-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="74c08-145">Результаты обогащения</span><span class="sxs-lookup"><span data-stu-id="74c08-145">Enrichment results</span></span>

<span data-ttu-id="74c08-146">Чтобы начать процесс обогащения, выберите **Выполнить** на панели команд.</span><span class="sxs-lookup"><span data-stu-id="74c08-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="74c08-147">Вы также можете позволить системе запускать обогащение автоматически как часть [запланированного обновления](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="74c08-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="74c08-148">Время обработки зависит от размера данных вашего клиента.</span><span class="sxs-lookup"><span data-stu-id="74c08-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="74c08-149">После завершения процесса обогащения вы можете просмотреть недавно обогащенные данные профилей клиентов в разделе **Мои обогащения**.</span><span class="sxs-lookup"><span data-stu-id="74c08-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="74c08-150">Кроме того, вы найдете время последнего обновления и количество обогащенных профилей.</span><span class="sxs-lookup"><span data-stu-id="74c08-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="74c08-151">Вы можете получить доступ к детализированному представлению каждого обогащенного профиля, выбрав **Просмотр обогащенных данных**.</span><span class="sxs-lookup"><span data-stu-id="74c08-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="74c08-152">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="74c08-152">Next steps</span></span>

<span data-ttu-id="74c08-153">Основывайтесь на ваших обогащенных данных клиентов.</span><span class="sxs-lookup"><span data-stu-id="74c08-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="74c08-154">Создайте [сегменты](segments.md) и [меры](measures.md), и даже [экспортируйте данные](export-destinations.md), чтобы предоставить вашим клиентам индивидуальный подход.</span><span class="sxs-lookup"><span data-stu-id="74c08-154">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
