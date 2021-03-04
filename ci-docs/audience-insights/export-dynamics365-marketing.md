---
title: Экспорт данных Customer Insights в Dynamics 365 Marketing
description: Узнайте, как настроить подключение к Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269070"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Соединитель для Dynamics 365 Marketing (предварительная версия)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Используйте [сегменты](segments.md) для создания кампаний и связи с определенными группами клиентов с помощью Dynamics 365 Marketing. Дополнительные сведения см. в [Используйте сегменты из Dynamics 365 Customer Insights с Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Необходимые условия

- Записи контактов должны присутствовать в Dynamics 365 Marketing, прежде чем вы сможете экспортировать сегмент из Customer Insights в Marketing. См. дополнительные сведения о загрузке контактов в [Dynamics 365 Marketing с помощью Common Data Services](connect-power-query.md).

  > [!NOTE]
  > Экспорт сегментов из аналитики аудитории в Marketing не приведет к созданию новых записей контактов в экземплярах Marketing. Записи контактов из Marketing должны быть загружены в аналитику аудитории и использованы как источник данных. Их также необходимо включить в объединенную сущность «Клиент», чтобы сопоставить идентификаторы клиентов с идентификаторами контактов, прежде чем сегменты можно будет экспортировать.

## <a name="configure-the-connector-for-marketing"></a>Настройка соединителя для Marketing

1. В аналитике аудитории перейдите **Администрирование** > **Экспорт пунктов назначения**.

1. В пункте **Dynamics 365 Marketing** выберите **Настроить**.

1. Дайте вашему пункту назначения экспорта узнаваемое имя в поле **Отображаемое имя**.

1. Введите URL-адрес Marketing вашей организации в поле **Адрес сервера**.

1. В разделе **Учетная запись администратора сервера** выберите **Войти** и выберите учетную запись Dynamics 365 Marketing.

1. Сопоставьте поле идентификатора клиента с идентификатором контакта Dynamics 365.

1. Выберите **Далее**.

1. Выберите один или несколько сегментов.

1. Нажмите кнопку **Сохранить**.

## <a name="export-the-data"></a>Экспорт данных

Вы можете [экспортировать данных по требованию](export-destinations.md). Экспорт также будет выполняться с каждым [запланированным обновлением](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]