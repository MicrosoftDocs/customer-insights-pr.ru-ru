---
title: Экспорт сегментов в Campaign Monitor (предварительная версия)
description: Узнайте, как настроить подключение и экспорт в Campaign Monitor.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c04fc26dc690cf32b45913257e82b9a0f617185
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196318"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Экспорт сегментов в Campaign Monitor (предварительная версия)

Экспортируйте сегменты унифицированных профилей клиентов в Campaign Monitor и используйте их для маркетинговых действий.

## <a name="prerequisites"></a>Предварительные условия

- [Учетная запись Campaign Monitor](https://www.campaignmonitor.com/) и соответствующие учетные данные администратора.
- [ИД списка Campaign Monitor](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- [Сгенерированный ключ API](https://www.campaignmonitor.com/api/getting-started/) из пункта **Параметры учетной записи** в Campaign Monitor для получения идентификатора списка API.
- [Настроенные сегменты](segments.md) в Customer Insights.
- Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.

## <a name="known-limitations"></a>Известные ограничения

- До 1 млн профилей клиентов на экспорт в Campaign Monitor, что может занять до 20 минут. Количество профилей клиентов, которые вы можете экспортировать в Campaign Monitor, зависит от вашего контракта с Campaign Monitor.
- Только сегменты.

## <a name="set-up-connection-to-campaign-monitor"></a>Настройка подключения к Campaign Monitor

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Перейти в раздел **Администрирование** > **Подключения**.

1. Выберите **Добавить подключение** и выберите **Campaign Monitor**.

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. Укажите, кто может использовать это подключение. По умолчанию это только администраторы. Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ознакомьтесь с положениями [Соответствие и конфиденциальность данных](connections.md#data-privacy-and-compliance) и выберите **Принимаю**.

1. Выберите **Подключить** для инициализации подключения к Campaign Monitor.

1. Выберите **Проверка подлинности в Campaign Monitor** и укажите свои учетные данные администратора для Campaign Monitor.

1. Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.

1. Выберите **Сохранить**, чтобы завершить подключение.

## <a name="configure-an-export"></a>Настройка экспорта

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Чтобы создать новый экспорт, выберите **Добавить экспорт**.

1. В поле **Подключение для экспорта** выберите подключение из раздела Campaign Monitor. Свяжитесь с администратором, если подключение недоступно.

1. Введите имя экспорта.

1. Введите свой **ИД списка Campaign Monitor**.

1. В разделе **Сопоставление данных** в поле **Эл. почта** выберите поле, которое представляет адрес электронной почты клиента. Необходимо экспортировать сегменты в Campaign Monitor.

1. Выберите сегменты, которые нужно экспортировать.

1. Выберите **Сохранить**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
