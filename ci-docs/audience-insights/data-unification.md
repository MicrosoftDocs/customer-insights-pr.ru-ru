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
ms.openlocfilehash: 73d8006c670268420f8cd6a2b37cb214ba1bbd6c
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597895"
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