---
title: Примеры OData для API-интерфейсов Dynamics 365 Customer Insights
description: Часто используемые примеры протокола Open Data Protocol (OData) для запросов к API-интерфейсам Customer Insights для просмотра данных.
ms.date: 05/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: cdadd72bfe4272d8d83d923baaa6fd40d008473b
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808477"
---
# <a name="odata-query-examples"></a>Примеры запросов OData

Open Data Protocol (OData) — это протокол доступа к данным, основанный на базовых протоколах, таких как HTTP. Он использует общепринятые методологии, такие как REST для Интернета. Существуют различные виды библиотек и инструментов, которые можно применять для использования служб OData.

В этой статье перечислены некоторые часто запрашиваемые примеры запросов, которые помогут вам в создании собственных реализаций на основе [API-интерфейсов Customer Insights](apis.md).

Необходимо изменить примеры запросов, чтобы они работали в целевых средах: 

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}`, где {instanceId} — это идентификатор GUID среды Customer Insights, которую вы хотите запросить. [Операция ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) дает возможность найти {InstanceId}, к которому у вас есть доступ.
- {CID}: идентификатор GUID единой записи клиента. Пример: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: идентификатор первичного ключа записи клиента в источнике данных. Пример: `CNTID_1002`
- {DSname}: строка с именем сущности источника данных, которая передается в Customer Insights. Пример: `Website_contacts`.
- {SegmentName}: строка с именем выходной сущности сегмента в Customer Insights. Пример: `Male_under_40`.

## <a name="customer"></a>клиент

В следующей таблице содержится набор примеров запросов для сущности *Клиент*.

|Тип запроса |Пример  | Заметка  |
|---------|---------|---------|
|Единый идентификатор клиентов     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Альтернативный ключ    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Альтернативные ключи сохраняются в единой сущности клиента.       |
|Выберите   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|Входит в    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Альтернативный ключ + In   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Поиск (Search)  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Возвращает первые 10 результатов для строки поиска      |
|Членство в сегменте  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Возвращает заданное количество строк из объекта сущности.      |

## <a name="unified-activity"></a>Объединенное действие

В следующей таблице содержится набор примеров запросов для сущности *UnifiedActivity*.

|Тип запроса |Пример  | Заметка  |
|---------|---------|---------|
|Действие CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Перечисляет действия определенного профиля клиента |
|Интервал времени действия    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Действия профиля клиента в интервал времени       |
|Тип активности    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Действие по отображаемому имени     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Сортировка действий    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Сортировка действий по возрастанию или по убыванию       |
|Действие, расширенное за счет членства в сегменте  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Другие примеры

В следующей таблице содержится набор примеров запросов для других сущностей.

|Тип запроса |Пример  | Заметка  |
|---------|---------|---------|
|Меры CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Обогащенные бренды CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Обогащенные интересы CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|Предложение In + Развернуть     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Неподдерживаемые запросы OData

Следующие запросы не поддерживаются в Customer Insights:

- `$filter` в принятых исходных сущностях. Запросы $filter можно выполнять только к системным сущностям, созданным Customer Insights.
- `$expand` из запроса `$search`. Пример: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` из `$select`, если только выбрано подмножество атрибутов. Пример: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- Бренд, обогащенный `$expand`, или интересы людей для конкретного клиента. Пример: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Запрашивайте выходные сущности модели прогнозирования через альтернативный ключ. Пример: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
