---
title: Аналитика сегментов для существующих сегментов
description: Получите представление о существующих сегментах, чтобы увидеть различия и сходства.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: article
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 92e1b05dd08588a5da446af5b17b2d6ce57490ce
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406764"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="41273-103">Аналитика сегментов (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="41273-103">Segment insights (preview)</span></span>

<span data-ttu-id="41273-104">Откройте для себя дополнительную информацию и понимание ваших существующих сегментов.</span><span class="sxs-lookup"><span data-stu-id="41273-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="41273-105">Узнайте, что отличает два сегмента или что у них общего.</span><span class="sxs-lookup"><span data-stu-id="41273-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="41273-106">Пересечение сегментов</span><span class="sxs-lookup"><span data-stu-id="41273-106">Segment overlap</span></span>

<span data-ttu-id="41273-107">Анализ перекрытия сегментов показывает, сколько и какие клиенты являются общими для двух или более сегментов.</span><span class="sxs-lookup"><span data-stu-id="41273-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="41273-108">Например, как сегмент постоянных клиентов пересекается с сегментом, который содержит клиентов, которые удовлетворены вашей услугой или продуктом.</span><span class="sxs-lookup"><span data-stu-id="41273-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="41273-109">Вы также можете проанализировать, как перекрытие изменяется для определенных атрибутов.</span><span class="sxs-lookup"><span data-stu-id="41273-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="41273-110">Запуск анализа перекрытия</span><span class="sxs-lookup"><span data-stu-id="41273-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="41273-111">Перейдите к пункту **Сегменты** и выберите вкладку **Аналитика (предварительная версия)**.</span><span class="sxs-lookup"><span data-stu-id="41273-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="41273-112">Выберите **Создать** и выберите параметр **Перекрытие** на панели **Выбрать тип аналитики**.</span><span class="sxs-lookup"><span data-stu-id="41273-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="41273-113">Выберите интересующие вас сегменты и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="41273-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="41273-114">При желании выберите одно или несколько полей, представляющих интерес, для анализа перекрытий для каждого возможного значения поля и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="41273-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="41273-115">Укажите имя для анализа перекрытия, необязательное отображаемое имя и описание.</span><span class="sxs-lookup"><span data-stu-id="41273-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="41273-116">Выберите **Сохранить**, чтобы начать анализ.</span><span class="sxs-lookup"><span data-stu-id="41273-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="41273-117">Анализ перекрытия готов, когда состояние меняется с "Обновление" на "Успешно".</span><span class="sxs-lookup"><span data-stu-id="41273-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="41273-118">Просмотр и оптимизация анализа перекрытий</span><span class="sxs-lookup"><span data-stu-id="41273-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="41273-119">После завершения анализа найдите подробности об этом анализе в разделе **Сегменты** > **Аналитика (предварительная версия)**.</span><span class="sxs-lookup"><span data-stu-id="41273-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Детали анализа перекрытия сегментов":::

<span data-ttu-id="41273-121">Выберите аналитические сведения, чтобы увидеть результаты анализа:</span><span class="sxs-lookup"><span data-stu-id="41273-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="41273-122">Количество участников, перекрывающихся в сегментах, выбранных для анализа.</span><span class="sxs-lookup"><span data-stu-id="41273-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="41273-123">Количество участников, включенных в один из сегментов, но не в остальные сегменты.</span><span class="sxs-lookup"><span data-stu-id="41273-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="41273-124">Если вы выбрали поля при настройке анализа перекрытия, вы найдете их на соответствующих вкладках.</span><span class="sxs-lookup"><span data-stu-id="41273-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="41273-125">Вы можете использовать раскрывающийся список фильтров, чтобы выбрать любой интересующий уровень атрибута, и таблица внизу покажет соответствующие данные.</span><span class="sxs-lookup"><span data-stu-id="41273-125">You can use the filter drop-down to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="41273-126">Дифференциаторы сегментов</span><span class="sxs-lookup"><span data-stu-id="41273-126">Segment differentiators</span></span>

<span data-ttu-id="41273-127">Различия сегментов помогают вам узнать, что отличает сегмент от остальных ваших клиентов или от другого сегмента.</span><span class="sxs-lookup"><span data-stu-id="41273-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="41273-128">Вам просто нужно выбрать сегмент, и система определит атрибуты профиля и показатели, которые отличают выбранный сегмент.</span><span class="sxs-lookup"><span data-stu-id="41273-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="41273-129">Запуск анализа дифференциатора</span><span class="sxs-lookup"><span data-stu-id="41273-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="41273-130">Перейдите к пункту **Сегменты** и выберите вкладку **Аналитика (предварительная версия)**.</span><span class="sxs-lookup"><span data-stu-id="41273-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="41273-131">Выберите **Создать** и выберите параметр **Перекрытие** на панели **Выбрать тип аналитики**.</span><span class="sxs-lookup"><span data-stu-id="41273-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="41273-132">Выберите сегмент, который вы хотите проанализировать, как **Первичный сегмент** и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="41273-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="41273-133">Выберите **Все клиенты** или **Вторичный сегмент**, с которым хотите сравнить ваш основной сегмент, и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="41273-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="41273-134">При желании выберите одно или несколько интересующих вас полей, чтобы сосредоточить анализ на конкретных атрибутах, и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="41273-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="41273-135">Укажите имя для анализа перекрытия, необязательное отображаемое имя и описание.</span><span class="sxs-lookup"><span data-stu-id="41273-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="41273-136">Выберите **Сохранить**, чтобы начать анализ.</span><span class="sxs-lookup"><span data-stu-id="41273-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="41273-137">Анализ перекрытия готов, когда состояние меняется с "Обновление" на "Успешно".</span><span class="sxs-lookup"><span data-stu-id="41273-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="41273-138">Просмотр и оптимизация анализа дифференциаторов</span><span class="sxs-lookup"><span data-stu-id="41273-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="41273-139">После завершения анализа найдите подробности об этом анализе в разделе **Сегменты** > **Аналитика (предварительная версия)**.</span><span class="sxs-lookup"><span data-stu-id="41273-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Детали анализа дифференциатора сегментов":::

<span data-ttu-id="41273-141">Выберите аналитические сведения, чтобы увидеть результаты анализа.</span><span class="sxs-lookup"><span data-stu-id="41273-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="41273-142">Анализ дифференциатора включает две вкладки.</span><span class="sxs-lookup"><span data-stu-id="41273-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="41273-143">На вкладке **Атрибуты** перечислены атрибуты профиля, которые рассматриваются как отличительные признаки.</span><span class="sxs-lookup"><span data-stu-id="41273-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="41273-144">На вкладке **Меры** перечислены дифференциаторы.</span><span class="sxs-lookup"><span data-stu-id="41273-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="41273-145">Каждая вкладка содержит следующие данные:</span><span class="sxs-lookup"><span data-stu-id="41273-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="41273-146">Ранжированный список дифференциаторов, отсортированных по разнице баллов.</span><span class="sxs-lookup"><span data-stu-id="41273-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="41273-147">**Оценка различия** для каждого дифференциатора.</span><span class="sxs-lookup"><span data-stu-id="41273-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="41273-148">Показатель различия представляет степень различия атрибута между двумя сегментами.</span><span class="sxs-lookup"><span data-stu-id="41273-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="41273-149">Чем выше оценка различия, тем больше атрибуты различаются между двумя сегментами.</span><span class="sxs-lookup"><span data-stu-id="41273-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="41273-150">Выберите оценку, чтобы открыть панель **Оценка разницы** с распределением значений для этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="41273-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="41273-151">Управление анализом сегментов</span><span class="sxs-lookup"><span data-stu-id="41273-151">Manage segment insights</span></span>

<span data-ttu-id="41273-152">Вы можете использовать следующие опции для своей аналитики из панели команд:</span><span class="sxs-lookup"><span data-stu-id="41273-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="41273-153">**Назад**, чтобы вернуться к списку аналитики</span><span class="sxs-lookup"><span data-stu-id="41273-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="41273-154">**Обновление** для повторного запуска анализа</span><span class="sxs-lookup"><span data-stu-id="41273-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="41273-155">**Удалить**, чтобы удалить этот анализ</span><span class="sxs-lookup"><span data-stu-id="41273-155">**Delete** to remove this insight</span></span>
