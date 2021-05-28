---
title: Сущности и наборы данных
description: Просмотр данных на странице сущностей.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: f81128183b6e20e1078ad38c42c771d343909270
ms.sourcegitcommit: c1841ab91fbef9ead9db0f63fbc669cc3af80c12
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049410"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="09e77-103">Сущности в аналитике аудитории</span><span class="sxs-lookup"><span data-stu-id="09e77-103">Entities in audience insights</span></span>

<span data-ttu-id="09e77-104">После [настройки ваших источников данных](data-sources.md) перейдите на страницу **Сущности** для оценки качества полученных данных.</span><span class="sxs-lookup"><span data-stu-id="09e77-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="09e77-105">Сущности считаются наборами данных.</span><span class="sxs-lookup"><span data-stu-id="09e77-105">Entities are considered datasets.</span></span> <span data-ttu-id="09e77-106">Множественные возможности Dynamics 365 Customer Insights построены вокруг этих сущностей.</span><span class="sxs-lookup"><span data-stu-id="09e77-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="09e77-107">Внимательно изучив их, вы сможете проверить выходные данные этих возможностей.</span><span class="sxs-lookup"><span data-stu-id="09e77-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="09e77-108">Страница **Сущности** содержит список сущностей и содержит несколько столбцов:</span><span class="sxs-lookup"><span data-stu-id="09e77-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="09e77-109">**Имя**: имя вашей сущности данных.</span><span class="sxs-lookup"><span data-stu-id="09e77-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="09e77-110">Если вы видите предупреждающий символ рядом с именем сущности, это означает, что данные для этой сущности не были успешно загружены.</span><span class="sxs-lookup"><span data-stu-id="09e77-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="09e77-111">**Источник**: тип источника данных, который получил сущность</span><span class="sxs-lookup"><span data-stu-id="09e77-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="09e77-112">**Кем создано**: имя лица, создавшего сущность.</span><span class="sxs-lookup"><span data-stu-id="09e77-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="09e77-113">**Создано**: дата и время создания сущности</span><span class="sxs-lookup"><span data-stu-id="09e77-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="09e77-114">**Кем обновлено**: имя лица, обновившего сущность.</span><span class="sxs-lookup"><span data-stu-id="09e77-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="09e77-115">**Последнее обновление**: дата и время последнего обновления сущности</span><span class="sxs-lookup"><span data-stu-id="09e77-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="09e77-116">**Последнее обновление**: дата и время последнего обновления данных</span><span class="sxs-lookup"><span data-stu-id="09e77-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="09e77-117">Изучение данных конкретной сущности</span><span class="sxs-lookup"><span data-stu-id="09e77-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="09e77-118">Выберите сущность, чтобы изучить различные поля и записи, включенные в эту сущность.</span><span class="sxs-lookup"><span data-stu-id="09e77-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="09e77-119">![Выбор сущности](media/data-manager-entities-data.png "Выберите сущность")</span><span class="sxs-lookup"><span data-stu-id="09e77-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="09e77-120">На вкладке **Данные** отображается таблица со сведениями об отдельных записях сущности.</span><span class="sxs-lookup"><span data-stu-id="09e77-120">The **Data** tab shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="09e77-121">![Таблица полей](media/data-manager-entities-fields.PNG "Таблица полей")</span><span class="sxs-lookup"><span data-stu-id="09e77-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="09e77-122">Вкладка **Атрибуты** выбрана по умолчанию и показывает таблицу для просмотра сведений о выбранной сущности, таких как имена полей, типы данных и типы.</span><span class="sxs-lookup"><span data-stu-id="09e77-122">The **Attributes** tab is selected by default and shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="09e77-123">Столбец **Тип** показывает связанные типы Common Data Model, которые либо автоматически идентифицируются системой, либо [сопоставлены вручную](map-entities.md) пользователями.</span><span class="sxs-lookup"><span data-stu-id="09e77-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="09e77-124">Это семантические типы, которые могут отличаться от типов данных атрибутов, например, поля *Эл. адрес* ниже имеет тип данных *Текст*, но его (семантический) тип Common Data Model может быть *Email* или *EmailAddress*.</span><span class="sxs-lookup"><span data-stu-id="09e77-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="09e77-125">Обе таблицы показывают только образец данных вашей сущности.</span><span class="sxs-lookup"><span data-stu-id="09e77-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="09e77-126">Чтобы просмотреть полный набор данных, перейдите на страницу **Источники данных**, выберите сущность, выберите **Изменить**, затем просмотрите данные этой сущности в редакторе Power Query, как описано в разделе [Источники данных](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="09e77-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="09e77-127">Чтобы узнать больше о данных, полученных в сущности, в столбце **Сводка** приведены некоторые важные характеристики данных, такие как значения NULL, отсутствующие значения, уникальные значения, количества и распределения, в зависимости от ваших данных.</span><span class="sxs-lookup"><span data-stu-id="09e77-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="09e77-128">Выберите значок диаграммы, чтобы просмотреть сводку данных.</span><span class="sxs-lookup"><span data-stu-id="09e77-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="09e77-129">![Символ сводки](media/data-manager-entities-summary.png "Таблица сводки данных")</span><span class="sxs-lookup"><span data-stu-id="09e77-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="09e77-130">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="09e77-130">Next step</span></span>

<span data-ttu-id="09e77-131">См. тему [Унификация](data-unification.md), чтобы узнать, как *сопоставлять*, *искать соответствия* и *объединять* полученные данные.</span><span class="sxs-lookup"><span data-stu-id="09e77-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
