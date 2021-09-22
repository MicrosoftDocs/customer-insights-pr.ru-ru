---
title: Создание связи между аналитикой аудитории и аналитикой взаимодействий
description: Создайте активную связь между аналитикой аудитории и аналитикой взаимодействий, чтобы обеспечить двунаправленный обмен данными.
ms.date: 07/22/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 870209a7e19fec464ec41462a02365771bd653bd
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461029"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Создание связи между аналитикой аудитории и аналитикой взаимодействий

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Интеграция аналитики взаимодействия и аналитики аудитории связывает среды из обеих возможностей и позволяет двунаправленно обмениваться данными между ними.

Используйте объединенные профили и сегменты из аналитики аудитории, чтобы получить больше возможностей анализа в аналитике взаимодействий. Экспортируйте события, которые имеют высокую ценность для бизнеса, из аналитики взаимодействий. Используйте эти события для добавления данных в объединенные профили в аналитике аудитории.

## <a name="prerequisites"></a>Предварительные условия

- Профили аналитики аудитории должны храниться в учетной записи Azure Data Lake Storage, которой вы владеете, или в [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md)&ndash;управляемом озере данных. 

- Вам потребуются разрешения администратора как для среды аналитики взаимодействия, так и для среды аналитики аудитории.

- Связанные среды должны находиться в одном географическом регионе.

> [!NOTE]
> - Если ваша подписка на аналитику аудитории является пробной, в которой используется озеро данных Data Lake, управляемое внутри аналитики аудитории, свяжитесь с [pirequest@microsoft.com](mailto:pirequest@microsoft.com) для получения помощи. 
> - Если в вашей среде аналитики аудитории используется ваше собственное хранилище Azure Data Lake Storage для хранения данных, вам необходимо добавить субъект-службу Azure аналитики взаимодействия в свою учетную запись хранения. Для получения подробной информации перейдите в раздел [Подключение к учетной записи Azure Data Lake Storage с субъект-службой Azure для аналитики аудитории](../audience-insights/connect-service-principal.md). Кроме того, ваша среда аналитики аудитории должна иметь связанную [среду Dataverse](../audience-insights/get-started-paid.md). 

## <a name="create-an-environment-link"></a>Создание связи сред

Вы можете создать связь сред, обновив параметры **Администратор** > **Среда** в аналитике взаимодействия.

**Чтобы установить активную связь между аналитикой аудитории и аналитикой взаимодействий**

1. На странице **Администрирование среды** выберите вкладку **Связать среды**.

    :::image type="content" source="media/integrate1.png" alt-text="Настройка среды.":::

1. Выберите **Настроить среды** в верхнем левом углу или внизу экрана.

     :::image type="content" source="media/integrate2.png" alt-text="Выбор среды анализа аудитории.":::

1. Выберите среду аналитики аудитории, затем выберите ***Далее**, чтобы завершить. Теперь вы можете выбрать дополнительные функции для связанных сред.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Включение атрибутов и сегментов объединенных профилей аналитики аудитории

После связывания сред вы можете выбрать дополнительные функции для связанных сред. Эти функции позволяют использовать атрибуты и сегменты объединенного профиля из аналитики аудитории для интерактивного анализа данных о клиентах.

**Чтобы анализировать веб-данные для аналитики взаимодействия**

1. На странице **Администрирование сред** включите выключатель **Передача данных из аналитики аудитории в аналитику взаимодействий**, затем выберите **Далее**.

    :::image type="content" source="media/integrate4.png" alt-text="Выберите функции.":::

1. Выберите атрибуты объединенных профилей, которые станут измерениями в аналитике взаимодействия. (Не все атрибуты являются полезными измерениями. Например, вряд ли вам понадобится **Имя** или **Фамилия** как атрибут для анализа событий вашего веб-сайта.)

    :::image type="content" source="media/integrate5.png" alt-text="Подбор измерений.":::

   >[!NOTE]
   > Все атрибуты профиля аналитики аудитории, представляющие идентификаторы (например, **ИД** и **альтернативный ИД**) отфильтровываются из доступных атрибутов и становятся измерениями в аналитике взаимодействия.

1. Когда вы закончите выбор атрибутов, выберите **Далее**.
1. Добавьте пользователей, которые могут просматривать измерения и сегменты профиля аналитики аудитории в аналитике взаимодействия.

    :::image type="content" source="media/integrate6.png" alt-text="Управление доступом к данным клиентов.":::

   > [!IMPORTANT]
   > Если вы явно не добавите пользователей на этом этапе, данные будут скрыты от пользователей в аналитике взаимодействия.

1. Просмотрите выбранные параметры, затем выберите **Готово**.

    :::image type="content" source="media/integrate7.png" alt-text="Просмотрите параметры данных клиентов.":::

## <a name="export-refined-events-to-audience-insights"></a>Экспорт уточненных событий в аналитику аудитории

После создания связи между средами вы можете экспортировать уточненные события из аналитики взаимодействия в аналитику аудитории и принять их как новый источник данных. 

Дополнительные сведения см. в разделе [Интеграция веб-данных из аналитики взаимодействия с аналитикой аудитории](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
