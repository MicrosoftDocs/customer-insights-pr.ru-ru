---
title: Ограничения служб в Dynamics 365 Customer Insights
description: Понимание ограничений обслуживания.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641778"
---
# <a name="service-limits-in-customer-insights"></a>Ограничения служб в Customer Insights

В этой статье описываются встроенные ограничения службы Customer Insights, назначение которых — обеспечить стабильность и надежность службы. Запросить изменение этих ограничений можно на [форуме идей](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="customer-insights"></a>Customer Insights

| Площадь  | Ограничения  | Примечания. |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Сегменты, меры и прогнозы | 300  | Общее количество [сегментов](segments.md), [мер](measures.md) и [прогнозов](predictions.md) вместе не может превышать 300.  |
| Связи | 20 уровней глубины отношений в путях сущностей. | При создании [сегментов](segments.md) или [мер](measures.md) с помощью интерфейса построителя пути к сущностям могут иметь до 20 переходов отношений между начальной и конечной сущностями.  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
