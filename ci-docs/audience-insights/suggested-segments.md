---
title: Предложенные сегменты на основе машинного обучения
description: Позвольте машинному обучению помочь вам найти новые и интересные сегменты на основе атрибутов клиентов.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: bbc22adcd7b6e756fa6128abd855795de7480f2d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597113"
---
# <a name="suggested-segments-preview"></a>Предлагаемые сегменты (предварительная версия)

Откройте для себя интересные сегменты своих клиентов с помощью модели ИИ. Эта функция машинного обучения предлагает сегменты на основе мер или атрибутов клиентов. Это может помочь улучшить ваши ключевые показатели эффективности или лучше понять влияние атрибутов в контексте других атрибутов. 

> [!NOTE]
> Функция предлагаемых сегментов использует автоматизированные средства для оценки данных и создания прогнозов на основе этих данных и, следовательно, может использоваться в качестве метода профилирования, как этот термин определен Общим регламентом по защите данных («GDPR»). Использование вами этой функции для обработки данных может регулироваться GDPR или другими законами или постановлениями. Вы несете ответственность за то, что использование Dynamics 365 Customer Insights, включая данную функцию, соответствует всем применимым законам и требованиям, включая законы, касающиеся конфиденциальности, личных данных, биометрических данных, защиты данных и конфиденциальности сообщений.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Страница предлагаемых сегментов в Customer Insights со сведениям о предложении на боковой панели.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Предлагаемые сегменты для улучшения ваших KPI

Как у пользователя аналитики аудитории, у вас, вероятно, есть ряд [созданных мер](measures.md), которые помогают отслеживать ваши ключевые показатели эффективности (KPI). Важно понимать, как определенные атрибуты влияют на эти KPI, чтобы создавать сегменты и проводить целенаправленную кампанию.   
Например, вы отслеживаете меру под названием *TotalSpendPerCustomer*. Как бизнес, вы хотели бы, чтобы это число росло. Выбор меры в качестве основного атрибута позволяет выбрать атрибуты, влияние которых вы хотите оценить. Допустим, *уровень участия*, *период участие* и *род деятельности*. Затем Customer Insights может предложить сегмент, который расскажет вам, кто больше всего влияет на этот показатель. Например, *Бухгалтеры* со статусом *Золото*, которые были с вашим бизнесом в течение *минимум пяти лет*, оказали наибольшее влияние на *TotalSpendPerCustomer*. Вы получите приблизительный размер сегмента для каждого предложения. Вы можете использовать эту информацию для создания кампаний для целевой аудитории.

## <a name="understand-what-influences-a-customer-attribute"></a>Понимание того, что влияет на атрибут клиента

Вы можете выбрать атрибут клиента вместо меры в качестве основного атрибута. На основе вашего выбора влияющих атрибутов модель ИИ создает серию предложений, которые показывают, как выбранные атрибуты влияют на основной атрибут.   
Например, вы выбираете *Участник вознаграждения (да/нет)* в качестве основного атрибута. *Срок использования*, *Род занятий* и *Количество запросов в службу поддержки* установлены как другие влияющие атрибуты. Модель ИИ может предлагать сегменты, указывающие, что в основном ИТ-специалисты со стажем работы более двух лет являются участниками вознаграждения. Другое предложение могло бы подчеркнуть, что бухгалтеры со стажем работы более одного года и с менее чем тремя запросами в службу поддержки являются участниками вознаграждения. 

## <a name="artificial-intelligence-usage"></a>Использование искусственного интеллекта

Используя первичный атрибут и влияющие атрибуты, алгоритм дерева решений предлагает интересные сегменты. Предложения основаны на правилах или шаблонах, которые были подобраны алгоритмом ИИ. В качестве предложений показаны только те сегменты, которые значительно отличаются от среднего. Сравнение со средней численностью основано на выбранной мере или первичном атрибуте.

### <a name="responsible-ai"></a>Ответственный ИИ

Предлагаемые сегменты позволяют выбирать атрибуты для создания новых сегментов и обработки выбранных данных. При выборе атрибутов, включающих такие конфиденциальные атрибуты, как раса, сексуальная ориентация или пол, вы должны убедиться, что вы можете обрабатывать эти данные и они вам действительно нужны. Вы несете ответственность за соблюдение всех законов, применимых к вашей организации, а также за соблюдение принципов и политик конфиденциальности вашей организации.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Различные результаты для основных атрибутов с категориальными и числовыми значениями

Предложения по сегментам различаются, если вы выбираете числовой атрибут или категориальный атрибут в качестве основного атрибута. Значения в категориальном атрибуте содержат две или более категорий или типов. Числовой атрибут содержит количественные данные и связан с измерением.

С числовым атрибутом, например *годовой доход* или *период участия* в качестве основного атрибута система предлагает сегменты, у которых среднее значение числового атрибута выше или ниже по сравнению со всеми клиентами.

Категорический атрибут вроде *удовлетворенность клиента* в качестве основного атрибута приводит к предлагаемым сегментам, в которых процент клиентов, принадлежащих к определенной категории, выше или ниже по сравнению с процентом всех клиентов, принадлежащих к той же категории. Например, *удовлетворенность клиентов* выбран в качестве основного атрибута и состоит из трех категорий (*низкая*, *средняя* и *высокая*). Для каждой категории будут предложены сегменты, в которых процент клиентов, принадлежащих к этой категории, значительно выше или ниже по сравнению с долей всех клиентов в той же категории. Если у 22% всех клиентов есть удовлетворенность *высокая*, следовательно, только сегменты, в которых доля клиентов с гораздо большей или меньшей долей *высокая* по сравнению с 22% будут предложены для этой категории. Аналогичным образом сегменты будут предложены для каждой из других категорий (*низкая* и *средняя*), если они статистически значимы.

> [!NOTE]
> В настоящее время мы поддерживаем только основные категориальные атрибуты, содержащие до 10 категорий. Если вы хотите видеть предложения сегментов на основе основного атрибута с более чем 10 категориями, мы рекомендуем сгруппировать некоторые категории, чтобы уменьшить количество категорий до 10 или меньше. Это ограничение применяется только к основным атрибутам. Для влияния на категориальные атрибуты в настоящее время мы поддерживаем максимум 100 категорий.

## <a name="generate-suggested-segments"></a>Создание предлагаемых сегментов

1. Перейдите **Сегменты**.

1. Выберите вкладку **Предложения (предварительная версия)**.

1. Выберите **Получить новые предложения**, чтобы начать работу с интерфейсом с подсказками.

1. Выберите меру или атрибут клиента в качестве основного атрибута и выберите **Далее**.

   :::image type="content" source="media/suggested-segments-primary-attribute.png" alt-text="Выбор основного атрибута для предложений по предлагаемым сегментам.":::

1. Выберите влияющие атрибуты и выберите **Сохранить**.
   
   > [!TIP]
   > Выбор нескольких влияющих атрибутов увеличивает шансы оценить, как они влияют на основной атрибут. Не включайте атрибуты, которые не влияют на основной атрибут. Например, если все ваши клиенты из определенной страны, не включайте атрибут *страна*, потому что он не повлияет на выходные данные.

1. В зависимости от количества профилей клиентов и выбранных атрибутов обработка выбранных атрибутов может занять несколько минут. 

## <a name="view-details-of-a-suggested-segment"></a>Просмотр сведений о предлагаемом сегменте

После того, как модель ИИ сгенерирует предложения, вы найдете их в списке в **Сегменты** > **Предложения (предварительная версия)**.
 
Выберите предлагаемый сегмент, чтобы просмотреть подробные сведения об этом предложении, включая сравнение среднего значения и количества участников сегмента. Вы также можете просмотреть значения атрибутов или правила, которым научилась модель ИИ, чтобы предложить выбранный сегмент.

## <a name="save-a-suggestion-as-a-segment"></a>Сохранение предложения в качестве сегмента

1. Перейдите **Сегменты** > **Предложения (предварительная версия)**.

1. Выберите сегмент для сохранения. 

1. На боковой панели выберите **Сохранить как сегмент**. 

1. После сохранения сегмента он отобразится в списке сегментов на вкладке **Все сегменты**. Теперь его можно [обновить, отредактировать или удалить, как и любой другой сегмент](segments.md).

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Обновите или отредактируйте набор предложений

1. Перейдите **Сегменты** > **Предложения (предварительная версия)**.

1. Выберите **Обновить предложения** для обновления предложений, сохранив настроенные атрибуты. Или выберите **Редактировать атрибуты** для изменения настроенных атрибутов. Система повторно запустит модель ИИ, сгенерирует предложения сегментов на основе последних данных и заменит текущие предложения.

## <a name="limitations"></a>Ограничения

1. Несовпадение предполагаемого размера сегмента: если вы выберете основной атрибут, который содержит пустые значения, это может повлиять на предполагаемый размер сегмента в предложениях сегментов. При сохранении такого сегмента фактический размер сегмента может отличаться от исходной оценки.
 
2. Первичные атрибуты логического типа не работают: в настоящее время мы поддерживаем только строковые и числовые типы данных в качестве первичных атрибутов.

3. Предлагаемые сегменты недостаточно различимы: имейте в виду, что выбранные атрибуты и распределение значений этих атрибутов влияют на результаты. Вы можете изменить свои влияющие атрибуты или даже свой основной атрибут, чтобы получить другие результаты.



[!INCLUDE[footer-include](../includes/footer-banner.md)]