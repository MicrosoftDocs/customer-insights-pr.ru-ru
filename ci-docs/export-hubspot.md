---
title: Экспорт данных Customer Insights в HubSpot
description: Узнайте, как настроить подключение и экспорт в HubSpot.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0281be288b2c4d9e5da7ad8e2ed25f7b51b8498e
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588914"
---
# <a name="export-segments-to-hubspot-preview"></a>Экспорт сегментов в HubSpot (предварительная версия)

Экспортируйте сегменты профилей Unified customer profile в HubSpot и используйте их для маркетинга по электронной почте.

## <a name="prerequisites-for-a-connection"></a>Предварительные требования для подключения

- [Учетная запись HubSpot](https://www.hubspot.com/) и соответствующие учетные данные администратора.
- [Ключ API](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) из HubSpot.
- [Настроенные сегменты](segments.md) в Customer Insights.

## <a name="known-limitations"></a>Известные ограничения

- До 100 000 профилей клиентов на экспорт в HubSpot, что может занять до 15 минут. Количество профилей клиентов, которые вы можете экспортировать в HubSpot, зависит от вашего контракта с HubSpot и ограничен им.
- Только сегменты.

## <a name="set-up-connection-to-hubspot"></a>Настройка подключения к HubSpot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Перейти в раздел **Администрирование** > **Подключения**.

1. Выберите **Добавить подключение** и выберите **HubSpot** для настройки подключения.

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. Укажите, кто может использовать это подключение. Если вы не предпримете никаких действий, по умолчанию это будут администраторы. Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введите учетные данные HubSpot при появлении запроса.

1. Ознакомьтесь с положениями [Соответствие и конфиденциальность данных](connections.md#data-privacy-and-compliance) и выберите **Принимаю**.

1. Выберите **Подключить** для инициализации подключения к HubSpot.

1. Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.

1. Выберите **Сохранить**, чтобы завершить подключение.

## <a name="configure-an-export"></a>Настройка экспорта

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Чтобы создать новый экспорт, выберите **Добавить экспорт**.

1. В поле **Подключение для экспорта** выберите подключение из раздела HubSpot. Если вы не видите название этого раздела, вам не доступны подключения этого типа.

1. В разделе **Сопоставление данных** в поле **Эл. почта** выберите поле, которое представляет адрес электронной почты клиента. Повторите те же действия для других необязательных полей.

1. Выберите сегменты, которые нужно экспортировать.

1. Выберите **Сохранить**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
