---
title: Создание и изменение мер
description: Определите связанные с клиентами меры для анализа и отражения производительности в определенных сферах бизнеса.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406762"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="c3206-103">Определение мер и управление ими</span><span class="sxs-lookup"><span data-stu-id="c3206-103">Define and manage measures</span></span>

<span data-ttu-id="c3206-104">**Меры** представляют ключевые показатели эффективности (КПЭ), которые отражают эффективность и работоспособность конкретных сфер бизнеса.</span><span class="sxs-lookup"><span data-stu-id="c3206-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="c3206-105">Аналитика аудитории обеспечивает интуитивно понятный интерфейс для создания различных типов мер с помощью конструктора запросов, который не требует от вас написания кода или проверки мер вручную.</span><span class="sxs-lookup"><span data-stu-id="c3206-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="c3206-106">Вы можете отслеживать свои бизнес-меры на странице **Дом**, просматривать меры для конкретных клиентов на странице **Карта клиента** и использовать меры для определения сегментов клиентов на странице **Сегменты**.</span><span class="sxs-lookup"><span data-stu-id="c3206-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="c3206-107">Создание меры</span><span class="sxs-lookup"><span data-stu-id="c3206-107">Create a measure</span></span>

<span data-ttu-id="c3206-108">В этом разделе рассматриваются шаги создания меры с нуля.</span><span class="sxs-lookup"><span data-stu-id="c3206-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="c3206-109">Вы можете создавать меры с данными из нескольких источников данных, которые связаны через сущность клиента.</span><span class="sxs-lookup"><span data-stu-id="c3206-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="c3206-110">Есть некоторые [ограничения обслуживания](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="c3206-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="c3206-111">В аналитике аудитории перейдите **Меры**.</span><span class="sxs-lookup"><span data-stu-id="c3206-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="c3206-112">Выберите **Новая мера**.</span><span class="sxs-lookup"><span data-stu-id="c3206-112">Select **New measure**.</span></span>

3. <span data-ttu-id="c3206-113">Выберите меру **Тип**:</span><span class="sxs-lookup"><span data-stu-id="c3206-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="c3206-114">**Атрибут клиента**: одно поле для каждого клиента, которое отражает оценку, значение или состояние для клиента.</span><span class="sxs-lookup"><span data-stu-id="c3206-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="c3206-115">Атрибуты клиента создаются как атрибуты в новой созданной системой сущности, называемой **Customer_Measure**.</span><span class="sxs-lookup"><span data-stu-id="c3206-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="c3206-116">**Мера клиентов**: анализ поведения клиентов с разбивкой по выбранным измерениям.</span><span class="sxs-lookup"><span data-stu-id="c3206-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="c3206-117">Для каждой меры создается новая сущность, возможно, с несколькими записями для каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="c3206-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="c3206-118">**Бизнес-мера**: отслеживает эффективность вашего бизнеса и его работоспособность.</span><span class="sxs-lookup"><span data-stu-id="c3206-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="c3206-119">Бизнес-меры могут иметь два разных выходных значения: числовой вывод, который отображается на странице **Дом**, или новая сущность, которую можно найти на странице **Сущности**.</span><span class="sxs-lookup"><span data-stu-id="c3206-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="c3206-120">Укажите **Имя** и, необязательно, **Отображаемое имя**, затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c3206-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="c3206-121">В разделе **Сущности** выберите первую сущность в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="c3206-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="c3206-122">На этом этапе вы должны решить, нужны ли дополнительные сущности как часть вашего определения меры.</span><span class="sxs-lookup"><span data-stu-id="c3206-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c3206-123">![Определение меры](media/measure-definition.png "Определение меры")</span><span class="sxs-lookup"><span data-stu-id="c3206-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="c3206-124">Чтобы добавить больше сущностей, выберите **Добавить сущность** и выберите сущности, которые вы хотите использовать для меры.</span><span class="sxs-lookup"><span data-stu-id="c3206-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c3206-125">Можно выбрать только сущности, имеющие отношения с начальной сущностью.</span><span class="sxs-lookup"><span data-stu-id="c3206-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="c3206-126">Дополнительные сведения об определении отношений см. в разделе [Отношения](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="c3206-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="c3206-127">При желании вы можете настроить переменные.</span><span class="sxs-lookup"><span data-stu-id="c3206-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="c3206-128">В разделе **Переменные** выберите **Создать переменную**.</span><span class="sxs-lookup"><span data-stu-id="c3206-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="c3206-129">Переменные — это расчеты, которые выполняются для каждой выбранной записи.</span><span class="sxs-lookup"><span data-stu-id="c3206-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="c3206-130">Например, суммирование продаж через POS и Интернет для каждой записи клиентов.</span><span class="sxs-lookup"><span data-stu-id="c3206-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="c3206-131">Укажите **Имя** для переменной.</span><span class="sxs-lookup"><span data-stu-id="c3206-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="c3206-132">В области **Выражение** выберите поле, с которого нужно начать расчет.</span><span class="sxs-lookup"><span data-stu-id="c3206-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="c3206-133">Введите выражение в область **Выражение**, выбирая больше полей, которые будут включены в ваш расчет.</span><span class="sxs-lookup"><span data-stu-id="c3206-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c3206-134">В настоящее время поддерживаются только арифметические выражения.</span><span class="sxs-lookup"><span data-stu-id="c3206-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="c3206-135">Кроме того, расчет переменных не поддерживается для сущностей из разных [путей сущностей](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="c3206-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="c3206-136">Выберите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="c3206-136">Select **Done**.</span></span>

11. <span data-ttu-id="c3206-137">В разделе **Определение меры** вы определите, как выбранные вами объекты и вычисленные переменные объединяются в новой сущности или атрибуте меры.</span><span class="sxs-lookup"><span data-stu-id="c3206-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="c3206-138">Выберите **Создать измерение**.</span><span class="sxs-lookup"><span data-stu-id="c3206-138">Select **New dimension**.</span></span> <span data-ttu-id="c3206-139">Вы можете думать о измерении как о функции *группировать по*.</span><span class="sxs-lookup"><span data-stu-id="c3206-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="c3206-140">Вывод данных вашей сущности или атрибута меры будет сгруппирован по всем определенным вами измерениям.</span><span class="sxs-lookup"><span data-stu-id="c3206-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c3206-141">![Выбор цикла агрегирования](media/measures-businessreport-measure-definition2.png "Выбор цикла агрегирования")</span><span class="sxs-lookup"><span data-stu-id="c3206-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="c3206-142">Выберите или введите следующую информацию как часть определения измерения:</span><span class="sxs-lookup"><span data-stu-id="c3206-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="c3206-143">**Сущность**: если вы определяете сущность меры, она должна содержать хотя бы один атрибут.</span><span class="sxs-lookup"><span data-stu-id="c3206-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="c3206-144">Если вы определите атрибут меры, он будет включать только один атрибут по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c3206-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="c3206-145">Это выбор касается выбора сущности, которая включает этот атрибут.</span><span class="sxs-lookup"><span data-stu-id="c3206-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="c3206-146">**Поле**: выберите конкретный атрибут, который требуется включить в сущность или атрибут меры.</span><span class="sxs-lookup"><span data-stu-id="c3206-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="c3206-147">**Группа**: выберите, хотите ли вы агрегировать данные на ежедневной, ежемесячной или годовой основе.</span><span class="sxs-lookup"><span data-stu-id="c3206-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="c3206-148">Это обязательный выбор только если вы выбрали атрибут типа данных.</span><span class="sxs-lookup"><span data-stu-id="c3206-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="c3206-149">**Как**: определяет имя вашего нового поля.</span><span class="sxs-lookup"><span data-stu-id="c3206-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="c3206-150">**Отображаемое имя**: определяет отображаемое имя вашего поля.</span><span class="sxs-lookup"><span data-stu-id="c3206-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c3206-151">Ваша бизнес-мера будет сохранена как сущность с одним числом и появится на странице **Дом**, если вы не добавите больше измерений к своей мере.</span><span class="sxs-lookup"><span data-stu-id="c3206-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="c3206-152">После добавления дополнительных измерений мера *не будет* отображаться на странице **Дом**.</span><span class="sxs-lookup"><span data-stu-id="c3206-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="c3206-153">При желании добавьте функции агрегирования.</span><span class="sxs-lookup"><span data-stu-id="c3206-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="c3206-154">Любое созданное вами агрегирование приводит к новому значению в сущности или атрибуте меры.</span><span class="sxs-lookup"><span data-stu-id="c3206-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="c3206-155">Поддерживаются следующие функции агрегирования: **Мин.**, **Макс.**, **Среднее**, **Медиана**, **Сумма**, **Количество уникальных**, **Первый** (принимает первую запись значения измерения) и **Последний** (принимает последнюю запись, добавленную к значению измерения).</span><span class="sxs-lookup"><span data-stu-id="c3206-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="c3206-156">Выберите **Сохранить**, чтобы применить изменения к мере.</span><span class="sxs-lookup"><span data-stu-id="c3206-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="c3206-157">Управление вашими мерами</span><span class="sxs-lookup"><span data-stu-id="c3206-157">Manage your measures</span></span>

<span data-ttu-id="c3206-158">После создания хотя бы одной меры вы увидите список мер на странице **Меры**.</span><span class="sxs-lookup"><span data-stu-id="c3206-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="c3206-159">Вы найдете информацию о типе меры, создателе, дате и времени создания, дате и времени последнего изменения, статусе (является ли мера активной, неактивной или сбойной) и дате и времени последнего обновления.</span><span class="sxs-lookup"><span data-stu-id="c3206-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="c3206-160">Когда вы выбираете меру из списка, вы можете увидеть предварительный просмотр ее результата.</span><span class="sxs-lookup"><span data-stu-id="c3206-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="c3206-161">Чтобы обновить все ваши меры одновременно, выберите **Обновить все** без выбора конкретной меры.</span><span class="sxs-lookup"><span data-stu-id="c3206-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c3206-162">![Действия для управления отдельными мерами](media/measure-actions.png "Действия для управления отдельными мерами")</span><span class="sxs-lookup"><span data-stu-id="c3206-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="c3206-163">Или выберите меру из списка и выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="c3206-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="c3206-164">Выберите имя меры, чтобы увидеть ее сведения.</span><span class="sxs-lookup"><span data-stu-id="c3206-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="c3206-165">**Изменить** конфигурацию меры.</span><span class="sxs-lookup"><span data-stu-id="c3206-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="c3206-166">**Переименовать** меру.</span><span class="sxs-lookup"><span data-stu-id="c3206-166">**Rename** the measure.</span></span>
- <span data-ttu-id="c3206-167">**Удалить** меру.</span><span class="sxs-lookup"><span data-stu-id="c3206-167">**Delete** the measure.</span></span>
- <span data-ttu-id="c3206-168">Выберите многоточие (...), затем **Обновить**, чтобы начать процесс обновления для меры.</span><span class="sxs-lookup"><span data-stu-id="c3206-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="c3206-169">Выберите многоточие (...), затем **Скачать**, чтобы получить .CSV файл меры.</span><span class="sxs-lookup"><span data-stu-id="c3206-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="c3206-170">Есть [шесть типов статусов](system.md#status-types) для задач/процессов.</span><span class="sxs-lookup"><span data-stu-id="c3206-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="c3206-171">Кроме того, большинство процессов [зависит от других последующих процессов](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="c3206-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="c3206-172">Вы можете выбрать статус процесса, чтобы увидеть детали выполнения всего задания.</span><span class="sxs-lookup"><span data-stu-id="c3206-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="c3206-173">После выбора **См. сведения** для одной из задач задания вы найдете дополнительную информацию: время обработки, дату последней обработки, а также все ошибки и предупреждения, связанные с задачей.</span><span class="sxs-lookup"><span data-stu-id="c3206-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="c3206-174">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="c3206-174">Next step</span></span>

<span data-ttu-id="c3206-175">Вы можете использовать существующие меры для создания своего первого клиентского сегмента на странице **Сегменты**.</span><span class="sxs-lookup"><span data-stu-id="c3206-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="c3206-176">Дополнительные сведения см. в разделе [Сегменты](segments.md).</span><span class="sxs-lookup"><span data-stu-id="c3206-176">For more information, see [Segments](segments.md).</span></span>
