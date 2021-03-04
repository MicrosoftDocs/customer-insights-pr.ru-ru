---
title: Соединитель Power Apps
description: Соедините с Power Apps и Power Automate.
ms.date: 01/19/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a8bbb9a09218d54228589d43c21c8894680b56e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268932"
---
# <a name="microsoft-power-apps-connector-preview"></a>Соединитель Microsoft Power Apps (предварительная версия)

Используйте унифицированные профили клиентов в своих персонализированных приложениях с помощью Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Подключение к Power Apps и Dynamics 365 Customer Insights

Customer Insights является одним из многих [доступных источников данных в Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).

Обратитесь к документации Power Apps, чтобы узнать, как [добавить подключение к данным в приложение](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection). Мы рекомендуем вам также просмотреть [как Power Apps использует делегирование для обработки больших наборов данных в приложениях на основе холста](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).

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

- Для получения дополнительной информации о делегировании см. раздел [Делегируемые функции и операции Power Apps](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Пример элемента управления галереи

Например, вы добавляете профили клиентов в [элемент управления коллекцией](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).

1. Добавьте элемент управления **Галерея** в приложение, которое вы создаете.

> [!div class="mx-imgBorder"]
> ![Добавление элемента галереи](media/connector-powerapps9.png "Добавление элемента галереи")

1. Выберите **Клиент** как источник данных для элементов.

    > [!div class="mx-imgBorder"]
    > ![Выберите источник данных](media/choose-datasource-powerapps.png "Выберите источник данных")

1. Вы можете изменить панель данных справа, чтобы выбрать, какое поле для сущности клиента отображать в галерее.

1. Если вы хотите показать какое-либо поле из выбранного клиента в галерее, заполните свойство "Текст" метки: **{Name_of_the_gallery}.Selected.{property_name}**

    Пример: Gallery1.Selected.address1_city

1. Чтобы отобразить унифицированную временную шкалу для клиента, добавьте элемент галереи и добавьте свойство элементов: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Пример: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]