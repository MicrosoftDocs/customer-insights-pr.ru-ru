---
title: Сегменты в анализе аудитории
description: Обзор сегментов, а также способов их создания и управления ими.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6cb7bd62bf0f61e6dc5811b20e5011e4a086c743
ms.sourcegitcommit: 84283d523a891298fca8aaf629d9f9ab2a1bc067
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2021
ms.locfileid: "6111403"
---
# <a name="segments-overview"></a><span data-ttu-id="f2b9c-103">Обзор сегментов</span><span class="sxs-lookup"><span data-stu-id="f2b9c-103">Segments overview</span></span>

<span data-ttu-id="f2b9c-104">Сегменты позволяют группировать клиентов по демографическим, транзакционным или поведенческим признакам.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="f2b9c-105">Вы можете использовать сегменты для таргетирования рекламных кампаний, продаж и действий поддержки клиентов для достижения своих бизнес-целей.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="f2b9c-106">Профили клиентов, соответствующие фильтрам определения сегмента, называются *участниками* сегмента.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="f2b9c-107">Есть некоторые [ограничения обслуживания](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="f2b9c-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="f2b9c-108">Создание нового сегмента</span><span class="sxs-lookup"><span data-stu-id="f2b9c-108">Create a new segment</span></span>

<span data-ttu-id="f2b9c-109">Существуют несколько способов создания нового сегмента:</span><span class="sxs-lookup"><span data-stu-id="f2b9c-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="f2b9c-110">Сложный сегмент с конструктором сегментов: [Пустой сегмент](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="f2b9c-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="f2b9c-111">Простые сегменты с одним оператором: [Быстрый сегмент](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="f2b9c-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="f2b9c-112">Способ поиска похожих клиентов на основе искусственного интеллекта: [Похожие клиенты](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="f2b9c-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="f2b9c-113">Предложения на основе искусственного интеллекта, основанные на мерах или атрибутах: [Предлагаемые сегменты для улучшения мер](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="f2b9c-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="f2b9c-114">Предложения, основанные на действиях: [Предлагаемые сегменты на основе действий клиентов](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="f2b9c-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="f2b9c-115">Управление существующими сегментами</span><span class="sxs-lookup"><span data-stu-id="f2b9c-115">Manage existing segments</span></span>

<span data-ttu-id="f2b9c-116">Перейдите на страницу **Сегменты**, чтобы просмотреть все сохраненные сегменты и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-116">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="f2b9c-117">Каждый сегмент представлен строкой, которая включает дополнительную информацию о сегменте.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-117">Each segment is represented by a row that includes additional information about the segment.</span></span>

:::image type="content" source="media/segments-selected-segment.png" alt-text="Выбранный сегмент с раскрывающимся списком вариантов и доступными вариантами.":::

<span data-ttu-id="f2b9c-119">При выборе сегмента доступны следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f2b9c-119">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="f2b9c-120">**Посмотреть** сведения о сегменте, включая тенденцию числа участников и предварительный просмотр участников сегмента.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-120">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="f2b9c-121">**Изменить** сегмент, чтобы изменить его свойства.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-121">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="f2b9c-122">**Создать дубликат** сегмента.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-122">**Create duplicate** of a segment.</span></span> <span data-ttu-id="f2b9c-123">Вы можете сразу изменить его свойства или просто сохранить дубликат.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-123">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="f2b9c-124">**Обновить** сегмент, чтобы включить последние данные.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-124">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="f2b9c-125">**Активировать** или **Деактивировать** сегмент.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-125">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="f2b9c-126">Сегменты могут иметь два возможных состояния — активный или неактивный.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-126">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="f2b9c-127">Эти состояния пригодятся при редактировании сегмента.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-127">These states come in handy when editing a segment.</span></span> <span data-ttu-id="f2b9c-128">Для неактивных сегментов определение сегмента существует, но пока не содержит никаких клиентов.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-128">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="f2b9c-129">Когда вы активируете сегмент, его состояние меняется с "неактивного" на "активное", и он начинает поиск клиентов, соответствующих определению сегмента.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-129">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="f2b9c-130">Если [запланированное обновление](system.md#schedule-tab) настроено, неактивные сегменты имеют **Статус**, перечисленный как **Пропущено**, что указывает на то, что попытки обновления даже не выполнялись.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-130">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="f2b9c-131">Когда неактивный сегмент активируется, он будет обновляться и будет включен в запланированные обновления.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-131">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="f2b9c-132">Кроме того, вы можете использовать функциональность **Планировать позже** в раскрывающемся списке **Включение/выключение** для указания будущей даты и времени активации и деактивации определенного сегмента.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-132">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="f2b9c-133">**Переименовать** сегмент.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-133">**Rename** the segment.</span></span>
- <span data-ttu-id="f2b9c-134">**Скачать** список участников в виде CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-134">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="f2b9c-135">**Управляйте экспортом**, чтобы увидеть сегмент, связанный с экспортом, и управлять им.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-135">**Manage exports** to see exports related segment and manage them.</span></span> [<span data-ttu-id="f2b9c-136">Подробнее об экспортах.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-136">Learn more about exports.</span></span>](export-destinations.md)
- <span data-ttu-id="f2b9c-137">**Удалить** сегмент.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-137">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="f2b9c-138">Обновление сегментов</span><span class="sxs-lookup"><span data-stu-id="f2b9c-138">Refresh segments</span></span>

<span data-ttu-id="f2b9c-139">Вы можете обновить все сегменты одновременно, выбрав **Обновить все** на странице **Сегменты** или вы можете обновить один или несколько сегментов, когда вы выбираете их и выбираете **обновить** из параметров.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-139">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="f2b9c-140">Кроме того, вы можете настроить повторяющееся обновление в пункте **Администратор** > **Система** > **Расписание**.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-140">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="f2b9c-141">Есть [шесть типов статусов](system.md#status-types) для задач/процессов.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-141">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="f2b9c-142">Кроме того, большинство процессов [зависит от других последующих процессов](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="f2b9c-142">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="f2b9c-143">Вы можете выбрать статус процесса, чтобы увидеть детали выполнения всего задания.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-143">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="f2b9c-144">После выбора **См. сведения** для одной из задач задания вы найдете дополнительную информацию: время обработки, дату последней обработки, а также все ошибки и предупреждения, связанные с задачей.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-144">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="export-segments"></a><span data-ttu-id="f2b9c-145">Экспортировать сегменты</span><span class="sxs-lookup"><span data-stu-id="f2b9c-145">Export segments</span></span>

<span data-ttu-id="f2b9c-146">Вы можете экспортировать сегмент со страницы сегментов или [страницы экспорта](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f2b9c-146">You can export a segment from the segments page or the [exports page](export-destinations.md).</span></span> 

1. <span data-ttu-id="f2b9c-147">Перейдите на страницу **Сегменты**.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-147">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="f2b9c-148">Выберите **Показать еще [...]** для сегмента, который вы хотите экспортировать.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-148">Select **Show more [...]** for the segment you want to export.</span></span>

1. <span data-ttu-id="f2b9c-149">Выберите **Управляйте экспортом** из раскрывающегося списка действий.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-149">Select **Manage exports** from the actions drop-down list.</span></span>

1. <span data-ttu-id="f2b9c-150">Откроется страница **Экспорты (предварительная версия) для сегмента**.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-150">The page **Exports (preview) for segment** opens.</span></span> <span data-ttu-id="f2b9c-151">Вы можете увидеть все настроенные экспорты, сгруппированные по экспортам, которые содержат текущий сегмент или не содержат его.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-151">You can see all configured exports grouped by by exports that contain the current segment or don't contain it.</span></span>

   1. <span data-ttu-id="f2b9c-152">Чтобы добавить выбранный сегмент в экспорт, выберите экспорт в списке и выберите **Добавить сегмент**.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-152">To add the selected segment to an export, select the export in the list and select **Add segment**.</span></span>

   1. <span data-ttu-id="f2b9c-153">Чтобы создать новый экспорт с выбранным сегментом, выберите **Добавить экспорт**.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-153">To create a new export with the selected segment, select **Add export**.</span></span> <span data-ttu-id="f2b9c-154">Для получения дополнительной информации о создании экспорта см. [Настройка нового экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f2b9c-154">For more information about creating exports, see [Set up a new export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f2b9c-155">Выберите **Назад**, чтобы вернуться на главную страницу сегментов.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-155">Select **Back** to return to the main page for segments.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="f2b9c-156">Просмотр истории обработки и участников сегмента</span><span class="sxs-lookup"><span data-stu-id="f2b9c-156">View processing history and segment members</span></span>

<span data-ttu-id="f2b9c-157">Вы можете увидеть консолидированные данные о сегменте, просмотрев его детали.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-157">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="f2b9c-158">На странице **Сегменты** выберите сегмент, который хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-158">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="f2b9c-159">Верхняя часть страницы содержит график тенденций, который отображает изменения в количестве участников.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-159">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="f2b9c-160">Наведите указатель мыши на точки данных, чтобы увидеть количество участников на определенную дату.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-160">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="f2b9c-161">Вы можете обновить интервал времени визуализации.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-161">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f2b9c-162">![Диапазон времени сегмента](media/segment-time-range.png "Диапазон времени сегмента")</span><span class="sxs-lookup"><span data-stu-id="f2b9c-162">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="f2b9c-163">Нижняя часть содержит список участников сегмента.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-163">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="f2b9c-164">Поля, которые появляются в этом списке, основаны на атрибутах сущностей вашего сегмента.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-164">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="f2b9c-165">Список представляет собой предварительный просмотр соответствующих участников сегмента и показывает первые 100 записей вашего сегмента, чтобы вы могли быстро оценить его и просмотреть его определения, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="f2b9c-165">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="f2b9c-166">Чтобы увидеть все соответствующие записи, вам нужно [экспортировать сегмент](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f2b9c-166">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
