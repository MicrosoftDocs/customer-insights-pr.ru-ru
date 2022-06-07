---
title: Аудит Dynamics 365 Customer Insights с помощью Azure Monitor
description: Узнайте, как отправлять журналы в Microsoft Azure Monitor.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 15ae772617efa4c64cf79d0bac10a0c3cb28ca30
ms.sourcegitcommit: a92bf5985263240fd07bad98d8e119b88cf2c9d9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/26/2022
ms.locfileid: "8807597"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Пересылка журналов в Dynamics 365 Customer Insights с помощью Azure Monitor (предварительная версия)

В Dynamics 365 Customer Insights предусмотрена прямая интеграция с Azure Monitor. Журналы ресурсов Azure Monitor позволяют вести мониторинг и отправлять журналы в [службу хранилища Azure](https://azure.microsoft.com/services/storage/),[Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview), а также передавать их в потоковом режиме в [Центры событий Azure](https://azure.microsoft.com/services/event-hubs/).

Customer Insights отправляет следующие журналы событий:

- **События аудита**
  - **APIEvent** — позволяет отслеживать изменения, внесенные через пользовательский интерфейс Dynamics 365 Customer Insights.
- **Операционные события**
  - **WorkflowEvent** — рабочий процесс позволяет настроить [источники данных](data-sources.md), [объединить](data-unification.md), [обогатить](enrichment-hub.md) и, наконец, [экспортировать](export-destinations.md) данные в другие системы. Все эти шаги можно выполнить по отдельности (например, запустить один экспорт). Их также можно выполнить организованно (например, обновление данных из источников данных, которое запускает процесс объединения, который будет получать обогащение и после завершения экспортировать данные в другую систему). Дополнительные сведения см. в разделе [Схема WorkflowEvent](#workflow-event-schema).
  - **APIEvent** — все вызовы API к экземпляру клиента для Dynamics 365 Customer Insights. Дополнительные сведения см. в разделе [Схема APIEvent](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Задание параметров диагностики

### <a name="prerequisites"></a>Предварительные условия

Для настройки диагностики в Customer Insights должны быть выполнены следующие предварительные условия:

- Необходимо иметь активную [подписку Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- Необходимо иметь разрешения [администратора](permissions.md#admin) в Customer Insights.
- Необходимо иметь роль **Участник** и **Администратор доступа пользователей** в отношении ресурса-пункта назначения в Azure. Этот ресурс может представлять собой учетную запись Azure Data Lake Storage, Центр событий Azure или рабочую область Azure Log Analytics. Дополнительные сведения см. в статье [Добавление или удаление назначений ролей Azure с помощью портала Azure](/azure/role-based-access-control/role-assignments-portal). Это разрешение необходимо при настройке параметров диагностики в Customer Insights. Его можно изменить после успешной настройки.
- Необходимо выполнить [требования к пункту назначения](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) для службы хранилища Azure, Центра событий Azure или Azure Log Analytics.
- Необходимо иметь хотя бы роль **Читатель** в отношении группы ресурсов, к которой принадлежит ресурс.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Настройка диагностики с помощью Azure Monitor

1. В Customer Insights выберите **Система** > **Диагностика** для просмотра пунктов назначений диагностики, настроенных для этого экземпляра.

1. Выберите **Добавить пункт назначения**.

   > [!div class="mx-imgBorder"]
   > ![Подключение к пункту назначения диагностики](media/diagnostics-pane.png "Подключение к пункту назначения диагностики")

1. Укажите имя в поле **Имя для пункта назначения диагностики**.

1. Выберите **клиента** подписки Azure, в которую входит ресурс-пункт назначения, и выберите **Вход**.

1. Выберите **тип ресурса** (учетная запись хранения, центр событий или анализ журналов).

1. Выберите **подписку** для ресурса-пункта назначения.

1. Выберите **группу ресурсов** для ресурса-пункта назначения.

1. Выберите **ресурс**.

1. Подтвердите согласие с заявлением **Соответствие и конфиденциальность данных**.

1. Выберите **Подключиться к системе**, чтобы подключиться к ресурсу-пункту назначения. Журналы начнут появляться в пункте назначения через 15 минут, если API используется и генерирует события.

### <a name="remove-a-destination"></a>Удаление пункта назначения

1. Выберите **Система** > **Диагностика**.

1. Выберите пункт назначения диагностики в списке.

1. В столбце **Действия** выберите значок **Удалить**.

1. Подтвердите удаление, чтобы прекратить пересылку журналов. Ресурс в подписке Azure удален не будет. Вы можете выбрать ссылку в столбце **Действия**, чтобы открыть портал Azure для выбранного ресурса и удалить его там.

## <a name="log-categories-and-event-schemas"></a>Категории журналов и схемы событий

В настоящее время поддерживаются [события API](apis.md) и события рабочих процессов, и используются следующие категории и схемы.
Схема журнала соответствует [общей схеме Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Категории

В Customer Insights предусмотрено две категории:

- **События аудита**: [события API](#api-event-schema) для отслеживания изменений в конфигурации службы. В эту категорию попадают операции `POST|PUT|DELETE|PATCH`.
- **Операционные события**: [события API](#api-event-schema) или [события рабочих процессов](#workflow-event-schema), генерируемые при использовании службы.  Например, это запросы `GET` или события выполнения рабочего процесса.

## <a name="configuration-on-the-destination-resource"></a>Настройка на ресурсе-пункте назначения

В зависимости от выбранного вами типа ресурса автоматически применяются следующие шаги:

### <a name="storage-account"></a>Storage account

Субъект-служба Customer Insights получает разрешение **Участник учетной записи хранения** в отношении выбранного ресурса и создает в выбранном пространстве имен два контейнера:

- `insight-logs-audit`, где содержатся **события аудита**
- `insight-logs-operational`, где содержатся **операционные события**

### <a name="event-hub"></a>Центр событий

Субъект-служба Customer Insights получает разрешение **Владелец данных Центров событий Azure** в отношении выбранного ресурса и создает в выбранном пространстве имен два центра событий:

- `insight-logs-audit`, где содержатся **события аудита**
- `insight-logs-operational`, где содержатся **операционные события**

### <a name="log-analytics"></a>Log Analytics

Субъект-служба Customer Insights получает разрешение **Участник Log Analytics** в отношении ресурса. Журналы будут доступны в разделе **Журналы** > **Таблицы** > **Управление журналами** в выбранной рабочей области Log Analytics. Разверните решение **Управление журналами** и найдите таблицы `CIEventsAudit` и `CIEventsOperational`.

- `CIEventsAudit`, где содержатся **события аудита**
- `CIEventsOperational`, где содержатся **операционные события**

Под окном **Запросы** разверните решение **Аудит** и найтие примеры запросов, выполнив поиск по слову `CIEvents`.

## <a name="event-schemas"></a>Схемы событий

События API и события рабочих процессов имеют схожую структуру; различия между ними см. в описании [схемы событий API](#api-event-schema) или [схемы событий рабочих процессов](#workflow-event-schema).

### <a name="api-event-schema"></a>Схема событий API

| Поле             | Тип данных  | Обязательное/необязательное | Описание       | Пример        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Метка времени | Обязательное          | Метка времени события (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Обязательное          | ResourceId экземпляра, создавшего событие         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Обязательное          | Имя операции, представляемой этим событием.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Обязательное          | Категория журнала события. `Operational` или `Audit`. Все HTTP-запросы POST/PUT/PATCH/DELETE HTTP помечаются как `Audit`, все остальное — как `Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Обязательное          | Состояние события. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Необязательное          | Состояние результата событие. Если операция соответствует вызову REST API, это код состояния HTTP.        | `200`             |
| `durationMs`      | Long      | Необязательное          | Длительность операции в секундах.     | `133`     |
| `callerIpAddress` | String    | Необязательное          | IP-адрес вызывающего объекта, если операция соответствует вызову API, который поступает с общедоступного IP-адреса.                                                 | `144.318.99.233`         |
| `identity`        | String    | Необязательное          | Объект JSON, описывающий идентификатор пользователя или приложения, выполнившего операцию.       | См. раздел [Идентификатор](#identity-schema).     |  
| `properties`      | String    | Необязательное          | Объект JSON с дополнительными свойствами для конкретной категории событий.      | См. раздел [Свойства](#api-properties-schema).    |
| `level`           | String    | Обязательное          | Уровень серьезности события.    | `Informational`, `Warning`, `Error` или `Critical`.           |
| `uri`             | String    | Необязательное          | Абсолютный URI запроса.    |               |

#### <a name="identity-schema"></a>Схема идентификатора

Объект JSON `identity` имеет следующую структуру.

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Поле                         | Описание                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Назначенная роль пользователя или приложения. Дополнительные сведения см. статье о [разрешениях пользователей](permissions.md).                                     |
| `Authorization.RequiredRoles` | Необходимые роли для выполнения операции. Роли `Admin` разрешено выполнять все операции.                                                    |
| `Claims`                      | Утверждения веб-токена JSON (JWT) пользователя или приложения. Свойства утверждений различаются в зависимости от организации и конфигурации Azure Active Directory. |

#### <a name="api-properties-schema"></a>Схема свойств API

[События API](apis.md) имеют следующие свойства.

| Поле                        | Описание                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Всегда `ApiEvent`, что помечает событие журнала как событие API.                                                                 |
| `properties.userAgent`       | Агент-браузер, отправивший запрос, или `unknown`.                                                                        |
| `properties.method`          | Метод HTTP: `GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Относительный путь запроса.                                                                                          |
| `properties.origin`          | URI, указывающий, откуда происходит получение данных, или `unknown`.                                                                  |
| `properties.operationStatus` | `Success` для кода состояния HTTP < 400 <br> `ClientError` для кода состояния HTTP < 500 <br> `Error` для кода состояния HTTP >= 500 |
| `properties.tenantId`        | ИД организации                                                                                                        |
| `properties.tenantName`      | Название организации.                                                                                              |
| `properties.callerObjectId`  | ObjectId вызывающего объекта в Azure Active Directory.                                                                         |
| `properties.instanceId`      | `instanceId` Customer Insights                                                                                         |

### <a name="workflow-event-schema"></a>Схема событий рабочих процессов

Рабочий процесс состоит из нескольких шагов: [прием источников данных](data-sources.md), [объединение](data-unification.md), [обогащение](enrichment-hub.md) и [экспорт](export-destinations.md) данных. Все эти шаги могут выполняться по отдельности или оркестированно в сочетании со следующими процессами.

#### <a name="operation-types"></a>Типы операций

| Тип операции     | Группа                                     |
| ----------------- | ----------------------------------------- |
| Прием (Ingestion)         | [Источники данных](data-sources.md)           |
| Подготовка данных (DataPreparation)   | [Источники данных](data-sources.md)           |
| Сопоставление (Map)               | [Объединение данных](data-unification.md)   |
| Поиск совпадений (Match)             | [Объединение данных](data-unification.md)   |
| Объединение (Merge)             | [Объединение данных](data-unification.md)   |
| Сохранение профиля (ProfileStore)      | [Профили клиентов](customer-profiles.md) |
| Поиск (Search)            | [Профили клиентов](customer-profiles.md) |
| Действие (Activity)          | [Действия](activities.md)                  |
| Меры атрибутов (AttributeMeasures) | [Сегменты и меры](segments.md)      |
| Меры сущностей (EntityMeasures)    | [Сегменты и меры](segments.md)      |
| Меры (Measures)          | [Сегменты и меры](segments.md)      |
| Сегментация (Segmentation)      | [Сегменты и меры](segments.md)      |
| Обогащение (Enrichment)        | [Обогащение](enrichment-hub.md)                                          |
| Аналитика (Intelligence)      | [Прогнозы](predictions-overview.md)                                          |
| AI Builder (AiBuilder)         | [Прогнозы](predictions-overview.md)                                          |
| Аналитические выводы (Insights)          | [Прогнозы](predictions-overview.md)                                          |
| Экспорт (Export)            | [Экспорты](export-destinations.md)                                          |
| Управление моделями (ModelManagement)   | [Прогнозы](custom-models.md)                                           |
| Связь (Relationship)      | [Объединение данных](relationships.md)                                           |

#### <a name="field-description"></a>Описание поля

| Поле           | Тип данных  | Обязательное/необязательное | Description                                                                                                                                                   | Пример                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Метка времени | Обязательное          | Метка времени события (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Обязательное          | ResourceId экземпляра, создавшего событие.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Обязательное          | Имя операции, представляемой этим событием. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Подробнее см. в разделе [Типы операций](#operation-types). | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Обязательное          | Категория журнала события. Всегда `Operational` для событий рабочих процессов                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | Обязательное          | Состояние события. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Long      | Необязательное          | Длительность операции в секундах.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Необязательное          | Объект JSON с дополнительными свойствами для конкретной категории событий.                                                                                        | См. подраздел [свойства рабочего процесса](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Обязательное          | Уровень серьезности события.                                                                                                                                  | `Informational`, `Warning` или `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Схема свойств рабочего процесса

События рабочих процессов имеют следующие свойства.

| Поле              | Workflow | Задача | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Да      | Да  | Всегда `WorkflowEvent`, что помечает событие как событие рабочего процесса.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Да      | Да  | Идентификатор выполнения рабочего процесса. Все события рабочего процесса и задачи в рамках выполнения рабочего процесса имеют одно и то же значение `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Да      | Да  | Идентификатор операции, см. раздел [Типы операций](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Да      | No   | Только для рабочих процессов. Количество задач, активируемых рабочим процессом.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Да      | Нет   | Необязательно. Только для событий рабочих процессов. [objectId в Azure Active Directory пользователя](/azure/marketplace/find-tenant-object-id#find-user-object-id), который активировал рабочий процесс; см. также `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Да      | Нет   | Полное (`full`) или добавочное (`incremental`) обновление.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Да      | Нет   | `OnDemand` или `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Да      | Нет   | `Running` или `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Да      | Да  | Метка времени UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Да      | Да  | Метка времени UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Да      | Да  | Метка времени UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Да      | Да  | `instanceId` Customer Insights                                                                                                                                                                                                                              |  
| `properties.identifier`                      | Нет       | Да  | - Для OperationType =`Export` идентификатор представляет собой GUID конфигурации экспорта. <br> - Для OperationType =`Enrichment` это GUID обогащения <br> - Для OperationType = `Measures` или `Segmentation` идентификатор представляет собой имя сущности. |
| `properties.friendlyName`                    | Нет       | Да  | Понятное имя экспорта или обрабатываемой сущности.                                                                                                                                                                                           |
| `properties.error`                           | Нет       | Да  | Необязательно. Сообщение об ошибке с дополнительными подробностями.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | Нет       | Да  | Необязательно. Только для OperationType = `Export`. Определяет тип экспорта. Дополнительные сведения см. в [обзоре пунктов назначения экспорта](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | Нет       | Да  | Необязательно. Только для OperationType = `Export`. Содержит список настроенных сущностей в экспорте.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | Нет       | Да  | Необязательно. Только для OperationType = `Export`. Подробное сообщение для экспорта.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | Нет       | Да  | Необязательно. Только для OperationType = `Segmentation`. Указывает общее количество участников в сегменте.                                                                                                                                                    |
