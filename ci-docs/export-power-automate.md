---
title: Соединитель Power Automate (предварительная версия) | Документация Microsoft
description: Создание потоков в Microsoft Power Automate из Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29a861dad926072f6f849d738d868f0f3b9306be
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081393"
---
# <a name="power-automate-connector-preview"></a>Соединитель Power Automate (предварительная версия)

Автоматически запускайте определенные события при изменении данных и управляйте более сложными потоками непосредственно в [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Известные ограничения

- Вы можете сделать максимум 100 звонков за 60 секунд. Вы можете вызывать конечную точку API несколько раз, используя параметр $skip. [Узнайте больше о параметре $skip](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Триггеры Power Automate

Используйте триггеры для создания облачных потоков и автоматизации повторяющихся задач, таких как уведомления или более сложные действия.

- Триггер при сбое обновления источника данных.
- Триггер при успешном обновлении источника данных.
- Триггер, когда порог пересекается на сегменте. Триггер ограничен пересечением выше порога.
- Триггер, когда порог пересекается на бизнес-мере. Поддерживаются только бизнес-меры без измерения. Триггер ограничен пересечением выше порога.
- Запускается по завершении полного обновления (источников данных, сегментов, мер...).
- Запускается после завершения обновления процесса объединения.

[Настройте свои триггеры в Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Действия Power Automate

Соединитель Power Automate обеспечивает другие действия, кроме доступных триггеров. Для получения дополнительных сведений см. [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Создание потока Power Automate

1. Откройте **Администратор** > **Пункты назначения экспорта**.

1. На плитке **Power Automate** выберите **Настроить**.

1. Откроется соединитель Customer Insights (предварительная версия) в Power Automate. **Войдите** в Power Automate.

1. Выберите один из доступных триггеров и добавьте дополнительные шаги в новый поток. Для получения дополнительной информации см. [Создание облачного потока в Power Automate](/power-automate/get-started-logic-flow).

Примеры использования потоков: 
- Отправьте сообщение в канал Microsoft Teams в случае сбоя обновления источника данных. 
- Отправьте электронное письмо владельцам данных, когда будет превышен порог сегмента.



[!INCLUDE [footer-include](includes/footer-banner.md)]
