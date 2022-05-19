---
title: Поиск и фильтрация профилей клиентов
description: Быстро ищите информацию об единых профилях клиентов и фильтруйте для указанных атрибутов.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: 35bfd6530b9b80a4b0ec8ff992d9014534721907
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647082"
---
# <a name="customer-profiles-search--filter-index"></a>Профили клиентов: индекс поиска и фильтра

Результатом объединения данных клиентов является сущность «Профиль клиента», которая обеспечивает единое представление общей клиентской базы. Чтобы быстро [найти информацию о конкретном клиенте или группе клиентов](customer-profiles.md), можно настроить возможности **Поиск** и **Фильтр** на странице **Клиенты**. Читайте дальше, чтобы узнать, как администраторы могут изменить атрибуты на странице **Индекс поиска и фильтра**, которые доступны пользователям для поиска и фильтрации.

   :::image type="content" source="media/search-filter.png" alt-text="Фильтр поиска":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="add-fields-and-specify-attributes"></a>Добавление полей и указание атрибутов

Если вы впервые как администратор определяете атрибуты, допускающие поиск, сначала необходимо определить индексированные поля. Мы предлагаем выбрать все атрибуты, с помощью которых пользователи могут искать и фильтровать клиентов на странице **Клиенты**. Можно указать только атрибуты, существующие в сущности профиля клиента, созданной в процессе объединения данных.

1. Открыть страницу **Клиенты** и выберите **Индекс поиска и фильтра**.

2. Выберите **+Добавить** чтобы указать индексированные поля.

3. Выберите в списке атрибуты, которые вы хотите добавить как индексированные поля. Вы всегда можете добавить больше атрибутов, выбрав **Добавить**. Вы также можете удалить любые выбранные атрибуты, выбрав символ **Удалить**.

## <a name="explore-the-indexed-customer-fields-table"></a>Изучение таблицы индексированных полей клиентов

В таблице представлены следующие сведения.

- **Имя**: представляет имя атрибута, как оно отображается в сущности профиля клиента.
- **Тип данных**: определяет, является ли тип данных строкой, числом или датой.
- **Включено в поиск**: указывается, может ли этот атрибут использоваться для поиска клиентов на странице **Клиенты** с помощью поля **Поиск**.
- **Добавить фильтр**: элемент управления для определения того, как этот атрибут может быть использован для фильтрации на странице **Клиенты**.

## <a name="editing-filtering-options-for-a-given-attribute"></a>Редактирование параметров фильтрации для определенного атрибута

Меню **Фильтр** на странице **Клиенты** может включать различное количество уровней атрибутов (например, различные возрастные группы для фильтрации клиентов).

1. Выберите **Добавить фильтр** для определенного атрибута на странице **Индекс поиска и фильтра**. Вы можете определить количество результатов и порядок, в котором они будут организованы. В зависимости от типа данных атрибута, появляется одна из следующих панелей.

- Атрибуты строкового типа: укажите желаемое количество результатов на панели **Параметры фильтра строк** и политику порядка, в котором они будут организованы.

- Атрибуты численного типа: укажите включаемые интервалы на панели **Параметры числового фильтра** и политику порядка, в котором они будут организованы.

- Атрибуты типа даты: укажите включаемые интервалы на панели **Параметры фильтра дат** и политику порядка, в котором они будут организованы.

2. Нажмите кнопку **Сохранить**, чтобы применить изменения.

3. Выберите **Выполнять**, когда будете готовы применить настройки. После обработки изменений вы найдете их в [карточках клиентов на странице клиента](customer-profiles.md). 

## <a name="next-steps"></a>Дальнейшие действия

Просмотрите [страницу единых профилей](customer-profiles.md) для поиска профилей или использования проиндексированных полей для просмотра подмножества всех единых профилей.


[!INCLUDE [footer-include](includes/footer-banner.md)]