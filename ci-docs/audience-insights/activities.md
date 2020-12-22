---
title: Действия клиента
description: Определите действия клиентов и просматривайте их на временной шкале клиентов.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1c95cba333266a73959de0a3afe1c8677130a3ec
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667245"
---
# <a name="customer-activities"></a><span data-ttu-id="a7030-103">Действия клиента</span><span class="sxs-lookup"><span data-stu-id="a7030-103">Customer activities</span></span>

<span data-ttu-id="a7030-104">Объедините действия клиентов из [различные источники данных](data-sources.md) в Dynamics 365 Customer Insights для создания временной шкалы клиентов, в которой перечислены действия в хронологическом порядке.</span><span class="sxs-lookup"><span data-stu-id="a7030-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="a7030-105">Вы можете включить временную шкалу в приложениях Customer Engagement в Dynamics 365 с помощью [Надстройки карточки клиента](customer-card-add-in.md) или на панели мониторинга Power BI.</span><span class="sxs-lookup"><span data-stu-id="a7030-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="a7030-106">Определение действия</span><span class="sxs-lookup"><span data-stu-id="a7030-106">Define an activity</span></span>

<span data-ttu-id="a7030-107">Источники данных включают сущности с данными транзакций и действий из нескольких источников данных.</span><span class="sxs-lookup"><span data-stu-id="a7030-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="a7030-108">Определите эти сущности и выберите действия, которые вы хотите просматривать на временной шкале клиента.</span><span class="sxs-lookup"><span data-stu-id="a7030-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="a7030-109">Выберите сущность, который включает ваше целевое действие или действия.</span><span class="sxs-lookup"><span data-stu-id="a7030-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="a7030-110">В аналитике аудитории перейдите **Данные** > **Действия**.</span><span class="sxs-lookup"><span data-stu-id="a7030-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="a7030-111">Выберите **Добавить действие**.</span><span class="sxs-lookup"><span data-stu-id="a7030-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a7030-112">У сущности должен быть хотя бы один атрибут типа **Дата**, который будет включен во временную шкалу клиента, и вы не можете добавлять сущности без полей **Дата**.</span><span class="sxs-lookup"><span data-stu-id="a7030-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="a7030-113">Элемент управления **Добавить действие** отключен, если такая сущность не найдена.</span><span class="sxs-lookup"><span data-stu-id="a7030-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="a7030-114">На панели **Добавить действие** установите значения для следующих полей:</span><span class="sxs-lookup"><span data-stu-id="a7030-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="a7030-115">**Сущность**: выберите сущность, которая включает данные транзакций или действий.</span><span class="sxs-lookup"><span data-stu-id="a7030-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="a7030-116">**Первичный ключ**: выберите поле, которое однозначно идентифицирует запись.</span><span class="sxs-lookup"><span data-stu-id="a7030-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="a7030-117">Оно не должно содержать никаких повторяющихся значений, пустых значений или отсутствующих значений.</span><span class="sxs-lookup"><span data-stu-id="a7030-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="a7030-118">**Отметка времени**: выберите поле, которое представляет время начала вашей действия.</span><span class="sxs-lookup"><span data-stu-id="a7030-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="a7030-119">**Событие**: выберите поле, которое является событием для действия.</span><span class="sxs-lookup"><span data-stu-id="a7030-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="a7030-120">**Веб-адрес**: выберите поле, представляющее URL-адрес, предоставляющий дополнительную информацию об этом действии.</span><span class="sxs-lookup"><span data-stu-id="a7030-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="a7030-121">Например, транзакционная система, которая является источником этого действия.</span><span class="sxs-lookup"><span data-stu-id="a7030-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="a7030-122">Этот URL-адрес может быть любым полем из источника данных, или он может быть создан как новое поле с использованием преобразования Power Query.</span><span class="sxs-lookup"><span data-stu-id="a7030-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="a7030-123">Эти данные URL будут храниться в сущности Unified Activity, которую можно использовать в нисходящем направлении с помощью API.</span><span class="sxs-lookup"><span data-stu-id="a7030-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="a7030-124">**Сведения**: при необходимости выберите поле, которое добавляется для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="a7030-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="a7030-125">**Значок**: при необходимости выберите значок, который представляет это действие.</span><span class="sxs-lookup"><span data-stu-id="a7030-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="a7030-126">**Тип действия**: определите ссылку на тип действия для Common Data Model, которая лучше всего описывает семантическое определение действия.</span><span class="sxs-lookup"><span data-stu-id="a7030-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="a7030-127">В разделе **Настройка отношения**, настройте детали, чтобы связать ваши данные о действии с соответствующим клиентом.</span><span class="sxs-lookup"><span data-stu-id="a7030-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a7030-128">![Определение отношения сущности](media/activities-entities-define.png "Определение отношения сущности")</span><span class="sxs-lookup"><span data-stu-id="a7030-128">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

    - <span data-ttu-id="a7030-129">**Поле сущности действия**: выберите поле в вашей сущности действия, которое будет использоваться для установления отношений с другой сущностью.</span><span class="sxs-lookup"><span data-stu-id="a7030-129">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="a7030-130">**Сущность клиента**: выберите соответствующую исходную сущность клиента, с которым будет связана ваша сущность действия.</span><span class="sxs-lookup"><span data-stu-id="a7030-130">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="a7030-131">Вы можете задавать связь только с теми исходным сущностями клиентов, которые используются в процессе унификации данных.</span><span class="sxs-lookup"><span data-stu-id="a7030-131">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="a7030-132">**Поле сущности клиента**: в этом поле отображается первичный ключ исходной сущности клиента, выбранный в процессе сопоставления.</span><span class="sxs-lookup"><span data-stu-id="a7030-132">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="a7030-133">Это поле первичного ключа в исходной сущности клиента используется для установления связи с сущностью действия.</span><span class="sxs-lookup"><span data-stu-id="a7030-133">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="a7030-134">**Имя**: если связь между этой сущностью действия и выбранной исходной сущностью клиента уже существует, имя отношения будет находиться в режиме только для чтения.</span><span class="sxs-lookup"><span data-stu-id="a7030-134">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="a7030-135">Если такого отношения не существует, будет создано новое отношение с указанным здесь именем.</span><span class="sxs-lookup"><span data-stu-id="a7030-135">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>

1. <span data-ttu-id="a7030-136">Нажмите кнопку **Сохранить**, чтобы применить изменения.</span><span class="sxs-lookup"><span data-stu-id="a7030-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="a7030-137">На странице **Действия** выберите **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="a7030-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="a7030-138">Есть [шесть типов статусов](system.md#status-types) для задач/процессов.</span><span class="sxs-lookup"><span data-stu-id="a7030-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="a7030-139">Кроме того, большинство процессов [зависит от других последующих процессов](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="a7030-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="a7030-140">Вы можете выбрать статус процесса, чтобы увидеть детали выполнения всего задания.</span><span class="sxs-lookup"><span data-stu-id="a7030-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="a7030-141">После выбора **См. сведения** для одной из задач задания вы найдете дополнительную информацию: время обработки, дату последней обработки, а также все ошибки и предупреждения, связанные с задачей.</span><span class="sxs-lookup"><span data-stu-id="a7030-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="a7030-142">Изменить действие</span><span class="sxs-lookup"><span data-stu-id="a7030-142">Edit an activity</span></span>

1. <span data-ttu-id="a7030-143">В аналитике аудитории перейдите **Данные** > **Действия**.</span><span class="sxs-lookup"><span data-stu-id="a7030-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="a7030-144">Выберите сущность действия, которую вы хотите редактировать, и выберите **Редактировать**.</span><span class="sxs-lookup"><span data-stu-id="a7030-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="a7030-145">Или вы можете навести указатель на строку сущности и выбрать значок **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="a7030-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="a7030-146">Щелкните значок **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="a7030-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="a7030-147">На панели **Изменить действие** обновите значения и выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a7030-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="a7030-148">На странице **Действия** выберите **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="a7030-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="a7030-149">Удаление действия</span><span class="sxs-lookup"><span data-stu-id="a7030-149">Delete an activity</span></span>

1. <span data-ttu-id="a7030-150">В аналитике аудитории перейдите **Данные** > **Действия**.</span><span class="sxs-lookup"><span data-stu-id="a7030-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="a7030-151">Выберите сущность действия, которую вы хотите удалить, и выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="a7030-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="a7030-152">Или вы можете навести указатель на строку сущности и выбрать значок **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="a7030-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="a7030-153">Кроме того, вы можете выбрать несколько сущностей действия для одновременного удаления.</span><span class="sxs-lookup"><span data-stu-id="a7030-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a7030-154">![Изменение или удаление отношения сущности](media/activities-entities-edit-delete.png "Изменение или удаление отношения сущности")</span><span class="sxs-lookup"><span data-stu-id="a7030-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="a7030-155">Выберите значок **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="a7030-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="a7030-156">Подтвердите удаление.</span><span class="sxs-lookup"><span data-stu-id="a7030-156">Confirm your deletion.</span></span>
