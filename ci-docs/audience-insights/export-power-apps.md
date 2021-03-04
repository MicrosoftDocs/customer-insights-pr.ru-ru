---
title: Соединитель Power Apps
description: Соедините с Power Apps и Power Automate.
ms.date: 01/19/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a8bbb9a09218d54228589d43c21c8894680b56e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268932"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="3e23d-103">Соединитель Microsoft Power Apps (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="3e23d-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="3e23d-104">Используйте унифицированные профили клиентов в своих персонализированных приложениях с помощью Power Apps.</span><span class="sxs-lookup"><span data-stu-id="3e23d-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="3e23d-105">Подключение к Power Apps и Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="3e23d-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="3e23d-106">Customer Insights является одним из многих [доступных источников данных в Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="3e23d-106">Customer Insights is one of the many [available sources for data in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="3e23d-107">Обратитесь к документации Power Apps, чтобы узнать, как [добавить подключение к данным в приложение](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="3e23d-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="3e23d-108">Мы рекомендуем вам также просмотреть [как Power Apps использует делегирование для обработки больших наборов данных в приложениях на основе холста](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="3e23d-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="3e23d-109">Доступные объекты</span><span class="sxs-lookup"><span data-stu-id="3e23d-109">Available entities</span></span>

<span data-ttu-id="3e23d-110">После добавления Customer Insights в качестве подключения к данным вы можете выбрать следующие сущности в Power Apps:</span><span class="sxs-lookup"><span data-stu-id="3e23d-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="3e23d-111">Клиент: чтобы использовать данные из [единого профиля клиента](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="3e23d-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="3e23d-112">UnifiedActivity: чтобы отображать [временную шкалу действия](activities.md) в приложении.</span><span class="sxs-lookup"><span data-stu-id="3e23d-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="3e23d-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="3e23d-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="3e23d-114">Извлекаемые сущности</span><span class="sxs-lookup"><span data-stu-id="3e23d-114">Retrievable entities</span></span>

<span data-ttu-id="3e23d-115">Вы можете извлечь только сущности **Клиент**, **UnifiedActivity** и **Сегменты** через соединитель Power Apps.</span><span class="sxs-lookup"><span data-stu-id="3e23d-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="3e23d-116">Другие сущности показаны, потому что базовый соединитель поддерживает их через триггеры в Power Automate.</span><span class="sxs-lookup"><span data-stu-id="3e23d-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="3e23d-117">Делегирование</span><span class="sxs-lookup"><span data-stu-id="3e23d-117">Delegation</span></span>

<span data-ttu-id="3e23d-118">Делегирование работает для сущности "Клиент" и сущности UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="3e23d-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="3e23d-119">Делегирование для сущности **Клиент**: чтобы использовать делегирование для этой сущности, поля должны быть проиндексированы в [Индекс поиска и фильтрации](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="3e23d-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="3e23d-120">Делегирование для **UnifiedActivity**: делегирование для этой сущности работает только для полей **ActivityId** и **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="3e23d-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="3e23d-121">Для получения дополнительной информации о делегировании см. раздел [Делегируемые функции и операции Power Apps](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="3e23d-121">For more information about delegation, see [Power Apps delegable functions and operations](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="3e23d-122">Пример элемента управления галереи</span><span class="sxs-lookup"><span data-stu-id="3e23d-122">Example gallery control</span></span>

<span data-ttu-id="3e23d-123">Например, вы добавляете профили клиентов в [элемент управления коллекцией](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="3e23d-123">For example, you add customer profiles to a [gallery control](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="3e23d-124">Добавьте элемент управления **Галерея** в приложение, которое вы создаете.</span><span class="sxs-lookup"><span data-stu-id="3e23d-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3e23d-125">![Добавление элемента галереи](media/connector-powerapps9.png "Добавление элемента галереи")</span><span class="sxs-lookup"><span data-stu-id="3e23d-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="3e23d-126">Выберите **Клиент** как источник данных для элементов.</span><span class="sxs-lookup"><span data-stu-id="3e23d-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="3e23d-127">![Выберите источник данных](media/choose-datasource-powerapps.png "Выберите источник данных")</span><span class="sxs-lookup"><span data-stu-id="3e23d-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="3e23d-128">Вы можете изменить панель данных справа, чтобы выбрать, какое поле для сущности клиента отображать в галерее.</span><span class="sxs-lookup"><span data-stu-id="3e23d-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="3e23d-129">Если вы хотите показать какое-либо поле из выбранного клиента в галерее, заполните свойство "Текст" метки: **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="3e23d-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="3e23d-130">Пример: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="3e23d-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="3e23d-131">Чтобы отобразить унифицированную временную шкалу для клиента, добавьте элемент галереи и добавьте свойство элементов: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="3e23d-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="3e23d-132">Пример: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="3e23d-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]