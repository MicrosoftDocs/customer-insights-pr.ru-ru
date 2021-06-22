---
title: Экспорт данных из Customer Insights
description: Управление экспортами для совместного использования данных.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253056"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="9430b-103">Обзор экспортов (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="9430b-103">Exports (preview) overview</span></span>

<span data-ttu-id="9430b-104">На странице **Экспорты** показаны все настроенные экспорты.</span><span class="sxs-lookup"><span data-stu-id="9430b-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="9430b-105">Экспорты используют определенные данные совместно с различными приложениями.</span><span class="sxs-lookup"><span data-stu-id="9430b-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="9430b-106">Они могут включать профили клиентов или сущности, схемы и сведения о сопоставлении.</span><span class="sxs-lookup"><span data-stu-id="9430b-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="9430b-107">Для каждого экспорта требуется [подключение, настроенное администратором, для управления аутентификацией и доступом](connections.md).</span><span class="sxs-lookup"><span data-stu-id="9430b-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="9430b-108">Перейдите в раздел **Данные** > **Экспорты** для просмотра страницы экспортов.</span><span class="sxs-lookup"><span data-stu-id="9430b-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="9430b-109">Все роли пользователей имеют доступ для просмотра настроенных экспортов.</span><span class="sxs-lookup"><span data-stu-id="9430b-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="9430b-110">Используйте поле поиска на панели команд для поиска экспортов по их имени, имени подключения или типу подключения.</span><span class="sxs-lookup"><span data-stu-id="9430b-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="9430b-111">Настройка нового экспорта</span><span class="sxs-lookup"><span data-stu-id="9430b-111">Set up a new export</span></span>

<span data-ttu-id="9430b-112">Чтобы настроить или отредактировать экспорт, вам необходимо иметь доступные подключения.</span><span class="sxs-lookup"><span data-stu-id="9430b-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="9430b-113">Подключения зависят от вашей [роли пользователя](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="9430b-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="9430b-114">Администраторы имеют доступ ко всем подключениям.</span><span class="sxs-lookup"><span data-stu-id="9430b-114">Administrators have access to all connections.</span></span> <span data-ttu-id="9430b-115">Они также могут создавать новые подключения при настройке экспорта.</span><span class="sxs-lookup"><span data-stu-id="9430b-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="9430b-116">Участники могут иметь доступ к определенным подключениям.</span><span class="sxs-lookup"><span data-stu-id="9430b-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="9430b-117">Они зависят от администраторов для настройки и совместного использования подключений.</span><span class="sxs-lookup"><span data-stu-id="9430b-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="9430b-118">В списке экспорта показаны участники, могут ли они редактировать или только просматривать экспорт в столбце **Ваши разрешения**.</span><span class="sxs-lookup"><span data-stu-id="9430b-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="9430b-119">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="9430b-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="9430b-120">Зрители могут только просматривать существующие экспорты, но не создавать их.</span><span class="sxs-lookup"><span data-stu-id="9430b-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="9430b-121">Определение нового экспорта</span><span class="sxs-lookup"><span data-stu-id="9430b-121">Define a new export</span></span>

1. <span data-ttu-id="9430b-122">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="9430b-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9430b-123">Выберите **Добавить экспорт**, чтобы создать новый экспорт.</span><span class="sxs-lookup"><span data-stu-id="9430b-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="9430b-124">В области **Настройка экспорта** выберите, какое соединение использовать.</span><span class="sxs-lookup"><span data-stu-id="9430b-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="9430b-125">[Подключения](connections.md) управляются администраторами.</span><span class="sxs-lookup"><span data-stu-id="9430b-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="9430b-126">Укажите необходимые данные и выберите **Сохранить** для создания экспорта.</span><span class="sxs-lookup"><span data-stu-id="9430b-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="9430b-127">Определите новый экспорт на основе существующего экспорта</span><span class="sxs-lookup"><span data-stu-id="9430b-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="9430b-128">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="9430b-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9430b-129">В списке экспортов выберите экспорт, который требуется дублировать.</span><span class="sxs-lookup"><span data-stu-id="9430b-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="9430b-130">Выберите **Создать дубликат** на панели команд, чтобы открыть область **Настройка экспорта** со сведениями выбранного экспорта.</span><span class="sxs-lookup"><span data-stu-id="9430b-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="9430b-131">Просмотрите и настройте экспорт и выберите **Сохранить** для создания нового экспорта.</span><span class="sxs-lookup"><span data-stu-id="9430b-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="9430b-132">Изменение экспорта</span><span class="sxs-lookup"><span data-stu-id="9430b-132">Edit an export</span></span>

1. <span data-ttu-id="9430b-133">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="9430b-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9430b-134">В списке экспортов выберите экспорт, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="9430b-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="9430b-135">На панели команд выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="9430b-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="9430b-136">Измените значения, которые требуется обновить, и выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9430b-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="9430b-137">Просмотр экспортов и сведений об экспорте</span><span class="sxs-lookup"><span data-stu-id="9430b-137">View exports and export details</span></span>

<span data-ttu-id="9430b-138">После создания пунктов назначения для экспорта они будут перечислены в разделе **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="9430b-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="9430b-139">Все пользователи могут видеть, какие данные находятся в совместном доступе, и их последний статус.</span><span class="sxs-lookup"><span data-stu-id="9430b-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="9430b-140">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="9430b-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9430b-141">Пользователи без прав на редактирование выбирают **Посмотреть** вместо **Изменить** для просмотра сведений об экспорте.</span><span class="sxs-lookup"><span data-stu-id="9430b-141">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="9430b-142">На боковой панели отображается конфигурация экспорта.</span><span class="sxs-lookup"><span data-stu-id="9430b-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="9430b-143">Без разрешений на редактирование вы не можете изменять значения.</span><span class="sxs-lookup"><span data-stu-id="9430b-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="9430b-144">Выберите **Закрыть**, чтобы вернуться на страницу экспорта.</span><span class="sxs-lookup"><span data-stu-id="9430b-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="9430b-145">Планирование и запуск экспортов</span><span class="sxs-lookup"><span data-stu-id="9430b-145">Schedule and run exports</span></span>

<span data-ttu-id="9430b-146">Каждый настраиваемый экспорт имеет расписание обновления.</span><span class="sxs-lookup"><span data-stu-id="9430b-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="9430b-147">Во время обновления система ищет новые или обновленные данные для включения в экспорт.</span><span class="sxs-lookup"><span data-stu-id="9430b-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="9430b-148">По умолчанию экспорт выполняется как часть каждого [планового обновления системы](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9430b-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9430b-149">Вы можете настроить расписание обновления или отключить его, чтобы запускать экспорт вручную.</span><span class="sxs-lookup"><span data-stu-id="9430b-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="9430b-150">Расписания экспорта зависят от состояния вашей среды.</span><span class="sxs-lookup"><span data-stu-id="9430b-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="9430b-151">Если выполняются обновления в [зависимостях](system.md#refresh-policies), когда должен начаться запланированный экспорт, система сначала установит зависимости, а затем выполнит экспорт.</span><span class="sxs-lookup"><span data-stu-id="9430b-151">If there are updates on [dependencies](system.md#refresh-policies) in progress when a scheduled export should start, the system will first complete the dependencies and then run the export.</span></span> <span data-ttu-id="9430b-152">Вы можете увидеть, когда последний раз экспорт был обновлен, в столбце **Обновлено**.</span><span class="sxs-lookup"><span data-stu-id="9430b-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="9430b-153">Расписание экспортов</span><span class="sxs-lookup"><span data-stu-id="9430b-153">Schedule exports</span></span>

<span data-ttu-id="9430b-154">Можно определять настраиваемые расписания обновления для отдельного экспорта или сразу нескольких экспортов.</span><span class="sxs-lookup"><span data-stu-id="9430b-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="9430b-155">Текущее расписание указано в столбце **Расписание** списка экспорта.</span><span class="sxs-lookup"><span data-stu-id="9430b-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="9430b-156">Разрешение на изменение расписания такое же, как и для [редактирования и определения экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="9430b-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="9430b-157">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="9430b-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9430b-158">Выберите экспорт для расписания.</span><span class="sxs-lookup"><span data-stu-id="9430b-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="9430b-159">На панели команд выберите **Расписание**.</span><span class="sxs-lookup"><span data-stu-id="9430b-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="9430b-160">В области **Расписание экспорт** установите **Запланировать запуск** как **Вкл** для автоматического запуска экспорта.</span><span class="sxs-lookup"><span data-stu-id="9430b-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="9430b-161">Установите его как **Выкл**, чтобы обновить его вручную.</span><span class="sxs-lookup"><span data-stu-id="9430b-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="9430b-162">Для автоматического обновления экспорта выберите значение **Повторение** и укажите для него сведения.</span><span class="sxs-lookup"><span data-stu-id="9430b-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="9430b-163">Заданное время применяется ко всем экземплярам повторения.</span><span class="sxs-lookup"><span data-stu-id="9430b-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="9430b-164">Это время, когда экспорт должен начать обновляться.</span><span class="sxs-lookup"><span data-stu-id="9430b-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="9430b-165">Примените и активируйте свои изменения, выбрав **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9430b-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="9430b-166">При редактировании расписания для нескольких экспортов необходимо сделать выбор в **Сохранять или переопределять расписания**:</span><span class="sxs-lookup"><span data-stu-id="9430b-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="9430b-167">**Соблюдать отдельные расписания**: сохранять ранее определенное расписание для выбранных экспортов и только отключать или включать их.</span><span class="sxs-lookup"><span data-stu-id="9430b-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="9430b-168">**Определить новое расписание для всех выбранных экспортов**: переопределить существующие расписания выбранных экспортов.</span><span class="sxs-lookup"><span data-stu-id="9430b-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="9430b-169">Выполнение экспортов по запросу</span><span class="sxs-lookup"><span data-stu-id="9430b-169">Run exports on demand</span></span>

<span data-ttu-id="9430b-170">Чтобы экспортировать данные, не дожидаясь запланированного обновления, перейдите в раздел **Данные** > **Экспорт**.</span><span class="sxs-lookup"><span data-stu-id="9430b-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="9430b-171">Чтобы запустить все экспорты, выберите **Выполнить все** на панели команд.</span><span class="sxs-lookup"><span data-stu-id="9430b-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="9430b-172">Это действие будет запускать только экспорт с активным расписанием.</span><span class="sxs-lookup"><span data-stu-id="9430b-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="9430b-173">Чтобы запустить отдельный экспорт, выберите его в списке и выберите **Запустить** на панели команд.</span><span class="sxs-lookup"><span data-stu-id="9430b-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="9430b-174">Вот как вы запускаете экспорт без активного расписания.</span><span class="sxs-lookup"><span data-stu-id="9430b-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="9430b-175">Удаление экспорта</span><span class="sxs-lookup"><span data-stu-id="9430b-175">Remove an Export</span></span>

1. <span data-ttu-id="9430b-176">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="9430b-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9430b-177">Выберите экспорт, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="9430b-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="9430b-178">На панели команд выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="9430b-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="9430b-179">Подтвердите удаление, выбрав **Удалить** на экране подтверждения.</span><span class="sxs-lookup"><span data-stu-id="9430b-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
