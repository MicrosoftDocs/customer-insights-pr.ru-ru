---
title: Действия клиента
description: Определите действия клиентов и просматривайте их на временной шкале клиентов.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 342aeb33f652d5d60cd25e13969766954bf56370
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304942"
---
# <a name="customer-activities"></a><span data-ttu-id="9d4a6-103">Действия клиента</span><span class="sxs-lookup"><span data-stu-id="9d4a6-103">Customer activities</span></span>

<span data-ttu-id="9d4a6-104">Комбинируйте действия клиентов из [различных источников данных](data-sources.md) в Dynamics 365 Customer Insights для создания временной шкалы, в которой перечислены действия в хронологическом порядке.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="9d4a6-105">Включите временную шкалу в приложения Dynamics 365 с помощью решения [Надстройка карточки клиента](customer-card-add-in.md) или на панель мониторинга Power BI.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="9d4a6-106">Определение действия</span><span class="sxs-lookup"><span data-stu-id="9d4a6-106">Define an activity</span></span>

<span data-ttu-id="9d4a6-107">Источники данных могут включать сущности с данными транзакций и действий из нескольких источников данных.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="9d4a6-108">Определите эти сущности и выберите действия, которые вы хотите просматривать на временной шкале клиента.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="9d4a6-109">Выберите сущность, который включает ваше целевое действие или действия.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="9d4a6-110">У сущности должен быть хотя бы один атрибут типа **Дата**, который будет включен во временную шкалу клиента, и вы не можете добавлять сущности без полей **Дата**.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="9d4a6-111">Элемент управления **Добавить действие** отключен, если такая сущность не найдена.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="9d4a6-112">В аналитике аудитории перейдите **Данные** > **Действия**.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="9d4a6-113">Выберите **Добавить действие**, чтобы начать процесс настройки действия.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="9d4a6-114">На шаге **Данные действия** установите значения для следующих полей:</span><span class="sxs-lookup"><span data-stu-id="9d4a6-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="9d4a6-115">**Имя действия**: выберите название для вашего действия.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="9d4a6-116">**Сущность**: выберите сущность, которая включает данные транзакций или действий.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="9d4a6-117">**Первичный ключ**: выберите поле, которое однозначно идентифицирует запись.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="9d4a6-118">Оно не должно содержать никаких повторяющихся значений, пустых значений или отсутствующих значений.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Настройка данных действий с именем, сущностью и первичным ключом.":::

1. <span data-ttu-id="9d4a6-120">Выберите **Далее**, чтобы перейти к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="9d4a6-121">На шаге **Отношение** настройте сведения, чтобы связать данные действия с соответствующим клиентом.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="9d4a6-122">Этот шаг визуализирует связь между сущностями.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="9d4a6-123">**Первый**: внешнее поле в вашей сущности действия, которое будет использоваться для установления связи с другой сущностью.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="9d4a6-124">**Второй**: соответствующая исходная сущность клиента, с которой будет иметь отношение ваша сущность действия.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="9d4a6-125">Вы можете устанавливать отношение только с исходными сущностями клиентов, которые используются в процессе унификации данных.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="9d4a6-126">**Третий**: если отношение между этой сущностью действия и выбранной исходной сущностью клиента уже существует, имя отношения будет доступно только для чтения.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="9d4a6-127">Если такой связи не существует, будет создана новая связь с именем, указанным в этом поле.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-127">If no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Определение отношения сущности.":::

1. <span data-ttu-id="9d4a6-129">Выберите **Далее**, чтобы перейти к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="9d4a6-130">На шаге **Объединение действий** выберите событие действия и время начала действия.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="9d4a6-131">**Обязательные поля**</span><span class="sxs-lookup"><span data-stu-id="9d4a6-131">**Required fields**</span></span>
      - <span data-ttu-id="9d4a6-132">**Действие события**: поле, которое является событием для этого действия.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-132">**Event activity**: Field that is the event for this activity.</span></span>
      - <span data-ttu-id="9d4a6-133">**Метка времени**: поле, представляющее время начала вашего действия.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="9d4a6-134">**Необязательные поля**</span><span class="sxs-lookup"><span data-stu-id="9d4a6-134">**Optional fields**</span></span>
      - <span data-ttu-id="9d4a6-135">**Дополнительные сведения**: поле с соответствующей информацией для этого действия.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      - <span data-ttu-id="9d4a6-136">**Значок**: значок, который лучше всего представляет этот тип действия.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-136">**Icon**: Icon that best represents this activity type.</span></span>
      - <span data-ttu-id="9d4a6-137">**Веб-адрес**: поле, содержащее URL-адрес с информацией об этом действии.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="9d4a6-138">Например, транзакционная система, которая является источником этого действия.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="9d4a6-139">Этот URL-адрес может быть любым полем из источника данных, или он может быть создан как новое поле с использованием преобразования Power Query.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="9d4a6-140">Данные URL-адреса будут храниться в сущности *Единое действие*, которая может потребляться ниже по потоку, используя [API-интерфейсы](apis.md).</span><span class="sxs-lookup"><span data-stu-id="9d4a6-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Укажите данные о действии клиентов в сущности единого действия.":::

1. <span data-ttu-id="9d4a6-142">Выберите **Далее** для перехода к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="9d4a6-143">Вы можете выбрать **Завершить и проверить** для сохранения действия сейчас с типом действия, установленным на **Другое**.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="9d4a6-144">На шаге **Тип действия** выберите тип действия и, при необходимости, выберите, хотите ли вы семантически сопоставить некоторые типы действий для использования в других областях Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="9d4a6-145">В настоящее время типы действий *Subscription* и *SalesOrderLine* могут быть семантически сопоставлены после согласования сопоставления полей.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-145">Currently, *Subscription* and *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="9d4a6-146">Если тип действия не соответствует новому действию, вы можете выбрать *Другое* или *Создать новый* для настраиваемого типа действия.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="9d4a6-147">Выберите **Далее** для перехода к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="9d4a6-148">На шаге **Проверка** проверьте свой выбор.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="9d4a6-149">Вернитесь к любому из предыдущих шагов и при необходимости обновите информацию.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-149">Go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Проверка указанных полей для действия.":::
   
1. <span data-ttu-id="9d4a6-151">Выберите **Сохранить действие**, чтобы применить ваши изменения, и выберите **Готово**, чтобы вернуться в раздел **Данные** > **Действия**.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="9d4a6-152">Здесь вы видите, какие действия настроены для отображения на временной шкале.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="9d4a6-153">На странице **Действия** выберите **Выполнить** для обработки действия.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="9d4a6-154">Есть [шесть типов статусов](system.md#status-types) для задач/процессов.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="9d4a6-155">Кроме того, большинство процессов [зависит от других последующих процессов](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="9d4a6-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="9d4a6-156">Вы можете выбрать статус процесса, чтобы увидеть детали выполнения всего задания.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="9d4a6-157">После выбора **См. сведения** для одной из задач задания вы найдете дополнительную информацию: время обработки, дату последней обработки, а также все ошибки и предупреждения, связанные с задачей.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="9d4a6-158">Управление существующими действиями</span><span class="sxs-lookup"><span data-stu-id="9d4a6-158">Manage existing activities</span></span>

<span data-ttu-id="9d4a6-159">В разделе **Данные** > **Действия** вы можете просматривать все сохраненные действия и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="9d4a6-160">Каждое действие представлено строкой, которая также включает сведения об источнике, сущности и типе действия.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="9d4a6-161">При выборе действия доступны следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="9d4a6-162">**Изменить**: открывает настройку действия на этапе проверки.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="9d4a6-163">На этом шаге вы можете изменить любую или всю текущую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="9d4a6-164">После изменения конфигурации выберите **Сохранить действие**, затем выберите **Выполнить** для обработки изменений.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="9d4a6-165">**Переименовать**: открывает диалоговое окно, в котором вы можете ввести другое имя для выбранного действия.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-165">**Rename**: Opens a dialog where you can enter a different name for the selected activity.</span></span> <span data-ttu-id="9d4a6-166">Нажмите кнопку **Сохранить**, чтобы применить изменения.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="9d4a6-167">**Удалить**: открывает диалоговое окно для подтверждения удаления выбранного действия.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="9d4a6-168">Вы также можете удалить сразу несколько действий, выбрав их, затем щелкнув значок удаления.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="9d4a6-169">Выберите **Удалить** для подтверждения удаления.</span><span class="sxs-lookup"><span data-stu-id="9d4a6-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
