---
title: Прием данных через соединитель Power Query
description: Соединители для источников данных на основе Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406743"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="4d550-103">Подключение к источникам данных Power Query</span><span class="sxs-lookup"><span data-stu-id="4d550-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="4d550-104">Power Query предлагает широкий набор соединителей для приема данных.</span><span class="sxs-lookup"><span data-stu-id="4d550-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="4d550-105">Большинство этих соединителей поддерживаются Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4d550-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="4d550-106">Добавление источников данных на основе соединителей Power Query обычно выполняется в соответствии с шагами, описанными в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="4d550-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="4d550-107">Однако в зависимости от используемого соединителя требуется различная информация.</span><span class="sxs-lookup"><span data-stu-id="4d550-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="4d550-108">Для получения дополнительной информации см. документацию по отдельным соединителям в разделе [Справочник по соединителям Power Query](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="4d550-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="4d550-109">Создание нового источника данных</span><span class="sxs-lookup"><span data-stu-id="4d550-109">Create a new data source</span></span>

1. <span data-ttu-id="4d550-110">В аналитике аудитории перейдите **Данные** > **Источники данных**.</span><span class="sxs-lookup"><span data-stu-id="4d550-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="4d550-111">Выберите **Добавить источник данных**.</span><span class="sxs-lookup"><span data-stu-id="4d550-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="4d550-112">Выберите метод **Импорт данных** и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4d550-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="4d550-113">Укажите **Имя** для источника данных и выберите **Далее** для создания источника данных.</span><span class="sxs-lookup"><span data-stu-id="4d550-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span>

1. <span data-ttu-id="4d550-114">Выберите один из [доступных соединителей](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="4d550-114">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="4d550-115">В этом примере мы выбираем соединитель **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="4d550-115">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="4d550-116">Введите необходимые данные в поле **Параметры соединения** для выбранного соединителя и выберите **Далее** для предварительного просмотра данных.</span><span class="sxs-lookup"><span data-stu-id="4d550-116">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="4d550-117">Выберите **Преобразовать данные**.</span><span class="sxs-lookup"><span data-stu-id="4d550-117">Select **Transform data**.</span></span> <span data-ttu-id="4d550-118">На этом этапе в источник данных будут добавлены сущности.</span><span class="sxs-lookup"><span data-stu-id="4d550-118">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="4d550-119">Сущности — это наборы данных.</span><span class="sxs-lookup"><span data-stu-id="4d550-119">Entities are datasets.</span></span> <span data-ttu-id="4d550-120">Если у вас есть база данных, которая включает в себя несколько наборов данных, каждый набор данных является своей собственной сущностью.</span><span class="sxs-lookup"><span data-stu-id="4d550-120">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="4d550-121">Диалог **Power Query — изменение запросов** позволяет просматривать и уточнять данные.</span><span class="sxs-lookup"><span data-stu-id="4d550-121">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="4d550-122">Сущности, идентифицированные системами в выбранном источнике данных, отображаются на левой панели.</span><span class="sxs-lookup"><span data-stu-id="4d550-122">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4d550-123">![Диалог изменения запросов](media/data-manager-configure-edit-queries.png "Диалог изменения запросов")</span><span class="sxs-lookup"><span data-stu-id="4d550-123">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="4d550-124">Также можно преобразовать ваши данные.</span><span class="sxs-lookup"><span data-stu-id="4d550-124">You can also transform your data.</span></span> <span data-ttu-id="4d550-125">Выберите сущность для изменения или преобразования.</span><span class="sxs-lookup"><span data-stu-id="4d550-125">Select an entity to edit or transform.</span></span> <span data-ttu-id="4d550-126">Используйте параметры в окне Power Query, чтобы применить преобразования.</span><span class="sxs-lookup"><span data-stu-id="4d550-126">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="4d550-127">Каждое преобразование перечисляется в разделе **Примененные шаги**.</span><span class="sxs-lookup"><span data-stu-id="4d550-127">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="4d550-128">Power Query предоставляет множество встроенных вариантов преобразования.</span><span class="sxs-lookup"><span data-stu-id="4d550-128">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="4d550-129">Дополнительные сведения см. в разделе [Преобразования Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="4d550-129">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="4d550-130">Вы можете добавить дополнительные сущности в источник данных, выбрав **Получить данные** в диалоге **Изменить запросы**.</span><span class="sxs-lookup"><span data-stu-id="4d550-130">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="4d550-131">Следующие преобразования настоятельно рекомендуются:</span><span class="sxs-lookup"><span data-stu-id="4d550-131">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="4d550-132">Если вы принимаете данные из файла CSV, первая строка часто содержит заголовки.</span><span class="sxs-lookup"><span data-stu-id="4d550-132">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="4d550-133">Перейдите в раздел **Таблица преобразования** и выберите **Использовать заголовки как первую строку**.</span><span class="sxs-lookup"><span data-stu-id="4d550-133">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="4d550-134">Убедитесь, что тип данных установлен правильно.</span><span class="sxs-lookup"><span data-stu-id="4d550-134">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="4d550-135">Выберите **Сохранить** внизу окна Power Query, чтобы сохранить преобразования.</span><span class="sxs-lookup"><span data-stu-id="4d550-135">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="4d550-136">После сохранения вы найдете свой источник данных в разделе **Данные** > **Источники данных**.</span><span class="sxs-lookup"><span data-stu-id="4d550-136">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="4d550-137">На странице **Источники данных** вы заметите, что новый источник данных находится в состоянии **Обновление**.</span><span class="sxs-lookup"><span data-stu-id="4d550-137">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="4d550-138">Доступные источники данных Power Query</span><span class="sxs-lookup"><span data-stu-id="4d550-138">Available Power Query data sources</span></span>

<span data-ttu-id="4d550-139">См. раздел [Справочник по соединителям Power Query](https://docs.microsoft.com/power-query/connectors/) для получения актуального списка соединителей, которые можно выбрать для импорта данных в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4d550-139">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="4d550-140">Соединители, отмеченные галочкой в столбце **Customer Insights (потоки данных)**, доступны для создания новых источников данных на основе Power Query.</span><span class="sxs-lookup"><span data-stu-id="4d550-140">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="4d550-141">Изучите документацию по конкретному соединителю, чтобы узнать больше о его обязательных требованиях, ограничениях и других деталях.</span><span class="sxs-lookup"><span data-stu-id="4d550-141">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="4d550-142">Изменение источников данных Power Query</span><span class="sxs-lookup"><span data-stu-id="4d550-142">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="4d550-143">Возможно, не удастся внести изменения в источники данных, которые в настоящее время используются в одном из процессов приложения (например, *сегментация*, *сопоставление* или *слияние*).</span><span class="sxs-lookup"><span data-stu-id="4d550-143">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="4d550-144">Используя страницу **Настройки**, можно отслеживать ход выполнения каждого из активных процессов.</span><span class="sxs-lookup"><span data-stu-id="4d550-144">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="4d550-145">Когда процесс завершается, вы можете вернуться на страницу **Источники данных** и внести изменения.</span><span class="sxs-lookup"><span data-stu-id="4d550-145">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="4d550-146">В аналитике аудитории перейдите **Данные** > **Источники данных**.</span><span class="sxs-lookup"><span data-stu-id="4d550-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="4d550-147">Выберите вертикальное многоточие рядом с источник данных, который вы хотите изменить, и выберите **Изменить** из раскрывающегося меню.</span><span class="sxs-lookup"><span data-stu-id="4d550-147">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4d550-148">![Параметр редактирования](media/edit-option-data-sources.png "Параметр редактирования")</span><span class="sxs-lookup"><span data-stu-id="4d550-148">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="4d550-149">Примените свои изменения и преобразования в диалоге **Power Query — изменение запросов**, как описано в разделе [Создание нового источника данных](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="4d550-149">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="4d550-150">Выберите **Сохранить** в Power Query после завершения редактирования, чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="4d550-150">Select **Save** in Power Query after completing your edits to save your changes.</span></span>
