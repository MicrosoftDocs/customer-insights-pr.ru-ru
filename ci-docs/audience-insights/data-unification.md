---
title: Объединение данных
description: Узнайте, как объединить полученные данные.
ms.date: 04/16/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 24321e9e11f9fd4e800526673726e5146ed33674
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406727"
---
# <a name="data-unification"></a>Объединение данных

После [настройки источников данных](data-sources.md) вы можете объединить данные. Объединение данных включает в себя три этапа: **Сопоставление**, **Поиск соответствий** и **Объединение**.

Процесс объединения данных позволяет объединить ранее разрозненные источники данных в один основной набор данных, обеспечивающий единое представление ваших клиентов. Этапы объединения являются обязательными и выполняются в следующем порядке:

1. [Map](map-entities.md)
2. [Совпадение](match-entities.md)
3. [Слияние](merge-entities.md)

После завершения объединения данных можно по желанию

- [настроить отношения между сущностями](relationships.md) для создания сложных сегментов,
- [обогатить свои данные](enrichment-hub.md), чтобы получить более широкий спектр информации о ваших клиентах,
- [определить действия](activities.md) из некоторых загруженных атрибутов.
