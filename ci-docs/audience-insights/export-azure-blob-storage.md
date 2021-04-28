---
title: Экспорт данных Customer Insights в хранилище BLOB-объектов Azure
description: Узнайте, как настроить подключение и экспорт в хранилище BLOB-объектов.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 294feff2f77c3756fbadb36c90aab430454f5967
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760251"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="7bd60-103">Экспорт списка сегментов и других данных в хранилище BLOB-объектов Azure (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="7bd60-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="7bd60-104">Сохраняйте данные Customer Insights в хранилище BLOB-объектов или переносите их в другие приложения.</span><span class="sxs-lookup"><span data-stu-id="7bd60-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="7bd60-105">Настройка подключения к хранилищу BLOB-объектов</span><span class="sxs-lookup"><span data-stu-id="7bd60-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="7bd60-106">Перейти в раздел **Администрирование** > **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="7bd60-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="7bd60-107">Выберите **Добавить подключение** и выберите **Хранилище BLOB-объектов Azure** для настройки подключения.</span><span class="sxs-lookup"><span data-stu-id="7bd60-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="7bd60-108">Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="7bd60-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="7bd60-109">Имя и тип подключения описывают это подключение.</span><span class="sxs-lookup"><span data-stu-id="7bd60-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="7bd60-110">Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.</span><span class="sxs-lookup"><span data-stu-id="7bd60-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="7bd60-111">Укажите, кто может использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="7bd60-111">Choose who can use this connection.</span></span> <span data-ttu-id="7bd60-112">Если вы не предпримете никаких действий, по умолчанию это будут администраторы.</span><span class="sxs-lookup"><span data-stu-id="7bd60-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="7bd60-113">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="7bd60-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="7bd60-114">Введите **Имя учетной записи**, **Ключ учетной записи** и **Контейнер** для вашей учетной записи хранилища BLOB-объектов.</span><span class="sxs-lookup"><span data-stu-id="7bd60-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="7bd60-115">Чтобы узнать больше о том, как найти имя учетной записи хранилища BLOB-объектов и ключ учетной записи, см. раздел [Управление параметрами учетной записи хранения на портале Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="7bd60-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="7bd60-116">Чтобы узнать, как создать контейнер, см. раздел [Создание контейнера](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="7bd60-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="7bd60-117">Выберите **Сохранить**, чтобы завершить подключение.</span><span class="sxs-lookup"><span data-stu-id="7bd60-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="7bd60-118">Настройка экспорта</span><span class="sxs-lookup"><span data-stu-id="7bd60-118">Configure an export</span></span>

<span data-ttu-id="7bd60-119">Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа.</span><span class="sxs-lookup"><span data-stu-id="7bd60-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="7bd60-120">Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="7bd60-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="7bd60-121">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="7bd60-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7bd60-122">Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.</span><span class="sxs-lookup"><span data-stu-id="7bd60-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="7bd60-123">В поле **Подключение для экспорта** выберите подключение из раздела "Хранилище BLOB-объектов Azure".</span><span class="sxs-lookup"><span data-stu-id="7bd60-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="7bd60-124">Если вы не видите название этого раздела, вам не доступны подключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="7bd60-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="7bd60-125">Установите флажок рядом с каждой сущностью, которую вы хотите экспортировать в этот пункт назначения.</span><span class="sxs-lookup"><span data-stu-id="7bd60-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="7bd60-126">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7bd60-126">Select **Save**.</span></span>

<span data-ttu-id="7bd60-127">Сохранение экспорта не запускает экспорт сразу.</span><span class="sxs-lookup"><span data-stu-id="7bd60-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="7bd60-128">Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7bd60-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="7bd60-129">Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="7bd60-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="7bd60-130">Экспортированные данные хранятся в настроенном вами контейнере хранилища BLOB-объектов.</span><span class="sxs-lookup"><span data-stu-id="7bd60-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="7bd60-131">Следующие пути к папкам автоматически создаются в вашем контейнере:</span><span class="sxs-lookup"><span data-stu-id="7bd60-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="7bd60-132">Для исходных сущностей и сущностей, созданных системой: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="7bd60-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="7bd60-133">Пример: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="7bd60-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="7bd60-134">Файл model.json для экспортируемых сущностей будет на уровне %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="7bd60-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="7bd60-135">Пример: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="7bd60-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
