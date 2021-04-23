---
title: Подключение к учетной записи Azure Data Lake Storage Gen2 с помощью субъекта службы
description: Используйте субъект-службу Azure для аналитики аудитории, чтобы подключиться к собственному озеру данных при его подключении к аналитике аудитории.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c670b0065a2833a6dc311d9e86d2b351140382ce
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596515"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>Подключение учетной записи Azure Data Lake Storage Gen2 с помощью субъекта-службы Azure для аналитики аудитории

У автоматизированных инструментов, использующих службы Azure, всегда должны быть ограниченные разрешения. Вместо того, чтобы приложения входили в систему как полностью привилегированный пользователь, Azure предлагает субъекты-службы. Прочтите, чтобы узнать, как связать аналитику аудитории с учетной записи Azure Data Lake Storage Gen2 с использованием субъекта-службы Azure вместо ключей учетной записи хранения. 

Вы можете использовать субъект-службу для безопасного [добавления или редактирования папки Common Data Model как источника данных](connect-common-data-model.md) или [создания новой или обновления существующей среды](manage-environments.md#create-an-environment-in-an-existing-organization).

> [!IMPORTANT]
> - Для учетной записи хранения Azure Data Lake Gen2, которая планирует использовать субъект-службу, должно быть [включено иерархическое пространство имен (HNS)](/azure/storage/blobs/data-lake-storage-namespace).
> - Для создания субъекта-службы вам потребуются разрешения администратора для вашей подписки Azure.

## <a name="create-azure-service-principal-for-audience-insights"></a>Создание субъекта-службы Azure для аналитики аудитории

Перед созданием нового субъекта-службы для аналитики аудитории проверьте, существует ли он в вашей организации.

### <a name="look-for-an-existing-service-principal"></a>Поиск существующего субъекта-службы

1. Перейдите на [Портал администрирования Azure](https://portal.azure.com) и войдите в свою организацию.

2. Выберите **Azure Active Directory** в службах Azure.

3. В **Управление** выберите **Корпоративные приложения**.

4. Найдите идентификатор основного приложения аналитики аудитории `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` или имя `Dynamics 365 AI for Customer Insights`.

5. Если вы найдете соответствующую запись, это означает, что субъект-служба для аналитики аудитории уже существует. Создавать ее не требуется.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Снимок экрана, показывающий существующий субъект-службу.":::
   
6. Если результаты не возвращаются, создайте новый субъект-службу.

### <a name="create-a-new-service-principal"></a>Создание субъекта-службы

1. Установите последнюю версию **Azure Active Directory PowerShell для Graph**. Для получения дополнительной информации см. [Установка Azure Active Directory PowerShell для Graph](/powershell/azure/active-directory/install-adv2).
   - На вашем компьютере нажмите клавишу Windows на клавиатуре и выполните поиск **Windows PowerShell** и **Запуск от имени администратора**.
   
   - В открывшемся окне PowerShell введите `Install-Module AzureAD`.

2. Создайте субъект-службу для аналитики аудитории с помощью модуля Azure AD PowerShell.
   - В окне PowerShell введите `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Замените "ваш идентификатор клиента" фактическим идентификатором вашего клиента, для которого вы хотите создать субъект-службу. Параметр имени среды `AzureEnvironmentName` является необязательным.
  
   - Введите `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Эта команда создает субъект-службу для аналитики аудитории для выбранного клиента.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Предоставление разрешений субъекту-службе для доступа к учетной записи хранения

Перейдите на портал Azure, чтобы предоставить субъекту-службе разрешения для учетной записи хранения, которую вы хотите использовать в аналитике аудитории.

1. Перейдите на [Портал администрирования Azure](https://portal.azure.com) и войдите в свою организацию.

1. Откройте учетную запись хранения, к которой у субъекта-службы должен быть доступ для аналитики аудитории.

1. Выберите **Контроль доступа (IAM)** на панели навигации и выберите **Добавить** > **Добавить назначение роли**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Снимок экрана, показывающий портал Azure при добавлении назначения роли.":::
   
1. В области **Добавить назначение роли** задайте следующие свойства:
   - Роль: *Участник данных хранилища BLOB-объектов*
   - Назначьте доступ: *Пользователь, группа или субъект-служба*
   - Выберите: *ИИ Dynamics 365 для Customer Insights* ([субъект-служба, которую вы создали](#create-a-new-service-principal))

1.  Нажмите кнопку **Сохранить**.

Внесение изменений может занять до 15 минут.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Введите идентификатор ресурса Azure или сведения о подписке Azure во вложении учетной записи хранения в аналитике аудитории.

Прикрепите учетную запись хранения Azure Data Lake в аналитике аудитории как [хранить выходные данные](manage-environments.md) или [использовать как источник данных](connect-common-data-service-lake.md). Выбор варианта Azure Data Lake позволяет выбирать между подходом на основе ресурсов или на основе подписки.

Выполните следующие шаги, чтобы предоставить необходимую информацию о выбранном подходе.

### <a name="resource-based-storage-account-connection"></a>Подключение к учетной записи хранения на основе ресурса

1. Перейдите на [Портал администрирования Azure](https://portal.azure.com), войдите в свою подписку и откройте учетную запись хранения.

1. Перейдите **Параметры** > **Свойства** на панели навигации.

1. Скопируйте значение идентификатора ресурса учетной записи хранения.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Скопируйте идентификатор ресурса учетной записи хранения.":::

1. В аналитике аудитории вставьте идентификатор ресурса в поле ресурса, отображаемое на экране подключения к учетной записи хранения.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Введите сведения идентификатора ресурса учетной записи хранения.":::   
   
1. Выполните оставшиеся шаги в аналитике аудитории, чтобы подключить учетную запись хранения.

### <a name="subscription-based-storage-account-connection"></a>Подключение к учетной записи хранения на основе подписки

1. Перейдите на [Портал администрирования Azure](https://portal.azure.com), войдите в свою подписку и откройте учетную запись хранения.

1. Перейдите **Параметры** > **Свойства** на панели навигации.

1. Просмотрите **Подписка**, **Группа ресурсов** и **Имя** учетной записи хранения, чтобы убедиться, что вы выбрали правильные значения в аналитике аудитории.

1. В аналитике аудитории выберите значения или для соответствующих полей при подключении учетной записи хранения.
   
1. Выполните оставшиеся шаги в аналитике аудитории, чтобы подключить учетную запись хранения.


[!INCLUDE[footer-include](../includes/footer-banner.md)]