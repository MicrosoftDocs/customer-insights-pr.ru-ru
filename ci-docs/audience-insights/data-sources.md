---
title: Использование источников данных для приема данных
description: Узнайте, как импортировать данные из различных источников.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643969"
---
# <a name="overview-about-data-sources"></a><span data-ttu-id="b02d6-103">Обзор источников данных</span><span class="sxs-lookup"><span data-stu-id="b02d6-103">Overview about data sources</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="b02d6-104">Возможность аналитики аудитории в Dynamics 365 Customer Insights подключается к данным из широкого набора источников.</span><span class="sxs-lookup"><span data-stu-id="b02d6-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="b02d6-105">Подключение к источнику данных часто называется процессом *приема данных*.</span><span class="sxs-lookup"><span data-stu-id="b02d6-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="b02d6-106">После приема данных вы можете [объединить](data-unification.md) их и принять действия с ними.</span><span class="sxs-lookup"><span data-stu-id="b02d6-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="b02d6-107">Добавить источник данных</span><span class="sxs-lookup"><span data-stu-id="b02d6-107">Add a data source</span></span>

<span data-ttu-id="b02d6-108">См. подробные статьи о том, как добавить источник данных, в зависимости от того, какой вариант вы выберете.</span><span class="sxs-lookup"><span data-stu-id="b02d6-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="b02d6-109">Добавить источник данных можно тремя основными способами:</span><span class="sxs-lookup"><span data-stu-id="b02d6-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="b02d6-110">Через десятки соединителей Power Query</span><span class="sxs-lookup"><span data-stu-id="b02d6-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="b02d6-111">Из папки Common Data Model</span><span class="sxs-lookup"><span data-stu-id="b02d6-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="b02d6-112">Из вашего собственного озера Common Data Service</span><span class="sxs-lookup"><span data-stu-id="b02d6-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="b02d6-113">Вы пока не можете добавлять данные из локальных источников данных.</span><span class="sxs-lookup"><span data-stu-id="b02d6-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="b02d6-114">Просмотр полученных данных</span><span class="sxs-lookup"><span data-stu-id="b02d6-114">Review ingested data</span></span>

<span data-ttu-id="b02d6-115">Вы увидите имя каждого принятого источника данных, его статус и время последнего обновления данных для этого источника.</span><span class="sxs-lookup"><span data-stu-id="b02d6-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="b02d6-116">Вы можете отсортировать список источников данных по каждому столбцу.</span><span class="sxs-lookup"><span data-stu-id="b02d6-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b02d6-117">![Добавлен источник данных](media/configure-data-datasource-added.png "Добавлен источник данных")</span><span class="sxs-lookup"><span data-stu-id="b02d6-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="b02d6-118">Состояние</span><span class="sxs-lookup"><span data-stu-id="b02d6-118">Status</span></span>  |<span data-ttu-id="b02d6-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="b02d6-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="b02d6-120">Успешно выполнено</span><span class="sxs-lookup"><span data-stu-id="b02d6-120">Successful</span></span>   |<span data-ttu-id="b02d6-121">Источник данных был успешно загружен, если время указано в столбце **Обновлено**.</span><span class="sxs-lookup"><span data-stu-id="b02d6-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="b02d6-122">Не начато</span><span class="sxs-lookup"><span data-stu-id="b02d6-122">Not started</span></span>   |<span data-ttu-id="b02d6-123">У источника данных еще нет загруженных данных или он все еще находится в режиме черновика.</span><span class="sxs-lookup"><span data-stu-id="b02d6-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="b02d6-124">Обновление</span><span class="sxs-lookup"><span data-stu-id="b02d6-124">Refreshing</span></span>    |<span data-ttu-id="b02d6-125">Выполняется прием данных.</span><span class="sxs-lookup"><span data-stu-id="b02d6-125">Data ingestion is in progress.</span></span> <span data-ttu-id="b02d6-126">Эту операцию можно отменить, выбрав **Остановить обновление** в столбце **Действия**.</span><span class="sxs-lookup"><span data-stu-id="b02d6-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="b02d6-127">Остановка обновления источника данных вернет его в последнее состояние обновления.</span><span class="sxs-lookup"><span data-stu-id="b02d6-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="b02d6-128">Не пройдено</span><span class="sxs-lookup"><span data-stu-id="b02d6-128">Failed</span></span>     |<span data-ttu-id="b02d6-129">При приеме данных возникли ошибки.</span><span class="sxs-lookup"><span data-stu-id="b02d6-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="b02d6-130">Выберите **Обновить статус** для просмотра дополнительных сведений о состоянии обновления, включая сведения об ошибках и обновления последующих процессов.</span><span class="sxs-lookup"><span data-stu-id="b02d6-130">Select **Refresh status** to review more details on the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="b02d6-131">Загрузка данных может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="b02d6-131">Loading data can take some time.</span></span> <span data-ttu-id="b02d6-132">После успешного обновления принятые данные можно проверить на странице **Сущности**.</span><span class="sxs-lookup"><span data-stu-id="b02d6-132">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="b02d6-133">Дополнительные сведения см. в разделе [Сущности](entities.md).</span><span class="sxs-lookup"><span data-stu-id="b02d6-133">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="b02d6-134">Обновление источника данных</span><span class="sxs-lookup"><span data-stu-id="b02d6-134">Refresh a data source</span></span>

<span data-ttu-id="b02d6-135">Источники данных можно обновлять по автоматическому расписанию или обновлять вручную по запросу.</span><span class="sxs-lookup"><span data-stu-id="b02d6-135">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="b02d6-136">Перейдите **Администрирование** > **Система** > [**Расписание**](system.md#schedule-tab) для настройки планового обновления всех ваших источников данных.</span><span class="sxs-lookup"><span data-stu-id="b02d6-136">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="b02d6-137">Чтобы обновить источник данных по запросу, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="b02d6-137">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="b02d6-138">В аналитике аудитории перейдите **Данные** > **Источники данных**</span><span class="sxs-lookup"><span data-stu-id="b02d6-138">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="b02d6-139">Выделите вертикальное многоточие рядом с источником данных, которое хотите обновить, и выберите **Обновить** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="b02d6-139">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="b02d6-140">Источник данных теперь запускается для ручного обновления.</span><span class="sxs-lookup"><span data-stu-id="b02d6-140">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="b02d6-141">Обновление источника данных обновит как схему сущностей, так и данные для всех сущностей, указанных в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="b02d6-141">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="b02d6-142">Выберите **Прекратить обновлять**, если вы хотите отменить существующее обновление, и источник данных вернется к своему последнему состоянию обновления.</span><span class="sxs-lookup"><span data-stu-id="b02d6-142">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="b02d6-143">Удаление источника данных</span><span class="sxs-lookup"><span data-stu-id="b02d6-143">Delete a data source</span></span>

1. <span data-ttu-id="b02d6-144">В аналитике аудитории перейдите **Данные** > **Источники данных**.</span><span class="sxs-lookup"><span data-stu-id="b02d6-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="b02d6-145">Выберите вертикальное многоточие рядом с источник данных, который вы хотите удалить, и выберите **Удалить** из раскрывающегося меню.</span><span class="sxs-lookup"><span data-stu-id="b02d6-145">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="b02d6-146">Подтвердите удаление.</span><span class="sxs-lookup"><span data-stu-id="b02d6-146">Confirm your deletion.</span></span>
