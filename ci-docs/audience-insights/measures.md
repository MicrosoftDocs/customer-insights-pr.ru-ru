---
title: Создание мер и управление ими
description: Определите меры для анализа и отражения эффективности вашего бизнеса.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269944"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="36a79-103">Определение мер и управление ими</span><span class="sxs-lookup"><span data-stu-id="36a79-103">Define and manage measures</span></span>

<span data-ttu-id="36a79-104">Меры помогают лучше понять поведение клиентов и эффективность бизнеса, извлекая соответствующие значения из [единых профилей](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="36a79-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="36a79-105">Например, компания хочет видеть *общие расходы на одного клиента*, чтобы понять историю покупок отдельного клиента.</span><span class="sxs-lookup"><span data-stu-id="36a79-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="36a79-106">Или измерить *общий объем продаж компании*, чтобы понять совокупный доход для всего бизнеса.</span><span class="sxs-lookup"><span data-stu-id="36a79-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="36a79-107">Меры создаются с помощью построителя мер, платформы запросов данных с различными операторами и простыми вариантами сопоставления.</span><span class="sxs-lookup"><span data-stu-id="36a79-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="36a79-108">Система позволяет фильтровать данные, группировать результаты, обнаруживать [пути отношений сущностей](relationships.md) и просматривать выходные данные.</span><span class="sxs-lookup"><span data-stu-id="36a79-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="36a79-109">Используйте конструктор мер для планирования бизнес-действий, запрашивая данные о клиентах и извлекая аналитические данные.</span><span class="sxs-lookup"><span data-stu-id="36a79-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="36a79-110">Например, создание меры *общие расходы на одного клиента* и *общий доход на одного клиента* помогает идентифицировать группу клиентов с высокими расходами, но высокой отдачей.</span><span class="sxs-lookup"><span data-stu-id="36a79-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="36a79-111">Вы можете [создать сегмент](segments.md), чтобы управлять следующими лучшими действиями.</span><span class="sxs-lookup"><span data-stu-id="36a79-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="36a79-112">Создание меры</span><span class="sxs-lookup"><span data-stu-id="36a79-112">Create a measure</span></span>

<span data-ttu-id="36a79-113">В этом разделе описывается создание новой меры с нуля.</span><span class="sxs-lookup"><span data-stu-id="36a79-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="36a79-114">Вы можете создать меру с атрибутами данных из сущностей данных, для которых настроена связь с сущностью "Клиент".</span><span class="sxs-lookup"><span data-stu-id="36a79-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="36a79-115">В аналитике аудитории перейдите **Меры**.</span><span class="sxs-lookup"><span data-stu-id="36a79-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="36a79-116">Выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="36a79-116">Select **New**.</span></span>

1. <span data-ttu-id="36a79-117">Выберите **Изменить имя** и укажите **Имя** для меры.</span><span class="sxs-lookup"><span data-stu-id="36a79-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="36a79-118">Если у вашей новой конфигурации меры есть только два поля, например, CustomerID и одно вычисление, выходные данные будут добавлены в виде нового столбца в сгенерированную системой сущность под названием Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="36a79-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="36a79-119">И вы сможете увидеть значение меры в едином профиле клиента.</span><span class="sxs-lookup"><span data-stu-id="36a79-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="36a79-120">Другие меры создадут свои собственные сущности.</span><span class="sxs-lookup"><span data-stu-id="36a79-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="36a79-121">В области конфигурации выберите функцию агрегирования из выпадающего меню **Выберите функцию**.</span><span class="sxs-lookup"><span data-stu-id="36a79-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="36a79-122">Функции агрегирования включают:</span><span class="sxs-lookup"><span data-stu-id="36a79-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="36a79-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="36a79-123">**Sum**</span></span>
   - <span data-ttu-id="36a79-124">**Среднее значение**</span><span class="sxs-lookup"><span data-stu-id="36a79-124">**Average**</span></span>
   - <span data-ttu-id="36a79-125">**Количество**</span><span class="sxs-lookup"><span data-stu-id="36a79-125">**Count**</span></span>
   - <span data-ttu-id="36a79-126">**Количество уникальных**</span><span class="sxs-lookup"><span data-stu-id="36a79-126">**Count Unique**</span></span>
   - <span data-ttu-id="36a79-127">**Макс**</span><span class="sxs-lookup"><span data-stu-id="36a79-127">**Max**</span></span>
   - <span data-ttu-id="36a79-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="36a79-128">**Min**</span></span>
   - <span data-ttu-id="36a79-129">**Первый**: берет первое значение записи данных</span><span class="sxs-lookup"><span data-stu-id="36a79-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="36a79-130">**Последний**: берет последнее значение, которое было добавлено к записи данных</span><span class="sxs-lookup"><span data-stu-id="36a79-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Операторы для расчета мер.":::

1. <span data-ttu-id="36a79-132">Выберите **Добавить атрибут**, чтобы выбрать данные, необходимые для создания этой меры.</span><span class="sxs-lookup"><span data-stu-id="36a79-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="36a79-133">Выберите вкладку **Атрибуты**.</span><span class="sxs-lookup"><span data-stu-id="36a79-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="36a79-134">Сущность данных: выберите сущность, которая включает в себя атрибут, который вы хотите измерить.</span><span class="sxs-lookup"><span data-stu-id="36a79-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="36a79-135">Атрибут данных: выберите атрибут, который вы хотите использовать в функции агрегирования для вычисления меры.</span><span class="sxs-lookup"><span data-stu-id="36a79-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="36a79-136">Одновременно можно выбрать только один атрибут.</span><span class="sxs-lookup"><span data-stu-id="36a79-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="36a79-137">Вы также можете выбрать атрибут данных из существующей меры, выбрав вкладку **Меры**. Или вы можете выполнить поиск по имени сущности или меры.</span><span class="sxs-lookup"><span data-stu-id="36a79-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="36a79-138">Выберите **Добавить**, чтобы добавить выбранный атрибут к мере.</span><span class="sxs-lookup"><span data-stu-id="36a79-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Выберите атрибут для использования в расчетах.":::

1. <span data-ttu-id="36a79-140">Чтобы создать более сложные меры, вы можете добавить дополнительные атрибуты или использовать математические операторы в своей функции меры.</span><span class="sxs-lookup"><span data-stu-id="36a79-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Создайте сложную меру с математическими операторами.":::

1. <span data-ttu-id="36a79-142">Чтобы добавить фильтры, выберите **Фильтр** в области конфигурации.</span><span class="sxs-lookup"><span data-stu-id="36a79-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="36a79-143">В разделе **Добавить атрибут** области **Фильтры** выберите атрибут, который вы хотите использовать для создания фильтров.</span><span class="sxs-lookup"><span data-stu-id="36a79-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="36a79-144">Задайте операторы фильтра, чтобы определить фильтр для каждого выбранного атрибута.</span><span class="sxs-lookup"><span data-stu-id="36a79-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="36a79-145">Выберите **Применить**, чтобы добавить фильтры к мере.</span><span class="sxs-lookup"><span data-stu-id="36a79-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="36a79-146">Чтобы добавить измерения, выберите **Измерение** в области конфигурации.</span><span class="sxs-lookup"><span data-stu-id="36a79-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="36a79-147">Измерения будут отображаться в виде столбцов в сущности выходных данных меры.</span><span class="sxs-lookup"><span data-stu-id="36a79-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="36a79-148">Выберите **Изменить измерения** для добавления атрибутов данных, по которым вы хотите сгруппировать значения меры.</span><span class="sxs-lookup"><span data-stu-id="36a79-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="36a79-149">Например, город или пол.</span><span class="sxs-lookup"><span data-stu-id="36a79-149">For example, city or gender.</span></span> <span data-ttu-id="36a79-150">По умолчанию измерение *CustomerID* выбрано для создания *мер на уровне клиента*.</span><span class="sxs-lookup"><span data-stu-id="36a79-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="36a79-151">Вы можете удалить измерение по умолчанию, если хотите создать *меры на уровне бизнеса*.</span><span class="sxs-lookup"><span data-stu-id="36a79-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="36a79-152">Выберите **Готово**, чтобы добавить измерения к мере.</span><span class="sxs-lookup"><span data-stu-id="36a79-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="36a79-153">Если существует несколько путей между отображаемой вами сущностью данных и сущностью "Клиент", вы должны выбрать один из указанных [путей отношений сущностей](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="36a79-153">If there are multiple paths between the data entity you mapped and the Customer entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="36a79-154">Результаты измерения могут отличаться в зависимости от выбранного пути.</span><span class="sxs-lookup"><span data-stu-id="36a79-154">Measure results can vary depending on the selected path.</span></span>
   1. <span data-ttu-id="36a79-155">Выберите **Параметры данных** и выберите путь к сущности, который следует использовать для идентификации вашей меры.</span><span class="sxs-lookup"><span data-stu-id="36a79-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span>
   1. <span data-ttu-id="36a79-156">Выберите **Готово**, чтобы применить ваш выбор.</span><span class="sxs-lookup"><span data-stu-id="36a79-156">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Выберите путь к сущности для меры.":::

1. <span data-ttu-id="36a79-158">Чтобы добавить дополнительные вычисления для меры, выберите **Создать расчет**.</span><span class="sxs-lookup"><span data-stu-id="36a79-158">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="36a79-159">Для новых вычислений вы можете использовать только сущности на том же пути к сущности.</span><span class="sxs-lookup"><span data-stu-id="36a79-159">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="36a79-160">Дополнительные расчеты будут отображаться в виде новых столбцов в сущности выходных данных меры.</span><span class="sxs-lookup"><span data-stu-id="36a79-160">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="36a79-161">Выберите **...** в расчете, чтобы **Дублировать**, **Переименовать** или **Удалить** расчет из меры.</span><span class="sxs-lookup"><span data-stu-id="36a79-161">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="36a79-162">В области **Предварительный просмотр** вы увидите схему данных сущности выходных данных меры, включая фильтры и измерения.</span><span class="sxs-lookup"><span data-stu-id="36a79-162">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="36a79-163">Предварительный просмотр динамически реагирует на изменения в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="36a79-163">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="36a79-164">Выберите **Выполнить** для расчета результатов для настроенной меры.</span><span class="sxs-lookup"><span data-stu-id="36a79-164">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="36a79-165">Выберите **Сохранить и закрыть**, если вы хотите сохранить текущую конфигурацию и выполнить меру позже.</span><span class="sxs-lookup"><span data-stu-id="36a79-165">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="36a79-166">Перейдите в **Меры**, чтобы увидеть только что созданную меру в списке.</span><span class="sxs-lookup"><span data-stu-id="36a79-166">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="36a79-167">Управление вашими мерами</span><span class="sxs-lookup"><span data-stu-id="36a79-167">Manage your measures</span></span>

<span data-ttu-id="36a79-168">После [создания меры](#create-a-measure) вы увидите список мер на странице **Меры**.</span><span class="sxs-lookup"><span data-stu-id="36a79-168">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="36a79-169">Вы найдете информацию о типе меры, создателе, дате создания, статусе и состоянии.</span><span class="sxs-lookup"><span data-stu-id="36a79-169">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="36a79-170">Когда вы выбираете меру из списка, вы можете предварительно просмотреть результат и загрузить файл CSV.</span><span class="sxs-lookup"><span data-stu-id="36a79-170">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="36a79-171">Чтобы обновить все ваши меры одновременно, выберите **Обновить все** без выбора конкретной меры.</span><span class="sxs-lookup"><span data-stu-id="36a79-171">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="36a79-172">![Действия для управления отдельными мерами](media/measure-actions.png "Действия для управления отдельными мерами")</span><span class="sxs-lookup"><span data-stu-id="36a79-172">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="36a79-173">Выберите меру из списка для следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="36a79-173">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="36a79-174">Выберите имя меры, чтобы увидеть ее сведения.</span><span class="sxs-lookup"><span data-stu-id="36a79-174">Select the measure name to see its details.</span></span>
- <span data-ttu-id="36a79-175">**Изменить** конфигурацию меры.</span><span class="sxs-lookup"><span data-stu-id="36a79-175">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="36a79-176">**Обновить** меру на основе последних данных.</span><span class="sxs-lookup"><span data-stu-id="36a79-176">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="36a79-177">**Переименовать** меру.</span><span class="sxs-lookup"><span data-stu-id="36a79-177">**Rename** the measure.</span></span>
- <span data-ttu-id="36a79-178">**Удалить** меру.</span><span class="sxs-lookup"><span data-stu-id="36a79-178">**Delete** the measure.</span></span>
- <span data-ttu-id="36a79-179">**Активировать** или **Деактивировать**.</span><span class="sxs-lookup"><span data-stu-id="36a79-179">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="36a79-180">Неактивные меры не обновляются во время [запланированное обновления](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="36a79-180">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="36a79-181">Есть [шесть типов статусов](system.md#status-types) для задач/процессов.</span><span class="sxs-lookup"><span data-stu-id="36a79-181">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="36a79-182">Кроме того, большинство процессов [зависит от других последующих процессов](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="36a79-182">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="36a79-183">Вы можете выбрать статус процесса, чтобы увидеть детали выполнения всего задания.</span><span class="sxs-lookup"><span data-stu-id="36a79-183">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="36a79-184">После выбора **См. сведения** для одной из задач задания вы найдете дополнительную информацию: время обработки, дату последней обработки, а также все ошибки и предупреждения, связанные с задачей.</span><span class="sxs-lookup"><span data-stu-id="36a79-184">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="36a79-185">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="36a79-185">Next step</span></span>

<span data-ttu-id="36a79-186">Вы можете использовать существующие меры для создания [сегмента клиентов](segments.md).</span><span class="sxs-lookup"><span data-stu-id="36a79-186">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]