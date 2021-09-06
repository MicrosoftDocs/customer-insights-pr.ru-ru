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
ms.openlocfilehash: bf1bbcd31333c8a557b59b001112042a1783546ab0cd2af394d8af2953a493f4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032774"
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