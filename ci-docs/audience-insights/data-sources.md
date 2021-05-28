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
ms.openlocfilehash: 3c0b4690e18285aa37eef481b3cfac951884ead6
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085546"
---
# <a name="data-sources-overview"></a><span data-ttu-id="51517-103">Обзор источников данных</span><span class="sxs-lookup"><span data-stu-id="51517-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="51517-104">Возможность аналитики аудитории в Dynamics 365 Customer Insights подключается к данным из широкого набора источников.</span><span class="sxs-lookup"><span data-stu-id="51517-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="51517-105">Подключение к источнику данных часто называется процессом *приема данных*.</span><span class="sxs-lookup"><span data-stu-id="51517-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="51517-106">После приема данных вы можете [объединить](data-unification.md) их и принять действия с ними.</span><span class="sxs-lookup"><span data-stu-id="51517-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="51517-107">Добавить источник данных</span><span class="sxs-lookup"><span data-stu-id="51517-107">Add a data source</span></span>

<span data-ttu-id="51517-108">См. подробные статьи о том, как добавить источник данных, в зависимости от того, какой вариант вы выберете.</span><span class="sxs-lookup"><span data-stu-id="51517-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="51517-109">Добавить источник данных можно тремя основными способами:</span><span class="sxs-lookup"><span data-stu-id="51517-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="51517-110">Через десятки соединителей Power Query</span><span class="sxs-lookup"><span data-stu-id="51517-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="51517-111">Из папки Common Data Model</span><span class="sxs-lookup"><span data-stu-id="51517-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="51517-112">Из вашего собственного озера Common Data Service</span><span class="sxs-lookup"><span data-stu-id="51517-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="51517-113">Добавление данных из локальных источников данных</span><span class="sxs-lookup"><span data-stu-id="51517-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="51517-114">Прием данных из локальных источников данных в аналитике аудитории поддерживается на основе потоков данных Power Platform.</span><span class="sxs-lookup"><span data-stu-id="51517-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="51517-115">Потоки данных можно включить в Customer Insights, [указав URL-адрес среды Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) при настройке среды.</span><span class="sxs-lookup"><span data-stu-id="51517-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="51517-116">Источники данных, которые создаются после привязки среды Dataverse к Customer Insights, будут использовать [потоки данных Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="51517-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="51517-117">Потоки данных поддерживают локальное подключение с использованием шлюза данных.</span><span class="sxs-lookup"><span data-stu-id="51517-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="51517-118">Удалите и воссоздайте источники данных, которые существовали до того, как среда Dataverse была связана с [использованием локальных шлюзов данных](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span><span class="sxs-lookup"><span data-stu-id="51517-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span></span>

<span data-ttu-id="51517-119">Шлюзы данных из существующей среды Power BI или Power Apps будут видны, и вы сможете повторно использовать их в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="51517-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="51517-120">На странице источников данных показаны ссылки для перехода в среду Power Platform, в которой можно просматривать и настраивать локальные шлюзы данных.</span><span class="sxs-lookup"><span data-stu-id="51517-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="51517-121">Просмотр полученных данных</span><span class="sxs-lookup"><span data-stu-id="51517-121">Review ingested data</span></span>

<span data-ttu-id="51517-122">Вы увидите имя каждого принятого источника данных, его статус и время последнего обновления данных для этого источника.</span><span class="sxs-lookup"><span data-stu-id="51517-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="51517-123">Вы можете отсортировать список источников данных по каждому столбцу.</span><span class="sxs-lookup"><span data-stu-id="51517-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="51517-124">![Добавлен источник данных](media/configure-data-datasource-added.png "Добавлен источник данных")</span><span class="sxs-lookup"><span data-stu-id="51517-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="51517-125">Состояние</span><span class="sxs-lookup"><span data-stu-id="51517-125">Status</span></span>  |<span data-ttu-id="51517-126">Описание:</span><span class="sxs-lookup"><span data-stu-id="51517-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="51517-127">Успешно выполнено</span><span class="sxs-lookup"><span data-stu-id="51517-127">Successful</span></span>   |<span data-ttu-id="51517-128">Источник данных был успешно загружен, если время указано в столбце **Обновлено**.</span><span class="sxs-lookup"><span data-stu-id="51517-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="51517-129">Не начато</span><span class="sxs-lookup"><span data-stu-id="51517-129">Not started</span></span>   |<span data-ttu-id="51517-130">У источника данных еще нет загруженных данных или он все еще находится в режиме черновика.</span><span class="sxs-lookup"><span data-stu-id="51517-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="51517-131">Обновление</span><span class="sxs-lookup"><span data-stu-id="51517-131">Refreshing</span></span>    |<span data-ttu-id="51517-132">Выполняется прием данных.</span><span class="sxs-lookup"><span data-stu-id="51517-132">Data ingestion is in progress.</span></span> <span data-ttu-id="51517-133">Эту операцию можно отменить, выбрав **Остановить обновление** в столбце **Действия**.</span><span class="sxs-lookup"><span data-stu-id="51517-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="51517-134">Остановка обновления источника данных вернет его в последнее состояние обновления.</span><span class="sxs-lookup"><span data-stu-id="51517-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="51517-135">Не удалось отправить</span><span class="sxs-lookup"><span data-stu-id="51517-135">Failed</span></span>     |<span data-ttu-id="51517-136">При приеме данных возникли ошибки.</span><span class="sxs-lookup"><span data-stu-id="51517-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="51517-137">Выберите значение в столбце **Состояние** источника данных, чтобы просмотреть более подробную информацию.</span><span class="sxs-lookup"><span data-stu-id="51517-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="51517-138">В области **Сведения о ходе выполнения** разверните **Источники данных**.</span><span class="sxs-lookup"><span data-stu-id="51517-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="51517-139">Выберите **Показать подробности** для просмотра дополнительных сведений о состоянии обновления, включая сведения об ошибках и обновления последующих процессов.</span><span class="sxs-lookup"><span data-stu-id="51517-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="51517-140">Загрузка данных может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="51517-140">Loading data can take some time.</span></span> <span data-ttu-id="51517-141">После успешного обновления принятые данные можно проверить на странице **Сущности**.</span><span class="sxs-lookup"><span data-stu-id="51517-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="51517-142">Дополнительные сведения см. в разделе [Сущности](entities.md).</span><span class="sxs-lookup"><span data-stu-id="51517-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="51517-143">Обновление источника данных</span><span class="sxs-lookup"><span data-stu-id="51517-143">Refresh a data source</span></span>

<span data-ttu-id="51517-144">Источники данных можно обновлять по автоматическому расписанию или обновлять вручную по запросу.</span><span class="sxs-lookup"><span data-stu-id="51517-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="51517-145">Перейдите **Администрирование** > **Система** > [**Расписание**](system.md#schedule-tab) для настройки планового обновления всех ваших источников данных.</span><span class="sxs-lookup"><span data-stu-id="51517-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="51517-146">Чтобы обновить источник данных по запросу, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="51517-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="51517-147">В аналитике аудитории перейдите **Данные** > **Источники данных**</span><span class="sxs-lookup"><span data-stu-id="51517-147">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="51517-148">Выделите вертикальное многоточие рядом с источником данных, которое хотите обновить, и выберите **Обновить** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="51517-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="51517-149">Источник данных теперь запускается для ручного обновления.</span><span class="sxs-lookup"><span data-stu-id="51517-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="51517-150">Обновление источника данных обновит как схему сущности, так и данные для всех сущностей, указанных в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="51517-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="51517-151">Выберите **Прекратить обновлять**, если вы хотите отменить существующее обновление, и источник данных вернется к своему последнему состоянию обновления.</span><span class="sxs-lookup"><span data-stu-id="51517-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="51517-152">Удаление источника данных</span><span class="sxs-lookup"><span data-stu-id="51517-152">Delete a data source</span></span>

1. <span data-ttu-id="51517-153">В аналитике аудитории перейдите **Данные** > **Источники данных**.</span><span class="sxs-lookup"><span data-stu-id="51517-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="51517-154">Выберите вертикальное многоточие рядом с источник данных, который вы хотите удалить, и выберите **Удалить** из раскрывающегося меню.</span><span class="sxs-lookup"><span data-stu-id="51517-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="51517-155">Подтвердите удаление.</span><span class="sxs-lookup"><span data-stu-id="51517-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
