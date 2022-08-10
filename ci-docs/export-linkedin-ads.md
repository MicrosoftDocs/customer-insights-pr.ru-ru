---
title: Экспорт сегментов в LinkedIn Ads (предварительная версия)
description: Узнайте, как настроить подключение и экспорт в LinkedIn Ads.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d1a9ae985043398f4bc38163be26ecf0c3c8e2ba
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196824"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Экспорт сегментов в LinkedIn Ads (предварительная версия)

Экспортируйте сегменты единых профилей клиентов в LinkedIn Ads для создания сопоставленных аудиторий. Используйте сопоставленные аудитории для таргетинга на компании и контакты.

## <a name="prerequisites"></a>Предварительные условия

- [Учетная запись LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) и соответствующие учетные данные администратора.
- [Идентификатор учетной записи LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).
- [Настроенные сегменты](segments.md) в Customer Insights.
- Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.

## <a name="known-limitations"></a>Известные ограничения

- До 100 000 профилей клиентов на экспорт в LinkedIn Ads, что может занять до 10 минут.
- Только сегменты. Сегмент должен содержать не менее 300 уникальных профилей.

## <a name="set-up-connection-to-linkedin-ads"></a>Настройка подключения к LinkedIn Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Перейти в раздел **Администрирование** > **Подключения**.

1. Выберите **Добавить подключение** и выберите **LinkedIn Ads**.

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. Укажите, кто может использовать это подключение. По умолчанию это только администраторы. Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Предоставьте ваш идентификатор учетной записи LinkedIn Campaign Manager.

1. Ознакомьтесь с положениями [Соответствие и конфиденциальность данных](connections.md#data-privacy-and-compliance) и выберите **Принимаю**.

1. Выберите **Подключиться** для инициализации подключения.

1. Выберите **Проверка подлинности в LinkedIn** и укажите свои учетные данные администратора для LinkedIn Campaign Manager.

1. Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.

1. Выберите **Сохранить**, чтобы завершить подключение.

## <a name="configure-an-export"></a>Настройка экспорта

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Выберите **Добавить экспорт**.

1. В поле **Подключение для экспорта** выберите подключение из раздела LinkedIn Ads. Свяжитесь с администратором, если подключение недоступно.

1. Введите имя экспорта.

1. Выберите, хотите ли вы экспортировать данные для выполнения [таргетинг на контакты](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) или [таргетинг на компании](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) в LinkedIn.

1. В разделе **Сопоставление данных** для целевого контакта выберите хотя бы одно поле, которое представляет адрес электронной почты клиента, Apple Ad ID, Google Ad ID, Google User ID или имя и фамилия. Если вы выбираете цель на компанию, выберите хотя бы одно поле, которое представляет название компании, домен электронной почты, URL-адрес страницы LinkedIn, символ акций или веб-сайт.

1. При желании добавьте поля для дальнейшего определения вашего экспорта. Выберите **Добавить атрибут**, чтобы сопоставить эти поля.

1. Выберите сегменты, которые нужно экспортировать. Сопоставленные аудитории в LinkedIn Campaign Manager будет автоматически созданы с именем сегментов, которые вы выбрали для экспорта. Каждый сегмент приведет к отдельному сопоставленной аудитории.

1. Выберите **Сохранить**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
