---
title: Подключение к учетной записи Azure Data Lake Storage с использованием субъекта-службы
description: Используйте субъект-службу Azure для подключения к собственному озеру данных Data Lake.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: b18d1f42b9510ebf23f0666322819865d132173b
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833413"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Подключение к учетной записи Azure Data Lake Storage с использованием субъекта-службы Azure

В этой статье рассказывается, как связать Dynamics 365 Customer Insights с учетной записью Azure Data Lake Storage, используя субъект-службу Azure, а не учетную запись хранения.

У автоматизированных инструментов, использующих службы Azure, всегда должны быть ограниченные разрешения. Вместо того, чтобы приложения входили в систему как полностью привилегированный пользователь, Azure предлагает субъекты-службы. Вы можете использовать субъекты-службы для безопасного [добавления или редактирования папки Common Data Model в качестве источника данных](connect-common-data-model.md) или [создания или обновления среды](create-environment.md).

> [!IMPORTANT]
>
> - Учетная запись Data Lake Storage, которая будет использовать субъект-службу, должна быть Gen2, в ней должно быть [активировано иерархическое пространство имен](/azure/storage/blobs/data-lake-storage-namespace). Учетные записи хранения Azure Data Lake Gen1 не поддерживаются.
> - Чтобы создать субъект-службу, вам потребуются права администратора для клиента Azure.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Создание субъекта-службы Azure для Customer Insights

Перед созданием нового субъекта-службы для Customer Insights проверьте, не существует ли он уже в вашей организации.

### <a name="look-for-an-existing-service-principal"></a>Поиск существующего субъекта-службы

1. Перейдите на [Портал администрирования Azure](https://portal.azure.com) и войдите в свою организацию.

2. В разделе **Службы Azure** выберите **Azure Active Directory**.

3. В разделе **Управление** выберите **Приложение Microsoft**.

4. Добавьте фильтр для параметра **Идентификатор приложения начинается с** `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` или выполните поиск по названию `Dynamics 365 AI for Customer Insights`.

5. Если вы найдете соответствующую запись, это означает, что субъект-служба уже существует.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Снимок экрана, показывающий существующую субъект-службу.":::

6. Если результаты не возвращаются, можно [создать новый субъект-службу](#create-a-new-service-principal). В большинстве случаев он уже существует, и вам нужно только предоставить разрешения для субъекта-службы на доступ к учетной записи хранения.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Предоставление разрешений субъекту-службе для доступа к учетной записи хранения

Перейдите на портал Azure, чтобы предоставить разрешения субъекту-службе для учетной записи хранения, которую вы хотите использовать в Customer Insights.

1. Перейдите на [Портал администрирования Azure](https://portal.azure.com) и войдите в свою организацию.

1. Откройте учетную запись хранения, к которой субъект-служба для Customer Insights должна иметь доступ.

1. На левой панели выберите **Контроль доступа (IAM)**, затем выберите **Добавить** > **Добавить назначение роли**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Снимок экрана, показывающий портал Azure при добавлении назначения роли.":::

1. На панели **Добавить назначение роли** задайте следующие свойства:
   - Роль: **Участник данных хранилища BLOB-объектов**
   - Назначьте доступ: **Пользователь, группа или субъект-служба**
   - Выберите участников: **Dynamics 365 AI для Customer Insights** ([субъект-служба](#create-a-new-service-principal), которую вы искали ранее в этой процедуре)

1. Выберите **Проверить + назначить**.

Внесение изменений может занять до 15 минут.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Введите идентификатор ресурса Azure или сведения о подписке Azure во вложении учетной записи хранения в Customer Insights

Вы можете привязать учетную запись Data Lake Storage в Customer Insights, чтобы [хранить выходные данные](manage-environments.md) или [использовать как источник данных](connect-dataverse-managed-lake.md). Этот параметр позволяет вам выбирать между подходом на основе ресурсов или подходом на основе подписки. В зависимости от выбранного вами подхода следуйте процедуре, описанной в одном из следующих разделов.

### <a name="resource-based-storage-account-connection"></a>Подключение к учетной записи хранения на основе ресурса

1. Перейдите на [Портал администрирования Azure](https://portal.azure.com), войдите в свою подписку и откройте учетную запись хранения.

1. В левой области перейдите в раздел **Параметры** > **Конечные точки**.

1. Скопируйте значение идентификатора ресурса учетной записи хранения.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Скопируйте идентификатор ресурса учетной записи хранения.":::

1. В Customer Insights вставьте идентификатор ресурса в поле ресурса, отображаемое на экране подключения учетной записи хранения.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Введите сведения идентификатора ресурса учетной записи хранения.":::   

1. Выполните оставшиеся шаги в разделе Customer Insights, чтобы подключить учетную запись хранения.

### <a name="subscription-based-storage-account-connection"></a>Подключение к учетной записи хранения на основе подписки

1. Перейдите на [Портал администрирования Azure](https://portal.azure.com), войдите в свою подписку и откройте учетную запись хранения.

1. На левой панели перейдите к **Параметры** > **Свойства**.

1. Проверьте **Подписка**, **Группа ресурсов** и **Имя** учетной записи хранения, чтобы убедиться, что вы выбрали правильные значения в Customer Insights.

1. В Customer Insights выберите значения для соответствующих полей при подключении учетной записи хранения.

1. Выполните оставшиеся шаги в разделе Customer Insights, чтобы подключить учетную запись хранения.

### <a name="create-a-new-service-principal"></a>Создание субъекта-службы

1. Установите последнюю версию Azure Active Directory PowerShell для Graph. Дополнительную информацию см. в разделе [Установка Azure Active Directory PowerShell для Graph](/powershell/azure/active-directory/install-adv2).

   1. Нажмите клавишу Windows на клавиатуре, найдите **Windows PowerShell** и выберите пункт **Запуск от имени администратора**.

   1. В открывшемся окне PowerShell введите `Install-Module AzureAD`.

2. Создайте субъект-службу для Customer Insights с помощью модуля Azure AD PowerShell.

   1. В окне PowerShell введите `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Замените *[ваш идентификатор каталога]* на фактический идентификатор каталога вашей подписки Azure, где вы хотите создать субъект-службу. Параметр имени среды `AzureEnvironmentName` является необязательным.
  
   1. Введите `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Эта команда создает субъект-службу для Customer Insights в выбранной подписке Azure.

[!INCLUDE [footer-include](includes/footer-banner.md)]