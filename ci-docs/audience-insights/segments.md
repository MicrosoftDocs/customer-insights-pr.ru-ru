---
title: Создание и управление сегментами
description: Создайте сегменты клиентов, чтобы сгруппировать их на основе различных атрибутов.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597073"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="c8d68-103">Создание и управление сегментами</span><span class="sxs-lookup"><span data-stu-id="c8d68-103">Create and manage segments</span></span>

<span data-ttu-id="c8d68-104">Сегменты позволяют группировать клиентов по демографическим, транзакционным или поведенческим признакам.</span><span class="sxs-lookup"><span data-stu-id="c8d68-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="c8d68-105">Вы можете использовать сегменты для таргетирования рекламных кампаний, продаж и действий поддержки клиентов для достижения своих бизнес-целей.</span><span class="sxs-lookup"><span data-stu-id="c8d68-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="c8d68-106">Вы можете определить сложные фильтры вокруг сущности "Профиль клиента" и связанных с ней сущностей.</span><span class="sxs-lookup"><span data-stu-id="c8d68-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="c8d68-107">Каждый сегмент после обработки создает набор записей о клиентах, которые можно экспортировать и выполнять действия с ними.</span><span class="sxs-lookup"><span data-stu-id="c8d68-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="c8d68-108">Есть некоторые [ограничения обслуживания](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="c8d68-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="c8d68-109">Если не указано иное, все сегменты — **Динамические сегменты**, которые регулярно обновляются.</span><span class="sxs-lookup"><span data-stu-id="c8d68-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="c8d68-110">В следующем примере показано использование возможностей сегментации.</span><span class="sxs-lookup"><span data-stu-id="c8d68-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="c8d68-111">Мы определили сегмент для клиентов, которые заказали товаров как минимум на 500 долларов США за последние 90 дней *и* которые были вовлечены в вызов обслуживание клиентов, который был передан на более высокий уровень.</span><span class="sxs-lookup"><span data-stu-id="c8d68-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c8d68-112">![Несколько групп](media/segmentation-group1-2.png "Несколько групп")</span><span class="sxs-lookup"><span data-stu-id="c8d68-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="c8d68-113">Создание нового сегмента</span><span class="sxs-lookup"><span data-stu-id="c8d68-113">Create a new segment</span></span>

<span data-ttu-id="c8d68-114">Сегменты управляются на странице **Сегменты**.</span><span class="sxs-lookup"><span data-stu-id="c8d68-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="c8d68-115">В аналитике аудитории перейдите на страницу **Сегменты**.</span><span class="sxs-lookup"><span data-stu-id="c8d68-115">In audience insights, go to the **Segments** page.</span></span>

1. <span data-ttu-id="c8d68-116">Выберите **Создать** > **Пустой сегмент**.</span><span class="sxs-lookup"><span data-stu-id="c8d68-116">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="c8d68-117">На панели **Создать сегмент** выберите тип сегмента и укажите **Имя**.</span><span class="sxs-lookup"><span data-stu-id="c8d68-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="c8d68-118">При желании укажите отображаемое имя и описание, которое поможет идентифицировать сегмент.</span><span class="sxs-lookup"><span data-stu-id="c8d68-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="c8d68-119">Выберите **Далее**, чтобы перейти на страницу **Конструктор сегментов**, где вы определяете группу.</span><span class="sxs-lookup"><span data-stu-id="c8d68-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="c8d68-120">Группа — это набор клиентов.</span><span class="sxs-lookup"><span data-stu-id="c8d68-120">A group is a set of customers.</span></span>

1. <span data-ttu-id="c8d68-121">Выберите сущность, которая содержит атрибут, по которому требуется выполнить сегментацию.</span><span class="sxs-lookup"><span data-stu-id="c8d68-121">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="c8d68-122">Выберите атрибут для сегментирования.</span><span class="sxs-lookup"><span data-stu-id="c8d68-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="c8d68-123">Этот атрибут может иметь один из четырех типов значений: числовое, строковое, дата или логическое значение.</span><span class="sxs-lookup"><span data-stu-id="c8d68-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="c8d68-124">Выберите оператор и значение для выбранного атрибута.</span><span class="sxs-lookup"><span data-stu-id="c8d68-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c8d68-125">![Пользовательский фильтр группы](media/customer-group-numbers.png "Фильтр группы пользователей")</span><span class="sxs-lookup"><span data-stu-id="c8d68-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="c8d68-126">Номер</span><span class="sxs-lookup"><span data-stu-id="c8d68-126">Number</span></span> |<span data-ttu-id="c8d68-127">Определение</span><span class="sxs-lookup"><span data-stu-id="c8d68-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="c8d68-128">1</span><span class="sxs-lookup"><span data-stu-id="c8d68-128">1</span></span>     |<span data-ttu-id="c8d68-129">Entity</span><span class="sxs-lookup"><span data-stu-id="c8d68-129">Entity</span></span>          |
   |<span data-ttu-id="c8d68-130">2</span><span class="sxs-lookup"><span data-stu-id="c8d68-130">2</span></span>     |<span data-ttu-id="c8d68-131">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c8d68-131">Attribute</span></span>          |
   |<span data-ttu-id="c8d68-132">3</span><span class="sxs-lookup"><span data-stu-id="c8d68-132">3</span></span>    |<span data-ttu-id="c8d68-133">Оператор</span><span class="sxs-lookup"><span data-stu-id="c8d68-133">Operator</span></span>         |
   |<span data-ttu-id="c8d68-134">4</span><span class="sxs-lookup"><span data-stu-id="c8d68-134">4</span></span>    |<span data-ttu-id="c8d68-135">значение</span><span class="sxs-lookup"><span data-stu-id="c8d68-135">Value</span></span>         |

8. <span data-ttu-id="c8d68-136">Если сущность связана с объединенной сущностью клиента через [отношения](relationships.md), вам нужно определить путь отношения, чтобы создать действительный сегмент.</span><span class="sxs-lookup"><span data-stu-id="c8d68-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="c8d68-137">Добавьте сущности из пути отношений, пока не сможете выбрать сущность **Клиент : CustomerInsights** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="c8d68-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="c8d68-138">Тогда выберите **Все записи** для каждого условия.</span><span class="sxs-lookup"><span data-stu-id="c8d68-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c8d68-139">![Путь отношений при создании сегмента](media/segments-multiple-relationships.png "Путь отношений при создании сегмента")</span><span class="sxs-lookup"><span data-stu-id="c8d68-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="c8d68-140">По умолчанию сегменты генерируют выходную сущность, содержащую все атрибуты профилей клиентов, которые соответствуют определенным фильтрам.</span><span class="sxs-lookup"><span data-stu-id="c8d68-140">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="c8d68-141">Если сегмент основан на других сущностях, кроме сущности *Клиент*, вы можете добавить дополнительные атрибуты из этих сущностей в выходную сущность.</span><span class="sxs-lookup"><span data-stu-id="c8d68-141">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="c8d68-142">Укажите **Атрибуты проекта** для выбора атрибутов, которые будут добавлены к выходной сущности.</span><span class="sxs-lookup"><span data-stu-id="c8d68-142">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  

   
   <span data-ttu-id="c8d68-143">Пример: сегмент основан на сущности, которая содержит данные о действиях клиента, которые связаны с сущностью *Клиент*.</span><span class="sxs-lookup"><span data-stu-id="c8d68-143">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="c8d68-144">Сегмент выполняет поиск всех клиентов, которые обращались в службу поддержки за последние 60 дней.</span><span class="sxs-lookup"><span data-stu-id="c8d68-144">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="c8d68-145">Вы можете добавить продолжительность звонка и количество звонков ко всем совпадающим записям клиентов в выходной сущности.</span><span class="sxs-lookup"><span data-stu-id="c8d68-145">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="c8d68-146">Эта информация может быть полезна для отправки часто звонящим клиентам сообщений электронной почты с полезными ссылками на статьи справки и раздел "Часто задаваемые вопросы".</span><span class="sxs-lookup"><span data-stu-id="c8d68-146">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

1. <span data-ttu-id="c8d68-147">Выберите **Сохранить**, чтобы сохранить сегмент.</span><span class="sxs-lookup"><span data-stu-id="c8d68-147">Select **Save** to save your segment.</span></span> <span data-ttu-id="c8d68-148">Ваш сегмент будет сохранен и обработан, если все требования будут подтверждены.</span><span class="sxs-lookup"><span data-stu-id="c8d68-148">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="c8d68-149">В противном случае он будет сохранен как черновик.</span><span class="sxs-lookup"><span data-stu-id="c8d68-149">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="c8d68-150">Выберите **Назад к сегментам**, чтобы вернуться к странице **Сегменты**.</span><span class="sxs-lookup"><span data-stu-id="c8d68-150">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="c8d68-151">Управление существующими сегментами</span><span class="sxs-lookup"><span data-stu-id="c8d68-151">Manage existing segments</span></span>

<span data-ttu-id="c8d68-152">На странице **Сегменты** вы можете просматривать все сохраненные сегменты и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="c8d68-152">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="c8d68-153">Каждый сегмент представлен строкой, которая включает дополнительную информацию о сегменте.</span><span class="sxs-lookup"><span data-stu-id="c8d68-153">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="c8d68-154">Вы можете отсортировать сегменты в столбце, выбрав заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="c8d68-154">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="c8d68-155">Используйте поле **Поиск** в верхнем правом углу, чтобы отфильтровать сегменты.</span><span class="sxs-lookup"><span data-stu-id="c8d68-155">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c8d68-156">![Параметры для управления существующим сегментом](media/segments-selected-segment.png "Параметры для управления существующим сегментом")</span><span class="sxs-lookup"><span data-stu-id="c8d68-156">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="c8d68-157">При выборе сегмента доступны следующие действия:</span><span class="sxs-lookup"><span data-stu-id="c8d68-157">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="c8d68-158">**Посмотреть** сведения о сегменте, включая тенденцию числа участников и предварительный просмотр участников сегмента.</span><span class="sxs-lookup"><span data-stu-id="c8d68-158">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="c8d68-159">**Изменить** сегмент, чтобы изменить его свойства.</span><span class="sxs-lookup"><span data-stu-id="c8d68-159">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="c8d68-160">**Создать дубликат** сегмента.</span><span class="sxs-lookup"><span data-stu-id="c8d68-160">**Create duplicate** of a segment.</span></span> <span data-ttu-id="c8d68-161">Вы можете сразу изменить его свойства или просто сохранить дубликат.</span><span class="sxs-lookup"><span data-stu-id="c8d68-161">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="c8d68-162">**Обновить** сегмент, чтобы включить последние данные.</span><span class="sxs-lookup"><span data-stu-id="c8d68-162">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="c8d68-163">**Активировать** или **Деактивировать** сегмент.</span><span class="sxs-lookup"><span data-stu-id="c8d68-163">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="c8d68-164">Сегменты могут иметь два возможных состояния — активный или неактивный.</span><span class="sxs-lookup"><span data-stu-id="c8d68-164">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="c8d68-165">Эти состояния пригодятся при редактировании сегмента.</span><span class="sxs-lookup"><span data-stu-id="c8d68-165">These states come in handy when editing a segment.</span></span> <span data-ttu-id="c8d68-166">Для неактивных сегментов определение сегмента существует, но пока не содержит никаких клиентов.</span><span class="sxs-lookup"><span data-stu-id="c8d68-166">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="c8d68-167">Когда вы активируете сегмент, его состояние меняется с "неактивного" на "активное", и он начинает поиск клиентов, соответствующих определению сегмента.</span><span class="sxs-lookup"><span data-stu-id="c8d68-167">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="c8d68-168">Если [запланированное обновление](system.md#schedule-tab) настроено, неактивные сегменты имеют **Статус**, перечисленный как **Пропущено**, что указывает на то, что попытки обновления даже не выполнялись.</span><span class="sxs-lookup"><span data-stu-id="c8d68-168">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="c8d68-169">Когда неактивный сегмент активируется, он будет обновляться и будет включен в запланированные обновления.</span><span class="sxs-lookup"><span data-stu-id="c8d68-169">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="c8d68-170">Кроме того, вы можете использовать функциональность **Планировать позже** в раскрывающемся списке **Включение/выключение** для указания будущей даты и времени активации и деактивации определенного сегмента.</span><span class="sxs-lookup"><span data-stu-id="c8d68-170">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="c8d68-171">**Переименовать** сегмент.</span><span class="sxs-lookup"><span data-stu-id="c8d68-171">**Rename** the segment.</span></span>
- <span data-ttu-id="c8d68-172">**Скачать** список участников в виде CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="c8d68-172">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="c8d68-173">Параметр **Добавить в** отправляет список идентификаторов клиентов в сегменте для обработки в другом приложении.</span><span class="sxs-lookup"><span data-stu-id="c8d68-173">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="c8d68-174">**Удалить** сегмент.</span><span class="sxs-lookup"><span data-stu-id="c8d68-174">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="c8d68-175">Обновление сегментов</span><span class="sxs-lookup"><span data-stu-id="c8d68-175">Refresh segments</span></span>

<span data-ttu-id="c8d68-176">Вы можете обновить все сегменты одновременно, выбрав **Обновить все** на странице **Сегменты** или вы можете обновить один или несколько сегментов, когда вы выбираете их и выбираете **обновить** из параметров.</span><span class="sxs-lookup"><span data-stu-id="c8d68-176">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="c8d68-177">Кроме того, вы можете настроить повторяющееся обновление в пункте **Администратор** > **Система** > **Расписание**.</span><span class="sxs-lookup"><span data-stu-id="c8d68-177">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="c8d68-178">Есть [шесть типов статусов](system.md#status-types) для задач/процессов.</span><span class="sxs-lookup"><span data-stu-id="c8d68-178">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="c8d68-179">Кроме того, большинство процессов [зависит от других последующих процессов](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="c8d68-179">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="c8d68-180">Вы можете выбрать статус процесса, чтобы увидеть детали выполнения всего задания.</span><span class="sxs-lookup"><span data-stu-id="c8d68-180">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="c8d68-181">После выбора **См. сведения** для одной из задач задания вы найдете дополнительную информацию: время обработки, дату последней обработки, а также все ошибки и предупреждения, связанные с задачей.</span><span class="sxs-lookup"><span data-stu-id="c8d68-181">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="c8d68-182">Загрузка и экспорт сегментов</span><span class="sxs-lookup"><span data-stu-id="c8d68-182">Download and export segments</span></span>

<span data-ttu-id="c8d68-183">Вы можете загрузить свои сегменты в файл CSV или экспортировать их в Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="c8d68-183">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="c8d68-184">Загрузка сегментов в файл CSV</span><span class="sxs-lookup"><span data-stu-id="c8d68-184">Download segments to a CSV file</span></span>

1. <span data-ttu-id="c8d68-185">В аналитике аудитории перейдите на страницу **Сегменты**.</span><span class="sxs-lookup"><span data-stu-id="c8d68-185">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="c8d68-186">Выберите многоточие на плитке определенного сегмента.</span><span class="sxs-lookup"><span data-stu-id="c8d68-186">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="c8d68-187">Выберите **Скачать как CSV** из раскрывающегося списка действий.</span><span class="sxs-lookup"><span data-stu-id="c8d68-187">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="c8d68-188">Экспорт сегментов в Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="c8d68-188">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="c8d68-189">Перед экспортом сегментов в Dynamics 365 Sales администратору необходимо [создать пункт назначения экспорта](export-destinations.md) для Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="c8d68-189">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="c8d68-190">В аналитике аудитории перейдите на страницу **Сегменты**.</span><span class="sxs-lookup"><span data-stu-id="c8d68-190">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="c8d68-191">Выберите многоточие на плитке определенного сегмента.</span><span class="sxs-lookup"><span data-stu-id="c8d68-191">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="c8d68-192">Выберите **Добавить в** в раскрывающемся списке действий и выберите пункт назначения экспорта, в который вы хотите отправить данные.</span><span class="sxs-lookup"><span data-stu-id="c8d68-192">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="c8d68-193">Черновой режим для сегментов</span><span class="sxs-lookup"><span data-stu-id="c8d68-193">Draft mode for segments</span></span>

<span data-ttu-id="c8d68-194">Если не все требования для обработки сегмента выполнены, вы можете сохранить сегмент как черновик и получить к нему доступ со страницы **Сегменты**.</span><span class="sxs-lookup"><span data-stu-id="c8d68-194">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="c8d68-195">Он будет сохранен как неактивный сегмент, и не может быть активирован, пока он не будет действителен.</span><span class="sxs-lookup"><span data-stu-id="c8d68-195">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="c8d68-196">Добавление дополнительных условий в группу</span><span class="sxs-lookup"><span data-stu-id="c8d68-196">Add more conditions to a group</span></span>

<span data-ttu-id="c8d68-197">Чтобы добавить больше условий в группу, вы можете использовать два логических оператора:</span><span class="sxs-lookup"><span data-stu-id="c8d68-197">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="c8d68-198">Оператор **И**: оба условия должны быть выполнены как часть процесса сегментации.</span><span class="sxs-lookup"><span data-stu-id="c8d68-198">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="c8d68-199">Эта опция наиболее полезна, когда вы определяете условия для разных сущностей.</span><span class="sxs-lookup"><span data-stu-id="c8d68-199">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="c8d68-200">Оператор **ИЛИ**: любое из условий должно быть выполнено как часть процесса сегментации.</span><span class="sxs-lookup"><span data-stu-id="c8d68-200">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="c8d68-201">Эта опция наиболее полезна, когда вы определяете несколько условий для одной сущности.</span><span class="sxs-lookup"><span data-stu-id="c8d68-201">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c8d68-202">![Оператор "ИЛИ", где должно быть выполнено любое из условий](media/segmentation-either-condition.png "Оператор "ИЛИ", где должно быть выполнено любое из условий")</span><span class="sxs-lookup"><span data-stu-id="c8d68-202">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="c8d68-203">В настоящее время можно вложить оператор **ИЛИ** в оператор **И**, но не наоборот.</span><span class="sxs-lookup"><span data-stu-id="c8d68-203">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="c8d68-204">Объединение нескольких групп</span><span class="sxs-lookup"><span data-stu-id="c8d68-204">Combine multiple groups</span></span>

<span data-ttu-id="c8d68-205">Каждая группа производит определенный набор клиентов.</span><span class="sxs-lookup"><span data-stu-id="c8d68-205">Each group produces a specific set of customers.</span></span> <span data-ttu-id="c8d68-206">Вы можете объединить эти группы, чтобы включить клиентов, необходимых для вашего бизнеса.</span><span class="sxs-lookup"><span data-stu-id="c8d68-206">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="c8d68-207">В аналитике аудитории перейдите на страницу **Сегменты** и выберите сегмент.</span><span class="sxs-lookup"><span data-stu-id="c8d68-207">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="c8d68-208">Выберите **Добавить группу**.</span><span class="sxs-lookup"><span data-stu-id="c8d68-208">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c8d68-209">![Добавление группы в группу клиентов](media/customer-group-add-group.png "Добавление группы в группу клиентов")</span><span class="sxs-lookup"><span data-stu-id="c8d68-209">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="c8d68-210">Выберите один из следующих операторов множества: **Объединение**, **Пересечение** или **Кроме**.</span><span class="sxs-lookup"><span data-stu-id="c8d68-210">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c8d68-211">![Добавление объединения в группу клиентов](media/customer-group-union.png "Добавление объединения в группу клиентов")</span><span class="sxs-lookup"><span data-stu-id="c8d68-211">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="c8d68-212">Выберите оператора множества, чтобы определить новую группу.</span><span class="sxs-lookup"><span data-stu-id="c8d68-212">Select a set operator to define a new group.</span></span> <span data-ttu-id="c8d68-213">Сохранение разных групп определяет, какие данные будут сохраняться:</span><span class="sxs-lookup"><span data-stu-id="c8d68-213">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="c8d68-214">**Объединение** объединяет две группы.</span><span class="sxs-lookup"><span data-stu-id="c8d68-214">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="c8d68-215">**Пересечение** перекрывает две группы.</span><span class="sxs-lookup"><span data-stu-id="c8d68-215">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="c8d68-216">Только данные, которые *общие* в обеих группах, сохраняются в унифицированной группе.</span><span class="sxs-lookup"><span data-stu-id="c8d68-216">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="c8d68-217">**За исключением** объединяет две группы.</span><span class="sxs-lookup"><span data-stu-id="c8d68-217">**Except** combines the two groups.</span></span> <span data-ttu-id="c8d68-218">Только данные в группе "А", которые *не общие* для данных в группе "Б", сохраняются.</span><span class="sxs-lookup"><span data-stu-id="c8d68-218">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="c8d68-219">Просмотр истории обработки и участников сегмента</span><span class="sxs-lookup"><span data-stu-id="c8d68-219">View processing history and segment members</span></span>

<span data-ttu-id="c8d68-220">Вы можете увидеть консолидированные данные о сегменте, просмотрев его детали.</span><span class="sxs-lookup"><span data-stu-id="c8d68-220">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="c8d68-221">На странице **Сегменты** выберите сегмент, который хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="c8d68-221">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="c8d68-222">Верхняя часть страницы содержит график тенденций, который отображает изменения в количестве участников.</span><span class="sxs-lookup"><span data-stu-id="c8d68-222">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="c8d68-223">Наведите указатель мыши на точки данных, чтобы увидеть количество участников на определенную дату.</span><span class="sxs-lookup"><span data-stu-id="c8d68-223">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="c8d68-224">Вы можете обновить интервал времени визуализации.</span><span class="sxs-lookup"><span data-stu-id="c8d68-224">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c8d68-225">![Диапазон времени сегмента](media/segment-time-range.png "Диапазон времени сегмента")</span><span class="sxs-lookup"><span data-stu-id="c8d68-225">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="c8d68-226">Нижняя часть содержит список участников сегмента.</span><span class="sxs-lookup"><span data-stu-id="c8d68-226">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="c8d68-227">Поля, которые появляются в этом списке, основаны на атрибутах сущностей вашего сегмента.</span><span class="sxs-lookup"><span data-stu-id="c8d68-227">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="c8d68-228">Список представляет собой предварительный просмотр соответствующих участников сегмента и показывает первые 100 записей вашего сегмента, чтобы вы могли быстро оценить его и просмотреть его определения, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="c8d68-228">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="c8d68-229">Чтобы увидеть все соответствующие записи, вам нужно [экспортировать сегмент](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c8d68-229">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="c8d68-230">Быстрые сегменты</span><span class="sxs-lookup"><span data-stu-id="c8d68-230">Quick segments</span></span>

<span data-ttu-id="c8d68-231">В дополнение к конструктору сегментов есть еще один путь создания сегментов.</span><span class="sxs-lookup"><span data-stu-id="c8d68-231">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="c8d68-232">Быстрые сегменты позволяют быстро создавать простые сегменты с одним оператором с быстрым анализом.</span><span class="sxs-lookup"><span data-stu-id="c8d68-232">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="c8d68-233">На странице **Сегменты** выберите **Создать** > **Быстро создать из**.</span><span class="sxs-lookup"><span data-stu-id="c8d68-233">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="c8d68-234">Выберите параметр **Профили** для построения сегмента на основе единой сущности клиента.</span><span class="sxs-lookup"><span data-stu-id="c8d68-234">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="c8d68-235">Выберите параметр **Меры**, чтобы построить сегмент вокруг каждого из типов показателей атрибута клиента, которые вы ранее создали на странице **Меры**.</span><span class="sxs-lookup"><span data-stu-id="c8d68-235">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="c8d68-236">Выберите параметр **Аналитика**, чтобы построить сегмент вокруг одной из выходных сущностей, которые вы сгенерировали, используя возможности **Прогнозы** или **Пользовательские модели**.</span><span class="sxs-lookup"><span data-stu-id="c8d68-236">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="c8d68-237">В диалоговом окне **Создать быстрый сегмент** выберите атрибут из раскрывающегося списка **Поле**.</span><span class="sxs-lookup"><span data-stu-id="c8d68-237">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="c8d68-238">Система предоставит некоторые дополнительные сведения, которые помогут вам создать лучшие сегменты ваших клиентов.</span><span class="sxs-lookup"><span data-stu-id="c8d68-238">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="c8d68-239">Для категориальных полей мы покажем количество 10 лучших клиентов.</span><span class="sxs-lookup"><span data-stu-id="c8d68-239">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="c8d68-240">Выберите **Значение** и выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="c8d68-240">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="c8d68-241">Для числового атрибута система покажет, какое значение атрибута попадает под процентиль каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="c8d68-241">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="c8d68-242">Выберите **Оператор** и **Значение**, затем выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="c8d68-242">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="c8d68-243">Система предоставит вам **Расчетный размер сегмента**.</span><span class="sxs-lookup"><span data-stu-id="c8d68-243">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="c8d68-244">Вы можете выбрать, создавать ли определенный вами сегмент или сначала вернуться к нему, чтобы получить другой размер сегмента.</span><span class="sxs-lookup"><span data-stu-id="c8d68-244">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c8d68-245">![Название и оценка для быстрого сегмента](media/quick-segment-name.png "Название и оценка для быстрого сегмента")</span><span class="sxs-lookup"><span data-stu-id="c8d68-245">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="c8d68-246">Задайте **Имя** для сегмента.</span><span class="sxs-lookup"><span data-stu-id="c8d68-246">Provide a **Name** for your segment.</span></span> <span data-ttu-id="c8d68-247">Если требуется, укажите **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="c8d68-247">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="c8d68-248">Нажмите **Сохранить**, чтобы создать сегмент.</span><span class="sxs-lookup"><span data-stu-id="c8d68-248">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="c8d68-249">После того как обработка сегмента завершена, вы можете просмотреть его, как и любой другой созданный вами сегмент.</span><span class="sxs-lookup"><span data-stu-id="c8d68-249">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="c8d68-250">Для следующих сценариев мы рекомендуем использовать конструктор сегментов, а не функцию рекомендуемых сегментов:</span><span class="sxs-lookup"><span data-stu-id="c8d68-250">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="c8d68-251">Создание сегментов с фильтрами на категориальных полях, где оператор отличается от оператора **Является**</span><span class="sxs-lookup"><span data-stu-id="c8d68-251">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="c8d68-252">Создание сегментов с фильтрами на числовых полях, где оператор отличается от операторов **Между**, **Больше** и **Меньше**</span><span class="sxs-lookup"><span data-stu-id="c8d68-252">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="c8d68-253">Создание сегментов с фильтрами по полям типа даты</span><span class="sxs-lookup"><span data-stu-id="c8d68-253">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="c8d68-254">Дальнейшие шаги</span><span class="sxs-lookup"><span data-stu-id="c8d68-254">Next steps</span></span>

<span data-ttu-id="c8d68-255">[Экспортируйте сегмент](export-destinations.md) и изучите [Карту клиента](customer-card-add-in.md) и [Соединители](export-power-bi.md), чтобы получить представление об уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="c8d68-255">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]