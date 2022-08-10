---
title: Экспорт сегментов в RollWorks (предварительная версия)
description: Узнайте, как настроить подключение и экспорт в RollWorks.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e13aeca4ee5309f85e7de2986cd1a2ba5d2992fb
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195628"
---
# <a name="export-segments-to-rollworks-preview"></a>Экспорт сегментов в RollWorks (предварительная версия)

Экспортируйте сегменты унифицированных профилей клиентов в RollWorks и используйте их для рекламы.

## <a name="prerequisites"></a>Предварительные условия

- [Учетная запись RollWorks](https://www.rollworks.com/) и соответствующие учетные данные администратора.
- [ИД рекламодателя RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Настроенные сегменты](segments.md) в Customer Insights.
- Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.

## <a name="known-limitations"></a>Известные ограничения

- До 250 000 профилей клиентов на экспорт в RollWorks, что может занять до 10 минут. Количество профилей клиентов, которые вы можете экспортировать в RollWorks, зависит от вашего контракта с RollWorks.
- Только сегменты.

## <a name="set-up-connection-to-rollworks"></a>Настройка подключения к RollWorks

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Перейти в раздел **Администрирование** > **Подключения**.

1. Выберите **Добавить подключение**, затем выберите **RollWorks**.

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. Укажите, кто может использовать это подключение.  По умолчанию это только администраторы. Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ознакомьтесь с положениями [Соответствие и конфиденциальность данных](connections.md#data-privacy-and-compliance) и выберите **Принимаю**.

1. Выберите **Подключиться** для инициализации подключения.

1. Выберите **Проверка подлинности в RollWorks** и укажите свои учетные данные администратора для RollWorks.

1. Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.

1. Выберите **Сохранить**, чтобы завершить подключение.

## <a name="configure-an-export"></a>Настройка экспорта

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Выберите **Добавить экспорт**.

1. В поле **Подключение для экспорта** выберите подключение из раздела RollWorks. Свяжитесь с администратором, если подключение недоступно.

1. Введите имя экспорта.

1. Введите ваш **ИД рекламодателя RollWorks**.

1. В разделе **Сопоставление данных** в поле **Эл. почта** выберите поле, которое представляет адрес электронной почты клиента.

1. Выберите сегменты, которые нужно экспортировать.

1. Выберите **Сохранить**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
