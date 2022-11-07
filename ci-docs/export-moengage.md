---
title: Экспорт сегментов в MoEngage
description: Узнайте, как настроить подключение к Braze и экспорт в MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: df38e9e88a9c116252fba26983b5f3711b46f051
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725282"
---
# <a name="export-segments-to-moengage-preview"></a>Экспорт сегментов в MoEngage (предварительная версия)

Экспортируйте сегменты единых профилей клиентов в MoEngage и используйте их для маркетинга по электронной почте в MoEngage.

## <a name="prerequisites-for-a-connection"></a>Предварительные требования для подключения

- [Учетная запись MoEngage](https://www.moengage.com/) и соответствующие учетные данные администратора.
- Ключ API MoEngage из «Настройки» > «API» в MoEngage.
- [Настроенные сегменты](segments.md) в Customer Insights.

## <a name="known-limitations"></a>Известные ограничения

- Приватный канал в сочетании с использованием собственного хранилища (BYOS) не поддерживается.
- До 100 000 профилей клиентов на экспорт в MoEngage, что может занять до 15 минут. Количество профилей клиентов, которые вы можете экспортировать в MoEngage, зависит от вашего контракта с MoEngage.
- Только сегменты.

## <a name="set-up-connection-to-moengage"></a>Настройка подключения к MoEngage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Перейти в раздел **Администрирование** > **Подключения**.

1. Выберите **Добавить подключение** и выберите **MoEngage** для настройки подключения.

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. Укажите, кто может использовать это подключение. Если вы не предпримете никаких действий, по умолчанию это будут администраторы. Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введите ваш [Идентификатор API данных MoEngage и ключ API](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. Ознакомьтесь с положениями [Соответствие и конфиденциальность данных](connections.md#data-privacy-and-compliance) и выберите **Принимаю**.

1. Выберите **Подключить** для инициализации подключения к MoEngage.

1. Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.

1. Выберите **Сохранить**, чтобы завершить подключение.

## <a name="configure-an-export"></a>Настройка экспорта

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Чтобы создать новый экспорт, выберите **Добавить экспорт**.

1. В поле **Подключение для экспорта** выберите подключение из раздела MoEngage. Если вы не видите название этого раздела, вам не доступны подключения этого типа.

1. В разделе **Сопоставление данных** в поле **Эл. почта** выберите поле, которое представляет адрес электронной почты клиента. Повторите те же действия для других необязательных полей.

1. Выберите сегменты, которые нужно экспортировать. Мы создадим один или несколько сегментов с теми же именами, что и выбранные сегменты в MoEngage в разделе **Сегменты** > **Настраиваемые сегменты**.

1. Выберите **Сохранить**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
