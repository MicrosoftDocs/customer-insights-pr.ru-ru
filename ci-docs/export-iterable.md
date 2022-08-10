---
title: Экспорт сегментов в Iterable (предварительная версия)
description: Узнайте, как настроить подключение к Braze и экспорт в Iterable.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ccf10b6e3a28a75f9d1bd3d8da3bf870ebc2b1b2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195445"
---
# <a name="export-segments-to-iterable-preview"></a>Экспорт сегментов в Iterable (предварительная версия)

Экспортируйте сегменты профилей Unified customer profile в Iterable и используйте их для маркетинговых мероприятий.

## <a name="prerequisites"></a>Предварительные условия

- [Учетная запись Iterable](https://iterable.com/) и соответствующие учетные данные администратора.
- [Ключ API для Iterable](https://support.iterable.com/hc/en-us/articles/360043464871)
- [Настроенные сегменты](segments.md) в Customer Insights.
- Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.

## <a name="known-limitations"></a>Известные ограничения

- До 1 млн профилей клиентов в Iterable, что может занять до 30 минут. Количество профилей клиентов, которые вы можете экспортировать в Iterable, зависит от вашего контракта с Iterable.
- Только сегменты.

## <a name="set-up-connection-to-iterable"></a>Настройте подключение к Iterable

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Перейти в раздел **Администрирование** > **Подключения**.

1. Выберите **Добавить подключение**, затем выберите **Iterable**.

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. Укажите, кто может использовать это подключение. По умолчанию это только администраторы. Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Предоставьте свой ключ API Iterable, чтобы продолжить вход.

1. Ознакомьтесь с положениями [Соответствие и конфиденциальность данных](connections.md#data-privacy-and-compliance) и выберите **Принимаю**.

1. Выберите **Подключиться** для инициализации подключения.

1. Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.

1. Выберите **Сохранить**, чтобы завершить подключение.

## <a name="configure-an-export"></a>Настройка экспорта

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Выберите **Добавить экспорт**.

1. В поле **Подключение для экспорта** выберите подключение из раздела Iterable. Свяжитесь с администратором, если подключение недоступно.

1. Введите имя экспорта.

1. В разделе **Сопоставление данных** в поле **Эл. почта** выберите поле, которое представляет адрес электронной почты клиента. Список, созданный в Iterable, получит то же имя, что и имя вашего сегмента в Dynamics 365 Customer Insights.

1. Выберите сегменты, которые нужно экспортировать.

1. Выберите **Сохранить**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
