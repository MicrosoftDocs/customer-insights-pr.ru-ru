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
ms.openlocfilehash: eba7871faf304d5945191b5b9bc215243b4f8a05
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483701"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Ограничения обслуживания в возможностях Customer Insights

В этой статье описываются встроенные ограничения службы Customer Insights, назначение которых — обеспечить стабильность и надежность службы. Запросить изменение этих ограничений можно на [форуме идей](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Аналитика аудитории

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Возможность ограничения обслуживания в аналитике аудитории Dynamics 365 Customer Insights

| Область  | Ограничения  | Примечания. |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Сегменты и меры | 100 сегментов или мер. | Общее количество активных [сегментов](audience-insights/segments.md) и [мер](audience-insights/measures.md) вместе не может превышать 100.  |
| Отношения | 20 уровней глубины отношений в путях сущностей. | При создании [сегментов](audience-insights/segments.md) или [мер](audience-insights/measures.md) с помощью интерфейса построителя пути к сущностям могут иметь до 20 переходов отношений между начальной и конечной сущностями.  |


## <a name="engagement-insights"></a>Аналитика взаимодействия

### <a name="workspace-and-event-quotas"></a>Рабочая область и квоты на события

Аналитика вовлеченности — это масштабируемое приложение, которое может поддерживать миллионы событий в секунду. Во время общедоступная предварительная версия события имеют порог объема. Также существует ограничение на количество рабочих областей в организации.

### <a name="engagement-insights-limits"></a>Границы аналитики взаимодействий

- Максимальный объем событий на рабочую область = 100 событий в секунду.

- Максимальное количество рабочих областей на организацию = 100.

Когда события превышают порог, это может привести к потере данных в отчетах, основанных на этих событиях. Вы можете [обратитесь в службу поддержки](https://go.microsoft.com/fwlink/?linkid=2145734), чтобы запросить увеличение объема до того, как вы превысите границы. Мы будем работать с вами, чтобы определить вашу потребность в увеличении объема и поддержать ваш запрос.


[!INCLUDE[footer-include](includes/footer-banner.md)]