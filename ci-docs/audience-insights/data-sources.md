---
title: Использование источников данных для приема данных
description: Узнайте, как импортировать данные из различных источников.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54dd7b629d4b4e7f640b932b0f9246e0602f46bd
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304712"
---
# <a name="data-sources-overview"></a><span data-ttu-id="e6517-103">Обзор источников данных</span><span class="sxs-lookup"><span data-stu-id="e6517-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="e6517-104">Возможность аналитики аудитории в Dynamics 365 Customer Insights подключается к данным из широкого набора источников.</span><span class="sxs-lookup"><span data-stu-id="e6517-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="e6517-105">Подключение к источнику данных часто называется процессом *приема данных*.</span><span class="sxs-lookup"><span data-stu-id="e6517-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="e6517-106">После приема данных вы можете [объединить](data-unification.md) их и принять действия с ними.</span><span class="sxs-lookup"><span data-stu-id="e6517-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="e6517-107">Добавить источник данных</span><span class="sxs-lookup"><span data-stu-id="e6517-107">Add a data source</span></span>

<span data-ttu-id="e6517-108">См. подробные статьи о том, как добавить источник данных, в зависимости от того, какой вариант вы выберете.</span><span class="sxs-lookup"><span data-stu-id="e6517-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="e6517-109">Добавить источник данных можно тремя основными способами:</span><span class="sxs-lookup"><span data-stu-id="e6517-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="e6517-110">Через десятки соединителей Power Query</span><span class="sxs-lookup"><span data-stu-id="e6517-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="e6517-111">Из папки Common Data Model</span><span class="sxs-lookup"><span data-stu-id="e6517-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="e6517-112">Из вашего собственного озера Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="e6517-112">From your own Microsoft Dataverse lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="e6517-113">Добавление данных из локальных источников данных</span><span class="sxs-lookup"><span data-stu-id="e6517-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="e6517-114">Прием данных из локальных источников данных в аналитике аудитории поддерживается на основе потоков данных Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="e6517-114">Ingesting data from on-premises data sources in audience insights is supported based on Microsoft Power Platform dataflows.</span></span> <span data-ttu-id="e6517-115">Потоки данных можно включить в Customer Insights, [указав URL-адрес среды Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) при настройке среды.</span><span class="sxs-lookup"><span data-stu-id="e6517-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="e6517-116">Источники данных, которые создаются после привязки среды Dataverse к Customer Insights, будут использовать [потоки данных Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e6517-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="e6517-117">Потоки данных поддерживают локальное подключение с использованием шлюза данных.</span><span class="sxs-lookup"><span data-stu-id="e6517-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="e6517-118">Удалите и воссоздайте источники данных, которые существовали до того, как среда Dataverse была связана с [использованием локальных шлюзов данных](/data-integration/gateway/service-gateway-app.md).</span><span class="sxs-lookup"><span data-stu-id="e6517-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/data-integration/gateway/service-gateway-app.md).</span></span>

<span data-ttu-id="e6517-119">Шлюзы данных из существующей среды Power BI или Power Apps будут видны, и вы сможете повторно использовать их в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e6517-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="e6517-120">На странице источников данных показаны ссылки для перехода к среде Microsoft Power Platform, в которой можно просматривать и настраивать локальные шлюзы данных.</span><span class="sxs-lookup"><span data-stu-id="e6517-120">The data sources page shows links to go to the Microsoft Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="e6517-121">Просмотр полученных данных</span><span class="sxs-lookup"><span data-stu-id="e6517-121">Review ingested data</span></span>

<span data-ttu-id="e6517-122">Вы увидите имя каждого принятого источника данных, его статус и время последнего обновления данных для этого источника.</span><span class="sxs-lookup"><span data-stu-id="e6517-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="e6517-123">Вы можете отсортировать список источников данных по каждому столбцу.</span><span class="sxs-lookup"><span data-stu-id="e6517-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e6517-124">![Добавлен источник данных](media/configure-data-datasource-added.png "Добавлен источник данных")</span><span class="sxs-lookup"><span data-stu-id="e6517-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="e6517-125">Состояние</span><span class="sxs-lookup"><span data-stu-id="e6517-125">Status</span></span>  |<span data-ttu-id="e6517-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="e6517-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="e6517-127">Успешно выполнено</span><span class="sxs-lookup"><span data-stu-id="e6517-127">Successful</span></span>   |<span data-ttu-id="e6517-128">Источник данных был успешно загружен, если время указано в столбце **Обновлено**.</span><span class="sxs-lookup"><span data-stu-id="e6517-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="e6517-129">Не начато</span><span class="sxs-lookup"><span data-stu-id="e6517-129">Not started</span></span>   |<span data-ttu-id="e6517-130">У источника данных еще нет загруженных данных или он все еще находится в режиме черновика.</span><span class="sxs-lookup"><span data-stu-id="e6517-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="e6517-131">Обновление</span><span class="sxs-lookup"><span data-stu-id="e6517-131">Refreshing</span></span>    |<span data-ttu-id="e6517-132">Выполняется прием данных.</span><span class="sxs-lookup"><span data-stu-id="e6517-132">Data ingestion is in progress.</span></span> <span data-ttu-id="e6517-133">Эту операцию можно отменить, выбрав **Остановить обновление** в столбце **Действия**.</span><span class="sxs-lookup"><span data-stu-id="e6517-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="e6517-134">Остановка обновления источника данных вернет его в последнее состояние обновления.</span><span class="sxs-lookup"><span data-stu-id="e6517-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="e6517-135">Не удалось отправить</span><span class="sxs-lookup"><span data-stu-id="e6517-135">Failed</span></span>     |<span data-ttu-id="e6517-136">При приеме данных возникли ошибки.</span><span class="sxs-lookup"><span data-stu-id="e6517-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="e6517-137">Выберите значение в столбце **Состояние** источника данных, чтобы просмотреть более подробную информацию.</span><span class="sxs-lookup"><span data-stu-id="e6517-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="e6517-138">В области **Сведения о ходе выполнения** разверните **Источники данных**.</span><span class="sxs-lookup"><span data-stu-id="e6517-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="e6517-139">Выберите **Показать подробности** для просмотра дополнительных сведений о состоянии обновления, включая сведения об ошибках и обновления последующих процессов.</span><span class="sxs-lookup"><span data-stu-id="e6517-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="e6517-140">Загрузка данных может занять время.</span><span class="sxs-lookup"><span data-stu-id="e6517-140">Loading data can take time.</span></span> <span data-ttu-id="e6517-141">После успешного обновления принятые данные можно проверить на странице **Сущности**.</span><span class="sxs-lookup"><span data-stu-id="e6517-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="e6517-142">Дополнительные сведения см. в разделе [Сущности](entities.md).</span><span class="sxs-lookup"><span data-stu-id="e6517-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="e6517-143">Обновление источника данных</span><span class="sxs-lookup"><span data-stu-id="e6517-143">Refresh a data source</span></span>

<span data-ttu-id="e6517-144">Источники данных можно обновлять по автоматическому расписанию или обновлять вручную по запросу.</span><span class="sxs-lookup"><span data-stu-id="e6517-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="e6517-145">Перейдите **Администрирование** > **Система** > [**Расписание**](system.md#schedule-tab) для настройки планового обновления всех ваших источников данных.</span><span class="sxs-lookup"><span data-stu-id="e6517-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="e6517-146">Чтобы обновить источник данных по запросу, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e6517-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="e6517-147">В аналитике аудитории перейдите **Данные** > **Источники данных**.</span><span class="sxs-lookup"><span data-stu-id="e6517-147">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="e6517-148">Выберите вертикальное многоточие рядом с источником данных, который вы хотите обновить, и выберите **Обновить** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="e6517-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the dropdown list.</span></span>

3. <span data-ttu-id="e6517-149">Источник данных теперь запускается для ручного обновления.</span><span class="sxs-lookup"><span data-stu-id="e6517-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="e6517-150">Обновление источника данных обновит как схему сущности, так и данные для всех сущностей, указанных в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="e6517-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="e6517-151">Выберите **Прекратить обновлять**, если вы хотите отменить существующее обновление, и источник данных вернется к своему последнему состоянию обновления.</span><span class="sxs-lookup"><span data-stu-id="e6517-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="e6517-152">Удаление источника данных</span><span class="sxs-lookup"><span data-stu-id="e6517-152">Delete a data source</span></span>

1. <span data-ttu-id="e6517-153">В аналитике аудитории перейдите **Данные** > **Источники данных**.</span><span class="sxs-lookup"><span data-stu-id="e6517-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="e6517-154">Выберите вертикальное многоточие рядом с источником данных, который вы хотите удалить, и выберите **Удалить** из раскрывающегося меню.</span><span class="sxs-lookup"><span data-stu-id="e6517-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the dropdown menu.</span></span>

3. <span data-ttu-id="e6517-155">Подтвердите удаление.</span><span class="sxs-lookup"><span data-stu-id="e6517-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
