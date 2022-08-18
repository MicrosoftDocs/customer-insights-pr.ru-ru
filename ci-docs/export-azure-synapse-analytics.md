---
title: Экспорт данных в Azure Synapse Analytics (предварительная версия)
description: Узнайте, как настроить подключение к Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 0e953cfff12df433d033717d58b28c2834468916
ms.sourcegitcommit: 086f75136132d561cd78a4c2cb1e1933e2301f32
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/11/2022
ms.locfileid: "9259860"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Экспорт данных в Azure Synapse Analytics (предварительная версия)

Azure Synapse — это служба аналитики, которая ускоряет анализ хранилищ данных и систем больших данных. Вы можете получать и использовать свои данные Customer Insights в [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Предварительные условия

> [!NOTE]
> Обязательно установите все **назначения ролей**, как описано.

- Ваша учетная запись пользователя Azure Active Directory (AD) должна иметь [роль администратора](permissions.md#add-users) в Customer Insights.

В Azure:

- Активная подписка Azure.

- Если использовать новую учетную запись Azure Data Lake Storage 2-го поколения, [субъект-служба для Customer Insights](connect-service-principal.md) имеет разрешения **участника данных хранилища BLOB-объектов**. В Data Lake Storage 2-го поколения **должно быть** включено [иерархическое пространство имен](/azure/storage/blobs/data-lake-storage-namespace).

- В группе ресурсов, в которой находится Azure Synapse workspace, *субъект-служба* и пользователь *Azure AD с разрешениями администратора в Customer Insights* должны иметь [разрешения](/azure/role-based-access-control/role-assignments-portal) не менее уровня **Читатель**.

- *Пользователь Azure AD с разрешениями администратора в Customer Insights* имеет разрешения **участника данных хранилища BLOB-объектов** в учетной записи Azure Data Lake Storage 2-го поколения, в которой находятся данные и связаны с Azure Synapse workspace. Узнайте больше об [использовании портала Azure для назначения роли Azure для доступа к данным BLOB-объектов и очередей](/azure/storage/common/storage-auth-aad-rbac-portal) и о [разрешениях участника данных больших двоичных объектов хранилища](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Для *[управляемого удостоверения рабочей области Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* имеются разрешения **Участника данных хранилища BLOB-объектов** в учетной записи Azure Data Lake Storage 2-го поколения, в которой данные расположены и связаны с Azure Synapse workspace. Узнайте больше об [использовании портала Azure для назначения роли Azure для доступа к данным BLOB-объектов и очередей](/azure/storage/common/storage-auth-aad-rbac-portal) и о [разрешениях участника данных больших двоичных объектов хранилища](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- В Azure Synapse workspace *субъекту-службе для Customer Insights* должна быть [назначена роль](/azure/synapse-analytics/security/how-to-set-up-access-control) **администратора Synapse**.

- Если ваша среда Customer Insights хранит данные в [собственном Azure Data Lake Storage](own-data-lake-storage.md), пользователь, устанавливающий соединение с Azure Synapse Analytics, должен иметь хотя бы встроенную роль **Читатель** в учетной записи Data Lake Storage. Дополнительные сведения см. в разделе [Назначение ролей Azure с помощью портала Azure](/azure/role-based-access-control/role-assignments-portal).

## <a name="set-up-connection-to-azure-synapse"></a>Настройка подключения к Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Перейти в раздел **Администрирование** > **Подключения**.

1. Выберите **Добавить подключение**, затем выберите **Azure Synapse Analytics**.

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. Укажите, кто может использовать это подключение. По умолчанию это только администраторы. Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Выберите или найдите подписку, в которой вы хотите использовать данные Customer Insights. Как только подписка выбрана, вы также можете выбрать параметры **Рабочая область**, **Учетная запись хранения** и **Контейнер**.

1. Ознакомьтесь с положениями [Соответствие и конфиденциальность данных](connections.md#data-privacy-and-compliance) и выберите **Принимаю**.

1. Выберите **Сохранить**, чтобы завершить подключение.

## <a name="configure-an-export"></a>Настройка экспорта

[!INCLUDE [export-permission-include](includes/export-permission.md)] Для настройки экспорта с общим подключением необходимы как минимум разрешения **Участник** в Customer Insights.

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Выберите **Добавить экспорт**.

1. В поле **Подключение для экспорта** выберите подключение из раздела Azure Synapse Analytics. Свяжитесь с администратором, если подключение недоступно.

1. Укажите узнаваемое **Отображаемое имя** для вашего экспорта и **Имя базы данных**. Экспорт создаст новую [базу данных озера Azure Synapse](/azure/synapse-analytics/database-designer/concepts-lake-database) в рабочей области, определенной в подключении.

1. Выберите объекты, в которые вы хотите экспортировать Azure Synapse Analytics.
   > [!NOTE]
   > Источники данных на основе [папки Common Data Model](connect-common-data-model.md) не поддерживаются.

1. Выберите **Сохранить**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Чтобы запросить данные, которые были экспортированы в Synapse Analytics, вам нужен доступ **Читатель данных хранилища BLOB-объектов** к целевому хранилищу в рабочей области экспорта.

## <a name="update-an-export"></a>Обновление экспорта

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Выберите **Изменить** для экспорта, который требуется обновить.

   - **Добавьте** или **Удалите** сущности из выборки. Если сущности удаляются из выборки, они не удаляются из базы данных Synapse Analytics. Однако будущие обновления данных не будут обновлять удаленные сущности в этой базе данных.

   - **Изменение имени базы данных** создает новую базу данных Synapse Analytics. База данных с именем, которое было настроено ранее, не будет получать никаких обновлений при будущих обновлениях.

[!INCLUDE [footer-include](includes/footer-banner.md)]
