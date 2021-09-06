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
ms.openlocfilehash: 2966f2ede1ddbe0245471771365cbf5b593be608764aa10ed28d962c52bb8067
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034880"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Возможность ограничения обслуживания в аналитике аудитории Dynamics 365 Customer Insights

В этой статье описываются встроенные ограничения службы Customer Insights, назначение которых — обеспечить стабильность и надежность службы. Запросить изменение этих ограничений можно на [форуме идей](https://go.microsoft.com/fwlink/?linkid=2074172). 
 
| Область  | Ограничения  | Примечания. |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Сегменты и меры | 100 сегментов или мер. | Общее количество активных [сегментов](segments.md) и [мер](measures.md) вместе не может превышать 100.  |
| Отношения | 20 уровней глубины отношений в путях сущностей. | При создании [сегментов](segments.md) или [мер](measures.md) с помощью интерфейса построителя пути к сущностям могут иметь до 20 переходов отношений между начальной и конечной сущностями.  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]