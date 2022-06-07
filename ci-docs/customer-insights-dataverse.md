---
title: Работайте с данными Customer Insights в Microsoft Dataverse
description: Узнайте, как связать Customer Insights с Microsoft Dataverse и ознакомьтесь с выходными сущностями, экспортируемыми в Dataverse.
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 3848e143bc7cb2f345bc698a274b92148ef00669
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833692"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Работайте с данными Customer Insights в Microsoft Dataverse

Customer Insights предоставляет возможность сделать выходные сущности доступными в виде [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Эта интеграция обеспечивает простой обмен данными и индивидуальную разработку с помощью подхода с минимальным кодом или без кода. [Выходные сущности](#output-entities) доступны в виде таблиц в среде Dataverse. Вы можете использовать данные для любого другого приложения на основе таблиц Dataverse. Эти таблицы позволяют реализовать такие сценарии, как автоматизированные рабочие процессы посредством Power Automate или создание приложений в Power Apps.

Подключение к вашему среде Dataverse также позволяет [принимать данные из локальных источников данных, используя Power Platform потоки данных и шлюзы](data-sources.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Предварительные условия

- Customer Insights и среды Dataverse должны размещаться в одном регионе.
- У вас должна быть глобальная роль администратора в среде Dataverse. Проверьте, [связана ли среда Dataverse](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) с определенными группами безопасности, и убедитесь, что вы добавлены в эти группы безопасности.
- Никакая другая среда Customer Insights еще не связана со средой Dataverse, к которой требуется подключиться. Узнайте, как [удалить существующее подключение к среде Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).
- Среду Microsoft Dataverse можно подключить только к одной учетной записи хранения. Это применимо только в том случае, если вы настроите среду на [использование Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Подключите среду Dataverse к Customer Insights

На шаге **Microsoft Dataverse** можно связать Customer Insights со средой Dataverse при одновременном [создании среды Customer Insights](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="обмен данными с Microsoft Dataverse автоматически включен для новых сред.":::

Администраторы могут настроить Customer Insights, чтобы выполнить подключение к существующей среде Dataverse. Путем предоставления URL-адреса для среды Dataverse, осуществляется подключение к их новой среде Customer Insights.

Если вы не хотите использовать существующую среду Dataverse, система создает новую среду для данных Customer Insights в вашем клиенте. [Администраторы Power Platform могут управлять тем, кто может создавать среды](/power-platform/admin/control-environment-creation). Если вы настраиваете новую среду Customer Insights, а администратор отключил возможность создания среды Dataverse для всех пользователей, кроме администраторов, возможно, вам не удастся создать новую среду.

**Включите обмен данными** с Dataverse, установив флажок функции обмена данными.

Если вы используете собственную учетную запись Data Lake Storage, вам также потребуется **Идентификатор разрешений**. Дополнительные сведения о том, как получить идентификатор разрешений, см. в следующем разделе.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Включить обмен данными с Dataverse из собственного Azure Data Lake Storage (предварительная версия)

Чтобы включить обмен данными с Microsoft Dataverse, когда ваша среда [использует вашу собственную учетную запись Azure Data Lake Storage](own-data-lake-storage.md), может потребоваться выполнить дополнительную настройку. У пользователя, настраивающего среду Customer Insights, должны быть как минимум разрешения **Модуль чтения данных BLOB-объектов хранилища** в контейнере *CustomerInsights* в учетной записи Azure Data Lake Storage.

1. Создайте две группы безопасности в своей подписке Azure — одну группу безопасности **Читатель** и одну группу безопасности **Участник** и задайте службу Microsoft Dataverse в качестве владельца обеих групп безопасности.
2. Управляйте списком управления доступом (ACL) в контейнере CustomerInsights в своей учетной записи хранения с помощью этих групп безопасности. Добавьте службу Microsoft Dataverse и любые бизнес-приложения на основе Dataverse, такие как Dynamics 365 Marketing, в группу безопасности **Читатель** с разрешениями **только для чтения**. Добавьте *только* приложение Customers Insights для группы безопасности **Участник** для предоставления разрешений на **чтение и запись**, чтобы записывать профили и аналитику.

### <a name="limitations"></a>Ограничения

Есть два ограничения при использовании Dataverse с собственной учетной записью Azure Data Lake Storage:

- Между организацией Dataverse и учетной записью Azure Data Lake Storage существует взаимно-однозначное сопоставление. Когда организация Dataverse подключена к учетной записи хранения, она не может подключиться к другой учетной записи хранения. За счет этого ограничения Dataverse не заполняет разные учетные записи хранения.
- Обмен данными не будет работать, если для доступа к вашей учетной записи хранения Azure Data Lake требуется настройка приватного канала Azure, так как он находится за межсетевым экраном. Dataverse в настоящее время не поддерживает подключение к частным конечным точкам через приватный канал.

### <a name="set-up-powershell"></a>Настройка PowerShell

Для выполнения сценариев PowerShell сначала необходимо соответствующим образом настроить PowerShell.

1. Установите последнюю версию [Azure Active Directory PowerShell для Graph](/powershell/azure/active-directory/install-adv2).
   1. На ПК нажмите клавишу Windows на клавиатуре и выполните поиск **Windows PowerShell**, затем выберите **Запуск от имени администратора**.
   1. В открывшемся окне PowerShell введите `Install-Module AzureAD`.
2. Импортируйте три модуля.
    1. В окне Powershell введите `Install-Module -Name Az.Accounts` и выполните следующее.
    1. Повторите для `Install-Module -Name Az.Resources` и `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Шаги настройки

1. Загрузите два сценария PowerShell, которые вам нужно запустить, из [репозитория GitHub](https://github.com/trin-msft/byol) нашего специалиста.
    1. `CreateSecurityGroups.ps1`
       - Чтобы выполнит этот сценарий PowerShell, требуются разрешения *администратора клиента*.
       - Этот сценарий PowerShell создает две группы безопасности в вашей подписке Azure. Один для группы Читатель, а другой для группы Участник и делает службу Microsoft Dataverse владельцем обеих этих групп безопасности.
       - Выполните этот сценарий PowerShell в Windows PowerShell, указав идентификатор подписки Azure, содержащий ваш Azure Data Lake Storage. Откройте сценарий PowerShell в редакторе, чтобы просмотреть дополнительную информацию и реализованную логику.
       - Сохраните оба значения ID группы безопасности, сгенерированные этим сценарием, потому что мы будем использовать их в сценарии `ByolSetup.ps1`.

        > [!NOTE]
        > Создание группы безопасности можно отключить в вашем клиенте. В этом случае потребуется ручная настройка, и ваш администратор Azure AD должен был [включить создание групп безопасности](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Вам нужны разрешения *Владелец данных BLOB-объектов хранилища* на уровне учетной записи хранения/контейнера для запуска этого сценария или этот сценарий создаст его для вас. Ваше назначение роли может быть удалено вручную после успешного запуска сценария.
        - Этот сценарий PowerShell добавляет необходимое управление доступом на основе ролей (RBAC) для службы Microsoft Dataverse и любых бизнес-приложений на основе Dataverse. Это также обновляет список управления доступом (ACL) в контейнере CustomerInsights для групп безопасности, созданных с помощью сценария `CreateSecurityGroups.ps1`. Группа Участник будет иметь разрешение *rwx*, а группа Читатели будут иметь только разрешение *r-x*.
        - Выполните этот сценарий PowerShell в Windows PowerShell, указав идентификатор подписки Azure, содержащий ваш Azure Data Lake Storage, имя учетной записи хранения, имя группы ресурсов и значения идентификаторов группы безопасности "Читатель" и "Участник". Откройте сценарий PowerShell в редакторе, чтобы просмотреть дополнительную информацию и реализованную логику.
        - Скопируйте выходную строку после успешного запуска сценария. Выходная строка выглядит следующим образом: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Введите выходную строку, скопированную вверху, в поле **Идентификатор разрешений** на шаге настройки среды для Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Параметры конфигурации, позволяющие включить обмен данными с вашими собственными Azure Data Lake Storage с Microsoft Dataverse.":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Удаление существующего подключения к среде Dataverse

При подключении к среде Dataverse сообщение об ошибке **Эта организация CDS уже подключена к другому экземпляру Customer Insights** означает, что среда Dataverse уже используется в среде Customer Insights. Вы можете удалить существующее соединение как глобальный администратор в среде Dataverse. Внесение изменений может занять несколько часов.

1. Перейдите к [Power Apps](https://make.powerapps.com).
1. Выберите среду из средства выбора сред.
1. Перейдите в **Решения**
1. Удалите решение с именем **Надстройка карточек клиентов Dynamics 365 Customer Insights (предварительная версия)**.

ИЛИ

1. Откройте свою среду Dataverse.
1. Перейдите в раздел **Дополнительные параметры** > **Решения**.
1. Удалите решение **CustomerInsightsCustomerCard**.

Если удалить соединение не удается из-за зависимостей, вам также потребуется удалить зависимости. Дополнительные сведения см. в разделе [Удаление зависимостей](/power-platform/alm/removing-dependencies).

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

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
