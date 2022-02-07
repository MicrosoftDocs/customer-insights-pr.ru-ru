---
title: Схемы сущностей Customer Insights в Common Data Model
description: Работа с сущностями в Common Data Model.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
---

# <a name="entity-schemas-in-common-data-model"></a>Схемы сущностей в Common Data Model



[Common Data Model](/common-data-model/) — это декларативная спецификация и определение стандартных сущностей с открытым исходным кодом, представляющих концепции и действия, часто используемые в различных организациях и приложениях повышения производительности. Эта модель распространяется и на данные наблюдений и анализа. Common Data Model предоставляет четко определенные, модульные и расширяемые бизнес-сущности, такие как учетная запись, подразделение, обращение, контакт, интерес, возможная сделка и продукт, а также взаимодействия и связи с поставщиками, работниками и клиентами, например действия и соглашения об уровне обслуживания. Любой может создавать определения на основе Common Data Model и расширять такие определения для учета дополнительных специфичных для бизнеса идей.

Эта модель общих данных позволяет приложениям и интеграторам данных легче взаимодействовать, предоставляя унифицированное определение данных. Common Data Model включает в себя богатую систему метаданных со стандартными сущностями, отношениями, иерархиями, характеристиками и многим другим. Она возникла из приложений Dynamics 365 и имеет открытый исходный код на GitHub с более чем 260 стандартными сущностями. Большая система внутренних и внешних партнеров вносит отраслевые концепции в общую модель данных Common Data Model.

Сегодня несколько систем и платформ реализуют общую модель данных Common Data Model, в том числе потоки данных Power BI и службы данных Azure. Это уже поддерживается в Microsoft Dataverse, Dynamics 365, Power Apps, Power BI и предстоящих службах данных Azure, напрямую увеличивая ценность [инициативы открытых данных](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Схемы сущностей Customer Insights

Чтобы создать полное представление о клиенте и сделать модели Customer Insights доступными в Common Data Model для расширяемости, мы опубликовали следующие схемы сущностей:

| Сущность | Описание |
|---------|---------|
|[CustomerActivity](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Действие, выполняемое пользователем, которое имеет наблюдательную ценность для бизнеса. |
|[CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Лицо или организация, которые либо занимаются, либо потенциально могут заниматься деловыми активностями. |
|[MeasureDefinition](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Определение ключевых показателей эффективности, разделенных на ноль или более измерений (такие, как ежемесячные активные пользователи, общие расходы по клиентам, средняя стоимость привлечения клиентов) |
|[Сегмент](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Определяет группу участников с общими чертами. |
|[SegmentMembership](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Участники, участвующие в данном сегменте. |

Для получения дополнительной информации см. документацию [Схемы сущностей Customer Insights в Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Просмотр сущностей с помощью навигатора сущностей Common Data Model

Вы можете просматривать сущности в [навигаторе сущностей Common Data Model](https://microsoft.github.io/CDM/). Выберите сущность в разделе «Приложение Insights», чтобы получить список сущностей Customer Insights и их определения.
> [!div class="mx-imgBorder"]
> ![Навигатор сущностей CDM, показывающий сущность CustomerActivity.](media/CDM-entity-navigator.png "Навигатор сущностей CDM, показывающий сущность CustomerActivity")


[!INCLUDE[footer-include](../includes/footer-banner.md)]
