---
title: Подключения к другим службам из Customer Insights.
description: Делитесь данными с другими службами.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 17e04b243e9b3d4375c86f5a890a18be35956835
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304988"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="37d6f-103">Обзор подключений (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="37d6f-103">Connections (preview) overview</span></span>

<span data-ttu-id="37d6f-104">Подключения — это ключ к обеспечению передачи данных в Customer Insights и обратно.</span><span class="sxs-lookup"><span data-stu-id="37d6f-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="37d6f-105">Каждое подключение устанавливает совместное использование данных с определенной службой.</span><span class="sxs-lookup"><span data-stu-id="37d6f-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="37d6f-106">Подключения — это основа для [настройки обогащения данных сторонних производителей](enrichment-hub.md) и [настройки экспорта](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="37d6f-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="37d6f-107">Одно и то же подключение можно использовать несколько раз.</span><span class="sxs-lookup"><span data-stu-id="37d6f-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="37d6f-108">Например, одно подключение с Dynamics 365 Marketing работает для нескольких экспортов, а одно подключение Leadspace можно использовать для нескольких обогащений.</span><span class="sxs-lookup"><span data-stu-id="37d6f-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="37d6f-109">Перейти в раздел **Администрирование** > **Подключения** для создания и просмотра подключений.</span><span class="sxs-lookup"><span data-stu-id="37d6f-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="37d6f-110">На вкладке **Подключения** отображаются все активные подключения.</span><span class="sxs-lookup"><span data-stu-id="37d6f-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="37d6f-111">В списке отображается строка для каждого подключения.</span><span class="sxs-lookup"><span data-stu-id="37d6f-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="37d6f-112">Получите краткий обзор, описание и узнайте, что вы можете делать с каждым параметром расширяемости на вкладке **Обнаружение**.</span><span class="sxs-lookup"><span data-stu-id="37d6f-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="37d6f-113">Экспорты</span><span class="sxs-lookup"><span data-stu-id="37d6f-113">Exports</span></span>

<span data-ttu-id="37d6f-114">Только администраторы могут настраивать новые подключения, но они могут предоставить участникам доступ к использованию существующих подключений.</span><span class="sxs-lookup"><span data-stu-id="37d6f-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="37d6f-115">Администраторы контролируют, куда могут поступать данные, участники определяют полезную нагрузку и частоту в соответствии со своими потребностями.</span><span class="sxs-lookup"><span data-stu-id="37d6f-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="37d6f-116">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="37d6f-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="37d6f-117">Обогащения</span><span class="sxs-lookup"><span data-stu-id="37d6f-117">Enrichments</span></span>

<span data-ttu-id="37d6f-118">Только администраторы могут настраивать новые подключения, но созданные подключения всегда доступны как администраторам, так и участникам.</span><span class="sxs-lookup"><span data-stu-id="37d6f-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="37d6f-119">Администраторы управляют учетными данными и дают согласие на передачу данных.</span><span class="sxs-lookup"><span data-stu-id="37d6f-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="37d6f-120">Затем эти подключения могут быть использованы как администраторами, так и участниками для обогащений.</span><span class="sxs-lookup"><span data-stu-id="37d6f-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="37d6f-121">Добавление нового подключения</span><span class="sxs-lookup"><span data-stu-id="37d6f-121">Add a new connection</span></span>

<span data-ttu-id="37d6f-122">Для добавления подключений вам необходимо иметь [разрешения администратора](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="37d6f-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="37d6f-123">Если вы подключаетесь к другим службам Microsoft, мы предполагаем, что обе службы находятся в одной организации.</span><span class="sxs-lookup"><span data-stu-id="37d6f-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="37d6f-124">Перейти в раздел **Администрирование** > **Подключения (предварительная версия)**.</span><span class="sxs-lookup"><span data-stu-id="37d6f-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="37d6f-125">Перейдите на вкладку **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="37d6f-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="37d6f-126">Выберите **Добавить подключение**, чтобы создать новое подключение.</span><span class="sxs-lookup"><span data-stu-id="37d6f-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="37d6f-127">Выберите из раскрывающегося меню, какой тип подключения вы хотите создать.</span><span class="sxs-lookup"><span data-stu-id="37d6f-127">Choose from the dropdown menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="37d6f-128">В области **Настроить подключение** укажите необходимые сведения.</span><span class="sxs-lookup"><span data-stu-id="37d6f-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="37d6f-129">**Отображаемое имя** и тип подключения описывают подключение.</span><span class="sxs-lookup"><span data-stu-id="37d6f-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="37d6f-130">Мы рекомендуем выбрать имя, которое объясняет назначение и цель этого подключения.</span><span class="sxs-lookup"><span data-stu-id="37d6f-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="37d6f-131">Точные поля зависят от того, к какой службе вы подключаетесь.</span><span class="sxs-lookup"><span data-stu-id="37d6f-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="37d6f-132">Подробнее о конкретном типе подключения вы можете узнать из статьи о целевой службе.</span><span class="sxs-lookup"><span data-stu-id="37d6f-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="37d6f-133">Чтобы создать подключение, выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="37d6f-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="37d6f-134">Вы также можете выбрать **Настроить** на плитке на вкладке **Обнаружить**.</span><span class="sxs-lookup"><span data-stu-id="37d6f-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="37d6f-135">Разрешение участникам использовать подключение для экспорта</span><span class="sxs-lookup"><span data-stu-id="37d6f-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="37d6f-136">При настройке или редактировании подключения для экспорта вы выбираете, каким пользователям разрешено использовать это конкретное подключение для определения [экспортов](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="37d6f-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="37d6f-137">По умолчанию подключение доступно пользователям с ролью администратора.</span><span class="sxs-lookup"><span data-stu-id="37d6f-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="37d6f-138">Вы можете изменить этот параметр в пункте **Укажите, кто может использовать это подключение** и разрешить пользователям с ролью участника использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="37d6f-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="37d6f-139">Участники не смогут просматривать или редактировать подключение.</span><span class="sxs-lookup"><span data-stu-id="37d6f-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="37d6f-140">Они будут видеть только отображаемое имя и его тип при создании экспорта.</span><span class="sxs-lookup"><span data-stu-id="37d6f-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="37d6f-141">Предоставляя общий доступ к подключению, вы разрешаете участникам использовать подключение.</span><span class="sxs-lookup"><span data-stu-id="37d6f-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="37d6f-142">Участники будут видеть общие подключения при настройке экспорта.</span><span class="sxs-lookup"><span data-stu-id="37d6f-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="37d6f-143">Они могут управлять каждым экспортом, использующим это конкретное подключение.</span><span class="sxs-lookup"><span data-stu-id="37d6f-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="37d6f-144">Вы можете изменить этот параметр, сохранив экспорты, которые уже были определены участниками.</span><span class="sxs-lookup"><span data-stu-id="37d6f-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="37d6f-145">Изменение подключения</span><span class="sxs-lookup"><span data-stu-id="37d6f-145">Edit a connection</span></span>

1. <span data-ttu-id="37d6f-146">Перейти в раздел **Администрирование** > **Подключения (предварительная версия)**.</span><span class="sxs-lookup"><span data-stu-id="37d6f-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="37d6f-147">Перейдите на вкладку **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="37d6f-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="37d6f-148">Выберите многоточие по вертикали для подключения, которое вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="37d6f-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="37d6f-149">Выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="37d6f-149">Select **Edit**.</span></span>

1. <span data-ttu-id="37d6f-150">Измените значения, которые требуется обновить, и выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="37d6f-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="37d6f-151">Удаление подключения</span><span class="sxs-lookup"><span data-stu-id="37d6f-151">Remove a connection</span></span>

<span data-ttu-id="37d6f-152">Если удаляемое подключение используется для обогащения или экспорта, вам сначала нужно отсоединить или удалить их.</span><span class="sxs-lookup"><span data-stu-id="37d6f-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="37d6f-153">Диалоговое окно удаления направит вас к нужному обогащению или экспорту.</span><span class="sxs-lookup"><span data-stu-id="37d6f-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> 

<span data-ttu-id="37d6f-154">Отсоединенные обогащения и экспорты становятся неактивными.</span><span class="sxs-lookup"><span data-stu-id="37d6f-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="37d6f-155">Вы активируете их повторно, добавляя к ним другое подключение на странице [Обогащения](enrichment-hub.md) или [Экспорты](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="37d6f-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="37d6f-156">Перейти в раздел **Администрирование** > **Подключения (предварительная версия)**.</span><span class="sxs-lookup"><span data-stu-id="37d6f-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="37d6f-157">Перейдите на вкладку **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="37d6f-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="37d6f-158">Выберите многоточие по вертикали для подключения, которое вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="37d6f-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="37d6f-159">В раскрывающемся меню выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="37d6f-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="37d6f-160">Открывается диалог запроса подтверждения.</span><span class="sxs-lookup"><span data-stu-id="37d6f-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="37d6f-161">Если есть обогащения или экспорты, использующие это подключение, нажмите кнопку, чтобы увидеть, чем используется подключение.</span><span class="sxs-lookup"><span data-stu-id="37d6f-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="37d6f-162">**Экспорты:** вы можете удалить или отсоединить экспорт, чтобы можно было удалить подключение.</span><span class="sxs-lookup"><span data-stu-id="37d6f-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="37d6f-163">Чтобы отсоединить экспорт, администраторы могут использовать действие **Отсоединить**.</span><span class="sxs-lookup"><span data-stu-id="37d6f-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="37d6f-164">Это действие доступно для отдельных или нескольких выбранных экспортов.</span><span class="sxs-lookup"><span data-stu-id="37d6f-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="37d6f-165">При отсоединении вы сохраняете конфигурацию экспорта, но он не будет выполняться, пока к нему не будет добавлено другое подключение.</span><span class="sxs-lookup"><span data-stu-id="37d6f-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="37d6f-166">**Обогащения:** вы можете удалить или деактивировать обогащения, чтобы можно было удалить подключение.</span><span class="sxs-lookup"><span data-stu-id="37d6f-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="37d6f-167">Когда у подключения больше нет зависимостей, вернитесь в раздел **Администрирование** > **Подключения** и попробуйте снова удалить подключение.</span><span class="sxs-lookup"><span data-stu-id="37d6f-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="37d6f-168">Для подтверждения удаления выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="37d6f-168">To confirm the deletion, select **Remove**.</span></span>

