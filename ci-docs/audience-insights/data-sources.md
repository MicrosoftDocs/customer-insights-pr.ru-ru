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
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887910"
---
# <a name="data-sources-overview"></a><span data-ttu-id="bd5ae-103">Обзор источников данных</span><span class="sxs-lookup"><span data-stu-id="bd5ae-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="bd5ae-104">Возможность аналитики аудитории в Dynamics 365 Customer Insights подключается к данным из широкого набора источников.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="bd5ae-105">Подключение к источнику данных часто называется процессом *приема данных*.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="bd5ae-106">После приема данных вы можете [объединить](data-unification.md) их и принять действия с ними.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="bd5ae-107">Добавить источник данных</span><span class="sxs-lookup"><span data-stu-id="bd5ae-107">Add a data source</span></span>

<span data-ttu-id="bd5ae-108">См. подробные статьи о том, как добавить источник данных, в зависимости от того, какой вариант вы выберете.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="bd5ae-109">Добавить источник данных можно тремя основными способами:</span><span class="sxs-lookup"><span data-stu-id="bd5ae-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="bd5ae-110">Через десятки соединителей Power Query</span><span class="sxs-lookup"><span data-stu-id="bd5ae-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="bd5ae-111">Из папки Common Data Model</span><span class="sxs-lookup"><span data-stu-id="bd5ae-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="bd5ae-112">Из вашего собственного озера Common Data Service</span><span class="sxs-lookup"><span data-stu-id="bd5ae-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="bd5ae-113">Добавление данных из локальных источников данных</span><span class="sxs-lookup"><span data-stu-id="bd5ae-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="bd5ae-114">Прием данных из локальных источников данных в аналитике аудитории поддерживается на основе потоков данных Power Platform.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="bd5ae-115">Потоки данных можно включить в Customer Insights, [указав URL-адрес среды Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) при настройке среды.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="bd5ae-116">Источники данных, которые создаются после привязки среды Dataverse к Customer Insights, будут использовать [потоки данных Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="bd5ae-117">Потоки данных поддерживают локальное подключение с использованием шлюзов данных.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-117">Dataflows support on-prem connectivity using the data gateways.</span></span> <span data-ttu-id="bd5ae-118">Удалите и воссоздайте источники данных, которые существовали до того, как среда Dataverse была связана с использованием локальных шлюзов данных.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-118">Remove and recreate data sources that existed before a Dataverse environment was associated to use the on-premises data gateways.</span></span>

<span data-ttu-id="bd5ae-119">Шлюзы данных из существующей среды Power BI или Power Apps будут видны, и вы сможете повторно использовать их в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="bd5ae-120">На странице источников данных показаны ссылки для перехода в среду Power Platform, в которой можно просматривать и настраивать локальные шлюзы данных.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="Снимок экрана страницы источников данных, на котором показаны ссылки, указывающие на среду Power Platform.":::

## <a name="review-ingested-data"></a><span data-ttu-id="bd5ae-122">Просмотр полученных данных</span><span class="sxs-lookup"><span data-stu-id="bd5ae-122">Review ingested data</span></span>

<span data-ttu-id="bd5ae-123">Вы увидите имя каждого принятого источника данных, его статус и время последнего обновления данных для этого источника.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-123">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="bd5ae-124">Вы можете отсортировать список источников данных по каждому столбцу.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-124">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bd5ae-125">![Добавлен источник данных](media/configure-data-datasource-added.png "Добавлен источник данных")</span><span class="sxs-lookup"><span data-stu-id="bd5ae-125">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="bd5ae-126">Состояние</span><span class="sxs-lookup"><span data-stu-id="bd5ae-126">Status</span></span>  |<span data-ttu-id="bd5ae-127">Описание:</span><span class="sxs-lookup"><span data-stu-id="bd5ae-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="bd5ae-128">Успешно выполнено</span><span class="sxs-lookup"><span data-stu-id="bd5ae-128">Successful</span></span>   |<span data-ttu-id="bd5ae-129">Источник данных был успешно загружен, если время указано в столбце **Обновлено**.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-129">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="bd5ae-130">Не начато</span><span class="sxs-lookup"><span data-stu-id="bd5ae-130">Not started</span></span>   |<span data-ttu-id="bd5ae-131">У источника данных еще нет загруженных данных или он все еще находится в режиме черновика.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-131">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="bd5ae-132">Обновление</span><span class="sxs-lookup"><span data-stu-id="bd5ae-132">Refreshing</span></span>    |<span data-ttu-id="bd5ae-133">Выполняется прием данных.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-133">Data ingestion is in progress.</span></span> <span data-ttu-id="bd5ae-134">Эту операцию можно отменить, выбрав **Остановить обновление** в столбце **Действия**.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-134">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="bd5ae-135">Остановка обновления источника данных вернет его в последнее состояние обновления.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-135">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="bd5ae-136">Не удалось отправить</span><span class="sxs-lookup"><span data-stu-id="bd5ae-136">Failed</span></span>     |<span data-ttu-id="bd5ae-137">При приеме данных возникли ошибки.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-137">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="bd5ae-138">Выберите значение в столбце **Состояние** источника данных, чтобы просмотреть более подробную информацию.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-138">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="bd5ae-139">В области **Сведения о ходе выполнения** разверните **Источники данных**.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-139">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="bd5ae-140">Выберите **Показать подробности** для просмотра дополнительных сведений о состоянии обновления, включая сведения об ошибках и обновления последующих процессов.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-140">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="bd5ae-141">Загрузка данных может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-141">Loading data can take some time.</span></span> <span data-ttu-id="bd5ae-142">После успешного обновления принятые данные можно проверить на странице **Сущности**.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-142">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="bd5ae-143">Дополнительные сведения см. в разделе [Сущности](entities.md).</span><span class="sxs-lookup"><span data-stu-id="bd5ae-143">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="bd5ae-144">Обновление источника данных</span><span class="sxs-lookup"><span data-stu-id="bd5ae-144">Refresh a data source</span></span>

<span data-ttu-id="bd5ae-145">Источники данных можно обновлять по автоматическому расписанию или обновлять вручную по запросу.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-145">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="bd5ae-146">Перейдите **Администрирование** > **Система** > [**Расписание**](system.md#schedule-tab) для настройки планового обновления всех ваших источников данных.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-146">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="bd5ae-147">Чтобы обновить источник данных по запросу, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="bd5ae-147">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="bd5ae-148">В аналитике аудитории перейдите **Данные** > **Источники данных**</span><span class="sxs-lookup"><span data-stu-id="bd5ae-148">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="bd5ae-149">Выделите вертикальное многоточие рядом с источником данных, которое хотите обновить, и выберите **Обновить** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-149">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="bd5ae-150">Источник данных теперь запускается для ручного обновления.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-150">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="bd5ae-151">Обновление источника данных обновит как схему сущности, так и данные для всех сущностей, указанных в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-151">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="bd5ae-152">Выберите **Прекратить обновлять**, если вы хотите отменить существующее обновление, и источник данных вернется к своему последнему состоянию обновления.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-152">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="bd5ae-153">Удаление источника данных</span><span class="sxs-lookup"><span data-stu-id="bd5ae-153">Delete a data source</span></span>

1. <span data-ttu-id="bd5ae-154">В аналитике аудитории перейдите **Данные** > **Источники данных**.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-154">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="bd5ae-155">Выберите вертикальное многоточие рядом с источник данных, который вы хотите удалить, и выберите **Удалить** из раскрывающегося меню.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-155">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="bd5ae-156">Подтвердите удаление.</span><span class="sxs-lookup"><span data-stu-id="bd5ae-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
