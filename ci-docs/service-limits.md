---
title: Ограничения служб в Customer Insights
description: Узнайте, какие пределы и ограничения существуют в службе SaaS Customer Insights.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c3863b1a72fd92ddc87755699feda11371ec9214
ms.sourcegitcommit: dfba60e17ae6dc1e2e3830e6365e2c1f87230afd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2022
ms.locfileid: "9463235"
---
# <a name="service-limits-in-customer-insights"></a>Ограничения служб в Customer Insights

 В Customer Insights имеются встроенные ограничения, назначение которых — обеспечить стабильность и надежность службы. Запросить изменение этих ограничений можно на [форуме идей](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Площадь  | Ограничения  | Примечания. |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Сегменты, меры и прогнозы | 300  | Общее количество [сегментов](segments.md), [мер](measures.md) и [прогнозов](predictions-overview.md) вместе не может превышать 300.  |
| Связи | 20 уровней глубины отношений в путях сущностей. | При создании [сегментов](segments.md) или [мер](measures.md) с помощью интерфейса построителя пути к сущностям могут иметь до 20 переходов отношений между начальной и конечной сущностями.  |
|Прием данных| Параллельные оценки для источников данных Power Query ограничены. | Customer Insights имеет те же самые [ограничения обновления, как и потоки данных в PowerBI.com](/power-query/power-query-online-limits#refresh-limits). |

## <a name="fair-scheduling-of-jobs"></a>Справедливое планирование заданий

Customer Insights — это служба SaaS, использующая общие ресурсы Azure. Клиенты, как правило, имеют рабочие нагрузки переменной интенсивности и по разным графикам. Чтобы обеспечить справедливый доступ к базовым ресурсам, мы следим за тем, чтобы системные процессы выполнялись в справедливом порядке. Примерами системных процессов являются задания, связанные с объединением данных, обновлением сегментов или расчетом показателей. Справедливое планирование защищает вас от очередей за ресурсами, если возникает всплеск запрошенных заданий. В то же время Customer Insights не гарантирует, что все задания, которые вы ставите в очередь, обрабатываются параллельно.

[!INCLUDE [footer-include](includes/footer-banner.md)]
