---
title: Соединитель Power Automate | Документация Майкрософт
description: Создание потоков в Microsoft Power Automate из Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e973bb11b31c9e70b695ebec8aa2700fdaa5e44f
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597941"
---
# <a name="power-automate-connector-preview"></a>Соединитель Power Automate (предварительная версия)

Автоматически запускайте определенные события при изменении данных и управляйте более сложными потоками непосредственно в [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Триггеры Power Automate

Используйте триггеры для создания облачных потоков и автоматизации повторяющихся задач, таких как уведомления или более сложные действия. 

- Триггер при сбое обновления источника данных. 
- Триггер при успешном обновлении источника данных.
- Триггер, когда порог пересекается на сегменте. Триггер ограничен пересечением выше порога.
- Триггер, когда порог пересекается на бизнес-мере. Триггер ограничен пересечением выше порога.
- Запускается по завершении полного обновления (источников данных, сегментов, мер...).
- Запускается, когда обновление процесса объединения (сопоставление, поиск соответствия, объединение) завершено.

[Настройте свои триггеры в Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Действия Power Automate
Соединитель Power Automate обеспечивает другие действия, кроме доступных триггеров. Для получения дополнительных сведений см. [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Создание потока Power Automate

1. В аналитике аудитории перейдите **Администрирование** > **Экспорт пунктов назначения**.

1. На плитке **Power Automate** выберите **Настроить**.

1. Откроется соединитель Customer Insights (предварительная версия) в Power Automate. **Войдите** в Power Automate.

1. Выберите один из доступных триггеров и добавьте дополнительные шаги в новый поток. Для получения дополнительной информации см. [Создание облачного потока в Power Automate](/power-automate/get-started-logic-flow).

Примеры использования потоков: 
- Отправьте сообщение в канал Microsoft Teams в случае сбоя обновления источника данных. 
- Отправьте электронное письмо владельцам данных, когда будет превышен порог сегмента.



[!INCLUDE[footer-include](../includes/footer-banner.md)]