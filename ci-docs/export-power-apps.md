---
title: Соединитель Power Apps (предварительная версия)
description: Соедините с Power Apps и Power Automate.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 8807e82e65ea20d1a7f7dc07552229f377927eed
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196916"
---
# <a name="power-apps-connector-preview"></a>Соединитель Power Apps (предварительная версия)

Используйте унифицированные профили клиентов в своих персонализированных приложениях с помощью Microsoft Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Подключение к Power Apps и Dynamics 365 Customer Insights

Customer Insights является одним из многих [доступных источников данных в Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Обратитесь к документации Power Apps, чтобы узнать, как [добавить подключение к данным в приложение](/powerapps/maker/canvas-apps/add-data-connection). Мы рекомендуем вам также просмотреть [как Power Apps использует делегирование для обработки больших наборов данных в приложениях на основе холста](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Доступные объекты

После добавления Customer Insights в качестве подключения к данным выберите следующие сущности в Power Apps:

- **Клиент**: чтобы использовать данные из [единого профиля клиента](customer-profiles.md).
- **UnifiedActivity**: для отображения [временной шкалы действия](activities.md) в приложении.
- **ContactProfile**: для отображения контактов клиента. Эта сущность доступна только в средах Customer Insights для организаций.

## <a name="limitations"></a>Ограничения

### <a name="retrievable-entities"></a>Извлекаемые сущности

Вы можете получить только сущности **Customer**, **UnifiedActivity**, **Segments** и **ContactProfile** через соединитель Power Apps. ContactProfile доступна только в средах Customer Insights для организаций. Другие сущности показаны, потому что базовый соединитель поддерживает их через триггеры в Power Automate.

Вы можете сделать максимум 100 звонков за 60 секунд. Вы можете вызывать конечную точку API несколько раз, используя параметр $skip. [Узнайте больше о параметре $skip](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Делегирование

Делегирование работает для сущности **Клиент** и сущности **UnifiedActivity**.

- Делегирование для сущности **Клиент**: чтобы использовать делегирование для этой сущности, поля должны быть проиндексированы в [индекс поиска и фильтрации](search-filter-index.md).  
- Делегирование для **UnifiedActivity**: делегирование для этой сущности работает только для полей **ActivityId** и **CustomerId**.  
- Делегирование для **ContactProfile**: делегирование для этой сущности работает только для полей **ContactId** и **CustomerId**. ContactProfile доступна только в средах Customer Insights для организаций.

Для получения дополнительной информации о делегировании перейдите к [делегируемым функциям и операциям Power Apps](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="example-gallery-control"></a>Пример элемента управления галереи

При желании добавьте профили клиентов в [элемент управления коллекцией](/powerapps/maker/canvas-apps/add-gallery).

1. Добавьте элемент управления **коллекция** в приложение, которое вы создаете.
  
   :::image type="content" source="media/connector-powerapps9.png" alt-text="Добавление элемента галереи.":::

1. Выберите **Клиент** как источник данных для элементов.

   :::image type="content" source="media/choose-datasource-powerapps.png" alt-text="Выберите источник данных.":::

1. Измените панель данных справа, чтобы выбрать, какое поле для сущности клиента отображать в галерее.

1. Если вы хотите показать какое-либо поле из выбранного клиента в коллекции, заполните свойство **Текст** метки с помощью **{Name_of_the_gallery}.Selected{property_name}**.  
    - Например: _Gallery1.Selected.address1_city_

1. Чтобы отобразить единую временную шкалу для клиента, добавьте элемент коллекции и добавьте свойство **элементы** с помощью **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Например: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_

[!INCLUDE [footer-include](includes/footer-banner.md)]
