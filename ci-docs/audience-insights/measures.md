---
title: Создание мер и управление ими
description: Определите меры для анализа и отражения эффективности вашего бизнеса.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 402e5ef3515bce0e6f56788781b7bd909738aaa6
ms.sourcegitcommit: b833e333745d321edeaf96d3ed14458cbce02ff1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049266"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="922d5-103">Определение мер и управление ими</span><span class="sxs-lookup"><span data-stu-id="922d5-103">Define and manage measures</span></span>

<span data-ttu-id="922d5-104">Меры помогают лучше понять поведение клиентов и эффективность бизнеса.</span><span class="sxs-lookup"><span data-stu-id="922d5-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="922d5-105">Они смотрят на соответствующие значения из [единых профилей](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="922d5-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="922d5-106">Например, компания хочет видеть *общие расходы на одного клиента*, чтобы понять историю покупок отдельного клиента или измерить *общий объем продаж компании*, чтобы понять совокупный доход всего бизнеса.</span><span class="sxs-lookup"><span data-stu-id="922d5-106">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="922d5-107">Меры создаются с помощью построителя мер, платформы запросов данных с различными операторами и простыми вариантами сопоставления.</span><span class="sxs-lookup"><span data-stu-id="922d5-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="922d5-108">Система позволяет фильтровать данные, группировать результаты, обнаруживать [пути отношений сущностей](relationships.md) и просматривать выходные данные.</span><span class="sxs-lookup"><span data-stu-id="922d5-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="922d5-109">Используйте конструктор мер для планирования бизнес-действий, запрашивая данные о клиентах и извлекая аналитические данные.</span><span class="sxs-lookup"><span data-stu-id="922d5-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="922d5-110">Например, создание меры *общие расходы на одного клиента* и *общий доход на одного клиента* помогает идентифицировать группу клиентов с высокими расходами, но высокой отдачей.</span><span class="sxs-lookup"><span data-stu-id="922d5-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="922d5-111">Вы можете [создать сегмент](segments.md), чтобы управлять следующими лучшими действиями.</span><span class="sxs-lookup"><span data-stu-id="922d5-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="922d5-112">Создание собственной меры с нуля</span><span class="sxs-lookup"><span data-stu-id="922d5-112">Build your own measure from scratch</span></span>

<span data-ttu-id="922d5-113">В этом разделе описывается создание новой меры с нуля.</span><span class="sxs-lookup"><span data-stu-id="922d5-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="922d5-114">Вы можете создать меру с атрибутами данных из сущностей данных, для которых настроена связь с сущностью "Клиент".</span><span class="sxs-lookup"><span data-stu-id="922d5-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="922d5-115">В аналитике аудитории перейдите **Меры**.</span><span class="sxs-lookup"><span data-stu-id="922d5-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="922d5-116">Выберите **Создать** и выберите **Создать собственные**.</span><span class="sxs-lookup"><span data-stu-id="922d5-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="922d5-117">Выберите **Изменить имя** и укажите **Имя** для меры.</span><span class="sxs-lookup"><span data-stu-id="922d5-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="922d5-118">Если ваша новая конфигурация меры имеет только два поля, например CustomerID и одно вычисление, выходные данные будут добавлены в виде нового столбца в сгенерированную системой сущность с именем Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="922d5-118">If your new measure configuration has only two fields, for example, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="922d5-119">И вы сможете увидеть значение меры в едином профиле клиента.</span><span class="sxs-lookup"><span data-stu-id="922d5-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="922d5-120">Другие меры создадут свои собственные сущности.</span><span class="sxs-lookup"><span data-stu-id="922d5-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="922d5-121">В области конфигурации выберите функцию агрегирования из выпадающего меню **Выберите функцию**.</span><span class="sxs-lookup"><span data-stu-id="922d5-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="922d5-122">Функции агрегирования включают:</span><span class="sxs-lookup"><span data-stu-id="922d5-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="922d5-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="922d5-123">**Sum**</span></span>
   - <span data-ttu-id="922d5-124">**Среднее значение**</span><span class="sxs-lookup"><span data-stu-id="922d5-124">**Average**</span></span>
   - <span data-ttu-id="922d5-125">**Количество**</span><span class="sxs-lookup"><span data-stu-id="922d5-125">**Count**</span></span>
   - <span data-ttu-id="922d5-126">**Количество уникальных**</span><span class="sxs-lookup"><span data-stu-id="922d5-126">**Count Unique**</span></span>
   - <span data-ttu-id="922d5-127">**Макс**</span><span class="sxs-lookup"><span data-stu-id="922d5-127">**Max**</span></span>
   - <span data-ttu-id="922d5-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="922d5-128">**Min**</span></span>
   - <span data-ttu-id="922d5-129">**Первый**: берет первое значение записи данных</span><span class="sxs-lookup"><span data-stu-id="922d5-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="922d5-130">**Последний**: берет последнее значение, которое было добавлено к записи данных</span><span class="sxs-lookup"><span data-stu-id="922d5-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Операторы для расчета мер.":::

1. <span data-ttu-id="922d5-132">Выберите **Добавить атрибут**, чтобы выбрать данные, необходимые для создания этой меры.</span><span class="sxs-lookup"><span data-stu-id="922d5-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="922d5-133">Выберите вкладку **Атрибуты**.</span><span class="sxs-lookup"><span data-stu-id="922d5-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="922d5-134">Сущность данных: выберите сущность, которая включает в себя атрибут, который вы хотите измерить.</span><span class="sxs-lookup"><span data-stu-id="922d5-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="922d5-135">Атрибут данных: выберите атрибут, который вы хотите использовать в функции агрегирования для вычисления меры.</span><span class="sxs-lookup"><span data-stu-id="922d5-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="922d5-136">Одновременно можно выбрать только один атрибут.</span><span class="sxs-lookup"><span data-stu-id="922d5-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="922d5-137">Вы также можете выбрать атрибут данных из существующей меры, выбрав вкладку **Меры**. Или вы можете выполнить поиск по имени сущности или меры.</span><span class="sxs-lookup"><span data-stu-id="922d5-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="922d5-138">Выберите **Добавить**, чтобы добавить выбранный атрибут к мере.</span><span class="sxs-lookup"><span data-stu-id="922d5-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Выберите атрибут для использования в расчетах.":::

1. <span data-ttu-id="922d5-140">Чтобы создать более сложные меры, вы можете добавить дополнительные атрибуты или использовать математические операторы в своей функции меры.</span><span class="sxs-lookup"><span data-stu-id="922d5-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Создайте сложную меру с математическими операторами.":::

1. <span data-ttu-id="922d5-142">Чтобы добавить фильтры, выберите **Фильтр** в области конфигурации.</span><span class="sxs-lookup"><span data-stu-id="922d5-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="922d5-143">В разделе **Добавить атрибут** области **Фильтры** выберите атрибут, который вы хотите использовать для создания фильтров.</span><span class="sxs-lookup"><span data-stu-id="922d5-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="922d5-144">Задайте операторы фильтра, чтобы определить фильтр для каждого выбранного атрибута.</span><span class="sxs-lookup"><span data-stu-id="922d5-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="922d5-145">Выберите **Применить**, чтобы добавить фильтры к мере.</span><span class="sxs-lookup"><span data-stu-id="922d5-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="922d5-146">Чтобы добавить измерения, выберите **Измерение** в области конфигурации.</span><span class="sxs-lookup"><span data-stu-id="922d5-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="922d5-147">Измерения будут отображаться в виде столбцов в сущности выходных данных меры.</span><span class="sxs-lookup"><span data-stu-id="922d5-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="922d5-148">Выберите **Изменить измерения** для добавления атрибутов данных, по которым вы хотите сгруппировать значения меры.</span><span class="sxs-lookup"><span data-stu-id="922d5-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="922d5-149">Например, город или пол.</span><span class="sxs-lookup"><span data-stu-id="922d5-149">For example, city or gender.</span></span> <span data-ttu-id="922d5-150">По умолчанию измерение *CustomerID* выбрано для создания *мер на уровне клиента*.</span><span class="sxs-lookup"><span data-stu-id="922d5-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="922d5-151">Вы можете удалить измерение по умолчанию, если хотите создать *меры на уровне бизнеса*.</span><span class="sxs-lookup"><span data-stu-id="922d5-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="922d5-152">Выберите **Готово**, чтобы добавить измерения к мере.</span><span class="sxs-lookup"><span data-stu-id="922d5-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="922d5-153">Если в ваших данных есть значения, которые нужно заменить целым числом, например, заменить *NULL* на *0*, выберите **Правила**.</span><span class="sxs-lookup"><span data-stu-id="922d5-153">If there are values in your data that you need to replace with an integer, for example, replace *null* with *0*, select **Rules**.</span></span> <span data-ttu-id="922d5-154">Настройте правило и убедитесь, что вы выбираете только целые числа в качестве замены.</span><span class="sxs-lookup"><span data-stu-id="922d5-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="922d5-155">Если существуют несколько путей между сопоставленной вами сущностью и сущностью *Клиент*, вам нужно выбрать один из определенных [путей к отношениям сущности](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="922d5-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="922d5-156">Результаты измерения могут отличаться в зависимости от выбранного пути.</span><span class="sxs-lookup"><span data-stu-id="922d5-156">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="922d5-157">Выберите **Параметры данных** и выберите путь к сущности, который следует использовать для идентификации вашей меры.</span><span class="sxs-lookup"><span data-stu-id="922d5-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="922d5-158">Если есть только один путь к сущности *Клиент*, этот элемент управления не будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="922d5-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="922d5-159">Выберите **Готово**, чтобы применить ваш выбор.</span><span class="sxs-lookup"><span data-stu-id="922d5-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Выберите путь к сущности для меры.":::

1. <span data-ttu-id="922d5-161">Чтобы добавить дополнительные вычисления для меры, выберите **Создать расчет**.</span><span class="sxs-lookup"><span data-stu-id="922d5-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="922d5-162">Для новых вычислений вы можете использовать только сущности на том же пути к сущности.</span><span class="sxs-lookup"><span data-stu-id="922d5-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="922d5-163">Дополнительные расчеты будут отображаться в виде новых столбцов в сущности выходных данных меры.</span><span class="sxs-lookup"><span data-stu-id="922d5-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="922d5-164">Выберите **...** в расчете, чтобы **Дублировать**, **Переименовать** или **Удалить** расчет из меры.</span><span class="sxs-lookup"><span data-stu-id="922d5-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="922d5-165">В области **Предварительный просмотр** вы увидите схему данных сущности выходных данных меры, включая фильтры и измерения.</span><span class="sxs-lookup"><span data-stu-id="922d5-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="922d5-166">Предварительный просмотр динамически реагирует на изменения в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="922d5-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="922d5-167">Выберите **Выполнить** для расчета результатов для настроенной меры.</span><span class="sxs-lookup"><span data-stu-id="922d5-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="922d5-168">Выберите **Сохранить и закрыть**, если вы хотите сохранить текущую конфигурацию и выполнить меру позже.</span><span class="sxs-lookup"><span data-stu-id="922d5-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="922d5-169">Перейдите в **Меры**, чтобы увидеть только что созданную меру в списке.</span><span class="sxs-lookup"><span data-stu-id="922d5-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="922d5-170">Использование шаблона для построения меры</span><span class="sxs-lookup"><span data-stu-id="922d5-170">Use a template to build a measure</span></span>

<span data-ttu-id="922d5-171">Вы можете использовать предопределенные шаблоны часто используемых мер для их создания.</span><span class="sxs-lookup"><span data-stu-id="922d5-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="922d5-172">Подробные описания шаблонов и пошаговый процесс помогут вам в эффективном создании мер.</span><span class="sxs-lookup"><span data-stu-id="922d5-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="922d5-173">Шаблоны основаны на сопоставленных данных из сущности *Единое действие*.</span><span class="sxs-lookup"><span data-stu-id="922d5-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="922d5-174">Поэтому убедитесь, что вы настроили [действия клиентов](activities.md) перед созданием меры на основе шаблона.</span><span class="sxs-lookup"><span data-stu-id="922d5-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="922d5-175">Доступные шаблоны мер:</span><span class="sxs-lookup"><span data-stu-id="922d5-175">Available measure templates:</span></span> 
- <span data-ttu-id="922d5-176">Средняя ценность транзакции</span><span class="sxs-lookup"><span data-stu-id="922d5-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="922d5-177">Общая сумма транзакций</span><span class="sxs-lookup"><span data-stu-id="922d5-177">Total transaction value</span></span>
- <span data-ttu-id="922d5-178">Средний доход за день</span><span class="sxs-lookup"><span data-stu-id="922d5-178">Average daily revenue</span></span>
- <span data-ttu-id="922d5-179">Средний доход за год</span><span class="sxs-lookup"><span data-stu-id="922d5-179">Average yearly revenue</span></span>
- <span data-ttu-id="922d5-180">Количество транзакций</span><span class="sxs-lookup"><span data-stu-id="922d5-180">Transaction count</span></span>
- <span data-ttu-id="922d5-181">Заработанные баллы за лояльность</span><span class="sxs-lookup"><span data-stu-id="922d5-181">Loyalty points earned</span></span>
- <span data-ttu-id="922d5-182">Активированные баллы за лояльность</span><span class="sxs-lookup"><span data-stu-id="922d5-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="922d5-183">Остаток баллов за лояльность</span><span class="sxs-lookup"><span data-stu-id="922d5-183">Loyalty points balance</span></span>
- <span data-ttu-id="922d5-184">Активный период клиента</span><span class="sxs-lookup"><span data-stu-id="922d5-184">Active customer lifespan</span></span>
- <span data-ttu-id="922d5-185">Длительность членства в программе лояльности</span><span class="sxs-lookup"><span data-stu-id="922d5-185">Loyalty membership duration</span></span>
- <span data-ttu-id="922d5-186">Время с последней покупки</span><span class="sxs-lookup"><span data-stu-id="922d5-186">Time since last purchase</span></span>

<span data-ttu-id="922d5-187">Следующая процедура описывает шаги для создания новой меры с использованием шаблона.</span><span class="sxs-lookup"><span data-stu-id="922d5-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="922d5-188">В аналитике аудитории перейдите **Меры**.</span><span class="sxs-lookup"><span data-stu-id="922d5-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="922d5-189">Выберите **Создать** и выберите **Выбрать шаблон**.</span><span class="sxs-lookup"><span data-stu-id="922d5-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Снимок экрана раскрывающегося меню при создании новой меры с выделением на шаблоне.":::

1. <span data-ttu-id="922d5-191">Найдите шаблон, который соответствует вашим потребностям, и выберите **Выбрать шаблон**.</span><span class="sxs-lookup"><span data-stu-id="922d5-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="922d5-192">Просмотрите необходимые данные и выберите **Начать**, если у вас есть все данные.</span><span class="sxs-lookup"><span data-stu-id="922d5-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="922d5-193">В области **Изменить имя** задайте имя для вашей меры и выходной сущности.</span><span class="sxs-lookup"><span data-stu-id="922d5-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="922d5-194">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="922d5-194">Select **Done**.</span></span>

1. <span data-ttu-id="922d5-195">В разделе **Настройка периода времени** определите интервал времени используемых данных.</span><span class="sxs-lookup"><span data-stu-id="922d5-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="922d5-196">Выберите, хотите ли вы, чтобы новая мера охватывала весь набор данных, выбрав **Все время**.</span><span class="sxs-lookup"><span data-stu-id="922d5-196">Choose if you want the new measure to cover the entire data set by selecting **All time**.</span></span> <span data-ttu-id="922d5-197">Или, если вы хотите, чтобы мера была сосредоточена на **Определенный период времени**.</span><span class="sxs-lookup"><span data-stu-id="922d5-197">Or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Снимок экрана, показывающий раздел периода времени при настройке меры из шаблона.":::

1. <span data-ttu-id="922d5-199">В следующем разделе выберите **Добавить данные**, чтобы выбрать действия и сопоставить соответствующие данные из вашей сущности *Единое действие*.</span><span class="sxs-lookup"><span data-stu-id="922d5-199">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="922d5-200">Шаг 1 из 2: в разделе **Тип действия** выберите тип сущности, который вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="922d5-200">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="922d5-201">Для **Действия** выберите сущности, которые нужно сопоставить.</span><span class="sxs-lookup"><span data-stu-id="922d5-201">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="922d5-202">Шаг 2 из 2: выберите атрибут из сущности *Единое действие* для компонента, требуемого формулой.</span><span class="sxs-lookup"><span data-stu-id="922d5-202">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="922d5-203">Например, для средней суммы транзакции это атрибут, представляющий сумму транзакции.</span><span class="sxs-lookup"><span data-stu-id="922d5-203">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="922d5-204">Для параметра **Временная метка действия** выберите атрибут из сущности единого действия, который представляет дату и время действия.</span><span class="sxs-lookup"><span data-stu-id="922d5-204">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="922d5-205">После успешного сопоставления данных вы можете увидеть статус **Завершено** и имя сопоставленных действий и атрибутов.</span><span class="sxs-lookup"><span data-stu-id="922d5-205">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Снимок экрана с завершенной конфигурацией шаблона меры.":::

1. <span data-ttu-id="922d5-207">Теперь вы можете выбрать **Выполнить** для расчета результатов меры.</span><span class="sxs-lookup"><span data-stu-id="922d5-207">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="922d5-208">Чтобы уточнить его позже, выберите **Сохранить черновик**.</span><span class="sxs-lookup"><span data-stu-id="922d5-208">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="922d5-209">Управление вашими мерами</span><span class="sxs-lookup"><span data-stu-id="922d5-209">Manage your measures</span></span>

<span data-ttu-id="922d5-210">Вы можете найти список мер на странице **Меры**.</span><span class="sxs-lookup"><span data-stu-id="922d5-210">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="922d5-211">Вы найдете информацию о типе меры, создателе, дате создания, статусе и состоянии.</span><span class="sxs-lookup"><span data-stu-id="922d5-211">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="922d5-212">Когда вы выбираете меру из списка, вы можете предварительно просмотреть результат и загрузить файл CSV.</span><span class="sxs-lookup"><span data-stu-id="922d5-212">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="922d5-213">Чтобы обновить все ваши меры одновременно, выберите **Обновить все** без выбора конкретной меры.</span><span class="sxs-lookup"><span data-stu-id="922d5-213">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="922d5-214">![Действия для управления отдельными мерами](media/measure-actions.png "Действия для управления отдельными мерами")</span><span class="sxs-lookup"><span data-stu-id="922d5-214">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="922d5-215">Выберите меру из списка для следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="922d5-215">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="922d5-216">Выберите имя меры, чтобы увидеть ее сведения.</span><span class="sxs-lookup"><span data-stu-id="922d5-216">Select the measure name to see its details.</span></span>
- <span data-ttu-id="922d5-217">**Изменить** конфигурацию меры.</span><span class="sxs-lookup"><span data-stu-id="922d5-217">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="922d5-218">**Обновить** меру на основе последних данных.</span><span class="sxs-lookup"><span data-stu-id="922d5-218">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="922d5-219">**Переименовать** меру.</span><span class="sxs-lookup"><span data-stu-id="922d5-219">**Rename** the measure.</span></span>
- <span data-ttu-id="922d5-220">**Удалить** меру.</span><span class="sxs-lookup"><span data-stu-id="922d5-220">**Delete** the measure.</span></span>
- <span data-ttu-id="922d5-221">**Активировать** или **Деактивировать**.</span><span class="sxs-lookup"><span data-stu-id="922d5-221">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="922d5-222">Неактивные меры не обновляются во время [запланированное обновления](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="922d5-222">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="922d5-223">Есть [шесть типов статусов](system.md#status-types) для задач/процессов.</span><span class="sxs-lookup"><span data-stu-id="922d5-223">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="922d5-224">Кроме того, большинство процессов [зависит от других последующих процессов](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="922d5-224">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="922d5-225">Вы можете выбрать статус процесса, чтобы увидеть детали выполнения всего задания.</span><span class="sxs-lookup"><span data-stu-id="922d5-225">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="922d5-226">После выбора **См. сведения** для одной из задач задания вы найдете дополнительную информацию: время обработки, дату последней обработки, а также все ошибки и предупреждения, связанные с задачей.</span><span class="sxs-lookup"><span data-stu-id="922d5-226">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="922d5-227">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="922d5-227">Next step</span></span>

<span data-ttu-id="922d5-228">Вы можете использовать существующие меры для создания [сегмента клиентов](segments.md).</span><span class="sxs-lookup"><span data-stu-id="922d5-228">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
