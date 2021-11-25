---
title: Ограничения служб в Dynamics 365 Customer Insights
description: Понимание ограничений обслуживания.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eb25e050b8aa768e6e1d8d4c5adce6095cccc346
ms.sourcegitcommit: 31a9b531dacd3a6465b3030c704ff5c085b7e122
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2021
ms.locfileid: "7791997"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Ограничения обслуживания в возможностях Customer Insights

В этой статье описываются встроенные ограничения службы Customer Insights, назначение которых — обеспечить стабильность и надежность службы. Запросить изменение этих ограничений можно на [форуме идей](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Аналитика аудитории

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Возможность ограничения обслуживания в аналитике аудитории Dynamics 365 Customer Insights

| С областями  | Ограничения  | Примечания. |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Сегменты, меры и прогнозы | 300  | Общее количество [сегментов](audience-insights/segments.md), [мер](audience-insights/measures.md) и [прогнозов](audience-insights/predictions.md) вместе не может превышать 300.  |
| Связи | 20 уровней глубины отношений в путях сущностей. | При создании [сегментов](audience-insights/segments.md) или [мер](audience-insights/measures.md) с помощью интерфейса построителя пути к сущностям могут иметь до 20 переходов отношений между начальной и конечной сущностями.  |


## <a name="engagement-insights"></a>Аналитика взаимодействия

### <a name="workspace-and-event-quotas"></a>Рабочая область и квоты на события

Аналитика вовлеченности — это масштабируемое приложение, которое может поддерживать миллионы событий в секунду. Во время общедоступная предварительная версия события имеют порог объема. Также существует ограничение на количество рабочих областей в организации.

### <a name="engagement-insights-limits"></a>Границы аналитики взаимодействий

- Максимальный объем событий на рабочую область = 100 событий в секунду.

- Максимальное количество рабочих областей на организацию = 100.

Когда события превышают порог, это может привести к потере данных в отчетах, основанных на этих событиях. Вы можете [обратитесь в службу поддержки](https://go.microsoft.com/fwlink/?linkid=2145734), чтобы запросить увеличение объема до того, как вы превысите границы. Мы будем работать с вами, чтобы определить вашу потребность в увеличении объема и поддержать ваш запрос.


[!INCLUDE[footer-include](includes/footer-banner.md)]
