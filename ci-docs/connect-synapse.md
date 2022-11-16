---
title: Подключиться к источнику данных Azure Synapse (предварительная версия).
description: Используйте базу данных в Azure Synapse как источник данных в Dynamics 365 Customer Insights.
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 675fd03c44a7a7a492b111895d79c2e77f93a5b5
ms.sourcegitcommit: 4ba74816ebfa46412c64c40a61e1f31c4ccc40f2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2022
ms.locfileid: "9738172"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Подключиться к источнику данных Azure Synapse Analytics (предварительная версия).

Azure Synapse Analytics — это служба корпоративной аналитики, которая ускоряет получение аналитик из хранилищ данных и систем больших данных. Azure Synapse Analytics объединяет лучшие технологии SQL, используемые в корпоративных хранилищах данных, технологии Spark, используемые для больших данных, Data Explorer для анализа журналов и временных рядов, конвейеры для интеграции данных и ETL/ELT, а также глубокую интеграцию с другими службами Azure, такими как Power BI, Cosmos DB и AzureML.

Дополнительные сведения см. в разделе [Azure Synapse Обзор](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Предварительные условия

> [!NOTE]
> Рабочие области Synapse, в которых [включен брандмауэр](/azure/synapse-analytics/security/synapse-workspace-ip-firewall), в настоящее время не поддерживаются.
> [!IMPORTANT]
> Обязательно установите все **назначения ролей**, как описано.  

**В Customer Insights**:

* Необходимо иметь роль **администратора** в Customer Insights. Узнать больше о [разрешениях пользователей в Customer Insights](permissions.md#add-users).

**В Azure**:

- Активная подписка Azure.

- Если использовать новую учетную запись Azure Data Lake Storage Gen2, *субъекту-службе*, то есть "Dynamics 365 AI for Customer Insights", нужны разрешения **участника данных больших двоичных объектов хранилища**. Дополнительные сведения о [подключении к Azure Data Lake Storage с субъектом-службой для Customer Insights](connect-service-principal.md). В Data Lake Storage 2-го поколения **должно быть** включено [иерархическое пространство имен](/azure/storage/blobs/data-lake-storage-namespace).

- В группе ресурсов, в которой находится Azure Synapse workspace, *субъект-служба*, то есть "Dynamics 365 AI for Customer Insights", и *пользователь для Customer Insights* должны иметь разрешения не менее **Читатель**. Дополнительные сведения см. в разделе [Назначение ролей Azure с помощью портала Azure](/azure/role-based-access-control/role-assignments-portal).

- *Пользователю* требуются разрешения **Участник данных больших двоичных объектов хранилища** в учетной записи Azure Data Lake Storage 2-го поколения, в которой данные расположены и связаны с рабочей областью Azure Synapse. Узнайте больше об [использовании портала Azure для назначения роли Azure для доступа к данным BLOB-объектов и очередей](/azure/storage/common/storage-auth-aad-rbac-portal) и о [разрешениях участника данных больших двоичных объектов хранилища](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Для *[управляемого удостоверения рабочей области Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* требуются разрешения **Участник данных больших двоичных объектов хранилища** в учетной записи Azure Data Lake Storage 2-го поколения, в которой данные расположены и связаны с рабочей областью Azure Synapse. Узнайте больше об [использовании портала Azure для назначения роли Azure для доступа к данным BLOB-объектов и очередей](/azure/storage/common/storage-auth-aad-rbac-portal) и о [разрешениях участника данных больших двоичных объектов хранилища](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- В Azure Synapse workspace *субъекту-службе для Customer Insights*, то есть "Dynamics 365 AI for Customer Insights", должна быть назначена роль **администратора Synapse**. **Пользователю** нужна хотя бы роль **Участник Synapse**, назначенная для рабочей области. Дополнительные сведения см. в разделе [Как настроить контроль доступа к вашей рабочей области Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

- Если ваша среда Customer Insights хранит данные в [собственном Azure Data Lake Storage](own-data-lake-storage.md), пользователь, устанавливающий соединение с Azure Synapse Analytics, должен иметь хотя бы встроенную роль **Читатель** в учетной записи Data Lake Storage. Дополнительные сведения см. в разделе [Назначение ролей Azure с помощью портала Azure](/azure/role-based-access-control/role-assignments-portal).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Подключение к базам данных озера данных в Azure Synapse Analytics

1. Перейдите в раздел **Данные** > **Источники данных**.

1. Выберите **Добавить источник данных**.

1. Выбрать метод **Azure Synapse Analytics(Предварительная версия)**.

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Диалоговое окно для подключения к данным Synapse Analytics":::
  
1. Введите **Имя** для источника данных и, при желании, **Описание**.

1. Выберите [доступное подключение](connections.md) для Azure Synapse Analytics или [создайте новое](export-azure-synapse-analytics.md#set-up-connection-to-azure-synapse).

1. Выберите **База данных** из рабочей области, подключенной в выбранном Azure Synapse Analytics подключении и выберите **Далее**. В настоящее время мы поддерживаем только тип базы данных *База данных озера*.

1. Выберите сущности для приема из подключенной базы данных и выберите **Далее**.

1. При необходимости выберите сущности данных, для которых разрешено профилирование данных.

1. Выбирать **Сохранить**, чтобы применить ваш выбор и начать прием данных из недавно созданного источник данных, связанного с таблицами базы данных озера в Azure Synapse Analytics. Открывается страница **Источники данных** с новым источником данных в статусе **Обновление**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Загрузка данных может занять время. После успешного обновления принятые данные можно проверить на странице [**Сущности**](entities.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
