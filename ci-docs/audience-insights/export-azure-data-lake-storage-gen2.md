---
title: Экспорт данных Customer Insights в Azure Data Lake Storage Gen2
description: Узнайте, как настроить подключение к Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760067"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="1f3eb-103">Настройка подключения к Azure Data Lake Storage 2-го поколения (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="1f3eb-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="1f3eb-104">Перейти в раздел **Администрирование** > **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="1f3eb-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1f3eb-105">Выберите **Добавить подключение** и выберите **Azure Data Lake 2-го поколения** для настройки подключения.</span><span class="sxs-lookup"><span data-stu-id="1f3eb-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="1f3eb-106">Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="1f3eb-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1f3eb-107">Имя и тип подключения описывают это подключение.</span><span class="sxs-lookup"><span data-stu-id="1f3eb-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1f3eb-108">Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.</span><span class="sxs-lookup"><span data-stu-id="1f3eb-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1f3eb-109">Укажите, кто может использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="1f3eb-109">Choose who can use this connection.</span></span> <span data-ttu-id="1f3eb-110">Если вы не предпримете никаких действий, по умолчанию это будут администраторы.</span><span class="sxs-lookup"><span data-stu-id="1f3eb-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1f3eb-111">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1f3eb-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1f3eb-112">Введите **Имя учетной записи**, **Ключ учетной записи** и **Контейнер** для своего Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="1f3eb-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="1f3eb-113">Чтобы узнать, как создать учетную запись хранения для использования с Azure Data Lake Storage Gen2, см. [Создать учетную запись хранения](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="1f3eb-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="1f3eb-114">Чтобы узнать больше о том, как найти имя учетной записи хранения Azure Data Lake 2-го поколения и ключ учетной записи, см. раздел [Управление параметрами учетной записи хранения на портале Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="1f3eb-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="1f3eb-115">Выберите **Сохранить**, чтобы завершить подключение.</span><span class="sxs-lookup"><span data-stu-id="1f3eb-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="1f3eb-116">Настройка экспорта</span><span class="sxs-lookup"><span data-stu-id="1f3eb-116">Configure an export</span></span>

<span data-ttu-id="1f3eb-117">Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа.</span><span class="sxs-lookup"><span data-stu-id="1f3eb-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1f3eb-118">Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1f3eb-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1f3eb-119">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="1f3eb-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1f3eb-120">Чтобы создать новый экспорт, выберите **Добавить экспорт**.</span><span class="sxs-lookup"><span data-stu-id="1f3eb-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="1f3eb-121">В поле **Подключение для экспорта** выберите подключение из раздела **Azure Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="1f3eb-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="1f3eb-122">Если вы не видите название этого раздела, вам не доступны подключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="1f3eb-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1f3eb-123">Установите флажок рядом с каждой сущностью, которую вы хотите экспортировать в этот пункт назначения.</span><span class="sxs-lookup"><span data-stu-id="1f3eb-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="1f3eb-124">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1f3eb-124">Select **Save**.</span></span>

<span data-ttu-id="1f3eb-125">Сохранение экспорта не запускает экспорт сразу.</span><span class="sxs-lookup"><span data-stu-id="1f3eb-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1f3eb-126">Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1f3eb-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1f3eb-127">Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1f3eb-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="1f3eb-128">Экспортированные данные хранятся в настроенном вами контейнере хранилища Azure Data Lake 2-го поколения.</span><span class="sxs-lookup"><span data-stu-id="1f3eb-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
