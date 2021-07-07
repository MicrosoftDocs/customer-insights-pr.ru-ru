---
title: Просмотр профилей клиентов
description: Получите комбинированное представление о ваших унифицированных данных о клиентах.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: c9adb4d7db74573d0512ae7a68a0e7ab51c994a0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304620"
---
# <a name="customer-profiles"></a><span data-ttu-id="29be8-103">Профили клиентов</span><span class="sxs-lookup"><span data-stu-id="29be8-103">Customer profiles</span></span>

<span data-ttu-id="29be8-104">На странице **Клиенты** показано комбинированное представление ваших клиентов, основанное на данных профилей, собранных из [всех источников данных](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="29be8-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="29be8-105">Профили клиентов доступны, как только вы [создадите единую сущность клиента](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="29be8-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="29be8-106">Убедитесь, что вы завершили процесс унификации данных, чтобы получить более полное представление о ваших клиентах.</span><span class="sxs-lookup"><span data-stu-id="29be8-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="29be8-107">Страница также позволяет вам искать клиентов.</span><span class="sxs-lookup"><span data-stu-id="29be8-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="29be8-108">Клиентами могут быть частные лица или организации (предварительная версия).</span><span class="sxs-lookup"><span data-stu-id="29be8-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="29be8-109">Каждый профиль клиента или организации представлен плиткой.</span><span class="sxs-lookup"><span data-stu-id="29be8-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="29be8-110">Выберите плитку, чтобы увидеть дополнительную информацию об этом конкретном клиенте или организации.</span><span class="sxs-lookup"><span data-stu-id="29be8-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="29be8-111">Используйте элементы управления разбиением на страницы внизу страницы, чтобы увидеть дополнительные записи.</span><span class="sxs-lookup"><span data-stu-id="29be8-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="29be8-112">![Профили клиентов B2C](media/profiles-customers.png "Профили клиентов B2C")</span><span class="sxs-lookup"><span data-stu-id="29be8-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="29be8-113">Организации (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="29be8-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="29be8-114">![Профили клиентов B2B](media/profile-customers-b2b.png "Профили клиентов B2B")</span><span class="sxs-lookup"><span data-stu-id="29be8-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="29be8-115">Если вы не видите плитки при выборе **Клиенты** в навигации, ваш администратор должен [определить хотя бы один атрибут для поиска](search-filter-index.md) в пункте **Индекс поиска и фильтра**.</span><span class="sxs-lookup"><span data-stu-id="29be8-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="29be8-116">Поиск клиентов</span><span class="sxs-lookup"><span data-stu-id="29be8-116">Search for customers</span></span>

<span data-ttu-id="29be8-117">Для поиска клиентов введите имя или какой-либо другой атрибут в поле поиска.</span><span class="sxs-lookup"><span data-stu-id="29be8-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="29be8-118">Поиск работает только в сущности профиля клиента, созданной в процессе унификации данных.</span><span class="sxs-lookup"><span data-stu-id="29be8-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="29be8-119">Как администратор, вы можете настроить доступные для поиска атрибуты, используя страницу **Индекс поиска и фильтра**.</span><span class="sxs-lookup"><span data-stu-id="29be8-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="29be8-120">Дополнительные сведения см. в статье [Управление индексом поиска и фильтра](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="29be8-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="29be8-121">Фильтрация клиентов</span><span class="sxs-lookup"><span data-stu-id="29be8-121">Filter customers</span></span>

<span data-ttu-id="29be8-122">Вы можете фильтровать клиентов по полям сущности профиля клиента.</span><span class="sxs-lookup"><span data-stu-id="29be8-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="29be8-123">Подобно поиску, ваш администратор должен сначала определить поля как фильтруемые с помощью страницы **Индекс поиска и фильтра**.</span><span class="sxs-lookup"><span data-stu-id="29be8-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="29be8-124">Выберите **Фильтр** на странице **Клиенты**.</span><span class="sxs-lookup"><span data-stu-id="29be8-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="29be8-125">Установите флажки рядом с атрибутами, по которым требуется фильтровать клиентов.</span><span class="sxs-lookup"><span data-stu-id="29be8-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="29be8-126">![Профили клиентов](media/profiles-customers3.png "Профили клиентов")</span><span class="sxs-lookup"><span data-stu-id="29be8-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="29be8-127">Удалите фильтры, выбрав **Очистить фильтры** на странице **Клиенты**.</span><span class="sxs-lookup"><span data-stu-id="29be8-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="29be8-128">Страница сведений о клиенте</span><span class="sxs-lookup"><span data-stu-id="29be8-128">Customer details page</span></span>

<span data-ttu-id="29be8-129">Выберите любую плитку клиента, чтобы открыть **страницу сведений о клиенте**.</span><span class="sxs-lookup"><span data-stu-id="29be8-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="29be8-130">Это представление содержит единую информацию о выбранном клиенте.</span><span class="sxs-lookup"><span data-stu-id="29be8-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="29be8-131">Сведения о клиенте включают:</span><span class="sxs-lookup"><span data-stu-id="29be8-131">Customer details include:</span></span>

-   <span data-ttu-id="29be8-132">**Плитка профиля клиента**: на этой плитке показаны различные значения из сущности единого профиля клиента.</span><span class="sxs-lookup"><span data-stu-id="29be8-132">**Customer profile tile**: This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="29be8-133">Эти данные могут включать адрес электронной почты, имя, город и т. д.</span><span class="sxs-lookup"><span data-stu-id="29be8-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="29be8-134">**Возможные интересы, потенциальные бренды**: показывает, настроили ли вы первичное обогащение.</span><span class="sxs-lookup"><span data-stu-id="29be8-134">**Potential interests, potential brands**: Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="29be8-135">Он представляет потенциальные интересы и близость к брендам покупателя с профилем, аналогичным этому покупателю.</span><span class="sxs-lookup"><span data-stu-id="29be8-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="29be8-136">Дополнительные сведения см. в разделе [Обогащение профилей клиентов с повышением узнаваемости бренда и интересов](enrichment-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="29be8-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft.md).</span></span>

-   <span data-ttu-id="29be8-137">**Меры**: показывает, настроили ли вы одну или несколько мер определенного типа: меры атрибутов клиента.</span><span class="sxs-lookup"><span data-stu-id="29be8-137">**Measures**: Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="29be8-138">Они включают рассчитанные KPI для ваших клиентов на уровне отдельных клиентов.</span><span class="sxs-lookup"><span data-stu-id="29be8-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="29be8-139">Дополнительные сведения см. в разделе [Определение мер и управление ими](measures.md).</span><span class="sxs-lookup"><span data-stu-id="29be8-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="29be8-140">**Временная шкала действий**: показывает, настроили ли вы действия.</span><span class="sxs-lookup"><span data-stu-id="29be8-140">**Activity timeline**: Shows if you have configured activities.</span></span> <span data-ttu-id="29be8-141">На временной шкале отображаются действия этого клиента, отсортированные в хронологическом порядке, начиная с самых последних действий.</span><span class="sxs-lookup"><span data-stu-id="29be8-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="29be8-142">Дополнительные сведения см. в статье [Действия клиента](activities.md).</span><span class="sxs-lookup"><span data-stu-id="29be8-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="29be8-143">Выберите **Вернуться к клиентам**, чтобы вернуться на страницу поиска клиентов.</span><span class="sxs-lookup"><span data-stu-id="29be8-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="29be8-144">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="29be8-144">Next steps</span></span>

<span data-ttu-id="29be8-145">[Добавление дополнительных источников данных](data-sources.md) или [создание сегментов клиентов](segments.md).</span><span class="sxs-lookup"><span data-stu-id="29be8-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
