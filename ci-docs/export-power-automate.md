---
title: Соединитель Power Automate (предварительная версия) | Документация Microsoft
description: Создание потоков в Microsoft Power Automate из Dynamics 365 Customer Insights.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196134"
---
# <a name="power-automate-connector-preview"></a>Соединитель Power Automate (предварительная версия)

Автоматически запускайте определенные события при изменении данных и управляйте более сложными потоками непосредственно в [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Известные ограничения

- Максимум 100 вызовов за 60 секунд. Чтобы вызывать конечную точку API несколько раз, используйте [параметр $skip](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Триггеры Power Automate

Используйте триггеры для создания облачных потоков и автоматизации повторяющихся задач, таких как уведомления или более сложные действия. Используйте триггеры, когда:

- При сбое обновления источника данных.
- При успешном обновлении источника данных.
- Порог пересекается на сегменте. Триггер ограничен пересечением выше порога.
- Порог пересекается на бизнес-мере. Поддерживаются только бизнес-меры без измерения. Триггер ограничен пересечением выше порога.
- Полностью запланированное обновление завершено. Этот триггер не работает для обновлений, запускаемых вручную.
- Обновление процесса объединения завершено.

[Настройте свои триггеры в Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Действия Power Automate

Соединитель Power Automate обеспечивает другие действия, кроме доступных триггеров. Для получения дополнительных сведений см. [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Создание потока Power Automate

1. Перейти в раздел **Администрирование** > **Подключения**.

1. На плитке **Power Automate** выберите **Настроить**.

1. Откроется соединитель Customer Insights (предварительная версия) в Power Automate. **Войдите** в Power Automate.

1. Выберите один из доступных триггеров и добавьте дополнительные шаги в новый поток. Для получения дополнительной информации см. [Создание облачного потока в Power Automate](/power-automate/get-started-logic-flow).

Примеры использования потоков: 
- Отправьте сообщение в канал Microsoft Teams в случае сбоя обновления источника данных. 
- Отправьте электронное письмо владельцам данных, когда будет превышен порог сегмента.

[!INCLUDE [footer-include](includes/footer-banner.md)]
