---
title: Соединитель Power BI
description: Узнайте, как пользоваться соединитель Dynamics 365 Customer Insights в Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0607a4644ac7d7beb19e4faecf012efcd197d48c
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477104"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="d607b-103">Соединитель для Power BI (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="d607b-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="d607b-104">Создавайте визуализации для ваших данных с помощью Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="d607b-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="d607b-105">Создавайте дополнительные аналитические данные и создавайте отчеты с вашими унифицированными данными клиентов.</span><span class="sxs-lookup"><span data-stu-id="d607b-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d607b-106">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="d607b-106">Prerequisites</span></span>

- <span data-ttu-id="d607b-107">У вас есть унифицированные профили клиентов.</span><span class="sxs-lookup"><span data-stu-id="d607b-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="d607b-108">Последняя версия [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) установлена на вашем компьютере.</span><span class="sxs-lookup"><span data-stu-id="d607b-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="d607b-109">[Дополнительные сведения о Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="d607b-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="d607b-110">Настройка соединителя для Power BI</span><span class="sxs-lookup"><span data-stu-id="d607b-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="d607b-111">В Power BI Desktop выберите **Файл** > **Получить данные**.</span><span class="sxs-lookup"><span data-stu-id="d607b-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="d607b-112">Выберите **Показать больше** и найдите **Dynamics 365 Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="d607b-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="d607b-113">Нажмите **Подключиться**.</span><span class="sxs-lookup"><span data-stu-id="d607b-113">Select **Connect**.</span></span>

1. <span data-ttu-id="d607b-114">**Войдите** с той же учетной записью организации, которую вы используете для Customer Insights, и выберите **Подключить**.</span><span class="sxs-lookup"><span data-stu-id="d607b-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="d607b-115">Учетная запись, которую вы указываете на этом шаге, используется для получения данных из Customer Insights и не обязательно должна быть той же, в которую вы вошли в Power BI.</span><span class="sxs-lookup"><span data-stu-id="d607b-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="d607b-116">Чтобы сбросить учетную запись, которая используется для получения данных, откройте Power BI и перейдите **Файл** > **Параметры** > **Настройки** > **Параметры источника данных**.</span><span class="sxs-lookup"><span data-stu-id="d607b-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="d607b-117">В списке источников данных выберите **Вход в Dynamics 365 Customer Insights** и выберите **Очистить разрешения**.</span><span class="sxs-lookup"><span data-stu-id="d607b-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="d607b-118">В диалоговом окне **Навигатор**.</span><span class="sxs-lookup"><span data-stu-id="d607b-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="d607b-119">Вы увидите список всех сред, к которым у вас есть доступ.</span><span class="sxs-lookup"><span data-stu-id="d607b-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="d607b-120">Разверните среду и откройте любую из папок (сущности, меры, сегменты, обогащения).</span><span class="sxs-lookup"><span data-stu-id="d607b-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="d607b-121">Например, откройте папку **Сущности**, чтобы увидеть все сущности, которые вы можете импортировать.</span><span class="sxs-lookup"><span data-stu-id="d607b-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="d607b-122">![Навигатор соединителя Power BI](media/power-bi-navigator.png "Навигатор соединителя Power BI")</span><span class="sxs-lookup"><span data-stu-id="d607b-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="d607b-123">Установите флажки рядом с сущностями, которые требуется включить, и **Загрузить**.</span><span class="sxs-lookup"><span data-stu-id="d607b-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="d607b-124">Можно выбрать несколько сущностей из нескольких сред.</span><span class="sxs-lookup"><span data-stu-id="d607b-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="d607b-125">Вы увидите диалоговое окно загрузки, пока ваши сущности загружаются.</span><span class="sxs-lookup"><span data-stu-id="d607b-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="d607b-126">После загрузки всех выбранных вами сущностей вы можете использовать возможности Power BI для визуализации данных.</span><span class="sxs-lookup"><span data-stu-id="d607b-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="d607b-127">Большие наборы данных</span><span class="sxs-lookup"><span data-stu-id="d607b-127">Large data sets</span></span>

<span data-ttu-id="d607b-128">Соединитель Customer Insights для Power BI предназначен для работы с наборами данных, содержащими до 1 миллиона профилей клиентов.</span><span class="sxs-lookup"><span data-stu-id="d607b-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="d607b-129">Импорт больших наборов данных может работать, но это занимает много времени.</span><span class="sxs-lookup"><span data-stu-id="d607b-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="d607b-130">Кроме того, у процесса может возникнуть тайм-аут из-за ограничений Power BI.</span><span class="sxs-lookup"><span data-stu-id="d607b-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="d607b-131">Дополнительные сведения см. в разделе [Power BI: рекомендации для больших наборов данных](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="d607b-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="d607b-132">Работа с подмножеством данных</span><span class="sxs-lookup"><span data-stu-id="d607b-132">Work with a subset of data</span></span>

<span data-ttu-id="d607b-133">Рассмотрите возможность работы с подмножеством ваших данных.</span><span class="sxs-lookup"><span data-stu-id="d607b-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="d607b-134">Например, вы можете создать [сегменты](segments.md) вместо экспорта всех записей о клиентах в Power BI.</span><span class="sxs-lookup"><span data-stu-id="d607b-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="d607b-135">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="d607b-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="d607b-136">Среда Customer Insights не отображается в Power BI</span><span class="sxs-lookup"><span data-stu-id="d607b-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="d607b-137">Среды, в которых есть более одного [отношения](relationships.md), определенного между двумя идентичными сущностями в аналитике аудитории, не будут доступны в соединителе Power BI.</span><span class="sxs-lookup"><span data-stu-id="d607b-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="d607b-138">Вы можете определить и удалить дублирующиеся отношения.</span><span class="sxs-lookup"><span data-stu-id="d607b-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="d607b-139">В аналитике аудитории перейдите **Данные** > **Отношения** в среде, которой вам не хватает в Power BI.</span><span class="sxs-lookup"><span data-stu-id="d607b-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="d607b-140">Определите повторяющиеся отношения:</span><span class="sxs-lookup"><span data-stu-id="d607b-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="d607b-141">Проверьте, не определено ли более одного отношения между одними и теми же двумя сущностями.</span><span class="sxs-lookup"><span data-stu-id="d607b-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="d607b-142">Проверьте, существует ли отношение между двумя сущностями, которые обе участвуют в процессе объединения.</span><span class="sxs-lookup"><span data-stu-id="d607b-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="d607b-143">Между всеми сущностями, включенными в процесс объединения, существует явное отношение.</span><span class="sxs-lookup"><span data-stu-id="d607b-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="d607b-144">Удалите все обнаруженные повторяющиеся отношения.</span><span class="sxs-lookup"><span data-stu-id="d607b-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="d607b-145">После удаления дублированного отношения попробуйте настроить соединитель Power BI снова.</span><span class="sxs-lookup"><span data-stu-id="d607b-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="d607b-146">Среда должна стать доступной.</span><span class="sxs-lookup"><span data-stu-id="d607b-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

