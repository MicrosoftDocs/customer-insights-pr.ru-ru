---
title: Схемы сущностей Customer Insights в Common Data Model
description: Работа с сущностями в Common Data Model.
ms.date: 04/17/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 6667e411a1b56e13105a6b59b7b5d249bc8141ea
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596377"
---
# <a name="entity-schemas-in-common-data-model"></a>Схемы сущностей в Common Data Model

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Common Data Model](/common-data-model/) — это декларативная спецификация и определение стандартных сущностей с открытым исходным кодом, представляющих концепции и действия, часто используемые в различных организациях и приложениях повышения производительности. Эта модель распространяется и на данные наблюдений и анализа. Common Data Model предоставляет четко определенные, модульные и расширяемые бизнес-сущности, такие как учетная запись, подразделение, обращение, контакт, интерес, возможная сделка и продукт, а также взаимодействия и связи с поставщиками, работниками и клиентами, например действия и соглашения об уровне обслуживания. Любой может создавать определения на основе Common Data Model и расширять такие определения для учета дополнительных специфичных для бизнеса идей.

Эта модель общих данных позволяет приложениям и интеграторам данных легче взаимодействовать, предоставляя унифицированное определение данных. Common Data Model включает в себя богатую систему метаданных со стандартными сущностями, отношениями, иерархиями, характеристиками и многим другим. Она возникла из приложений Dynamics 365 и имеет открытый исходный код на GitHub с более чем 260 стандартными сущностями. Большая система внутренних и внешних партнеров вносит отраслевые концепции в общую модель данных Common Data Model.

Сегодня несколько систем и платформ реализуют Common Data Services, в том числе потоки данных Power BI и службы данных Azure. Она уже поддерживается в Common Data Service, Dynamics 365, Power Apps, Power BI и будущих службах данных Azure, непосредственно увеличивая ценность для [Open Data Initiative](https://www.microsoft.com/open-data-initiative).

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

Вы можете просматривать сущности в [навигаторе сущностей Common Data Model](https://microsoft.github.io/CDM/). Выберите кнопку **Загрузить с GitHub!** и перейдите к разделу **foundationCommon** > **crmCommon** > **решения** > **customerInsights**, где вы найдете список сущностей Customer Insights и их определения.
> [!div class="mx-imgBorder"]
> ![Навигатор сущностей CDM, показывающий сущность CustomerActivity](media/CDM-entity-navigator.png "Навигатор сущностей CDM, показывающий сущность CustomerActivity")


[!INCLUDE[footer-include](../includes/footer-banner.md)]