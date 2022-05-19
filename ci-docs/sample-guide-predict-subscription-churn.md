---
title: Пример руководства по прогнозу оттока подписок
description: Используйте этот пример руководства, чтобы попробовать готовую модель прогноза оттока подписок.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 5a8eeafecacef3d0bb4a798b698cf490423ca98d
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741427"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Пример руководства по прогнозу оттока подписок

Мы покажем вам комплексный пример прогноза оттока подписок, используя примеры данных, представленные ниже. 

## <a name="scenario"></a>Сценарий

Contoso — компания, производящая кофе и кофемашины высокого качества, которые они продают через свой веб-сайт Contoso Coffee. Недавно они открыли бизнес по подписке, чтобы клиенты могли получать кофе на регулярной основе. Их цель — понять, какие клиенты с подпиской могут отменить свою подписку в ближайшие несколько месяцев. Зная, кто из их клиентов **вероятно уйдет**, они могут сэкономить на маркетинговых усилиях, сосредоточив внимание на их удержании как клиентов.

## <a name="prerequisites"></a>Предварительные условия

- По крайней мере [разрешения участника](permissions.md) в Customer Insights.
- Мы рекомендуем вам выполнить следующие шаги [в новой среде](manage-environments.md).

## <a name="task-1---ingest-data"></a>Задача 1. Прием данных

Обзор статей [о приеме данных](data-sources.md) и [импорт источников данных с помощью соединителей Power Query](connect-power-query.md) специально. Следующая информация предполагает, что вы в целом ознакомились с приемом данных. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Получение данных о клиентах с платформы eCommerce

1. Создайте источник данных с именем **eCommerce**, выберите вариант импорта и выберите соединитель **Текст/CSV**.

1. Введите URL-адрес для контактов eCommerce https://aka.ms/ciadclasscontacts.

1. При редактировании данных выберите **Преобразовать**, затем **Использовать первую строку в качестве заголовков**.

1. Обновите тип данных для столбцов, перечисленных ниже:

   - **DateOfBirth**: дата
   - **CreatedOn**: дата/время/часовой пояс

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Преобразовать дату рождения в дату.":::

1. В поле **Имя** на правой панели переименуйте свой источник данных с **Query** на **eCommerceContacts**

1. Сохраните источник данных.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Получение данных о клиентах из схемы лояльности

1. Создайте источник данных с именем **LoyaltyScheme**, выберите вариант импорта и выберите соединитель **Текст/CSV**.

1. Введите URL-адрес для контактов eCommerce https://aka.ms/ciadclasscustomerloyalty.

1. При редактировании данных выберите **Преобразовать**, затем **Использовать первую строку в качестве заголовков**.

1. Обновите тип данных для столбцов, перечисленных ниже:

   - **DateOfBirth**: дата
   - **RewardsPoints**: целое число
   - **CreatedOn**: дата/время

1. В поле **Имя** на правой панели переименуйте свой источник данных с **Query** на **loyCustomers**.

1. Сохраните источник данных.

### <a name="ingest-subscription-information"></a>Прием информации о подписке

1. Создайте источник данных с именем **SubscriptionHistory**, выберите вариант импорта и выберите соединитель **Текст/CSV**.

1. Введите URL-адрес для контактов eCommerce https://aka.ms/ciadchurnsubscriptionhistory.

1. При редактировании данных выберите **Преобразовать**, затем **Использовать первую строку в качестве заголовков**.

1. Обновите тип данных для столбцов, перечисленных ниже:

   - **SubscriptioID**: целое число
   - **SubscriptionAmount**: валюта
   - **SubscriptionEndDate**: дата/время
   - **SubscriptionStartDate**: дата/время
   - **TransactionDate**: дата/время
   - **IsRecurring**: True/False
   - **Is_auto_renew**: True/False
   - **RecurringFrequencyInMonths**: целое число

1. В поле **Имя** на правой панели переименуйте свой источник данных с **Query** на **SubscriptionHistory**.

1. Сохраните источник данных.

### <a name="ingest-customer-data-from-website-reviews"></a>Получение данных о клиентах из отзывов веб-сайтов

1. Создайте источник данных с именем **Website**, выберите вариант импорта и выберите соединитель **Текст/CSV**.

1. Введите URL-адрес для контактов eCommerce https://aka.ms/ciadclasswebsite.

1. При редактировании данных выберите **Преобразовать**, затем **Использовать первую строку в качестве заголовков**.

1. Обновите тип данных для столбцов, перечисленных ниже:

   - **ReviewRating**: целое число
   - **ReviewDate**: дата

1. В поле "Имя" на правой панели переименуйте свой источник данных с **Query** на **webReviews**.

## <a name="task-2---data-unification"></a>Задача 2. Унификация данных

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-the-subscription-churn-prediction"></a>Задача 3. Настройте прогноз оттока подписок

С унифицированными профилями клиентов теперь мы можем запустить прогноз оттока подписок. Подробные инструкции см. в разделе [Прогноз оттока подписок](predict-subscription-churn.md). 

1. Перейдите **Аналитика** > **Обнаружить** и выберите **Модель оттока клиентов**.

1. Выберите вариант **Подписка** и выберите **Начать**.

1. Назовите модель **OOB Subscription Churn Prediction** и выходную сущность **OOBSubscriptionChurnPrediction**.

1. Определите два условия для модели оттока:

   * **Дней с момента окончания подписки**: **не менее 60 дней**. Если клиент не продлил свою подписку в течение этого периода после окончания срока ее действия, он считается ушедшим. 

   * **Определение оттока**: **не менее 93 дней**. Модель предсказывает продолжительность оттока клиентов. Чем дальше в будущее, тем менее точны результаты.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Выберите для модели Окно прогноза и Определение оттока.":::

1. Выберите **Добавление необходимых данных** и выберите **Добавить данные** для истории подписок.

1. Добавьте сущность **Subscription : SubscriptionHistory** и сопоставьте поля из eCommerce с соответствующими полями, необходимыми для модели.

1. Присоедините сущность **Subscription : SubscriptionHistory** к **eCommerceContacts : eCommerce**, назовите отношение **eCommerceSubscription**.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Присоедините сущности eCommerce.":::

1. В разделе действия клиентов добавьте сущность **webReviews : Website** и сопоставьте поля из webReviews с соответствующими полями, необходимыми для модели. 
   - Первичный ключ: ReviewId
   - Метка времени: ReviewDate
   - Событие: ReviewRating

1. Настройте действие для обзоров веб-сайтов. Выберите действие **Обзор** и присоедините сущность **webReviews : Website** к **eCommerceContacts : eCommerce**.

1. Выберите **Далее**, чтобы задать расписание модели.

   Модель должна регулярно обучаться, чтобы изучать новые закономерности при поступлении новых данных. В данном примере выберите **Ежемесячно**.

1. Изучив все сведения, выберите **Сохранить и выполнить**.

## <a name="task-4---review-model-results-and-explanations"></a>Задача 4. Обзор результатов модели и объяснения

Дайте модели завершить обучение и оценку данных. Теперь вы можете просмотреть объяснения модели оттока подписок. Для получения дополнительной информации см. [Просмотр статуса прогноза и результатов](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Задача 5. Создайте сегмент клиентов с высоким риском оттока

Выполнение производственной модели создает новую сущность, которую вы можете увидеть в **Данные** > **Сущности**.   

Вы можете создать новый сегмент на основе сущности, созданной моделью.

1.  Перейдите **Сегменты**. Выберите **Создать** и выберите **Создать из** > **Аналитика**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Создание сегмента с выходом модели.":::

1. Выберите конечную точку **OOBSubscriptionChurnPrediction** и определите сегмент: 
   - Поле: ChurnScore
   - Оператор: больше
   - Значение: 0,6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Настройте сегмент оттока подписок.":::

Теперь у вас есть динамически обновляемый сегмент, который определяет клиентов с высоким риском оттока для этого бизнеса по подписке.

Дополнительные сведения см. в разделе [Создание сегментов и управление ими](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]