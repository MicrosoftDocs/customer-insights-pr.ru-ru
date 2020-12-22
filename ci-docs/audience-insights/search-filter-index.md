---
title: Поиск и фильтрация профилей клиентов
description: Быстро ищите информацию об единых профилях клиентов и фильтруйте для указанных атрибутов.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406766"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="03cb0-103">Профили клиентов: индекс поиска и фильтра</span><span class="sxs-lookup"><span data-stu-id="03cb0-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="03cb0-104">Результатом объединения данных клиентов является сущность «Профиль клиента», которая обеспечивает единое представление общей клиентской базы.</span><span class="sxs-lookup"><span data-stu-id="03cb0-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="03cb0-105">Чтобы быстро [найти информацию о конкретном клиенте или группе клиентов](customer-profiles.md), можно настроить возможности **Поиск** и **Фильтр** на странице **Клиенты**.</span><span class="sxs-lookup"><span data-stu-id="03cb0-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="03cb0-106">Читайте дальше, чтобы узнать, как администраторы могут изменить атрибуты на странице **Индекс поиска и фильтра**, которые доступны пользователям для поиска и фильтрации.</span><span class="sxs-lookup"><span data-stu-id="03cb0-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="03cb0-107">![Фильтр поиска](media/search-filter.png "Фильтр поиска")</span><span class="sxs-lookup"><span data-stu-id="03cb0-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="03cb0-108">Добавление полей и указание атрибутов</span><span class="sxs-lookup"><span data-stu-id="03cb0-108">Add fields and specify attributes</span></span>

<span data-ttu-id="03cb0-109">Если вы впервые как администратор определяете атрибуты, допускающие поиск, сначала необходимо определить индексированные поля.</span><span class="sxs-lookup"><span data-stu-id="03cb0-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="03cb0-110">Мы предлагаем выбрать все атрибуты, с помощью которых пользователи могут искать и фильтровать клиентов на странице **Клиенты**.</span><span class="sxs-lookup"><span data-stu-id="03cb0-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="03cb0-111">Можно указать только атрибуты, существующие в сущности профиля клиента, созданной в процессе объединения данных.</span><span class="sxs-lookup"><span data-stu-id="03cb0-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="03cb0-112">Открыть страницу **Клиенты** и выберите **Индекс поиска и фильтра**.</span><span class="sxs-lookup"><span data-stu-id="03cb0-112">Open the **Customers** page and select **Search & filter index**.</span></span>

> [!NOTE]
> <span data-ttu-id="03cb0-113">Мы создаем конфигурацию индекса поиска по умолчанию для доступных атрибутов в сущности «Клиент» из следующих семантических типов, определенных на странице «Карта».</span><span class="sxs-lookup"><span data-stu-id="03cb0-113">We create a default search index configuration on the available attributes in the Customer entity from the following semantic types as defined on the Map page.</span></span>
> - <span data-ttu-id="03cb0-114">Имя, фамилия, отчество, полное имя пользователя</span><span class="sxs-lookup"><span data-stu-id="03cb0-114">Person First name, Last name, Middle name, Full Name</span></span>
> - <span data-ttu-id="03cb0-115">Название организации</span><span class="sxs-lookup"><span data-stu-id="03cb0-115">Organization Name</span></span>
> - <span data-ttu-id="03cb0-116">Адрес электронной почты</span><span class="sxs-lookup"><span data-stu-id="03cb0-116">Email address</span></span>
> - <span data-ttu-id="03cb0-117">Номер телефона</span><span class="sxs-lookup"><span data-stu-id="03cb0-117">Phone number</span></span>
> - <span data-ttu-id="03cb0-118">Сведения о расположении</span><span class="sxs-lookup"><span data-stu-id="03cb0-118">Location information</span></span>

2. <span data-ttu-id="03cb0-119">Выберите **+Добавить** чтобы указать индексированные поля.</span><span class="sxs-lookup"><span data-stu-id="03cb0-119">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="03cb0-120">Выберите в списке атрибуты, которые вы хотите добавить как индексированные поля.</span><span class="sxs-lookup"><span data-stu-id="03cb0-120">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="03cb0-121">Вы всегда можете добавить больше атрибутов, выбрав **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="03cb0-121">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="03cb0-122">Вы также можете удалить любые выбранные атрибуты, выбрав символ **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="03cb0-122">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="03cb0-123">Изучение таблицы индексированных полей клиентов</span><span class="sxs-lookup"><span data-stu-id="03cb0-123">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="03cb0-124">В таблице представлены следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="03cb0-124">The following information is presented in the table.</span></span>

- <span data-ttu-id="03cb0-125">**Имя**: представляет имя атрибута, как оно отображается в сущности профиля клиента.</span><span class="sxs-lookup"><span data-stu-id="03cb0-125">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="03cb0-126">**Тип данных**: определяет, является ли тип данных строкой, числом или датой.</span><span class="sxs-lookup"><span data-stu-id="03cb0-126">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="03cb0-127">**Включено в поиск**: указывается, может ли этот атрибут использоваться для поиска клиентов на странице **Клиенты** с помощью поля **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="03cb0-127">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="03cb0-128">**Добавить фильтр**: элемент управления для определения того, как этот атрибут может быть использован для фильтрации на странице **Клиенты**.</span><span class="sxs-lookup"><span data-stu-id="03cb0-128">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="03cb0-129">Редактирование параметров фильтрации для определенного атрибута</span><span class="sxs-lookup"><span data-stu-id="03cb0-129">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="03cb0-130">Меню **Фильтр** на странице **Клиенты** может включать различное количество уровней атрибутов (например, различные возрастные группы для фильтрации клиентов).</span><span class="sxs-lookup"><span data-stu-id="03cb0-130">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="03cb0-131">Выберите **Добавить фильтр** для определенного атрибута на странице **Индекс поиска и фильтра**.</span><span class="sxs-lookup"><span data-stu-id="03cb0-131">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="03cb0-132">Вы можете определить количество результатов и порядок, в котором они будут организованы.</span><span class="sxs-lookup"><span data-stu-id="03cb0-132">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="03cb0-133">В зависимости от типа данных атрибута, появляется одна из следующих панелей.</span><span class="sxs-lookup"><span data-stu-id="03cb0-133">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="03cb0-134">Атрибуты строкового типа: укажите желаемое количество результатов на панели **Параметры фильтра строк** и политику порядка, в котором они будут организованы.</span><span class="sxs-lookup"><span data-stu-id="03cb0-134">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="03cb0-135">Атрибуты численного типа: укажите включаемые интервалы на панели **Параметры числового фильтра** и политику порядка, в котором они будут организованы.</span><span class="sxs-lookup"><span data-stu-id="03cb0-135">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="03cb0-136">Атрибуты типа даты: укажите включаемые интервалы на панели **Параметры фильтра дат** и политику порядка, в котором они будут организованы.</span><span class="sxs-lookup"><span data-stu-id="03cb0-136">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="03cb0-137">Нажмите кнопку **Сохранить**, чтобы применить изменения.</span><span class="sxs-lookup"><span data-stu-id="03cb0-137">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="03cb0-138">Выберите **Выполнять**, когда будете готовы применить настройки.</span><span class="sxs-lookup"><span data-stu-id="03cb0-138">Select **Run** once you're ready to apply your settings.</span></span>
