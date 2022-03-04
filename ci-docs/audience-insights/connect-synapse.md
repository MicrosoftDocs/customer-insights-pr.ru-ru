---
title: Принять данные из Azure Synapse Analytics
description: Используйте базу данных в Azure Synapse как источник данных в Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 163bef897880f0497bf00e90fd095621a2d14378
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/25/2022
ms.locfileid: "8356030"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Подключиться к источнику данных Azure Synapse (предварительная версия).

Azure Synapse Analytics — это служба корпоративной аналитики, которая ускоряет получение аналитик из хранилищ данных и систем больших данных. Azure Synapse Analytics объединяет лучшие технологии SQL, используемые в корпоративных хранилищах данных, технологии Spark, используемые для больших данных, Data Explorer для анализа журналов и временных рядов, конвейеры для интеграции данных и ETL/ELT, а также глубокую интеграцию с другими службами Azure, такими как Power BI, Cosmos DB и AzureML.

Дополнительные сведения см. в разделе [Azure Synapse Обзор](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Предварительные условия

Для настройки подключения из Customer Insights к Azure Synapse должны быть выполнены следующие предварительные условия.

> [!IMPORTANT]
> Обязательно установите все **назначения ролей**, как описано.  

## <a name="prerequisites-in-customer-insights"></a>Предварительные требования в Customer Insights

* Необходимо иметь роль **администратора** в Customer Insights. Узнать больше о [разрешениях пользователей в аналитике аудитории](permissions.md#assign-roles-and-permissions).

В Azure: 

- Активная подписка Azure.

- При использовании новой учетной записи Azure Data Lake Storage 2-го поколения *субъекту службы для аналитики аудитории* необходимы разрешения **участника данных больших двоичных объектов хранилищ**. Дополнительные сведения о [подключении к Azure Data Lake Storage с субъектом-службой для аналитики аудитории](connect-service-principal.md). В Data Lake Storage 2-го поколения **должно быть** включено [иерархическое пространство имен](/azure/storage/blobs/data-lake-storage-namespace).

- В группе ресурсов, в которой расположена рабочая область Azure Synapse, *субъект-службе* и *пользователю для аналитики аудитории* необходимо назначить по крайней мере разрешения **Читатель**. Дополнительные сведения см. в разделе [Назначение ролей Azure с помощью портала Azure](/azure/role-based-access-control/role-assignments-portal).

- *Пользователю* требуются разрешения **Участник данных больших двоичных объектов хранилища** в учетной записи Azure Data Lake Storage 2-го поколения, в которой данные расположены и связаны с рабочей областью Azure Synapse. Узнайте больше об [использовании портала Azure для назначения роли Azure для доступа к данным BLOB-объектов и очередей](/azure/storage/common/storage-auth-aad-rbac-portal) и о [разрешениях участника данных больших двоичных объектов хранилища](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Для *[управляемого удостоверения рабочей области Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* требуются разрешения **Участник данных больших двоичных объектов хранилища** в учетной записи Azure Data Lake Storage 2-го поколения, в которой данные расположены и связаны с рабочей областью Azure Synapse. Узнайте больше об [использовании портала Azure для назначения роли Azure для доступа к данным BLOB-объектов и очередей](/azure/storage/common/storage-auth-aad-rbac-portal) и о [разрешениях участника данных больших двоичных объектов хранилища](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- В рабочей области Azure Synapse *субъект-служба для аналитики аудитории* должна быть назначена роль **Администратор Synapse**. Дополнительные сведения см. в разделе [Как настроить контроль доступа к вашей рабочей области Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Подключение к базам данных озера данных в Azure Synapse Analytics

1. Перейдите в раздел **Данные** > **Источники данных**.

1. Выберите **Добавить источник данных**.

1. Выбрать метод **Azure Synapse Analytics(Предварительная версия)**.

1. Укажите **Имя** для источника данных и выберите **Далее** для создания источника данных. 

1. Выберите [доступное подключение](connections.md) для Azure Synapse Analytics или создания новой.

1. Выберите **База данных озера** из рабочей области, подключенной в выбранном Azure Synapse Analytics подключении и выберите **Далее**.

1. Выберите сущности для приема из подключенной базы данных. 

1. При необходимости выберите сущности данных, для которых разрешено профилирование данных. 

1. Выбирать **Сохранить**, чтобы применить ваш выбор и начать прием данных из недавно созданного источник данных, связанного с таблицами базы данных озера в Azure Synapse Analytics.
