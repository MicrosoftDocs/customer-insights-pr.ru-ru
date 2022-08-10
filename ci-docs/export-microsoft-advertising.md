---
title: Экспорт сегментов в Microsoft Advertising (предварительная версия)
description: Узнайте, как настроить подключение и экспорт в Microsoft Advertising.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196548"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Экспорт сегментов в Microsoft Advertising (предварительная версия)

Экспортируйте сегменты Customer Insights в Microsoft Advertising для создания аудиторий Customer Match. Используйте эти аудитории для своих рекламных кампаний.

## <a name="prerequisites"></a>Предварительные условия

- [Учетная запись Microsoft Advertising](https://ads.microsoft.com/) и соответствующие учетные данные администратора.
- Идентификатор клиента Microsoft Advertising и идентификатор учетной записи. Найдите идентификатор клиента (`cid`) и идентификатор учетной записи (`aid`) в параметрах URL-адреса при входе в Microsoft Advertising.
- Условия использования Customer Match приняты.
- [Настроенные сегменты](segments.md) в Customer Insights.
- Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.

## <a name="known-limitations"></a>Известные ограничения

- До 500 000 профилей клиентов на экспорт в Microsoft Advertising, что может занять до 10 минут.
- Только сегменты.

## <a name="set-up-connection-to-microsoft-advertising"></a>Настройка подключения к Microsoft Advertising

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Перейти в раздел **Администрирование** > **Подключения**.

1. Выберите **Добавить подключение** и выберите **Microsoft Advertising**.

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. Укажите, кто может использовать это подключение. По умолчанию это администраторы. Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введите **Идентификатор клиента Microsoft Advertising**.

1. Ознакомьтесь с положениями [Соответствие и конфиденциальность данных](connections.md#data-privacy-and-compliance) и выберите **Принимаю**.

1. Выберите **Подключиться** для инициализации подключения.

1. Выберите **Проверка подлинности в Microsoft Advertising** и укажите свои учетные данные администратора для Microsoft Advertising.

1. Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.

1. Выберите **Сохранить**, чтобы завершить подключение.

## <a name="configure-an-export"></a>Настройка экспорта

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Выберите **Добавить экспорт**.

1. В поле **Подключение для экспорта** выберите подключение из раздела Microsoft Advertising. Свяжитесь с администратором, если подключение недоступно.

1. Введите имя экспорта.

1. Выберите сегменты для экспорта. Аудитории Customer Match в Microsoft Advertising создаются автоматически с именами сегментов, выбранных для экспорта. Каждый сегмент приведет к отдельной аудитории Customer Match.

1. Введите ваш **Идентификатор клиента Microsoft Advertising и идентификатор учетной записи**.

1. В разделе **Сопоставление данных** в поле **Эл. почта** выберите поле, которое представляет адрес электронной почты клиента.

1. Выберите **Сохранить**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
