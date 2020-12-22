---
title: Экспорт данных Customer Insights в Dynamics 365 Sales
description: Узнайте, как настроить подключение к Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643834"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Соединитель для Dynamics 365 Sales (предварительная версия)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Используйте свои данные о клиентах для создания маркетинговых списков, бизнес-процессов для дальнейших действий, а также рассылки предложений с помощью Dynamics 365 Sales.

## <a name="prerequisite"></a>Необходимые условия

Записи контактов, [полученные из Dynamics 365 Sales с помощью Common Data Service](connect-power-query.md).

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
