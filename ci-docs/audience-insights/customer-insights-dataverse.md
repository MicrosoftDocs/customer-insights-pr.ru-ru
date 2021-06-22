---
title: Набор данных Customer Insights в Microsoft Dataverse
description: Используйте сущности Customer Insights в виде таблиц в Microsoft Dataverse.
ms.date: 06/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 7157ad930f3cea17c12bd4f95028d291483329d3
ms.sourcegitcommit: e5425f060c8d80f9510283dc610ce70a4e709b1e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/15/2021
ms.locfileid: "6259207"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Работайте с данными Customer Insights в Microsoft Dataverse

Customer Insights предоставляет возможность сделать выходные сущности доступными в [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Эта интеграция обеспечивает простой обмен данными и индивидуальную разработку с помощью подхода с минимальным кодом или без кода. Выходные сущности будут доступны в виде таблиц в Dataverse. Эти таблицы позволяют использовать такие сценарии, как [автоматизированные рабочие процессы Power Automate](/power-automate/getting-started), [приложения на основе модели](/powerapps/maker/model-driven-apps/) и [приложения на основе холста](/powerapps/maker/canvas-apps/) в Power Apps. Вы можете использовать данные для любого другого приложения, основанного на таблицах Dataverse. Текущая реализация в основном поддерживает поиск, при котором данные из доступных сущностей аналитики аудитории могут быть извлечены для заданного идентификатора клиента.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Прикрепите среду Dataverse к Customer Insights

**Организации с существующими средами Dataverse**

Организации, которые уже используют Dataverse, могут [использовать одну из существующих сред Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization), когда администратор настраивает аналитику аудитории. Предоставляя URL-адрес для среды Dataverse, он прикрепляется к новой среде аналитики аудитории. Для обеспечения максимальной производительности, Customer Insights и среды Dataverse должны размещаться в одном регионе.

Чтобы прикрепить среду Dataverse, разверните **Дополнительные параметры** при создании среды аналитики аудитории. Предоставьте **URL-адрес среды Microsoft Dataverse** и установите флажок, чтобы **Включить обмен данными**.

:::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="alt":::

**Новая организация**

Если вы создадите новую организацию при настройке Customer Insights, вы автоматически получите новую среду Dataverse.

> [!NOTE]
> Если ваши организации уже используют Dataverse в их клиенте, важно помнить, что [создание среды Dataverse контролируется администратором](/power-platform/admin/control-environment-creation.md). Например, если вы настраиваете новую среду аналитики аудитории со учетной записью своей организации, а администратор отключил создание пробных сред Dataverse для всех кроме администраторов, вы не сможете создать новую пробную среду.
> 
> В пробных средах Dataverse, созданных в Customer Insights, есть 3 ГБ хранилища, которые не учитываются в общей емкости, предоставленной клиенту. Платные подписки получают право Dataverse на 15 ГБ для базы данных и 20 ГБ для хранения файлов.

## <a name="output-entities"></a>Выходные сущности

Некоторые выходные сущности из аналитики аудитории доступны в виде таблиц в Dataverse. В следующих разделах описывается ожидаемая схема этих таблиц.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Обогащение](#enrichment)
- [Прогноз](#prediction)


### <a name="customerprofile"></a>CustomerProfile

Эта таблица содержит единый профиль клиента из Customer Insights. Схема единого профиля клиента зависит от сущностей и атрибутов, используемых в процессе слияния. Схема профиля клиента обычно содержит подмножество атрибутов из [Определение Common Data Model для CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Таблица AlternateKey содержит ключи сущностей, участвовавших в процессе унификации.

|Column  |Тип  |Description  |
|---------|---------|---------|
|DataSourceName    |String         | Назовите источник данных. Например: `datasource5`        |
|EntityName        | String        | Имя сущности в аналитике аудитории. Например: `contact1`        |
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
