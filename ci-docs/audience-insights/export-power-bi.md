---
title: Соединитель Power BI
description: Узнайте, как пользоваться соединитель Dynamics 365 Customer Insights в Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406724"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="30dc3-103">Соединитель для Power BI (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="30dc3-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="30dc3-104">Создавайте визуализации для ваших данных с помощью Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="30dc3-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="30dc3-105">Создавайте дополнительные аналитические данные и создавайте отчеты с вашими унифицированными данными клиентов.</span><span class="sxs-lookup"><span data-stu-id="30dc3-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="30dc3-106">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="30dc3-106">Prerequisites</span></span>

- <span data-ttu-id="30dc3-107">У вас есть унифицированные профили клиентов.</span><span class="sxs-lookup"><span data-stu-id="30dc3-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="30dc3-108">Последняя версия [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) установлена на вашем компьютере.</span><span class="sxs-lookup"><span data-stu-id="30dc3-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="30dc3-109">[Дополнительные сведения о Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="30dc3-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="30dc3-110">Настройка соединителя для Power BI</span><span class="sxs-lookup"><span data-stu-id="30dc3-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="30dc3-111">В Power BI Desktop выберите **Файл** > **Получить данные**.</span><span class="sxs-lookup"><span data-stu-id="30dc3-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="30dc3-112">Выберите **Показать больше** и найдите **Dynamics 365 Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="30dc3-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="30dc3-113">Выберите результат и выберите **Подключить**.</span><span class="sxs-lookup"><span data-stu-id="30dc3-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="30dc3-114">**Войдите** с той же учетной записью организации, которую вы используете для Customer Insights, и выберите **Подключить**.</span><span class="sxs-lookup"><span data-stu-id="30dc3-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="30dc3-115">Учетная запись, которую вы указываете на этом шаге, используется для получения данных из Customer Insights и не обязательно должна быть той же, в которую вы вошли в Power BI.</span><span class="sxs-lookup"><span data-stu-id="30dc3-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="30dc3-116">Чтобы сбросить учетную запись, которая используется для получения данных, откройте Power BI и перейдите **Файл** > **Параметры** > **Настройки** > **Параметры источника данных**.</span><span class="sxs-lookup"><span data-stu-id="30dc3-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="30dc3-117">В списке источников данных выберите **Вход в Dynamics 365 Customer Insights** и выберите **Очистить разрешения**.</span><span class="sxs-lookup"><span data-stu-id="30dc3-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="30dc3-118">В диалоговом окне **Навигатор**.</span><span class="sxs-lookup"><span data-stu-id="30dc3-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="30dc3-119">Вы увидите список всех сред, к которым у вас есть доступ.</span><span class="sxs-lookup"><span data-stu-id="30dc3-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="30dc3-120">Разверните среду и откройте любую из папок (сущности, меры, сегменты, обогащения).</span><span class="sxs-lookup"><span data-stu-id="30dc3-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="30dc3-121">Например, откройте папку **Сущности**, чтобы увидеть все сущности, которые вы можете импортировать.</span><span class="sxs-lookup"><span data-stu-id="30dc3-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="30dc3-122">![Навигатор соединителя Power BI](media/power-bi-navigator.png "Навигатор соединителя Power BI")</span><span class="sxs-lookup"><span data-stu-id="30dc3-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="30dc3-123">Установите флажки рядом с сущностями, которые требуется включить, и **Загрузить**.</span><span class="sxs-lookup"><span data-stu-id="30dc3-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="30dc3-124">Можно выбрать несколько сущностей из нескольких сред.</span><span class="sxs-lookup"><span data-stu-id="30dc3-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="30dc3-125">Вы увидите диалоговое окно загрузки, пока ваши сущности загружаются.</span><span class="sxs-lookup"><span data-stu-id="30dc3-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="30dc3-126">После загрузки всех выбранных вами сущностей вы можете использовать возможности Power BI для визуализации данных.</span><span class="sxs-lookup"><span data-stu-id="30dc3-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="30dc3-127">Большие наборы данных</span><span class="sxs-lookup"><span data-stu-id="30dc3-127">Large data sets</span></span>

<span data-ttu-id="30dc3-128">Соединитель Customer Insights для Power BI предназначен для работы с наборами данных, содержащими до 1 миллиона профилей клиентов.</span><span class="sxs-lookup"><span data-stu-id="30dc3-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="30dc3-129">Импорт больших наборов данных может работать, но это занимает много времени.</span><span class="sxs-lookup"><span data-stu-id="30dc3-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="30dc3-130">Кроме того, у процесса может возникнуть тайм-аут из-за ограничений Power BI.</span><span class="sxs-lookup"><span data-stu-id="30dc3-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="30dc3-131">Дополнительные сведения см. в разделе [Power BI: рекомендации для больших наборов данных](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="30dc3-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="30dc3-132">Работа с подмножеством данных</span><span class="sxs-lookup"><span data-stu-id="30dc3-132">Work with a subset of data</span></span>

<span data-ttu-id="30dc3-133">Рассмотрите возможность работы с подмножеством ваших данных.</span><span class="sxs-lookup"><span data-stu-id="30dc3-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="30dc3-134">Например, вы можете создать [сегменты](segments.md) вместо экспорта всех записей о клиентах в Power BI.</span><span class="sxs-lookup"><span data-stu-id="30dc3-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
