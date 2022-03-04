---
title: Соединитель Power Apps
description: Соедините с Power Apps и Power Automate.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: ae2a3b7c05e9ed860da31853c47af2aec8634e7a
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229048"
---
# <a name="microsoft-power-apps-connector-preview"></a>Соединитель Microsoft Power Apps (предварительная версия)

Используйте унифицированные профили клиентов в своих персонализированных приложениях с помощью Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Подключение к Power Apps и Dynamics 365 Customer Insights

Customer Insights является одним из многих [доступных источников данных в Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Обратитесь к документации Power Apps, чтобы узнать, как [добавить подключение к данным в приложение](/powerapps/maker/canvas-apps/add-data-connection). Мы рекомендуем вам также просмотреть [как Power Apps использует делегирование для обработки больших наборов данных в приложениях на основе холста](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Доступные объекты

После добавления Customer Insights в качестве подключения к данным вы можете выбрать следующие сущности в Power Apps:

- **Клиент**: чтобы использовать данные из [единого профиля клиента](customer-profiles.md).
- **UnifiedActivity**: для отображения [временной шкалы действия](activities.md) в приложении.
- **ContactProfile**: для отображения контактов клиента. Эта сущность доступна только в средах аналитики аудитории для организаций.

## <a name="limitations"></a>Ограничения

### <a name="retrievable-entities"></a>Извлекаемые сущности

Вы можете получить только сущности **Customer**, **UnifiedActivity**, **Segments** и **ContactProfile** через соединитель Power Apps. ContactProfile доступна только в экземпляре аналитики аудитории для организаций. Другие сущности показаны, потому что базовый соединитель поддерживает их через триггеры в Power Automate.

### <a name="delegation"></a>Делегирование

Делегирование работает для сущности **Клиент** и сущности **UnifiedActivity**. 

- Делегирование для сущности **Клиент**: чтобы использовать делегирование для этой сущности, поля должны быть проиндексированы в [Индекс поиска и фильтрации](search-filter-index.md).  
- Делегирование для **UnifiedActivity**: делегирование для этой сущности работает только для полей **ActivityId** и **CustomerId**.  
- Делегирование для **ContactProfile**: делегирование для этой сущности работает только для полей **ContactId** и **CustomerId**. ContactProfile доступна только в средах аналитики аудитории для организаций.

Для получения дополнительной информации о делегировании перейдите к [делегируемым функциям и операциям Power Apps](/powerapps/maker/canvas-apps/delegation-overview). 

## <a name="example-gallery-control"></a>Пример элемента управления галереи

Вы можете добавить профили клиентов в [элемент управления коллекцией](/powerapps/maker/canvas-apps/add-gallery).

1. Добавьте элемент управления **коллекция** в приложение, которое вы создаете.

    > [!div class="mx-imgBorder"]
    > ![Добавление элемента галереи.](media/connector-powerapps9.png "Добавление элемента коллекции.")

2. Выберите **Клиент** как источник данных для элементов.

    > [!div class="mx-imgBorder"]
    > ![Выберите источник данных.](media/choose-datasource-powerapps.png "Выберите источник данных.")

3. Вы можете изменить панель данных справа, чтобы выбрать, какое поле для сущности клиента отображать в галерее.

4. Если вы хотите показать какое-либо поле из выбранного клиента в коллекции, заполните свойство **Текст** метки с помощью **{Name_of_the_gallery}.Selected{property_name}**.  
    - Например: _Gallery1.Selected.address1_city_

5. Чтобы отобразить единую временную шкалу для клиента, добавьте элемент коллекции и добавьте свойство **элементы** с помощью **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Например: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE[footer-include](../includes/footer-banner.md)]
