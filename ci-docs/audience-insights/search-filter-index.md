---
title: Поиск и фильтрация профилей клиентов
description: Быстро ищите информацию об единых профилях клиентов и фильтруйте для указанных атрибутов.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: b6cc0ad1a47a6c00e3bf220271f42870fc53621b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597159"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="2873f-103">Профили клиентов: индекс поиска и фильтра</span><span class="sxs-lookup"><span data-stu-id="2873f-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="2873f-104">Результатом объединения данных клиентов является сущность «Профиль клиента», которая обеспечивает единое представление общей клиентской базы.</span><span class="sxs-lookup"><span data-stu-id="2873f-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="2873f-105">Чтобы быстро [найти информацию о конкретном клиенте или группе клиентов](customer-profiles.md), можно настроить возможности **Поиск** и **Фильтр** на странице **Клиенты**.</span><span class="sxs-lookup"><span data-stu-id="2873f-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="2873f-106">Читайте дальше, чтобы узнать, как администраторы могут изменить атрибуты на странице **Индекс поиска и фильтра**, которые доступны пользователям для поиска и фильтрации.</span><span class="sxs-lookup"><span data-stu-id="2873f-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2873f-107">![Фильтр поиска](media/search-filter.png "Фильтр поиска")</span><span class="sxs-lookup"><span data-stu-id="2873f-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="2873f-108">Добавление полей и указание атрибутов</span><span class="sxs-lookup"><span data-stu-id="2873f-108">Add fields and specify attributes</span></span>

<span data-ttu-id="2873f-109">Если вы впервые как администратор определяете атрибуты, допускающие поиск, сначала необходимо определить индексированные поля.</span><span class="sxs-lookup"><span data-stu-id="2873f-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="2873f-110">Мы предлагаем выбрать все атрибуты, с помощью которых пользователи могут искать и фильтровать клиентов на странице **Клиенты**.</span><span class="sxs-lookup"><span data-stu-id="2873f-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="2873f-111">Можно указать только атрибуты, существующие в сущности профиля клиента, созданной в процессе объединения данных.</span><span class="sxs-lookup"><span data-stu-id="2873f-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="2873f-112">Открыть страницу **Клиенты** и выберите **Индекс поиска и фильтра**.</span><span class="sxs-lookup"><span data-stu-id="2873f-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="2873f-113">Выберите **+Добавить** чтобы указать индексированные поля.</span><span class="sxs-lookup"><span data-stu-id="2873f-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="2873f-114">Выберите в списке атрибуты, которые вы хотите добавить как индексированные поля.</span><span class="sxs-lookup"><span data-stu-id="2873f-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="2873f-115">Вы всегда можете добавить больше атрибутов, выбрав **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="2873f-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="2873f-116">Вы также можете удалить любые выбранные атрибуты, выбрав символ **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="2873f-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="2873f-117">Изучение таблицы индексированных полей клиентов</span><span class="sxs-lookup"><span data-stu-id="2873f-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="2873f-118">В таблице представлены следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="2873f-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="2873f-119">**Имя**: представляет имя атрибута, как оно отображается в сущности профиля клиента.</span><span class="sxs-lookup"><span data-stu-id="2873f-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="2873f-120">**Тип данных**: определяет, является ли тип данных строкой, числом или датой.</span><span class="sxs-lookup"><span data-stu-id="2873f-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="2873f-121">**Включено в поиск**: указывается, может ли этот атрибут использоваться для поиска клиентов на странице **Клиенты** с помощью поля **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="2873f-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="2873f-122">**Добавить фильтр**: элемент управления для определения того, как этот атрибут может быть использован для фильтрации на странице **Клиенты**.</span><span class="sxs-lookup"><span data-stu-id="2873f-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="2873f-123">Редактирование параметров фильтрации для определенного атрибута</span><span class="sxs-lookup"><span data-stu-id="2873f-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="2873f-124">Меню **Фильтр** на странице **Клиенты** может включать различное количество уровней атрибутов (например, различные возрастные группы для фильтрации клиентов).</span><span class="sxs-lookup"><span data-stu-id="2873f-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="2873f-125">Выберите **Добавить фильтр** для определенного атрибута на странице **Индекс поиска и фильтра**.</span><span class="sxs-lookup"><span data-stu-id="2873f-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="2873f-126">Вы можете определить количество результатов и порядок, в котором они будут организованы.</span><span class="sxs-lookup"><span data-stu-id="2873f-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="2873f-127">В зависимости от типа данных атрибута, появляется одна из следующих панелей.</span><span class="sxs-lookup"><span data-stu-id="2873f-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="2873f-128">Атрибуты строкового типа: укажите желаемое количество результатов на панели **Параметры фильтра строк** и политику порядка, в котором они будут организованы.</span><span class="sxs-lookup"><span data-stu-id="2873f-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="2873f-129">Атрибуты численного типа: укажите включаемые интервалы на панели **Параметры числового фильтра** и политику порядка, в котором они будут организованы.</span><span class="sxs-lookup"><span data-stu-id="2873f-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="2873f-130">Атрибуты типа даты: укажите включаемые интервалы на панели **Параметры фильтра дат** и политику порядка, в котором они будут организованы.</span><span class="sxs-lookup"><span data-stu-id="2873f-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="2873f-131">Нажмите кнопку **Сохранить**, чтобы применить изменения.</span><span class="sxs-lookup"><span data-stu-id="2873f-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="2873f-132">Выберите **Выполнять**, когда будете готовы применить настройки.</span><span class="sxs-lookup"><span data-stu-id="2873f-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2873f-133">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="2873f-133">Next steps</span></span>

<span data-ttu-id="2873f-134">Перейдите на страницу **Клиенты** для поиска профилей клиентов или используйте проиндексированные поля для просмотра подмножества всех профилей клиентов.</span><span class="sxs-lookup"><span data-stu-id="2873f-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]