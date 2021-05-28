---
title: Экспорт данных из Customer Insights
description: Управление экспортами для совместного использования данных.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016652"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="18eb9-103">Обзор экспортов (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="18eb9-103">Exports (preview) overview</span></span>

<span data-ttu-id="18eb9-104">На странице **Экспорты** показаны все настроенные экспорты.</span><span class="sxs-lookup"><span data-stu-id="18eb9-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="18eb9-105">Экспорты используют определенные данные совместно с различными приложениями.</span><span class="sxs-lookup"><span data-stu-id="18eb9-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="18eb9-106">Они могут включать профили клиентов или сущности, схемы и сведения о сопоставлении.</span><span class="sxs-lookup"><span data-stu-id="18eb9-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="18eb9-107">Для каждого экспорта требуется [подключение, настроенное администратором, для управления аутентификацией и доступом](connections.md).</span><span class="sxs-lookup"><span data-stu-id="18eb9-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="18eb9-108">Перейдите в раздел **Данные** > **Экспорты** для просмотра страницы экспортов.</span><span class="sxs-lookup"><span data-stu-id="18eb9-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="18eb9-109">Все роли пользователей имеют доступ для просмотра настроенных экспортов.</span><span class="sxs-lookup"><span data-stu-id="18eb9-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="18eb9-110">Используйте поле поиска на панели команд для поиска экспортов по их имени, имени подключения или типу подключения.</span><span class="sxs-lookup"><span data-stu-id="18eb9-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="18eb9-111">Настройка нового экспорта</span><span class="sxs-lookup"><span data-stu-id="18eb9-111">Set up a new export</span></span>

<span data-ttu-id="18eb9-112">Чтобы настроить или отредактировать экспорт, вам необходимо иметь доступные подключения.</span><span class="sxs-lookup"><span data-stu-id="18eb9-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="18eb9-113">Подключения зависят от вашей [роли пользователя](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="18eb9-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="18eb9-114">Администраторы имеют доступ ко всем подключениям.</span><span class="sxs-lookup"><span data-stu-id="18eb9-114">Administrators have access to all connections.</span></span> <span data-ttu-id="18eb9-115">Они также могут создавать новые подключения при настройке экспорта.</span><span class="sxs-lookup"><span data-stu-id="18eb9-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="18eb9-116">Участники могут иметь доступ к определенным подключениям.</span><span class="sxs-lookup"><span data-stu-id="18eb9-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="18eb9-117">Они зависят от администраторов для настройки и совместного использования подключений.</span><span class="sxs-lookup"><span data-stu-id="18eb9-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="18eb9-118">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="18eb9-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="18eb9-119">Зрители могут только просматривать существующие экспорты, но не создавать их.</span><span class="sxs-lookup"><span data-stu-id="18eb9-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="18eb9-120">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="18eb9-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="18eb9-121">Выберите **Добавить экспорт** для создания нового пункта назначения экспорта.</span><span class="sxs-lookup"><span data-stu-id="18eb9-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="18eb9-122">В области **Настройка экспорта** выберите, какое соединение использовать.</span><span class="sxs-lookup"><span data-stu-id="18eb9-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="18eb9-123">[Подключения](connections.md) управляются администраторами.</span><span class="sxs-lookup"><span data-stu-id="18eb9-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="18eb9-124">Укажите необходимые данные и выберите **Сохранить** для создания экспорта.</span><span class="sxs-lookup"><span data-stu-id="18eb9-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="18eb9-125">Изменение экспорта</span><span class="sxs-lookup"><span data-stu-id="18eb9-125">Edit an export</span></span>

1. <span data-ttu-id="18eb9-126">Выберите многоточие по вертикали для пункта назначения экспорта, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="18eb9-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="18eb9-127">В раскрывающемся меню выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="18eb9-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="18eb9-128">Измените значения, которые требуется обновить, и выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="18eb9-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="18eb9-129">Просмотр экспорта и сведений об экспорте</span><span class="sxs-lookup"><span data-stu-id="18eb9-129">View Exports and export details</span></span>

<span data-ttu-id="18eb9-130">После создания пунктов назначения для экспорта они будут перечислены в разделе **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="18eb9-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="18eb9-131">Все пользователи могут видеть, какие данные находятся в совместном доступе, и их последний статус.</span><span class="sxs-lookup"><span data-stu-id="18eb9-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="18eb9-132">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="18eb9-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="18eb9-133">Пользователи без прав на редактирование выбирают **Посмотреть** вместо **Изменить** для просмотра сведений об экспорте.</span><span class="sxs-lookup"><span data-stu-id="18eb9-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="18eb9-134">На этой боковой панели показаны настройки этого экспорта.</span><span class="sxs-lookup"><span data-stu-id="18eb9-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="18eb9-135">Без разрешений на редактирование вы не можете изменять значения.</span><span class="sxs-lookup"><span data-stu-id="18eb9-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="18eb9-136">Выберите **Закрыть**, чтобы вернуться на страницу экспорта.</span><span class="sxs-lookup"><span data-stu-id="18eb9-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="18eb9-137">Выполнение экспортов по запросу</span><span class="sxs-lookup"><span data-stu-id="18eb9-137">Run exports on demand</span></span>

<span data-ttu-id="18eb9-138">После настройки экспорта он будет запускаться с каждым [запланированным обновлением](system.md#schedule-tab) до тех пор, пока у него есть рабочее подключение.</span><span class="sxs-lookup"><span data-stu-id="18eb9-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="18eb9-139">Чтобы экспортировать данные, не дожидаясь запланированного обновления, перейдите в раздел **Данные** > **Экспорт**.</span><span class="sxs-lookup"><span data-stu-id="18eb9-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="18eb9-140">В этом случае у вас есть два варианта.</span><span class="sxs-lookup"><span data-stu-id="18eb9-140">You have two options:</span></span>

- <span data-ttu-id="18eb9-141">Чтобы запустить все экспорты, выберите **Выполнить все** на панели команд.</span><span class="sxs-lookup"><span data-stu-id="18eb9-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="18eb9-142">Чтобы запустить один экспорт, выберите многоточие (...) в элементе списка, затем выберите **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="18eb9-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="18eb9-143">Удаление экспорта</span><span class="sxs-lookup"><span data-stu-id="18eb9-143">Remove an Export</span></span>

1. <span data-ttu-id="18eb9-144">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="18eb9-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="18eb9-145">Выберите многоточие по вертикали для экспорта, который вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="18eb9-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="18eb9-146">В раскрывающемся меню выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="18eb9-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="18eb9-147">Подтвердите удаление, выбрав **Удалить** на экране подтверждения.</span><span class="sxs-lookup"><span data-stu-id="18eb9-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
