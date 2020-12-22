---
title: Пошаговое обновление для источников данных на основе Power Query
description: Обновите новые и обновленные данные для больших источников данных на основе Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b7e834f5f2fd1328563139675d7f850008348734
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406754"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="a9a77-103">Инкрементное обновление для источников данных на основе Power Query</span><span class="sxs-lookup"><span data-stu-id="a9a77-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="a9a77-104">Инкрементное обновление для источников данных дает следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="a9a77-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="a9a77-105">**Быстрее обновляется** — только данные, которые изменились, обновляются.</span><span class="sxs-lookup"><span data-stu-id="a9a77-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="a9a77-106">Например, вы можете обновить только последние пять дней исторического набора данных.</span><span class="sxs-lookup"><span data-stu-id="a9a77-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="a9a77-107">**Повышенная надежность** — при меньших обновлениях вам не нужно поддерживать соединения с ненадежными исходными системами слишком долго, что снижает риск проблем с подключением.</span><span class="sxs-lookup"><span data-stu-id="a9a77-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="a9a77-108">**Снижение потребления ресурсов** — обновление только подмножества ваших общих данных приводит к более эффективному использованию вычислительных ресурсов и уменьшает воздействие на окружающую среду.</span><span class="sxs-lookup"><span data-stu-id="a9a77-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="a9a77-109">Настройка инкрементного обновления</span><span class="sxs-lookup"><span data-stu-id="a9a77-109">Configure incremental refresh</span></span>

<span data-ttu-id="a9a77-110">Аналитика аудитории позволяет выполнять пошаговое обновление для источников данных, импортированных через Power Query, которые поддерживают пошаговый прием.</span><span class="sxs-lookup"><span data-stu-id="a9a77-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="a9a77-111">Например, базы данных SQL Azure с полями даты и времени, которые указывают время последнего обновления записей данных.</span><span class="sxs-lookup"><span data-stu-id="a9a77-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="a9a77-112">[Создание нового источника данных на основе Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="a9a77-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="a9a77-113">Укажите имя источника данных.</span><span class="sxs-lookup"><span data-stu-id="a9a77-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="a9a77-114">Выберите источник данных, который поддерживает инкрементное обновление, например базу данных SQL Azure.</span><span class="sxs-lookup"><span data-stu-id="a9a77-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="a9a77-115">Выберите сущности или таблицы для приема.</span><span class="sxs-lookup"><span data-stu-id="a9a77-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="a9a77-116">Выполните шаги преобразования и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a9a77-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="a9a77-117">В диалоговом окне **Настройка инкрементного обновления** выберите **Настроить**, чтобы открыть **Настройки инкрементного обновления**.</span><span class="sxs-lookup"><span data-stu-id="a9a77-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="a9a77-118">Если вы выберете **Пропустить**, источник данных обновит весь набор данных.</span><span class="sxs-lookup"><span data-stu-id="a9a77-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="a9a77-119">Вы также можете применить инкрементное обновление позже, отредактировав существующий источник данных.</span><span class="sxs-lookup"><span data-stu-id="a9a77-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="a9a77-120">В разделе **Настройки инкрементного обновления** вы настроите инкрементное обновление для всех сущностей, выбранных вами при создании источника данных.</span><span class="sxs-lookup"><span data-stu-id="a9a77-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a9a77-121">![Настройка сущностей в источнике данных для инкрементного обновления](media/incremental-refresh-settings.png "Настройка сущностей в источнике данных для инкрементного обновления")</span><span class="sxs-lookup"><span data-stu-id="a9a77-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="a9a77-122">Выберите сущность и предоставьте следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="a9a77-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="a9a77-123">**Определить первичный ключ**: выберите первичный ключ для сущности или таблицы.</span><span class="sxs-lookup"><span data-stu-id="a9a77-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="a9a77-124">**Определите поле "последнее обновление"**: в этом поле отображаются только атрибуты типа дата или время.</span><span class="sxs-lookup"><span data-stu-id="a9a77-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="a9a77-125">Выберите атрибут, который указывает, когда записи были в последний раз обновлены.</span><span class="sxs-lookup"><span data-stu-id="a9a77-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="a9a77-126">Он будет использоваться для идентификации записей, попадающих в интервал времени инкрементного обновления.</span><span class="sxs-lookup"><span data-stu-id="a9a77-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="a9a77-127">**Проверять обновления каждые**: укажите, какой длины должен быть интервал времени инкрементного обновления.</span><span class="sxs-lookup"><span data-stu-id="a9a77-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="a9a77-128">Выберите **Сохранить**, чтобы завершить создание источника данных.</span><span class="sxs-lookup"><span data-stu-id="a9a77-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="a9a77-129">Первоначальное обновление данных будет полным обновлением.</span><span class="sxs-lookup"><span data-stu-id="a9a77-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="a9a77-130">После этого инкрементное обновление данных происходит в соответствии с настройками предыдущего шага.</span><span class="sxs-lookup"><span data-stu-id="a9a77-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>
