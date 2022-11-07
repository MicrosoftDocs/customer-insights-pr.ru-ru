---
title: Экспорт сегментов в Facebook Ads Manager (предварительная версия) (содержит видео)
description: Узнайте, как настроить подключение и экспорт в Facebook Ads Manager.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c7a4b1be1c959d70fad929b56452169b40e5b592
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724632"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Экспорт сегментов в Facebook Ads Manager (предварительная версия)

Экспортируйте сегменты унифицированных профилей клиентов в Facebook Ads Manager для создания кампаний в Facebook и Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>Предварительные условия

- [Учетная запись Facebook Ads](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), включающая в себя [бизнес-аккаунт Facebook](https://business.facebook.com/).
- Привилегии администратора в учетной записи [Facebook Ads](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).
- Пользовательские условия аудитории должны быть приняты пользователем, настраивающим соединение в Customer Insights.

## <a name="known-limitations"></a>Известные ограничения

- До 10 млн профилей клиентов на экспорт в Facebook Ads Manager, что может занять до 90 минут.
- Только сегменты.
- Интеграция с Facebook Ads не поддерживает пользователей с более чем 25 рекламными учетными записями.
- Тип *списка клиентов* Facebook только в [ пользовательские аудитории](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
  > [!NOTE]
  > В некоторых случаях в раскрывающемся списке можно увидеть пользовательские аудитории разных типов. Выбор типа, отличного от *список клиентов*, приведет к сбою экспорта.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Настройка подключения к Facebook Ads Manager

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Перейти в раздел **Администрирование** > **Подключения**.

1. Выберите **Добавить подключение** и выберите **Facebook Ads Manager**.

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Проверка подлинности с помощью Facebook Ads:

   1. Выберите **Продолжить с Facebook**, чтобы войти в свой рекламный аккаунт Facebook.

   1. Дайте разрешение **ads_management** после аутентификации с Facebook.

   1. Выберите **рекламный аккаунт Facebook**, с которым хотите работать.

   1. Выберите **Существующая пользовательская аудитория** из раскрывающегося списка или создайте **Новая пользовательская аудитория**.

1. Ознакомьтесь с положениями [Соответствие и конфиденциальность данных](connections.md#data-privacy-and-compliance) и выберите **Принимаю**.

1. Выберите **Сохранить**, чтобы завершить подключение.

## <a name="configure-an-export"></a>Настройка экспорта

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Выберите **Добавить экспорт**.

1. В поле **Подключение для экспорта** выберите подключение из раздела Facebook Ads Manager. Свяжитесь с администратором, если подключение недоступно.

1. Введите имя экспорта.

1. В поле **Подключите данные** выберите **Адрес электронной почты**, **Имя и адрес** или **Телефон**, чтобы отправить в Facebook Ads Manager.

1. Сопоставьте соответствующие атрибуты из вашей унифицированной сущности клиента с выбранным ключевым идентификатором.
   > [!TIP]
   > Наилучшие шансы на соответствие возникают, если вы выбираете **Адрес электронной почты** в качестве ключевого идентификатора. Добавление дополнительных идентификаторов может улучшить сопоставление.

1. Выберите **Добавить атрибут** для отображения дополнительных атрибутов для отправки в Facebook Ads Manager. Атрибуты из Facebook Ads Manager сопоставляются следующим понятным именам: **FN** = **Имя**, **LN** = **Фамилия**, **FI** = **Буква имени**, **PHONE** = **Телефон**, **GEN** = **Пол**, **DOB** = **Дата рождения**, **ST** = **Штат**, **CT** = **Город**, **ZIP** = **Почтовый индекс**, **COUNTRY** = **Страна/регион**

1. Выберите сегменты, которые нужно экспортировать.

1. Выберите **Сохранить**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
