---
title: Соединитель Power Apps
description: Соедините с Power Apps и Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: fc0af656cd5b436d9efd65b2a2c75dde9c9deb9dbcdd56ffc6a960f5878a631f
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031811"
---
# <a name="microsoft-power-apps-connector-preview"></a>Соединитель Microsoft Power Apps (предварительная версия)

Используйте унифицированные профили клиентов в своих персонализированных приложениях с помощью Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Подключение к Power Apps и Dynamics 365 Customer Insights

Customer Insights является одним из многих [доступных источников данных в Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Обратитесь к документации Power Apps, чтобы узнать, как [добавить подключение к данным в приложение](/powerapps/maker/canvas-apps/add-data-connection). Мы рекомендуем вам также просмотреть [как Power Apps использует делегирование для обработки больших наборов данных в приложениях на основе холста](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Доступные объекты

После добавления Customer Insights в качестве подключения к данным вы можете выбрать следующие сущности в Power Apps:

- Клиент: чтобы использовать данные из [единого профиля клиента](customer-profiles.md).
- UnifiedActivity: чтобы отображать [временную шкалу действия](activities.md) в приложении.

## <a name="limitations"></a>Ограничения

### <a name="retrievable-entities"></a>Извлекаемые сущности

Вы можете извлечь только сущности **Клиент**, **UnifiedActivity** и **Сегменты** через соединитель Power Apps. Другие сущности показаны, потому что базовый соединитель поддерживает их через триггеры в Power Automate.  

### <a name="delegation"></a>Делегирование

Делегирование работает для сущности "Клиент" и сущности UnifiedActivity. 

- Делегирование для сущности **Клиент**: чтобы использовать делегирование для этой сущности, поля должны быть проиндексированы в [Индекс поиска и фильтрации](search-filter-index.md).  

- Делегирование для **UnifiedActivity**: делегирование для этой сущности работает только для полей **ActivityId** и **CustomerId**.  

- Для получения дополнительной информации о делегировании см. раздел [Делегируемые функции и операции Power Apps](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Пример элемента управления галереи

Например, вы добавляете профили клиентов в [элемент управления коллекцией](/powerapps/maker/canvas-apps/add-gallery).

1. Добавьте элемент управления **Галерея** в приложение, которое вы создаете.

> [!div class="mx-imgBorder"]
> ![Добавление элемента галереи.](media/connector-powerapps9.png "Добавление элемента галереи")

1. Выберите **Клиент** как источник данных для элементов.

    > [!div class="mx-imgBorder"]
    > ![Выберите источник данных.](media/choose-datasource-powerapps.png "Выберите источник данных")

1. Вы можете изменить панель данных справа, чтобы выбрать, какое поле для сущности клиента отображать в галерее.

1. Если вы хотите показать какое-либо поле из выбранного клиента в галерее, заполните свойство "Текст" метки: **{Name_of_the_gallery}.Selected.{property_name}**

    Пример: Gallery1.Selected.address1_city

1. Чтобы отобразить унифицированную временную шкалу для клиента, добавьте элемент галереи и добавьте свойство элементов: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Пример: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]