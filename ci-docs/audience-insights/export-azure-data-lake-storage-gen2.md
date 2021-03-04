---
title: Экспорт данных Customer Insights в Azure Data Lake Storage Gen2
description: Узнайте, как настроить подключение к Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477195"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="ce906-103">Соединитель для Azure Data Lake Storage Gen2 (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="ce906-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="ce906-104">Сохраняйте данные Customer Insights в Azure Data Lake Storage Gen2 или переносите их в другие приложения.</span><span class="sxs-lookup"><span data-stu-id="ce906-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="ce906-105">Настройка соединителя для Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="ce906-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="ce906-106">В аналитике аудитории перейдите **Администрирование** > **Экспорт пунктов назначения**.</span><span class="sxs-lookup"><span data-stu-id="ce906-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ce906-107">В **Azure Data Lake Storage Gen2** выберите **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="ce906-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="ce906-108">Дайте вашему месту назначения узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="ce906-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="ce906-109">Введите **Имя учетной записи**, **Ключ учетной записи** и **Контейнер** для своего Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="ce906-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="ce906-110">Чтобы узнать, как создать учетную запись хранения для использования с Azure Data Lake Storage Gen2, см. [Создать учетную запись хранения](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="ce906-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="ce906-111">Чтобы узнать больше о том, как найти имя учетной записи хранения Azure Data Lake Gen2 и ключ учетной записи, см. [Управление параметрами учетной записи хранения на портале Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="ce906-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="ce906-112">Выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ce906-112">Select **Next**.</span></span>

1. <span data-ttu-id="ce906-113">Установите флажок рядом с каждой сущностью, которую вы хотите экспортировать в этот пункт назначения.</span><span class="sxs-lookup"><span data-stu-id="ce906-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="ce906-114">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ce906-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ce906-115">Экспорт данных</span><span class="sxs-lookup"><span data-stu-id="ce906-115">Export the data</span></span>

<span data-ttu-id="ce906-116">Вы можете [экспортировать данных по требованию](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ce906-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="ce906-117">Экспорт также будет выполняться с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ce906-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
