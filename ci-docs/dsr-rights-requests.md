---
title: Запросы субъектов данных (DSR) в соответствии с GDPR | Документация Майкрософт
description: Отреагируйте на запросы субъекта данных для возможности аналитики аудитории Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350285"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Запросы субъектов данных (DSR) в соответствии с GDPR

Общий регламент по защите данных Европейского союза (GDPR) действует с 25 мая 2018 года. Это дает значительные права отдельным лицам в отношении их данных. GDPR призван защищать и обеспечивать права частных лиц на конфиденциальность. Вы можете узнать больше о приверженности Microsoft обеспечению безопасности и соответствия требованиям на веб-сайте [Центр управления безопасностью Microsoft](https://www.microsoft.com/trust-center).

Мы стремимся помочь нашим клиентам выполнить их требования GDPR. Она включает в себя право удалять и экспортировать данные, которые включают личные сведения, такие как ИД пользователей, номера телефонов и адреса электронной почты. Администраторы могут выполнять запросы пользователей на удаление или экспорт личных данных.

## <a name="audience-insights"></a>Аналитика аудитории

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Реагирование на запросы удаления субъекта данных GDPR для возможности аналитики аудитории Dynamics 365 Customer Insights

"Право на удаление" персональных данных из данных клиентов организации — одно из основных прав, предусмотренных Общим регламентом по защите данных (GDPR). Под удалением персональных данных понимается удаление всех персональных данных и формируемых системой журналов, за исключением информации журнала аудита.

#### <a name="manage-data-subject-delete-requests"></a>Управление запросами на удаление от субъектов данных

Аналитика аудитории предлагает следующие встроенные в продукт возможности удаления личных данных для конкретного клиента или пользователя:

- **Управление запросами на удаление данных клиента**: данные клиента в Customer Insights поступают из исходных источников данных, внешних по отношению к Customer Insights. Все запросы GDPR на удаление должны быть выполнены в оригинальном источнике данных.
- **Управление запросами на удаление пользовательских данных Customer Insights**: данные для пользователей создаются Customer Insights. Все запросы GDPR на удаление данных должны быть выполнены в Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Управление запросами на удаление данных клиента

Администратор Customer Insights может выполнить следующие действия, чтобы удалить данные клиента, которые были удалены в источнике данных:

1. Выполните вход в Dynamics 365 Customer Insights.
2. В аналитике аудитории перейдите **Данные** > **Источники данных**
3. Для каждого источника данных в списке, который содержит удаленные данные клиента:
   1. Выберите (...), затем выберите **обновить**.
   2. Проверьте состояние источника данных в разделе **Состояние**. Галочка означает, что обновление прошло успешно. Предупреждающий треугольник означает, что что-то пошло не так. Если отображается предупреждающий треугольник, свяжитесь с D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Обработка запросов GDPR на удаление данных клиента.](audience-insights/media/gdpr-data-sources.png "Обработка запросов GDPR на удаление данных клиента")

##### <a name="manage-delete-requests-for-user-data"></a>Управление запросами на удаление данных пользователей

Администратор Customer Insights может выполнить следующие действия для удаления данных пользователя Customer Insights:

1. Выполните вход в Dynamics 365 Customer Insights.
2. В аналитике аудитории перейдите **Администрирование** > **Разрешения**.
3. Установите флажок для пользователя, которого необходимо удалить.
4. Выберите **Удалить**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Ответ на запросы GDPR экспорта данных от субъектов данных

В рамках нашего обязательства сотрудничать с вами на пути к Общему регламенту по защите данных (GDPR) мы разработали документацию, которая поможет вам подготовиться. В этой документации описаны шаги, которые вы можете предпринять сегодня, чтобы обеспечить соответствие GDPR при использовании аналитики аудитории.

#### <a name="manage-export-and-view-requests"></a>Управление запросами на экспорт и просмотр

Право на переносимость данных гарантирует субъектам данных возможность запросить копию своих персональных данных в электронном формате ("структурированный, широко распространенный, машиночитаемый и совместимый с разными системами формат данных"), которая может быть передана другому управляющему данными.

##### <a name="export-customer-data-tenant-admin"></a>Экспорт данных клиентов (администратор клиента)

Для экспорта данных администратор клиента может выполнить следующие действия:

1. Отправить электронное письмо на адрес D365CI@microsoft.com, указав адрес электронной почты клиента в запросе. Рабочая группа Customer Insights отправит электронное письмо на зарегистрированный адрес электронной почты администратора клиента с просьбой подтвердить экспорт данных.
2. Подтвердите подтверждение экспорта данных для запрошенного клиента.
3. Получите экспортированные данные через адрес электронной почты администратора клиента.

##### <a name="export-user-data-tenant-admin"></a>Экспорт данных пользователей (администратор клиента)

1. Отправить электронное письмо на адрес D365CI@microsoft.com, указав адрес электронной почты пользователя в запросе. Рабочая группа Customer Insights отправит электронное письмо на зарегистрированный адрес электронной почты администратора клиента с просьбой подтвердить экспорт данных.
2. Подтвердите подтверждение экспорта данных для запрошенного пользователя.
3. Получите экспортированные данные через адрес электронной почты администратора клиента.

## <a name="consent-management-preview"></a>Управление согласием (предварительная версия)

Возможность управления согласием не собирает данные о пользователях напрямую. Она только импортирует и обрабатывает данные согласия, предоставленные пользователями в других приложениях.

Чтобы удалить данные о согласии для определенных пользователей, удалите их из источников данных, принятых для функции управления согласием. После обновления источника данных удаленные данные также будут удалены в Центре согласия. Приложения, использующие сущность согласия, также удаляют данные, которые были удалены в источнике, после [обновления](audience-insights/system.md#refresh-processes). Мы рекомендуем быстро обновлять источники данных после ответа на запрос субъекта данных об удалении данных пользователя из всех других процессов и приложений.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]