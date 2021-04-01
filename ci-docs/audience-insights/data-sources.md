---
title: Использование источников данных для приема данных
description: Узнайте, как импортировать данные из различных источников.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 780dc61a82d6ed9856a37dc8f164fa946d982bbe
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595963"
---
# <a name="data-sources-overview"></a><span data-ttu-id="4a816-103">Обзор источников данных</span><span class="sxs-lookup"><span data-stu-id="4a816-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="4a816-104">Возможность аналитики аудитории в Dynamics 365 Customer Insights подключается к данным из широкого набора источников.</span><span class="sxs-lookup"><span data-stu-id="4a816-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="4a816-105">Подключение к источнику данных часто называется процессом *приема данных*.</span><span class="sxs-lookup"><span data-stu-id="4a816-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="4a816-106">После приема данных вы можете [объединить](data-unification.md) их и принять действия с ними.</span><span class="sxs-lookup"><span data-stu-id="4a816-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="4a816-107">Добавить источник данных</span><span class="sxs-lookup"><span data-stu-id="4a816-107">Add a data source</span></span>

<span data-ttu-id="4a816-108">См. подробные статьи о том, как добавить источник данных, в зависимости от того, какой вариант вы выберете.</span><span class="sxs-lookup"><span data-stu-id="4a816-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="4a816-109">Добавить источник данных можно тремя основными способами:</span><span class="sxs-lookup"><span data-stu-id="4a816-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="4a816-110">Через десятки соединителей Power Query</span><span class="sxs-lookup"><span data-stu-id="4a816-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="4a816-111">Из папки Common Data Model</span><span class="sxs-lookup"><span data-stu-id="4a816-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="4a816-112">Из вашего собственного озера Common Data Service</span><span class="sxs-lookup"><span data-stu-id="4a816-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="4a816-113">Вы пока не можете добавлять данные из локальных источников данных.</span><span class="sxs-lookup"><span data-stu-id="4a816-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="4a816-114">Просмотр полученных данных</span><span class="sxs-lookup"><span data-stu-id="4a816-114">Review ingested data</span></span>

<span data-ttu-id="4a816-115">Вы увидите имя каждого принятого источника данных, его статус и время последнего обновления данных для этого источника.</span><span class="sxs-lookup"><span data-stu-id="4a816-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="4a816-116">Вы можете отсортировать список источников данных по каждому столбцу.</span><span class="sxs-lookup"><span data-stu-id="4a816-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4a816-117">![Добавлен источник данных](media/configure-data-datasource-added.png "Добавлен источник данных")</span><span class="sxs-lookup"><span data-stu-id="4a816-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="4a816-118">Состояние</span><span class="sxs-lookup"><span data-stu-id="4a816-118">Status</span></span>  |<span data-ttu-id="4a816-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="4a816-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="4a816-120">Успешно выполнено</span><span class="sxs-lookup"><span data-stu-id="4a816-120">Successful</span></span>   |<span data-ttu-id="4a816-121">Источник данных был успешно загружен, если время указано в столбце **Обновлено**.</span><span class="sxs-lookup"><span data-stu-id="4a816-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="4a816-122">Не начато</span><span class="sxs-lookup"><span data-stu-id="4a816-122">Not started</span></span>   |<span data-ttu-id="4a816-123">У источника данных еще нет загруженных данных или он все еще находится в режиме черновика.</span><span class="sxs-lookup"><span data-stu-id="4a816-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="4a816-124">Обновление</span><span class="sxs-lookup"><span data-stu-id="4a816-124">Refreshing</span></span>    |<span data-ttu-id="4a816-125">Выполняется прием данных.</span><span class="sxs-lookup"><span data-stu-id="4a816-125">Data ingestion is in progress.</span></span> <span data-ttu-id="4a816-126">Эту операцию можно отменить, выбрав **Остановить обновление** в столбце **Действия**.</span><span class="sxs-lookup"><span data-stu-id="4a816-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="4a816-127">Остановка обновления источника данных вернет его в последнее состояние обновления.</span><span class="sxs-lookup"><span data-stu-id="4a816-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="4a816-128">Не удалось отправить</span><span class="sxs-lookup"><span data-stu-id="4a816-128">Failed</span></span>     |<span data-ttu-id="4a816-129">При приеме данных возникли ошибки.</span><span class="sxs-lookup"><span data-stu-id="4a816-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="4a816-130">Выберите значение в столбце **Состояние** источника данных, чтобы просмотреть более подробную информацию.</span><span class="sxs-lookup"><span data-stu-id="4a816-130">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="4a816-131">В области **Сведения о ходе выполнения** разверните **Источники данных**.</span><span class="sxs-lookup"><span data-stu-id="4a816-131">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="4a816-132">Выберите **Показать подробности** для просмотра дополнительных сведений о состоянии обновления, включая сведения об ошибках и обновления последующих процессов.</span><span class="sxs-lookup"><span data-stu-id="4a816-132">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="4a816-133">Загрузка данных может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="4a816-133">Loading data can take some time.</span></span> <span data-ttu-id="4a816-134">После успешного обновления принятые данные можно проверить на странице **Сущности**.</span><span class="sxs-lookup"><span data-stu-id="4a816-134">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="4a816-135">Дополнительные сведения см. в разделе [Сущности](entities.md).</span><span class="sxs-lookup"><span data-stu-id="4a816-135">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="4a816-136">Обновление источника данных</span><span class="sxs-lookup"><span data-stu-id="4a816-136">Refresh a data source</span></span>

<span data-ttu-id="4a816-137">Источники данных можно обновлять по автоматическому расписанию или обновлять вручную по запросу.</span><span class="sxs-lookup"><span data-stu-id="4a816-137">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="4a816-138">Перейдите **Администрирование** > **Система** > [**Расписание**](system.md#schedule-tab) для настройки планового обновления всех ваших источников данных.</span><span class="sxs-lookup"><span data-stu-id="4a816-138">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="4a816-139">Чтобы обновить источник данных по запросу, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4a816-139">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="4a816-140">В аналитике аудитории перейдите **Данные** > **Источники данных**</span><span class="sxs-lookup"><span data-stu-id="4a816-140">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="4a816-141">Выделите вертикальное многоточие рядом с источником данных, которое хотите обновить, и выберите **Обновить** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="4a816-141">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="4a816-142">Источник данных теперь запускается для ручного обновления.</span><span class="sxs-lookup"><span data-stu-id="4a816-142">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="4a816-143">Обновление источника данных обновит как схему сущностей, так и данные для всех сущностей, указанных в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="4a816-143">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="4a816-144">Выберите **Прекратить обновлять**, если вы хотите отменить существующее обновление, и источник данных вернется к своему последнему состоянию обновления.</span><span class="sxs-lookup"><span data-stu-id="4a816-144">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="4a816-145">Удаление источника данных</span><span class="sxs-lookup"><span data-stu-id="4a816-145">Delete a data source</span></span>

1. <span data-ttu-id="4a816-146">В аналитике аудитории перейдите **Данные** > **Источники данных**.</span><span class="sxs-lookup"><span data-stu-id="4a816-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="4a816-147">Выберите вертикальное многоточие рядом с источник данных, который вы хотите удалить, и выберите **Удалить** из раскрывающегося меню.</span><span class="sxs-lookup"><span data-stu-id="4a816-147">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="4a816-148">Подтвердите удаление.</span><span class="sxs-lookup"><span data-stu-id="4a816-148">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]