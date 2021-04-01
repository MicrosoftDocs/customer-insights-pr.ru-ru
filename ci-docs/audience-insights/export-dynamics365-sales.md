---
title: Экспорт данных Customer Insights в Dynamics 365 Sales
description: Узнайте, как настроить подключение к Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598125"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Соединитель для Dynamics 365 Sales (предварительная версия)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Используйте свои данные о клиентах для создания маркетинговых списков, бизнес-процессов для дальнейших действий, а также рассылки предложений с помощью Dynamics 365 Sales.

## <a name="prerequisite"></a>Необходимые условия

1. Записи контактов должны присутствовать в Dynamics 365 Sales, прежде чем вы сможете экспортировать сегмент из Customer Insights в Sales. См. дополнительные сведения о загрузке контактов в [Dynamics 365 Sales с помощью Common Data Services](connect-power-query.md).

   > [!NOTE]
   > Экспорт сегментов из аналитики аудитории в Sales не приведет к созданию новых записей контактов в экземплярах Sales. Записи контактов из Sales должны быть загружены в аналитику аудитории и использованы как источник данных. Их также необходимо включить в объединенную сущность «Клиент», чтобы сопоставить идентификаторы клиентов с идентификаторами контактов, прежде чем сегменты можно будет экспортировать.

## <a name="configure-the-connector-for-sales"></a>Настройка соединителя для Sales

1. В аналитике аудитории перейдите **Администрирование** > **Экспорт пунктов назначения**.

1. В пункте **Dynamics 365 Sales** выберите **Настроить**.

1. Дайте вашему пункту назначения экспорта узнаваемое имя в поле **Отображаемое имя**.

1. Введите URL-адрес Sales вашей организации в поле **Адрес сервера**.

1. В разделе **Учетная запись администратора сервера** выберите **Войти** и выберите учетную запись Dynamics 365 Sales.

1. Сопоставьте поле идентификатора клиента с идентификатором контакта Dynamics 365.

1. Выберите **Далее**.

1. Выберите один или несколько сегментов.

1. Нажмите кнопку **Сохранить**.

## <a name="export-the-data"></a>Экспорт данных

Вы можете [экспортировать данных по требованию](export-destinations.md). Экспорт также будет выполняться с каждым [запланированным обновлением](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]