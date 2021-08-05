---
title: Ограничения обслуживания
description: Понимание ограничений обслуживания.
ms.date: 07/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 81253332cbea3110c0b3804db3a4d03b514f92d4
ms.sourcegitcommit: 9a99e48e96dfb3d895db428f37c30ae55eea66b7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2021
ms.locfileid: "6604385"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Возможность ограничения обслуживания в аналитике аудитории Dynamics 365 Customer Insights

В этой статье описываются встроенные ограничения службы Customer Insights, назначение которых — обеспечить стабильность и надежность службы. Запросить изменение этих ограничений можно на [форуме идей](https://go.microsoft.com/fwlink/?linkid=2074172). 
 
| Область  | Ограничения  | Примечания. |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Сегменты и меры | 100 сегментов или мер. | Общее количество активных [сегментов](segments.md) и [мер](measures.md) вместе не может превышать 100.  |
| Отношения | 20 уровней глубины отношений в путях сущностей. | При создании [сегментов](segments.md) или [мер](measures.md) с помощью интерфейса построителя пути к сущностям могут иметь до 20 переходов отношений между начальной и конечной сущностями.  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]