---
title: Экспорт сегментов в DotDigital (предварительная версия)
description: Узнайте, как настроить подключение и экспорт в DotDigital.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cabaea84e31f8fe97bc558a8dca8d93bc40f43b7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196088"
---
# <a name="export-segments-to-dotdigital-preview"></a>Экспорт сегментов в DotDigital (предварительная версия)

Экспортируйте сегменты унифицированных профилей клиентов в адресные книги DotDigital и используйте их для кампаний, электронного маркетинга и создания клиентских сегментов с помощью DotDigital.

## <a name="prerequisites"></a>Предварительные условия

- [Учетная запись DotDigital](https://dotdigital.com/) и [Пользователь API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- Идентификатор DotDigital из [новый](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) или существующей адресной книги в DotDigital. Идентификатор можно найти в URL-адресе, когда вы выбираете и открываете адресную книгу.
- [Настроенные сегменты](segments.md) в Customer Insights.
- Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.

## <a name="known-limitations"></a>Известные ограничения

- До 1 миллиона профилей клиентов на экспорт в DotDigital, что может занять до трех часов из-за ограничений на стороне провайдера. Количество профилей клиентов, которые вы можете экспортировать в DotDigital, зависит от вашего контракта с DotDigital.
- Только сегменты.

## <a name="set-up-connection-to-dotdigital"></a>Настройка подключения к DotDigital

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Перейти в раздел **Администрирование** > **Подключения**.

1. Выберите **Добавить подключение**, затем выберите **DotDigital**.

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. Укажите, кто может использовать это подключение. По умолчанию это только администраторы. Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введите **имя пользователя API DotDigital и пароль**.

1. Введите ваш **Идентификатор адресной книги DotDigital**.

1. Ознакомьтесь с положениями [Соответствие и конфиденциальность данных](connections.md#data-privacy-and-compliance) и выберите **Принимаю**.

1. Выберите **Подключиться** для инициализации подключения.

1. Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.

1. Выберите **Сохранить**, чтобы завершить подключение.

## <a name="configure-an-export"></a>Настройка экспорта

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Выберите **Добавить экспорт**.

1. В поле **Подключение для экспорта** выберите подключение из раздела DotDigital. Свяжитесь с администратором, если подключение недоступно.

1. Введите имя экспорта.

1. В разделе **Сопоставление данных** в поле **Эл. почта** выберите поле, которое представляет адрес электронной почты клиента.

1. При желании экспортируйте **имя**, **фамилия**, **ФИО**, **Пол**, а также **Почтовый индекс**.

1. Выберите сегменты, которые нужно экспортировать.

1. Выберите **Сохранить**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

В DotDigital найдите свои сегменты в [адресных книгах DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

[!INCLUDE [footer-include](includes/footer-banner.md)]
