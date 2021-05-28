---
title: Объединение сущностей для унификации данных
description: Объедините сущности для создания унифицированных профилей клиентов.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2cab702509596dd87c0c9b9769d1af8ba8387f9d
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085592"
---
# <a name="merge-entities"></a><span data-ttu-id="e197b-103">Объединение сущностей</span><span class="sxs-lookup"><span data-stu-id="e197b-103">Merge entities</span></span>

<span data-ttu-id="e197b-104">Фаза слияния — это последняя фаза в процессе унификации данных.</span><span class="sxs-lookup"><span data-stu-id="e197b-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="e197b-105">Его целью является согласование противоречивых данных.</span><span class="sxs-lookup"><span data-stu-id="e197b-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="e197b-106">Примерами противоречивых данных могут быть имя клиента, найденное в двух ваших наборах данных, но отображаемое в каждом из них немного по-разному ("Грант Маршалл" и "Грант Маршал"), или номер телефона, который отличается по формату (617-803-091X и 617803091X).</span><span class="sxs-lookup"><span data-stu-id="e197b-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="e197b-107">Объединение этих конфликтующих точек данных выполняется на основе "атрибут за атрибутом".</span><span class="sxs-lookup"><span data-stu-id="e197b-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Страница объединения в процессе унификации данных с таблицей с объединенными полями, которые определяют единый профиль клиента.":::

<span data-ttu-id="e197b-109">После завершения [фазы поиска соответствий](match-entities.md), вы начинаете фазу слияния, выбрав плитку **Слияние** на странице **Объединить**.</span><span class="sxs-lookup"><span data-stu-id="e197b-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="e197b-110">Проверка рекомендаций системы</span><span class="sxs-lookup"><span data-stu-id="e197b-110">Review system recommendations</span></span>

<span data-ttu-id="e197b-111">В разделе **Данные** > **Унифицировать** > **Объединить** вы выбираете и исключаете атрибуты для объединения в сущность единого профиля клиента.</span><span class="sxs-lookup"><span data-stu-id="e197b-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="e197b-112">Единый профиль клиента — это результат процесса унификации данных.</span><span class="sxs-lookup"><span data-stu-id="e197b-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="e197b-113">Некоторые атрибуты автоматически объединяются системой.</span><span class="sxs-lookup"><span data-stu-id="e197b-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="e197b-114">Чтобы просмотреть атрибуты, включенные в один из автоматически объединяемых атрибутов, выберите этот объединенный атрибут на вкладке **Поля клиентов** в таблице.</span><span class="sxs-lookup"><span data-stu-id="e197b-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="e197b-115">Атрибуты, составляющие этот объединенный атрибут, отображаются в двух новых строках под объединенным атрибутом.</span><span class="sxs-lookup"><span data-stu-id="e197b-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="e197b-116">Разделение, переименование, исключение и редактирование объединенных полей</span><span class="sxs-lookup"><span data-stu-id="e197b-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="e197b-117">Вы можете изменить способ обработки объединенных атрибутов в системе для создания единого профиля клиента.</span><span class="sxs-lookup"><span data-stu-id="e197b-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="e197b-118">Выберите **Показать больше** и выберите то, что вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="e197b-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Параметры в раскрывающемся меню «Показать еще» для управления объединенными атрибутами.":::

<span data-ttu-id="e197b-120">Дополнительные сведения см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="e197b-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="e197b-121">Разделение объединенных полей</span><span class="sxs-lookup"><span data-stu-id="e197b-121">Separate merged fields</span></span>

<span data-ttu-id="e197b-122">Чтобы разделить объединенные поля, найдите атрибут в таблице.</span><span class="sxs-lookup"><span data-stu-id="e197b-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="e197b-123">Разделенные поля отображаются как отдельные точки данных в едином профиле клиента.</span><span class="sxs-lookup"><span data-stu-id="e197b-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="e197b-124">Выберите объединенное поле.</span><span class="sxs-lookup"><span data-stu-id="e197b-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="e197b-125">Выберите **Показать еще** и выберите **Разделить поля**.</span><span class="sxs-lookup"><span data-stu-id="e197b-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="e197b-126">Подтвердите разделение.</span><span class="sxs-lookup"><span data-stu-id="e197b-126">Confirm the separation.</span></span>

1. <span data-ttu-id="e197b-127">Выберите **Сохранить** и **Выполнить** для обработки изменений.</span><span class="sxs-lookup"><span data-stu-id="e197b-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="e197b-128">Переименование объединенных полей</span><span class="sxs-lookup"><span data-stu-id="e197b-128">Rename merged fields</span></span>

<span data-ttu-id="e197b-129">Измените отображаемое имя объединенных атрибутов.</span><span class="sxs-lookup"><span data-stu-id="e197b-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="e197b-130">Вы не можете изменить имя сущности выходных данных.</span><span class="sxs-lookup"><span data-stu-id="e197b-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="e197b-131">Выберите объединенное поле.</span><span class="sxs-lookup"><span data-stu-id="e197b-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="e197b-132">Выберите **Показать еще** и выберите **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="e197b-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="e197b-133">Подтвердите измененное отображаемое имя.</span><span class="sxs-lookup"><span data-stu-id="e197b-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="e197b-134">Выберите **Сохранить** и **Выполнить** для обработки изменений.</span><span class="sxs-lookup"><span data-stu-id="e197b-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="e197b-135">Исключение объединенных полей</span><span class="sxs-lookup"><span data-stu-id="e197b-135">Exclude merged fields</span></span>

<span data-ttu-id="e197b-136">Исключите атрибут из единого профиля клиента.</span><span class="sxs-lookup"><span data-stu-id="e197b-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="e197b-137">Если поле используется в других процессах, например в сегменте, удалите его из этих процессов, прежде чем исключать его из профиля клиента.</span><span class="sxs-lookup"><span data-stu-id="e197b-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="e197b-138">Выберите объединенное поле.</span><span class="sxs-lookup"><span data-stu-id="e197b-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="e197b-139">Выберите **Показать еще** и выберите **Исключить**.</span><span class="sxs-lookup"><span data-stu-id="e197b-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="e197b-140">Подтвердите исключение.</span><span class="sxs-lookup"><span data-stu-id="e197b-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="e197b-141">Выберите **Сохранить** и **Выполнить** для обработки изменений.</span><span class="sxs-lookup"><span data-stu-id="e197b-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="e197b-142">На странице **Объединить** выберите **Исключенные поля**, чтобы увидеть список всех исключенных полей.</span><span class="sxs-lookup"><span data-stu-id="e197b-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="e197b-143">Эта панель позволяет вам снова добавлять исключенные поля.</span><span class="sxs-lookup"><span data-stu-id="e197b-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="e197b-144">Объединение полей вручную</span><span class="sxs-lookup"><span data-stu-id="e197b-144">Manually combine fields</span></span>

<span data-ttu-id="e197b-145">Укажите объединенный атрибут вручную.</span><span class="sxs-lookup"><span data-stu-id="e197b-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="e197b-146">На странице **Объединить** выберите **Объединить поля**.</span><span class="sxs-lookup"><span data-stu-id="e197b-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="e197b-147">Укажите **Имя** и **Имя поля выходных данных**.</span><span class="sxs-lookup"><span data-stu-id="e197b-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="e197b-148">Выберите поле для добавления.</span><span class="sxs-lookup"><span data-stu-id="e197b-148">Choose a field to add.</span></span> <span data-ttu-id="e197b-149">Выберите **Добавить поля**, чтобы объединить дополнительные поля.</span><span class="sxs-lookup"><span data-stu-id="e197b-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="e197b-150">Подтвердите исключение.</span><span class="sxs-lookup"><span data-stu-id="e197b-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="e197b-151">Выберите **Сохранить** и **Выполнить** для обработки изменений.</span><span class="sxs-lookup"><span data-stu-id="e197b-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="e197b-152">Изменение порядка полей</span><span class="sxs-lookup"><span data-stu-id="e197b-152">Change the order of fields</span></span>

<span data-ttu-id="e197b-153">Некоторые сущности содержат больше деталей, чем другие.</span><span class="sxs-lookup"><span data-stu-id="e197b-153">Some entities contain more details than others.</span></span> <span data-ttu-id="e197b-154">Если сущность включает последние данные о поле, вы можете установить приоритет перед другими сущностями при объединении значений.</span><span class="sxs-lookup"><span data-stu-id="e197b-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="e197b-155">Выберите объединенное поле.</span><span class="sxs-lookup"><span data-stu-id="e197b-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="e197b-156">Выберите **Показать еще** и выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="e197b-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="e197b-157">В области **Объединить поля** выберите **Переместить вверх/вниз**, чтобы установить порядок, или перетащите их в нужное место.</span><span class="sxs-lookup"><span data-stu-id="e197b-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="e197b-158">Подтвердите изменение.</span><span class="sxs-lookup"><span data-stu-id="e197b-158">Confirm the change.</span></span>

1. <span data-ttu-id="e197b-159">Выберите **Сохранить** и **Выполнить** для обработки изменений.</span><span class="sxs-lookup"><span data-stu-id="e197b-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="e197b-160">Выполните слияние</span><span class="sxs-lookup"><span data-stu-id="e197b-160">Run your merge</span></span>

<span data-ttu-id="e197b-161">Независимо от того, объединяете ли вы атрибуты вручную или позволяете системе объединить их, вы всегда можете выполнить свое слияние.</span><span class="sxs-lookup"><span data-stu-id="e197b-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="e197b-162">Выберите **Выполнить** на странице **Слияние**, чтобы запустить процесс.</span><span class="sxs-lookup"><span data-stu-id="e197b-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e197b-163">![Сохранение и выполнение слияния данных](media/configure-data-merge-save-run.png "Сохранение и выполнение слияния данных")</span><span class="sxs-lookup"><span data-stu-id="e197b-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="e197b-164">Выберите **Выполнить только объединение**, если вы хотите видеть только результат, отраженный в объединенной сущности клиента.</span><span class="sxs-lookup"><span data-stu-id="e197b-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="e197b-165">Последующие процессы будут обновлены, как [определено в расписании обновления](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e197b-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="e197b-166">Выберите **Выполнить объединение и нисходящие процессы**, чтобы обновить систему с вашими изменениями.</span><span class="sxs-lookup"><span data-stu-id="e197b-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="e197b-167">Все процессы, включая обогащение, сегменты и измерения, будут перезапущены автоматически.</span><span class="sxs-lookup"><span data-stu-id="e197b-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="e197b-168">После завершения всех последующих процессов в профилях клиентов отражаются все внесенные вами изменения.</span><span class="sxs-lookup"><span data-stu-id="e197b-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="e197b-169">Чтобы внести больше изменений и повторно запустить шаг, вы можете отменить текущее слияние.</span><span class="sxs-lookup"><span data-stu-id="e197b-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="e197b-170">Выберите **Обновляется...** и выберите **Отменить задание** на боковой панели, которая появляется.</span><span class="sxs-lookup"><span data-stu-id="e197b-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="e197b-171">Есть [шесть типов статусов](system.md#status-types) для задач/процессов.</span><span class="sxs-lookup"><span data-stu-id="e197b-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="e197b-172">Кроме того, большинство процессов [зависит от других последующих процессов](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="e197b-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="e197b-173">Вы можете выбрать статус процесса, чтобы увидеть детали выполнения всего задания.</span><span class="sxs-lookup"><span data-stu-id="e197b-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="e197b-174">После выбора **См. сведения** для одной из задач задания вы найдете дополнительную информацию: время обработки, дату последней обработки, а также все ошибки и предупреждения, связанные с задачей.</span><span class="sxs-lookup"><span data-stu-id="e197b-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="e197b-175">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="e197b-175">Next Step</span></span>

<span data-ttu-id="e197b-176">Настройте [действия](activities.md), [обогащение](enrichment-hub.md) или [отношения](relationships.md), чтобы узнать больше о ваших клиентах.</span><span class="sxs-lookup"><span data-stu-id="e197b-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="e197b-177">Если вы уже настроили действия, обогащение или сегменты, они будут обработаны автоматически с использованием последних данных о клиентах.</span><span class="sxs-lookup"><span data-stu-id="e197b-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
