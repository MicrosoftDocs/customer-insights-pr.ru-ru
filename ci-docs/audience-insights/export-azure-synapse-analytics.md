---
title: Экспорт данных Customer Insights в Azure Synapse Analytics
description: Узнайте, как настроить подключение к Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977393"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="c7772-103">Экспорт данных в Azure Synapse Analytics (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="c7772-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="c7772-104">Azure Synapse — это служба аналитики, которая ускоряет анализ хранилищ данных и систем больших данных.</span><span class="sxs-lookup"><span data-stu-id="c7772-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="c7772-105">Вы можете получать и использовать свои данные Customer Insights в [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="c7772-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c7772-106">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="c7772-106">Prerequisites</span></span>

<span data-ttu-id="c7772-107">Для настройки подключения из Customer Insights к Azure Synapse должны быть выполнены следующие предварительные условия.</span><span class="sxs-lookup"><span data-stu-id="c7772-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="c7772-108">Обязательно установите все **назначения ролей**, как описано.</span><span class="sxs-lookup"><span data-stu-id="c7772-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="c7772-109">Предварительные требования в Customer Insights</span><span class="sxs-lookup"><span data-stu-id="c7772-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="c7772-110">Вам присвоена роль **Администратор** в аналитике аудитории.</span><span class="sxs-lookup"><span data-stu-id="c7772-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="c7772-111">Узнайте больше об [установке разрешений пользователей в аналитики аудитории](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="c7772-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="c7772-112">В Azure:</span><span class="sxs-lookup"><span data-stu-id="c7772-112">In Azure:</span></span> 

- <span data-ttu-id="c7772-113">Активная подписка Azure.</span><span class="sxs-lookup"><span data-stu-id="c7772-113">An active Azure subscription.</span></span>

- <span data-ttu-id="c7772-114">При использовании новой учетной записи Azure Data Lake Storage 2-го поколения *субъекту службы для аналитики аудитории* необходимы разрешения **участника данных больших двоичных объектов хранилищ**.</span><span class="sxs-lookup"><span data-stu-id="c7772-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="c7772-115">Узнайте больше о [подключении к учетной записи Azure Data Lake Storage 2-го поколения с субъектом службы Azure для аналитики аудитории](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="c7772-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="c7772-116">В Data Lake Storage 2-го поколения **должно быть** включено [иерархическое пространство имен](/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="c7772-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="c7772-117">В группе ресурсов, в которой расположена рабочая область Azure Synapse, *субъект-службе* и *пользователю для аналитики аудитории* необходимо назначить по крайней мере разрешения **Читатель**.</span><span class="sxs-lookup"><span data-stu-id="c7772-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="c7772-118">Дополнительные сведения см. в разделе [Назначение ролей Azure с помощью портала Azure](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="c7772-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="c7772-119">*Пользователю* требуются разрешения **Участник данных больших двоичных объектов хранилища** в учетной записи Azure Data Lake Storage 2-го поколения, в которой данные расположены и связаны с рабочей областью Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="c7772-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="c7772-120">Узнайте больше об [использовании портала Azure для назначения роли Azure для доступа к данным BLOB-объектов и очередей](/azure/storage/common/storage-auth-aad-rbac-portal) и о [разрешениях участника данных больших двоичных объектов хранилища](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="c7772-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="c7772-121">Для *[управляемого удостоверения рабочей области Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* требуются разрешения **Участник данных больших двоичных объектов хранилища** в учетной записи Azure Data Lake Storage 2-го поколения, в которой данные расположены и связаны с рабочей областью Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="c7772-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="c7772-122">Узнайте больше об [использовании портала Azure для назначения роли Azure для доступа к данным BLOB-объектов и очередей](/azure/storage/common/storage-auth-aad-rbac-portal) и о [разрешениях участника данных больших двоичных объектов хранилища](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="c7772-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="c7772-123">В рабочей области Azure Synapse *субъект-служба для аналитики аудитории* должна быть назначена роль **Администратор Synapse**.</span><span class="sxs-lookup"><span data-stu-id="c7772-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="c7772-124">Дополнительные сведения см. в разделе [Как настроить контроль доступа к вашей рабочей области Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="c7772-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="c7772-125">Настройка подключения и экспорт в Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="c7772-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="c7772-126">Настройка подключения</span><span class="sxs-lookup"><span data-stu-id="c7772-126">Configure a connection</span></span>

1. <span data-ttu-id="c7772-127">Перейти в раздел **Администрирование** > **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="c7772-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c7772-128">Выберите **Добавить подключение** и выберите **Azure Synapse Analytics** или выберите **Настройка** на плитке **Azure Synapse Analytics** для настройки подключения.</span><span class="sxs-lookup"><span data-stu-id="c7772-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="c7772-129">Дайте вашему подключению узнаваемое имя в поле Отображаемое имя.</span><span class="sxs-lookup"><span data-stu-id="c7772-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="c7772-130">Имя и тип подключения описывают это подключение.</span><span class="sxs-lookup"><span data-stu-id="c7772-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="c7772-131">Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.</span><span class="sxs-lookup"><span data-stu-id="c7772-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c7772-132">Укажите, кто может использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="c7772-132">Choose who can use this connection.</span></span> <span data-ttu-id="c7772-133">Если вы не предпримете никаких действий, по умолчанию это будут администраторы.</span><span class="sxs-lookup"><span data-stu-id="c7772-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="c7772-134">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c7772-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c7772-135">Выберите или найдите подписку, в которой вы хотите использовать данные Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c7772-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="c7772-136">Как только подписка выбрана, вы также можете выбрать параметры **Рабочая область**, **Учетная запись хранения** и **Контейнер**.</span><span class="sxs-lookup"><span data-stu-id="c7772-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="c7772-137">Выберите **Сохранить**, чтобы сохранить подключение.</span><span class="sxs-lookup"><span data-stu-id="c7772-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="c7772-138">Настройка экспорта</span><span class="sxs-lookup"><span data-stu-id="c7772-138">Configure an export</span></span>

<span data-ttu-id="c7772-139">Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа.</span><span class="sxs-lookup"><span data-stu-id="c7772-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c7772-140">Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c7772-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c7772-141">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="c7772-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c7772-142">Чтобы создать новый экспорт, выберите **Добавить экспорт**.</span><span class="sxs-lookup"><span data-stu-id="c7772-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="c7772-143">В поле **Подключение для экспорта** выберите подключение из раздела **Azure Synapse Analytics**.</span><span class="sxs-lookup"><span data-stu-id="c7772-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="c7772-144">Если вы не видите название этого раздела, вам не доступны [подключения](connections.md) этого типа.</span><span class="sxs-lookup"><span data-stu-id="c7772-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="c7772-145">Укажите узнаваемое **Отображаемое имя** для вашего экспорта и **Имя базы данных**.</span><span class="sxs-lookup"><span data-stu-id="c7772-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="c7772-146">Выберите, в какие сущности вы хотите экспортировать Azure Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="c7772-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="c7772-147">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c7772-147">Select **Save**.</span></span>

<span data-ttu-id="c7772-148">Сохранение экспорта не запускает экспорт сразу.</span><span class="sxs-lookup"><span data-stu-id="c7772-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="c7772-149">Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c7772-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c7772-150">Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c7772-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="c7772-151">Обновление экспорта</span><span class="sxs-lookup"><span data-stu-id="c7772-151">Update an export</span></span>

1. <span data-ttu-id="c7772-152">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="c7772-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c7772-153">Выберите **Изменить** для экспорта, который требуется обновить.</span><span class="sxs-lookup"><span data-stu-id="c7772-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="c7772-154">**Добавьте** или **Удалите** сущности из выборки.</span><span class="sxs-lookup"><span data-stu-id="c7772-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="c7772-155">Если сущности удаляются из выборки, они не удаляются из базы данных Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="c7772-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="c7772-156">Однако будущие обновления данных не будут обновлять удаленные сущности в этой базе данных.</span><span class="sxs-lookup"><span data-stu-id="c7772-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="c7772-157">**Изменение имени базы данных** создает новую базу данных Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="c7772-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="c7772-158">База данных с именем, которое было настроено ранее, не будет получать никаких обновлений при будущих обновлениях.</span><span class="sxs-lookup"><span data-stu-id="c7772-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
