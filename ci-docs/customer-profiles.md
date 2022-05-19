---
title: Просмотр профилей клиентов
description: Получите комбинированное представление о ваших унифицированных данных о клиентах.
ms.date: 05/13/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 9bb7abc04afe38d73e1df9b252e1864fa6570d7e
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755798"
---
# <a name="customer-profiles"></a>Профили клиентов

На странице **Клиенты** представлен комбинированный вид ваших единых профилей клиентов. Профили клиентов станут доступны после того, как вы [создали единую сущности клиента](data-unification.md). Эта страница позволяет вам искать клиентов и определять указатель для этого поиска.

Клиентами могут быть частные лица или организации. Каждый профиль клиента представлен плиткой. Используйте элементы управления разбивкой на страницы, чтобы получить больше записей. На карточке отображаются поля из сущности *Клиент*, как определено в **Индекс поиска и фильтрации**. Порядок полей в каждой карточке выбирается системой.

Выберите плитку, чтобы просмотреть данные о выбранном клиенте на специальной странице под названием [Страница сведений о клиенте](customer-profiles.md#customer-details-page).

> [!div class="mx-imgBorder"]
> ![Страница клиентов с плитками результатов](media/customers-page-result-tiles-B2C.png "Страница клиентов с плитками результатов")

> [!NOTE]
> Если вы не видите плитки при выборе **Клиенты** в навигации ваш администратор должен [определить хотя бы один доступный для поиска атрибут](search-filter-index.md) в **Индекс поиска и фильтрации**.

## <a name="search-for-customers"></a>Поиск клиентов

Для поиска клиентов введите имя или какой-либо другой атрибут в поле поиска. Поиск работает только в пределах сущности *Клиент*, созданной в процессе объединения данных.

Как администратор, вы можете настроить доступные для поиска атрибуты, используя страницу **Индекс поиска и фильтра**. Для получения дополнительной информации перейдите в [Управление индексом поиска и фильтром](search-filter-index.md).

## <a name="filter-customers"></a>Фильтрация клиентов

Вы можете фильтровать клиентов по полям сущности *Клиент*. Подобно поиску, ваш администратор должен сначала определить поля как фильтруемые с помощью страницы **Индекс поиска и фильтра**.

1. Выберите **Показать фильтры** на странице **Клиенты**.

1. Установите флажки рядом с атрибутами, по которым требуется фильтровать клиентов.

1. Удалите фильтры, выбрав **Очистить фильтры** на странице **Клиенты**.

## <a name="customer-details-page"></a>Страница сведений о клиенте

Выберите любую плитку клиента, чтобы открыть **страницу сведений о клиенте**. Это представление содержит единую информацию о выбранном клиенте. Сведения о клиенте включают следующее:

**Плитка профиля клиента**: эта плитка показывает разные значения из единой сущности *Клиент*. Если поле не имеет значения для выбранного профиля клиента, оно не отображается. Плитка разбита на разделы:

- В первом разделе показан предварительно определенный набор полей, за которым следуют все поля, которые являются частью индекса поиска и фильтрации. Все поля, связанные с адресом, объединяются в одну строку, если профиль содержит такие поля.
- **Контакты для этого клиента**: в средах для организаций вы увидите все связанные контакты этого клиента во втором разделе. Каждый контакт отображается со своими полями. Пустые поля скрыты.
- **Дополнительные поля**: показывает остальные поля выбранного клиента, кроме идентификаторов.
- **Идентификаторы**: перечисляет все идентификаторы под соответствующим именем сущности. Поля идентифицируются как идентификаторы по их семантике, которая классифицирует их как таковые.

**Временная шкала активности**: показывает данные, если вы настроили действия. На временной шкале отображаются действия выбранного клиента, отсортированные в хронологическом порядке, начиная с самого последнего. Дополнительные сведения см. в [Действия клиента](activities.md).

**Аналитические выводы**:

- **Меры**: показывает, настроили ли вы одну или несколько мер для измерения атрибутов клиента. Они включают рассчитанные KPI для ваших клиентов на уровне отдельных клиентов. Для получения дополнительной информации перейдите в [Определение мер и управление ими](measures.md).

- **Потенциальные интересы, потенциальные бренды**: показывает, настроили ли вы расширение интересов по брендам или интересам. Он представляет потенциальные интересы и общности для брендов, основанных на других клиентах, профиль которых аналогичен выбранному профилю клиента. Для получения дополнительной информации перейдите [Обогатите профили клиентов с помощью общности брендов и интересов](enrichment-microsoft.md).

Чтобы вернуться на страницу поиска клиентов, выберите **Назад к клиентам**.

## <a name="next-steps"></a>Дальнейшие действия

[Добавьте больше источников данных](data-sources.md), [обогатите единые профили](enrichment-hub.md) или [создайте сегменты](segments.md) для работы с едиными профилями клиентов в других приложениях.

[!INCLUDE [footer-include](includes/footer-banner.md)]