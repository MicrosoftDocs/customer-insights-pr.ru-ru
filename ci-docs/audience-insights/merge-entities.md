---
title: Объединение сущностей для унификации данных
description: Объедините сущности для создания унифицированных профилей клиентов.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 045fd8d8f65161b91caabed2ac52494dc4fb3910
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406759"
---
# <a name="merge-entities"></a><span data-ttu-id="a191c-103">Объединение сущностей</span><span class="sxs-lookup"><span data-stu-id="a191c-103">Merge entities</span></span>

<span data-ttu-id="a191c-104">Фаза слияния — это последняя фаза в процессе унификации данных.</span><span class="sxs-lookup"><span data-stu-id="a191c-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="a191c-105">Его целью является согласование противоречивых данных.</span><span class="sxs-lookup"><span data-stu-id="a191c-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="a191c-106">Примерами противоречивых данных могут быть имя клиента, найденное в двух ваших наборах данных, но отображаемое в каждом из них немного по-разному ("Грант Маршалл" и "Грант Маршал"), или номер телефона, который отличается по формату (617-803-091X и 617803091X).</span><span class="sxs-lookup"><span data-stu-id="a191c-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="a191c-107">Объединение этих конфликтующих точек данных выполняется на основе "атрибут за атрибутом".</span><span class="sxs-lookup"><span data-stu-id="a191c-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="a191c-108">После завершения [фазы поиска соответствий](match-entities.md), вы начинаете фазу слияния, выбрав плитку **Слияние** на странице **Объединить**.</span><span class="sxs-lookup"><span data-stu-id="a191c-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="a191c-109">Проверка рекомендаций системы</span><span class="sxs-lookup"><span data-stu-id="a191c-109">Review system recommendations</span></span>

<span data-ttu-id="a191c-110">На странице **Слияние** вы выбираете и исключаете атрибуты для объединения в вашей единой сущности профиля клиента (результат процесса настройки).</span><span class="sxs-lookup"><span data-stu-id="a191c-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="a191c-111">Некоторые атрибуты автоматически объединяются системой.</span><span class="sxs-lookup"><span data-stu-id="a191c-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="a191c-112">Просмотр объединенных атрибутов</span><span class="sxs-lookup"><span data-stu-id="a191c-112">View merged attributes</span></span>

<span data-ttu-id="a191c-113">Чтобы просмотреть атрибуты, включенные в один из ваших автоматически объединенных атрибутов, выберите этот объединенный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a191c-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="a191c-114">Два атрибута, составляющие этот объединенный атрибут, отображаются в двух новых строках под объединенным атрибутом.</span><span class="sxs-lookup"><span data-stu-id="a191c-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a191c-115">![Выберите объединенный атрибут](media/configure-data-merge-profile-attributes.png "Выберите объединенный атрибут")</span><span class="sxs-lookup"><span data-stu-id="a191c-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="a191c-116">Разделение объединенных атрибутов</span><span class="sxs-lookup"><span data-stu-id="a191c-116">Separate merged attributes</span></span>

<span data-ttu-id="a191c-117">Чтобы разделить или отменить слияние любого из автоматически объединенных атрибутов, найдите атрибут в таблице **Атрибуты профиля**.</span><span class="sxs-lookup"><span data-stu-id="a191c-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="a191c-118">Выберите кнопку с многоточием (...).</span><span class="sxs-lookup"><span data-stu-id="a191c-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="a191c-119">В раскрывающемся списке выберите **Отдельные поля**.</span><span class="sxs-lookup"><span data-stu-id="a191c-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="a191c-120">Удаление объединенных атрибутов</span><span class="sxs-lookup"><span data-stu-id="a191c-120">Remove merged attributes</span></span>

<span data-ttu-id="a191c-121">Чтобы исключить атрибут из конечной сущности профиля клиента, найдите его в таблице **Атрибуты профиля**.</span><span class="sxs-lookup"><span data-stu-id="a191c-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="a191c-122">Выберите кнопку с многоточием (...).</span><span class="sxs-lookup"><span data-stu-id="a191c-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="a191c-123">В раскрывающемся списке выберите **Не объединять**.</span><span class="sxs-lookup"><span data-stu-id="a191c-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="a191c-124">Атрибут перемещается в раздел **Удалено из записи клиента**.</span><span class="sxs-lookup"><span data-stu-id="a191c-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="a191c-125">Добавление объединенного атрибута вручную</span><span class="sxs-lookup"><span data-stu-id="a191c-125">Manually add a merged attribute</span></span>

<span data-ttu-id="a191c-126">Чтобы добавить объединенный атрибут, перейдите на страницу **Слияние**.</span><span class="sxs-lookup"><span data-stu-id="a191c-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="a191c-127">Выберите **Добавить объединенный атрибут**.</span><span class="sxs-lookup"><span data-stu-id="a191c-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="a191c-128">Укажите **Имя**, чтобы идентифицировать его на странице **Слияние** позже.</span><span class="sxs-lookup"><span data-stu-id="a191c-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="a191c-129">При желании укажите **Отображаемое имя** для отображения в унифицированной сущности профиля клиента.</span><span class="sxs-lookup"><span data-stu-id="a191c-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="a191c-130">Настройте **Выберите повторяющиеся атрибуты**, чтобы выбрать атрибуты, которые вы хотите объединить из соответствующих сущностей.</span><span class="sxs-lookup"><span data-stu-id="a191c-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="a191c-131">Можно также искать атрибуты.</span><span class="sxs-lookup"><span data-stu-id="a191c-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="a191c-132">Задайте **Оценить по важности**, чтобы задать приоритет одного атрибута над другими.</span><span class="sxs-lookup"><span data-stu-id="a191c-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="a191c-133">Например, если сущность *WebAccountCSV* включает в себя самые точные данные об атрибуте *Полные имена*, вы могли бы задать приоритет этой сущности над *ContactCSV*, выбрав *WebAccountCSV*.</span><span class="sxs-lookup"><span data-stu-id="a191c-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="a191c-134">В результате *WebAccountCSV* переходит на первый приоритет, в то время как *ContactCSV* перемещается на второй приоритет при извлечении значений для атрибута *Полное имя*.</span><span class="sxs-lookup"><span data-stu-id="a191c-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="a191c-135">Выполните слияние</span><span class="sxs-lookup"><span data-stu-id="a191c-135">Run your merge</span></span>

<span data-ttu-id="a191c-136">Независимо от того, объединяете ли вы атрибуты вручную или позволяете системе объединить их, вы всегда можете выполнить свое слияние.</span><span class="sxs-lookup"><span data-stu-id="a191c-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="a191c-137">Выберите **Выполнить** на странице **Слияние**, чтобы запустить процесс.</span><span class="sxs-lookup"><span data-stu-id="a191c-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a191c-138">![Сохранение и выполнение слияния данных](media/configure-data-merge-save-run.png "Сохранение и выполнение слияния данных")</span><span class="sxs-lookup"><span data-stu-id="a191c-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="a191c-139">Для внесения дополнительных изменений и повторного выполнения шага вы можете отменить выполняющееся слияние.</span><span class="sxs-lookup"><span data-stu-id="a191c-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="a191c-140">Выберите **Обновляется...** и выберите **Отменить задание** на боковой панели, которая появляется.</span><span class="sxs-lookup"><span data-stu-id="a191c-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="a191c-141">После того как текст **Обновляется...** изменится на **Выполнено успешно**, слияние завершено и разрешило противоречия в ваших данных в соответствии с определенными вами политиками.</span><span class="sxs-lookup"><span data-stu-id="a191c-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="a191c-142">Объединенные и не объединенные атрибуты включены в единую сущность профиля.</span><span class="sxs-lookup"><span data-stu-id="a191c-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="a191c-143">Исключенные атрибуты не включены в единую сущность профиля.</span><span class="sxs-lookup"><span data-stu-id="a191c-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="a191c-144">Если это был не первый случай, когда вы успешно выполнили слияние, все последующие процессы, включая обогащение, сегментацию и меры, будут автоматически перезапущены.</span><span class="sxs-lookup"><span data-stu-id="a191c-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="a191c-145">После повторного выполнения всех последующих процессов в профилях клиентов отражаются все внесенные вами изменения.</span><span class="sxs-lookup"><span data-stu-id="a191c-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="a191c-146">Есть [шесть типов статусов](system.md#status-types) для задач/процессов.</span><span class="sxs-lookup"><span data-stu-id="a191c-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="a191c-147">Кроме того, большинство процессов [зависит от других последующих процессов](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="a191c-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="a191c-148">Вы можете выбрать статус процесса, чтобы увидеть детали выполнения всего задания.</span><span class="sxs-lookup"><span data-stu-id="a191c-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="a191c-149">После выбора **См. сведения** для одной из задач задания вы найдете дополнительную информацию: время обработки, дату последней обработки, а также все ошибки и предупреждения, связанные с задачей.</span><span class="sxs-lookup"><span data-stu-id="a191c-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="a191c-150">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="a191c-150">Next Step</span></span>

<span data-ttu-id="a191c-151">Настройте [действия](activities.md), [обогащение](enrichment-microsoft-graph.md) или [отношения](relationships.md), чтобы узнать больше о ваших клиентах.</span><span class="sxs-lookup"><span data-stu-id="a191c-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="a191c-152">Если вы уже настроили действия, обогащение или отношения, или если вы определили сегменты, они будут автоматически обработаны для использования последних данных клиентов.</span><span class="sxs-lookup"><span data-stu-id="a191c-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>


