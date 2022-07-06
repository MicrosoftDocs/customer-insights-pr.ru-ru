---
title: Используйте единые профили в Dynamics 365 Marketing
description: Узнайте, как интегрировать единые профили и сегменты в Dynamics 365 Marketing.
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99ec463299a24ea81cfe26bb785e36bdefdcd080
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054448"
---
# <a name="use-unified-customer-profiles-in-dynamics-365-marketing"></a>Использование единых профилей клиентов Unified customer profile в Dynamics 365 Marketing

[Dynamics 365 Marketing](/dynamics365/marketing/overview) повышает качество обслуживания клиентов, позволяя организовывать персонализированные циклы взаимодействия по всем точкам соприкосновения, чтобы укрепить отношения и заработать лояльность. Приложение Dynamics 365 Marketing легко работает с Dynamics 365 Sales Dynamics 365 Customer Insights, Microsoft Teams и другими продуктами и позволяет принимать более быстрые и качественные решения, используя возможности данных и искусственного интеллекта.

Возможности благодаря связывания данных Customer Insights с Marketing:

- Ориентация на унифицированные профили и сегменты клиентов. Это позволяет взаимодействовать с каждым клиентом независимо от места расположения данных клиента.
- Базовый динамический контент (например, персонализированные токены) в электронных письмах, SMS и push-уведомлениях по таким показателям, как статус лояльности, дата продления подписки, головная организация или любой другой показатель, который вы захватили в едином профиле Customer Insights.
- Загрузка данных из Marketing в Customer Insights и объединение их с данными клиентов из других источников.
- Применение средств очистки, обогащения и нечеткого соответствия данных Customer Insights.

## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>Использование богатых профилей клиентов в маркетинге в режиме реального времени

Маркетинг в режиме реального времени позволяет создавать [пользовательские триггеры](/dynamics365/marketing/real-time-marketing-custom-triggers), которые запускают циклы взаимодействия с клиентом на основе действий клиента. Чем более персонализированными будут ваши данные, тем более актуальными и персонализированными будут ваши циклы взаимодействия. Это главная ценность объединения Marketing и Customer Insights. Вы можете [унифицировать данные](data-unification.md) из любого источника, а затем использовать их для сверхперсонализированных циклов взаимодействия с клиентом.

Подробнее: [Узнайте, как использовать профили и сегменты Customer Insights в маркетинге в режиме реального времени](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>Использование унифицированных сегментов с исходящими циклами взаимодействия с клиентом

Customer Insights позволяет уточнять данные из многих источников и объединять их в агрегированные сегменты клиентов. [Связывая Customer Insights с исходящим маркетингом](export-dynamics365-marketing.md), эти сегменты автоматически появляются *и* обновляются в конструкторе циклов взаимодействия с клиентом.

Подробнее: [Использование сегментов из Dynamics 365 Customer Insights с Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>Извлечение данных из собственных Azure Data Lake Storage

Вы не ограничены облачным хранилищем, если хотите использовать данные Customer Insights с Marketing. Если у вас уже есть собственная настройка Azure Data Lake Storage, вы можете подключиться к Customer Insights, а затем поделиться данными с приложением Marketing так же, как и с облачной настройкой.

Подробнее: [Включение совместного использования данных с Dataverse из собственных данных Azure Data Lake Storage](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)
