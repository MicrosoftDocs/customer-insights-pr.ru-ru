---
title: Работайте с данными Customer Insights в Microsoft Dataverse
description: Узнайте, как связать Customer Insights с Microsoft Dataverse и ознакомьтесь с выходными сущностями, экспортируемыми в Dataverse.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 0d536259f310b41fe12922baeebdc4569937db08
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303845"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Работайте с данными Customer Insights в Microsoft Dataverse

Customer Insights предоставляет возможность сделать выходные сущности доступными в [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Эта интеграция обеспечивает простой обмен данными и индивидуальную разработку с помощью подхода с минимальным кодом или без кода. [Выходные сущности](#output-entities) доступны в виде таблиц в среде Dataverse. Вы можете использовать данные для любого другого приложения на основе таблиц Dataverse. Эти таблицы позволяют реализовать такие сценарии, как автоматизированные рабочие процессы посредством Power Automate или создание приложений в Power Apps.

Подключение к вашему среде Dataverse также позволяет [принимать данные из локальных источников данных, используя Power Platform потоки данных и шлюзы](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Предварительные условия

- Customer Insights и среды Dataverse должны размещаться в одном регионе.
- Настроена роль глобального администратора в среде Dataverse. Проверьте, [связана ли среда Dataverse](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) с определенными группами безопасности, и убедитесь, что вы добавлены в эти группы безопасности.
- Никакая другая среда Customer Insights еще не связана со средой Dataverse, к которой требуется подключиться. Узнайте, как [удалить существующее подключение к среде Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).
- Среда Microsoft Dataverse, подключенная к одной учетной записи хранения, если вы настроили среду на [использование своего Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Объем обслуживания емкости хранилища Dataverse

Подписка на Customer Insights дает вам право на дополнительные возможности для существующих ресурсов вашей организации [Емкость хранилища Dataverse](/power-platform/admin/capacity-storage). Дополнительная емкость зависит от количества профилей, которые использует ваша подписка.

**Пример:**

Предположим, вы получаете 15 ГБ для хранения базы данных и 20 ГБ для хранения файлов на 100 000 профилей клиентов. Если ваша подписка включает 300 000 профилей клиентов, общая емкость хранилища составляет 45 ГБ (3 x 15 ГБ) для хранения базы данных и 60 ГБ для хранения файлов (3 x 20 ГБ). Точно так же, если у вас есть подписка "бизнес-бизнес" с 30 000 учетных записей, общая емкость хранилища составляет 45 ГБ (3 x 15 ГБ) для хранения базы данных и 60 ГБ для хранения файлов (3 x 20 ГБ).

Емкость журнала не является добавочной и фиксирована для вашей организации.

Дополнительные сведения об объемах обслуживания емкости см. в разделе [Руководство по лицензированию Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Подключите среду Dataverse к Customer Insights

На шаге **Microsoft Dataverse** можно связать Customer Insights со средой Dataverse при одновременном [создании среды Customer Insights](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="обмен данными с Microsoft Dataverse автоматически включен для новых сред.":::

1. Укажите URL-адрес вашей среды Dataverse или оставьте поле пустым, чтобы оно было создано для вас.

   > [!NOTE]
   > После установления связи между Customer Insights и Dataverse не меняйте название организации для среды Dataverse. Название организации используется в URL-адресе Dataverse и измененное имя разрывает подключение с Customer Insights.

   [Администраторы Power Platform могут управлять тем, кто может создавать новые среды Dataverse](/power-platform/admin/control-environment-creation). Если вы пытаетесь настроить новую среду Customer Insights и не можете, возможно, что администратор отключил возможность создания сред Dataverse для всех пользователей, кроме администраторов.

1. Если вы используете собственную учетную запись Data Lake Storage:
   1. Выберите **Включить обмен данными** с Dataverse.
   1. Введите **Идентификатор разрешений**. Чтобы получить идентификатор разрешений, [включите обмен данными с Dataverse из вашего собственного Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Включить обмен данными с Dataverse из собственного Azure Data Lake Storage (предварительная версия)

В [вашей собственной учетной записи Azure Data Lake Storage](own-data-lake-storage.md) проверьте, что у пользователя, настраивающего среду Customer Insights, имеются как минимум разрешения **Модуль чтения данных BLOB-объектов хранилища** в контейнере `customerinsights` в учетной записи хранилища.

### <a name="limitations"></a>Ограничения

- Только взаимно-однозначное сопоставление между организацией Dataverse и учетной записью Azure Data Lake Storage. Когда организация Dataverse подключена к учетной записи хранения, она не может подключиться к другой учетной записи хранения. За счет этого ограничения Dataverse не заполняет разные учетные записи хранения.
- Обмен данными не будет работать, если для доступа к вашей учетной записи Azure Data Lake Storage требуется настройка приватного канала Azure, так как он находится за межсетевым экраном. Dataverse в настоящее время не поддерживает подключение к частным конечным точкам через приватный канал.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Настройка групп безопасности вашего собственного Azure Data Lake Storage

1. Создайте две группы безопасности в своей подписке Azure — одну группу безопасности **Читатель** и одну группу безопасности **Участник** и задайте службу Microsoft Dataverse в качестве владельца обеих групп безопасности.

1. Управляйте списком управления доступом (ACL) в контейнере `customerinsights` в своей учетной записи хранения с помощью этих групп безопасности.
   1. Добавьте службу Microsoft Dataverse и любые бизнес-приложения на основе Dataverse, такие как Dynamics 365 Marketing, в группу безопасности **Читатель** с разрешениями **только для чтения**.
   1. Добавьте *только* приложение Customers Insights для группы безопасности **Участник** для предоставления разрешений на **чтение и запись**, чтобы записывать профили и аналитику.

### <a name="set-up-powershell"></a>Настройка PowerShell

Настройте PowerShell для выполнения сценариев PowerShell.

1. Установите последнюю версию [Azure Active Directory PowerShell для Graph](/powershell/azure/active-directory/install-adv2).
   1. На ПК нажмите клавишу Windows на клавиатуре и выполните поиск **Windows PowerShell**, затем выберите **Запуск от имени администратора**.
   1. В открывшемся окне PowerShell введите `Install-Module AzureAD`.

1. Импортируйте три модуля.
   1. В окне Powershell введите `Install-Module -Name Az.Accounts` и выполните следующее.
   1. Повторите для `Install-Module -Name Az.Resources` и `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Выполнение сценариев PowerShell и получение идентификатора разрешения

1. Загрузите два сценария PowerShell, которые вам нужно запустить, из [репозитория GitHub](https://github.com/trin-msft/byol) нашего специалиста.
   - `CreateSecurityGroups.ps1`: требует разрешений администратора клиента.
   - `ByolSetup.ps1`: требуются разрешения владельца данных BLOB-объектов хранилища на уровне учетной записи хранения или контейнера. Этот скрипт создаст разрешение для вас. Ваше назначение роли может быть удалено вручную после успешного запуска сценария.

1. Выполните `CreateSecurityGroups.ps1` в Windows PowerShell, указав идентификатор подписки Azure, содержащий ваш Azure Data Lake Storage. Откройте сценарий PowerShell в редакторе, чтобы просмотреть дополнительную информацию и реализованную логику.

   Этот скрипт создает две группы безопасности в вашей подписке Azure: одну для группы "Читатель" и другую для группы "Участник". Служба Microsoft Dataverse является владельцем обеих этих групп безопасности.

1. Сохраните оба значения ID группы безопасности, сгенерированные этим сценарием, чтобы использовать их в сценарии `ByolSetup.ps1`.

   > [!NOTE]
   > Создание группы безопасности можно отключить в вашем клиенте. В этом случае потребуется ручная настройка, и ваш администратор Azure AD должен был [включить создание групп безопасности](/azure/active-directory/enterprise-users/groups-self-service-management).

1. Выполните сценарий `ByolSetup.ps1` в Windows PowerShell, указав идентификатор подписки Azure, содержащий ваш Azure Data Lake Storage, имя учетной записи хранения, имя группы ресурсов и значения идентификаторов группы безопасности "Читатель" и "Участник". Откройте сценарий PowerShell в редакторе, чтобы просмотреть дополнительную информацию и реализованную логику.

   Этот сценарий добавляет необходимое управление доступом на основе ролей для службы Microsoft Dataverse и любых бизнес-приложений на основе Dataverse. Это также обновляет список управления доступом (ACL) в контейнере `customerinsights` для групп безопасности, созданных с помощью сценария `CreateSecurityGroups.ps1`. Группа "Участник" получает разрешение *rwx*, а группа "Читатели" получает только разрешение *r-x*.

1. Скопируйте выходную строку, которая выглядит следующим образом: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Введите скопированную выходную строку в поле **Идентификатор разрешений** на шаге настройки среды для Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Параметры конфигурации, позволяющие включить обмен данными с вашими собственными Azure Data Lake Storage с Microsoft Dataverse.":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Удаление существующего подключения к среде Dataverse

При подключении к среде Dataverse сообщение об ошибке **Эта организация CDS уже подключена к другому экземпляру Customer Insights** означает, что среда Dataverse уже используется в среде Customer Insights. Вы можете удалить существующее соединение как глобальный администратор в среде Dataverse. Внесение изменений может занять несколько часов.

1. Перейдите к [Power Apps](https://make.powerapps.com).
1. Выберите среду из средства выбора сред.
1. Перейдите в **Решения**.
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

| Column            | Type        | Description                                                                              |
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

| Column               | Type        | Description                                          |
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


[!INCLUDE [footer-include](includes/footer-banner.md)]
