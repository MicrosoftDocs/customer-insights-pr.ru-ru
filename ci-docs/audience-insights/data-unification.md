---
title: Объединение данных
description: Узнайте, как объединить полученные данные.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: cb96763d4b5b67b5110db757eb7d160c294d6fc3
ms.sourcegitcommit: b78c9680b213204e6b0ed47f0147205083f6a98f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "6539085"
---
# <a name="data-unification-overview"></a>Обзор унификации данных

После [настройки источников данных](data-sources.md) вы можете объединить данные. Объединение данных включает в себя три этапа: **Сопоставление**, **Поиск соответствий** и **Объединение**.

Процесс объединения данных позволяет объединить ранее разрозненные источники данных в один основной набор данных, обеспечивающий единое представление ваших клиентов. Этапы объединения являются обязательными и выполняются в следующем порядке:

1. [Map](map-entities.md)
2. [Совпадение](match-entities.md)
3. [Слияние](merge-entities.md)

После завершения объединения данных можно по желанию

- [настроить отношения между сущностями](relationships.md) для создания сложных сегментов,
- [обогатить свои данные](enrichment-hub.md), чтобы получить более широкий спектр информации о ваших клиентах,
- [определить действия](activities.md) из некоторых загруженных атрибутов.


[!INCLUDE[footer-include](../includes/footer-banner.md)]