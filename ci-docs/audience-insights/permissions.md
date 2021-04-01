---
title: Управление разрешениями пользователей
description: Узнайте о разрешениях и ролях пользователей.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e58bb1a3bd4c0920ff984daffabbf16162185f3d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595718"
---
# <a name="user-permissions"></a><span data-ttu-id="59388-103">Разрешения пользователя</span><span class="sxs-lookup"><span data-stu-id="59388-103">User permissions</span></span>

<span data-ttu-id="59388-104">На странице **Разрешения** вы настроите роли и разрешения для использования аналитики аудитории.</span><span class="sxs-lookup"><span data-stu-id="59388-104">The **Permissions** page is where you'll set up roles and permissions for using audience insights.</span></span>

<span data-ttu-id="59388-105">У вас должны быть разрешения администратора для просмотра страницы.</span><span class="sxs-lookup"><span data-stu-id="59388-105">You need to have administrator permissions to see the page.</span></span> <span data-ttu-id="59388-106">Чтобы получить доступ к странице разрешений в аналитике аудитории, перейдите **Администрирование** > **Разрешения**.</span><span class="sxs-lookup"><span data-stu-id="59388-106">To access the permissions page in audience insights, go to **Admin** > **Permissions**.</span></span>

<span data-ttu-id="59388-107">Существует три типа ролей:</span><span class="sxs-lookup"><span data-stu-id="59388-107">There are three types of roles:</span></span>

## <a name="viewer"></a><span data-ttu-id="59388-108">Наблюдатель</span><span class="sxs-lookup"><span data-stu-id="59388-108">Viewer</span></span>

- <span data-ttu-id="59388-109">Исследование аналитических данных и сегментов на страницах **Главная** и **Сегменты**.</span><span class="sxs-lookup"><span data-stu-id="59388-109">Explore insights and segments within the **Home** and **Segments** pages.</span></span>
- <span data-ttu-id="59388-110">Поиск и фильтрация профилей клиентов с использованием страницы **Клиенты**.</span><span class="sxs-lookup"><span data-stu-id="59388-110">Search and filter customer profiles using the **Customers** page.</span></span> <span data-ttu-id="59388-111">Поля должны быть допускающими поиск.</span><span class="sxs-lookup"><span data-stu-id="59388-111">Fields must be searchable.</span></span>
- <span data-ttu-id="59388-112">Просмотр и изучение страницы **Обогащение**.</span><span class="sxs-lookup"><span data-stu-id="59388-112">View and explore the **Enrichment** page.</span></span>
- <span data-ttu-id="59388-113">Исследование и экспорт сущностей с помощью страницы **Сущности**.</span><span class="sxs-lookup"><span data-stu-id="59388-113">Explore and export entities using the **Entities** page.</span></span>
- <span data-ttu-id="59388-114">Просмотр состояния системных процессов с помощью страницы **Система**.</span><span class="sxs-lookup"><span data-stu-id="59388-114">View the status of system processes  using the **System** page.</span></span>
- <span data-ttu-id="59388-115">Экспортируйте сегменты на странице **Сегменты**.</span><span class="sxs-lookup"><span data-stu-id="59388-115">Export segments from the **Segments** page.</span></span>
- <span data-ttu-id="59388-116">Установите и используйте панель мониторинга **Power BI Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="59388-116">Install and use the **Power BI Customer Insights** dashboard.</span></span>

## <a name="contributor"></a><span data-ttu-id="59388-117">Участник</span><span class="sxs-lookup"><span data-stu-id="59388-117">Contributor</span></span>

- <span data-ttu-id="59388-118">Все разрешения, доступные наблюдателю.</span><span class="sxs-lookup"><span data-stu-id="59388-118">All permissions available to the Viewer.</span></span>
- <span data-ttu-id="59388-119">Загрузка и преобразование данных с использованием страницы **Источники данных**.</span><span class="sxs-lookup"><span data-stu-id="59388-119">Load and transform data using the **Data sources** page.</span></span>
- <span data-ttu-id="59388-120">Заполнение разделов *Унификация данных* (**Сопоставление**, **Совпадение** и **Объединение**), которые приводят к единой сущности профиля клиента.</span><span class="sxs-lookup"><span data-stu-id="59388-120">Complete the *Data Unification* sections (**Map**, **Match**, and **Merge**) which result in the unified customer profile entity.</span></span>
- <span data-ttu-id="59388-121">Определение **Отношений** и **Действий**.</span><span class="sxs-lookup"><span data-stu-id="59388-121">Define **Relationships** and **Activities**.</span></span>
- <span data-ttu-id="59388-122">Создание сегментов, используя страницу **Сегменты**.</span><span class="sxs-lookup"><span data-stu-id="59388-122">Create segments using the **Segments** page.</span></span>
- <span data-ttu-id="59388-123">Создание мер, используя страницу **Меры**.</span><span class="sxs-lookup"><span data-stu-id="59388-123">Create measures using the **Measures** page.</span></span>
- <span data-ttu-id="59388-124">Управление конфигурацией и обогащение профилей клиентов со страницы **обогащение** (только для собственных обогащений).</span><span class="sxs-lookup"><span data-stu-id="59388-124">Manage configuration and enrich customer profiles from the **Enrichment** page (for first party enrichments only).</span></span>

## <a name="administrator"></a><span data-ttu-id="59388-125">Администратор</span><span class="sxs-lookup"><span data-stu-id="59388-125">Administrator</span></span>

- <span data-ttu-id="59388-126">Все разрешения, доступные участнику.</span><span class="sxs-lookup"><span data-stu-id="59388-126">All permissions available to the Contributor.</span></span>
- <span data-ttu-id="59388-127">Изменение настроек на странице **Система**, включая рабочий язык и расписание обновлений для ваших системных процессов.</span><span class="sxs-lookup"><span data-stu-id="59388-127">Change settings on the **System** page, including the working language and refresh schedules for your system processes.</span></span>
- <span data-ttu-id="59388-128">Просмотр и добавление разрешений с помощью страницы **Разрешения**.</span><span class="sxs-lookup"><span data-stu-id="59388-128">View and add permissions using the **Permissions** page.</span></span>
- <span data-ttu-id="59388-129">Задание определений поиска и фильтрации для страницы "Клиенты", используя страницу **Индекс поиска и фильтра** (доступна через страницу **Клиенты**).</span><span class="sxs-lookup"><span data-stu-id="59388-129">Set search and filter definitions for the Customers page using the **Search & filter index** page (accessible via the **Customers** page).</span></span>
- <span data-ttu-id="59388-130">Определение мест назначения сегмента Dynamics 365 Sales, используя страницу **Пункты назначения экспорта**.</span><span class="sxs-lookup"><span data-stu-id="59388-130">Define Dynamics 365 Sales segment destinations using the **Export destinations** page.</span></span>
- <span data-ttu-id="59388-131">Управление конфигурацией и обогащение профилей клиентов со страницы **обогащение** (для всех обогащений).</span><span class="sxs-lookup"><span data-stu-id="59388-131">Manage configuration and enrich customer profiles from the **Enrichment** page (for all enrichments).</span></span>
- <span data-ttu-id="59388-132">Установка и использование **Надстройки карточек клиентов**.</span><span class="sxs-lookup"><span data-stu-id="59388-132">Install and use the **Customer Card Add-in**.</span></span>
- <span data-ttu-id="59388-133">Добавьте и используйте **соединитель Power Apps**.</span><span class="sxs-lookup"><span data-stu-id="59388-133">Add and use the **Power Apps connector**.</span></span>
- <span data-ttu-id="59388-134">Разрешение использования [API Customer Insights](apis.md).</span><span class="sxs-lookup"><span data-stu-id="59388-134">Enable usage of [Customer Insights APIs](apis.md).</span></span>

## <a name="assign-roles-and-permissions"></a><span data-ttu-id="59388-135">Назначение ролей и разрешений</span><span class="sxs-lookup"><span data-stu-id="59388-135">Assign roles and permissions</span></span>

1. <span data-ttu-id="59388-136">В аналитике аудитории перейдите **Администрирование** > **Разрешения**.</span><span class="sxs-lookup"><span data-stu-id="59388-136">In audience insights, go to **Admin** > **Permissions**.</span></span>

1. <span data-ttu-id="59388-137">Выберите **Добавить пользователей**, чтобы открыть область **Добавить/изменить разрешения**.</span><span class="sxs-lookup"><span data-stu-id="59388-137">Select **Add users** to open the **Add/Edit permissions** pane.</span></span>

1. <span data-ttu-id="59388-138">Использовать поле **Поиск**, чтобы найти пользователя или группу Azure Active Directory, чьи права вы хотите настроить.</span><span class="sxs-lookup"><span data-stu-id="59388-138">Use the **Search** field to find the Azure Active Directory user or group whose permissions you want to adjust.</span></span> <span data-ttu-id="59388-139">Выберите **Роль**, чтобы назначить этому пользователю или группе.</span><span class="sxs-lookup"><span data-stu-id="59388-139">Select a **Role** to assign to that user or group.</span></span>

1. <span data-ttu-id="59388-140">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="59388-140">Select **Save**.</span></span> <span data-ttu-id="59388-141">Текущая среда будет автоматически предоставлена пользователю или участникам группы, права которой вы изменили.</span><span class="sxs-lookup"><span data-stu-id="59388-141">The current environment will automatically be shared with the user or members of the group whose permissions you've changed.</span></span> <span data-ttu-id="59388-142">Пользователи могут получить доступ к приложению Customer Insights и работать в соответствии со своей ролью.</span><span class="sxs-lookup"><span data-stu-id="59388-142">Users can access the Customer Insights app and work according to their specified role.</span></span>

## <a name="view-current-permissions"></a><span data-ttu-id="59388-143">Просмотр текущих разрешений</span><span class="sxs-lookup"><span data-stu-id="59388-143">View current permissions</span></span>

<span data-ttu-id="59388-144">В аналитике аудитории перейдите **Администрирование** > **Разрешения**, чтобы узнать, какие назначения ролей в настоящее время активны.</span><span class="sxs-lookup"><span data-stu-id="59388-144">In audience insights, go to **Admin** > **Permissions** to see what role assignments are currently active.</span></span>

- <span data-ttu-id="59388-145">В столбце **Тип** указан один пользователь, группа или приложение.</span><span class="sxs-lookup"><span data-stu-id="59388-145">The **Type** column specifies a single user, group, or application.</span></span> <span data-ttu-id="59388-146">Система поддерживает отдельных пользователей и группы.</span><span class="sxs-lookup"><span data-stu-id="59388-146">The system supports individual users and groups.</span></span>
- <span data-ttu-id="59388-147">Роли указаны в столбце **Роль**.</span><span class="sxs-lookup"><span data-stu-id="59388-147">Roles are specified under the **Role** column.</span></span>
- <span data-ttu-id="59388-148">Выберите любой заголовок столбца, чтобы отсортировать результаты по значению этого столбца.</span><span class="sxs-lookup"><span data-stu-id="59388-148">Select any column title to sort the results by that column's value.</span></span>
- <span data-ttu-id="59388-149">Используйте поле **поиска** в верхней части страницы, чтобы найти конкретных пользователей.</span><span class="sxs-lookup"><span data-stu-id="59388-149">Use the **Search** field at the top of the page to locate specific users.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]