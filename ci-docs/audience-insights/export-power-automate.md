---
title: Соединитель Power Automate | Документация Майкрософт
description: Создавайте потоки в Microsoft Power Automate из Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406719"
---
# <a name="power-automate-connector-preview"></a>Соединитель Power Automate (предварительная версия)

Автоматически запускайте определенные события при изменении данных и управляйте более сложными потоками непосредственно в [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Триггеры Power Automate

Вы можете использовать различные триггеры, которые позволяют создавать потоки для автоматизации повторяющихся задач, таких как уведомления или более сложные действия. 

- Триггер при сбое обновления источника данных. 
- Триггер при успешном обновлении источника данных.
- Триггер, когда порог пересекается на сегменте. Триггер ограничен пересечением выше порога.
- Триггер, когда порог пересекается на бизнес-мере. Триггер ограничен пересечением выше порога.
- Запускается по завершении полного обновления (источников данных, сегментов, мер...).
- Запускается, когда обновление процесса объединения (сопоставление, поиск соответствия, объединение) завершено.

[Настройте свои триггеры в Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Действия Power Automate
Соединитель Power Automate обеспечивает другие действия, кроме доступных триггеров. Для получения дополнительных сведений см. [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Создание потока Power Automate в аналитике аудитории

1. В аналитике аудитории перейдите **Администрирование** > **Система**.

1. На странице **Система** выберите вкладку **Состояние**.

1. В разделе **Источники данных** выберите **Потоки** и выберите **Создать поток** из раскрывающегося списка.
   > [!div class="mx-imgBorder"]
   > ![Соединитель Power Automate, показывающий действие "Создать поток"](media/power-automate-connector-create-flow.png "Соединитель Power Automate, показывающий действие "Создать поток"")

1. В Power Automate выберите один из доступных триггеров, чтобы создать предпочтительный поток. Если вы создаете свой первый поток, вам сначала нужно пройти аутентификацию с соединителем Power Automate.
