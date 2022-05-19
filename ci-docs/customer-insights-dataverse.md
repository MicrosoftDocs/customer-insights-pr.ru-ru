---
title: Набор данных Customer Insights в Microsoft Dataverse
description: Используйте сущности Customer Insights в виде таблиц в Microsoft Dataverse.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 1e629cd218b104b115f74f59a53a14e9d60fcc8a
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741381"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Работайте с данными Customer Insights в Microsoft Dataverse

Customer Insights предоставляет возможность сделать выходные сущности доступными в [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Эта интеграция обеспечивает простой обмен данными и индивидуальную разработку с помощью подхода с минимальным кодом или без кода. [Выходные сущности](#output-entities) доступны в виде таблиц в среде Dataverse. Вы можете использовать данные для любого другого приложения на основе таблиц Dataverse. Эти таблицы позволяют реализовать такие сценарии, как автоматизированные рабочие процессы посредством Power Automate или создание приложений в Power Apps. Текущая реализация в основном поддерживает поиск, в котором данные из доступных сущностей Customer Insights могут быть получены для заданного идентификатора клиента.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Прикрепите среду Dataverse к Customer Insights

**Имеющаяся организация**

Администраторы могут настроить Customer Insights для [использования существующей среды Dataverse](create-environment.md), когда они создают среду Customer Insights. Путем предоставления URL-адреса для среды Dataverse, осуществляется подключение к их новой среде Customer Insights. Customer Insights и среды Dataverse должны размещаться в одном регионе. 

Если вы не хотите использовать существующую среду Dataverse, система создает новую среду для данных Customer Insights в вашем клиенте. 

> [!NOTE]
> Если ваша организация уже использует Dataverse в их клиенте, важно помнить, что [создание среды Dataverse контролируется администратором](/power-platform/admin/control-environment-creation). Например, если вы настраиваете новую среду Customer Insights со своей учетной записью организации, а администратор отключил создание пробных сред Dataverse для всех, кроме администраторов, вы не можете создать новую пробную среду.
> 
> В пробных средах Dataverse, созданных в Customer Insights, есть 3 ГБ хранилища, которые не учитываются в общей емкости, предоставленной клиенту. Платные подписки получают право Dataverse на 15 ГБ для базы данных и 20 ГБ для хранения файлов.

**Новая организация**

Если вы создаете новую организацию при настройке Customer Insights, система автоматически создает новую среду Dataverse в вашей организации для вас.

## <a name="output-entities"></a>Выходные сущности

Некоторые выходные сущности из Customer Insights доступны в виде таблиц в Dataverse. В следующих разделах описывается ожидаемая схема этих таблиц.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Обогащение](#enrichment)
- [Прогноз](#prediction)
- [Членство в сегменте](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Эта таблица содержит единый профиль клиента из Customer Insights. Схема единого профиля клиента зависит от сущностей и атрибутов, используемых в процессе объединения данных. Схема профиля клиента обычно содержит подмножество атрибутов из [Определение Common Data Model для CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Таблица AlternateKey содержит ключи сущностей, участвовавших в процессе унификации.

|Column  |Тип  |Description  |
|---------|---------|---------|
|DataSourceName    |String         | Назовите источник данных. Например: `datasource5`        |
|EntityName        | String        | Имя сущности в Customer Insights. Например: `contact1`        |
|AlternateValue    |String         |Альтернативный идентификатор, сопоставленный с идентификатором клиента. Пример: `cntid_1078`         |
|KeyRing           | Многострочный текст        | Значение JSON  </br> Пример: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | String        | ID единого профиля клиента.         |
|AlternateKeyId     | GUID         |  Детерминированный GUID AlternateKey на основе msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Пример: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Эта таблица содержит действия пользователей, доступные в Customer Insights.

| Column            | Тип        | Description                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | Идентификатор профиля клиента                                                                      |
| ActivityId        | String      | Внутренний идентификатор действия клиента (первичный ключ)                                       |
| SourceEntityName  | String      | Имя исходной сущности                                                                |
| SourceActivityId  | String      | Первичный ключ из исходной сущности                                                       |
| ActivityType      | String      | Семантический тип действия или название настраиваемого действия                                        |
| ActivityTimeStamp | ДАТА И ВРЕМЯ    | Временная метка действия                                                                      |
| Title             | String      | Заголовок или имя действия                                                               |
| Description       | String      | Описание действия                                                                     |
| URL               | String      | Ссылка на внешний URL-адрес, относящийся к действию                                         |
| SemanticData      | Строка JSON | Включает список пар ключ-значение для полей семантического сопоставления, относящихся к типу действия |
| RangeIndex        | String      | Метка времени Unix, используемая для сортировки временной шкалы действия и запросов эффективного диапазона |
| mydynci_unifiedactivityid   | GUID | Внутренний идентификатор действия клиента (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Эта таблица содержит выходные данные мер на основе атрибутов клиента.

| Column             | Тип             | Description                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | Идентификатор профиля клиента        |
| Мер           | Строка JSON      | Включает список пар "ключ-значение" для имени меры и значений для данного клиента | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | Идентификатор профиля клиента |


### <a name="enrichment"></a>Обогащение

Эта таблица содержит результаты процесса обогащения.

| Column               | Тип             |  Description                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | Идентификатор профиля клиента                                 |
| EnrichmentProvider   | String           | Имя поставщика для обогащения                                  |
| EnrichmentType       | String           | Тип обогащения                                      |
| Значения               | Строка JSON      | Список атрибутов, созданных в процессе обогащения |
| msdynci_enrichmentid | GUID             | Детерминированный GUID, созданный из msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Прогноз

Эта таблица содержит результаты прогнозов модели.

| Column               | Тип        | Description                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | Идентификатор профиля клиента                                  |
| ModelProvider        | String      | Имя поставщика модели                                      |
| Модель                | String      | Имя модели                                                |
| Значения               | Строка JSON | Список атрибутов, созданных моделью |
| msdynci_predictionid | GUID        | Детерминированный GUID, созданный из msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Членство в сегменте

Эта таблица содержит информацию о членстве в сегментах профилей клиентов.

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | Идентификатор профиля клиента        |
| SegmentProvider      | String       | Приложение, которое публикует сегменты.      |
| SegmentMembershipType | String       | Тип клиента для этой записи о членстве в сегменте. Поддерживает несколько типов, таких как Клиент, Контакт или Организация. По умолчанию: клиент  |
| Сегменты       | Строка JSON  | Список уникальных сегментов, участником которых является профиль клиента      |
| msdynci_identifier  | String   | Уникальный идентификатор записи члена сегмента. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Детерминированный GUID, созданный из `msdynci_identifier`          |
