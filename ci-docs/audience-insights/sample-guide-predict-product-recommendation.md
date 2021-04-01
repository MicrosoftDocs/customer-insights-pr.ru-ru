---
title: Руководство по прогнозу рекомендаций продуктов
description: Используйте этот пример руководства, чтобы попробовать готовую модель прогноза рекомендаций продуктов.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 20072d14b160e54f5ad044adc1de6c079bf790e4
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595289"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a>Руководство по прогнозу рекомендаций продуктов (предварительная версия)

Мы покажем вам комплексный пример прогноза рекомендаций продуктов, используя примеры данных, представленные ниже.

## <a name="scenario"></a>Сценарий

Contoso — компания, производящая кофе и кофемашины высокого качества, которые они продают через свой веб-сайт Contoso Coffee. Их цель — понять, какие продукты они должны рекомендовать своим постоянным клиентам. Знание того, какие клиенты, **скорее всего, совершат покупку**, может помочь им сэкономить маркетинговые ресурсы, сосредоточив внимание на конкретных товарах.

## <a name="prerequisites"></a>Предварительные условия

- По крайней мере [разрешения участника](permissions.md) в Customer Insights.
- Мы рекомендуем вам выполнить следующие шаги [в новой среде](manage-environments.md).

## <a name="task-1---ingest-data"></a>Задача 1. Прием данных

Просмотрите статьи [о приеме данных](data-sources.md) и [импорте источников данных с помощью соединителей Power Query](connect-power-query.md). Следующая информация предполагает, что вы в целом ознакомились с приемом данных.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Получение данных о клиентах с платформы eCommerce

1. Создайте источник данных с именем **eCommerce**, выберите вариант импорта и выберите соединитель **Текст/CSV**.

1. Введите URL-адрес для контактов eCommerce https://aka.ms/ciadclasscontacts.

1. При редактировании данных выберите **Преобразовать**, затем **Использовать первую строку в качестве заголовков**.

1. Обновите тип данных для столбцов, перечисленных ниже:
   - **DateOfBirth**: дата
   - **CreatedOn**: дата/время/часовой пояс

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Преобразовать дату рождения в дату.":::

5. В поле "Имя" на правой панели переименуйте свой источник данных с **Query** на **eCommerceContacts**.

6. **Сохраните** источник данных.

### <a name="ingest-online-purchase-data"></a>Получение данных о покупках в Интернете

1. Добавьте другой набор данных к тому же источнику данных **eCommerce**. Снова выберите соединитель **Текст/CSV**.

1. Введите URL-адрес для данных **Интернет-покупки** https://aka.ms/ciadclassonline.

1. При редактировании данных выберите **Преобразовать**, затем **Использовать первую строку в качестве заголовков**.

1. Обновите тип данных для столбцов, перечисленных ниже:
   - **PurchasedOn**: дата/время
   - **TotalPrice**: валюта

1. В поле **Имя** на боковой панели переименуйте свой источник данных с **Query** на **eCommercePurchases**.

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

## <a name="task-2---data-unification"></a>Задача 2. Унификация данных

После приема данных мы запускаем процесс **Сопоставление, совпадение, объединение** для создания унифицированного профиля клиента. Дополнительные сведения см. в разделе [Унификация данных](data-unification.md).

### <a name="map"></a>Сопоставление

1. После приема данных сопоставьте контакты из данных eCommerce и лояльности с общими типами данных. Перейдите **Данные** > **Унификация** > **Сопоставление**.

2. Выберите сущности, которые представляют профиль клиента — **eCommerceContacts** и **loyCustomers**.

   ![унифицировать источники данных ecommerce и лояльности.](media/unify-ecommerce-loyalty.png)

3. Выберите **ContactId** как первичный ключ для **eCommerceContacts**, а **LoyaltyID** как первичный ключ для **loyCustomers**.

   ![Унифицируйте LoyaltyId как первичный ключ.](media/unify-loyaltyid.png)

### <a name="match"></a>Совпадение найдено

1. Перейдите на вкладку **Совпадение** и выберите **Задать порядок**.

2. В раскрывающемся списке **Первичный** выберите **eCommerceContacts : eCommerce** в качестве первичного источника и включите все записи.

3. В раскрывающемся списке **Сущность 2** выберите **loyCustomers: LoyaltyScheme** и включите все записи.

   ![Унифицировать совпадение eCommerce и лояльности.](media/unify-match-order.png)

4. Выберите **Создать правило**

5. Добавьте свое первое условие, используя FullName.

   - Для eCommerceContacts выберите **FullName** в раскрывающемся списке.
   - Для loyCustomers выберите **FullName** в раскрывающемся списке.
   - Выберите раскрывающийся список **Нормализовать** и выберите **Тип (телефон, имя, адрес, ...)**.
   - Задайте **Уровень точности**: **Базовый** и **Значение**: **Высоко**.

6. Введите имя **FullName, Email** для нового правила.

   - Добавьте второе условие для адреса электронной почты, выбрав **Добавить условие**
   - Для сущности eCommerceContacts выберите **EMail** в раскрывающемся списке.
   - Для сущности loyCustomers выберите **EMail** в раскрывающемся списке.
   - Оставьте поле "Нормализация" пустым.
   - Задайте **Уровень точности**: **Базовый** и **Значение**: **Высоко**.

   ![Унифицировать правило совпадения для имени и электронной почты.](media/unify-match-rule.png)

7. Выберите **Сохранить** и **Выполнить**.

### <a name="merge"></a>Объединение

1. Перейдите на вкладку **Объединение**.

1. В **ContactId** для сущности **loyCustomers** измените отображаемое имя на **ContactIdLOYALTY**, чтобы отличить его от других полученных идентификаторов.

   ![Переименовать contactid из идентификатора лояльности.](media/unify-merge-contactid.png)

1. Выберите **Сохранить** и **Выполнить**, чтобы начать процесс объединения.

## <a name="task-3---configure-product-recommendation-prediction"></a>Задача 3. Настройка прогноза рекомендаций продуктов

С унифицированными профилями клиентов теперь мы можем запустить прогноз оттока подписок.

1. Перейдите **Аналитика** > **Прогноз**, выберите **Рекомендация продукта**.

1. Выберите **Приступая к работе**.

1. Назовите модель **Прогноз модели рекомендации продуктов OOB** и сущность выходных данных **OOBProductRecommendationModelPrediction**.

1. Определите три условия для модели:

   - **Количество продуктов**: установите это значение как **5**. Этот параметр определяет, сколько продуктов вы хотите рекомендовать своим клиентам.

   - **Предлагать товары, которые клиенты недавно приобрели?**: выберите **Да**, чтобы указать, что вы хотите включить в рекомендацию продукты, которые ваши клиенты покупали ранее.

   - **Окно ретроспективного обзора:** выберите не менее **365 дней**. Этот параметр определяет, как далеко модель будет анализировать действия клиента, чтобы использовать их в качестве исходных данных для своих рекомендаций.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Настройки модели для модели рекомендаций по продукту.":::

1. Выберите **Необходимые данные** и выберите **Добавить данные** для истории покупок.

1. Добавьте сущность **eCommercePurchases : eCommerce** и сопоставьте поля из eCommerce с соответствующими полями, необходимыми для модели.

1. Присоедините сущность **eCommercePurchases : eCommerce** к **eCommerceContacts : eCommerce**.

   ![Присоедините сущности eCommerce.](media/model-purchase-join.png)

1. Выберите **Далее**, чтобы задать расписание модели.

   Модель должна регулярно обучаться, чтобы изучать новые закономерности при поступлении новых данных. В данном примере выберите **Ежемесячно**.

1. Изучив все сведения, выберите **Сохранить и выполнить**.


## <a name="task-4---review-model-results-and-explanations"></a>Задача 4. Обзор результатов модели и объяснения

Дайте модели завершить обучение и оценку данных. Теперь вы можете просмотреть объяснения модели рекомендаций продуктов. Для получения дополнительной информации см. [Просмотр статуса прогноза и результатов](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Задача 5. Создание сегмента часто покупаемых товаров

Выполнение производственной модели создает новую сущность, которую вы можете увидеть в **Данные** > **Сущности**.

Вы можете создать новый сегмент на основе сущности, созданной моделью.

1. Перейдите **Сегменты**. Выберите **Создать** и выберите **Создать из** > **Аналитика**.

   ![Создание сегмента с выходом модели.](media/segment-intelligence.png)

1. Выберите конечную точку **OOBProductRecommendationModelPrediction** и определите сегмент:

   - Поле: ProductID
   - Оператор: Значение
   - Значение: выберите три первых кода продукта.

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Создайте сегмент из результатов модели.":::

Теперь у вас есть динамически обновляемый сегмент, который определяет клиентов, которые более охотно покупают три наиболее рекомендуемых продукта. 

Дополнительные сведения см. в разделе [Создание сегментов и управление ими](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]