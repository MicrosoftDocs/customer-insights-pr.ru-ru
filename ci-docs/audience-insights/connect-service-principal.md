---
title: Подключение к учетной записи Azure Data Lake Storage с использованием субъекта-службы
description: Используйте субъект-службу Azure для подключения к собственному озеру данных Data Lake.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: faef3583337fd495e7baf40b0a208f1d9f10281a
ms.sourcegitcommit: 11b343f6622665251ab84ae39ebcd91fa1c928ca
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900291"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Подключение к учетной записи Azure Data Lake Storage с использованием субъекта-службы Azure

В этой статье рассказывается, как связать Dynamics 365 Customer Insights с учетной записью Azure Data Lake Storage, используя субъект-службу Azure, а не учетную запись хранения. 

У автоматизированных инструментов, использующих службы Azure, всегда должны быть ограниченные разрешения. Вместо того, чтобы приложения входили в систему как полностью привилегированный пользователь, Azure предлагает субъекты-службы. Вы можете использовать субъекты-службы для безопасного [добавления или редактирования папки Common Data Model в качестве источника данных](connect-common-data-model.md) или [создания или обновления среды](create-environment.md).

> [!IMPORTANT]
> - Учетная запись Data Lake Storage, которая будет использовать участника-службу, должна иметь [включенное иерархическое пространство имен](/azure/storage/blobs/data-lake-storage-namespace).
> - Для создания субъекта-службы вам потребуются права администратора в отношении вашей подписки Azure.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Создание субъекта-службы Azure для Customer Insights

Перед созданием нового субъекта-службы для Customer Insights проверьте, не существует ли он уже в вашей организации.

### <a name="look-for-an-existing-service-principal"></a>Поиск существующего субъекта-службы

1. Перейдите на [Портал администрирования Azure](https://portal.azure.com) и войдите в свою организацию.

2. В разделе **Службы Azure** выберите **Azure Active Directory**.

3. В **Управление** выберите **Корпоративные приложения**.

4. Найдите идентификатор приложения Microsoft:
   - Аналитика аудитории: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` с именем `Dynamics 365 AI for Customer Insights`
   - Аналитика взаимодействия: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` с именем `Dynamics 365 AI for Customer Insights engagement insights`

5. Если вы найдете соответствующую запись, это означает, что субъект-служба уже существует. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Снимок экрана, показывающий существующую субъект-службу.":::
   
6. Если результаты не возвращаются, создайте новый субъект-службу.

>[!NOTE]
>Чтобы использовать всю мощь Dynamics 365 Customer Insights, мы предлагаем вам добавить оба приложения в субъект-службу.

### <a name="create-a-new-service-principal"></a>Создание субъекта-службы

1. Установите последнюю версию Azure Active Directory PowerShell для Graph. Дополнительную информацию см. в разделе [Установка Azure Active Directory PowerShell для Graph](/powershell/azure/active-directory/install-adv2).

   1. На ПК нажмите клавишу Windows на клавиатуре и выполните поиск **Windows PowerShell**, затем выберите **Запуск от имени администратора**.
   
   1. В открывшемся окне PowerShell введите `Install-Module AzureAD`.

2. Создайте субъект-службу для Customer Insights с помощью модуля Azure AD PowerShell.

   1. В окне PowerShell введите `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Замените *[ваш идентификатор клиента]* фактическим идентификатором вашего клиента, для которого вы хотите создать субъект-службу. Параметр имени среды `AzureEnvironmentName` является необязательным.
  
   1. Введите `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Эта команда создает субъект-службу для аналитики аудитории для выбранного клиента. 

   1. Введите `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Эта команда создает субъект-службу для анализа взаимодействия в выбранном клиенте.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Предоставление разрешений субъекту-службе для доступа к учетной записи хранения

Перейдите на портал Azure, чтобы предоставить субъекту-службе разрешения для учетной записи хранения, которую вы хотите использовать в аналитике аудитории.

1. Перейдите на [Портал администрирования Azure](https://portal.azure.com) и войдите в свою организацию.

1. Откройте учетную запись хранения, к которой у субъекта-службы должен быть доступ для аналитики аудитории.

1. На левой панели выберите **Контроль доступа (IAM)**, затем выберите **Добавить** > **Добавить назначение роли**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Снимок экрана, показывающий портал Azure при добавлении назначения роли.":::

1. На панели **Добавить назначение роли** задайте следующие свойства:
   - Роль: **Участник данных хранилища BLOB-объектов**
   - Назначьте доступ: **Пользователь, группа или субъект-служба**
   - Выберите: **Dynamics 365 AI for Customer Insights** и **Dynamics 365 AI for Customer Insights engagement insights** (две [субъект-службы](#create-a-new-service-principal), которые вы создали ранее в этой процедуре)

1.  Нажмите кнопку **Сохранить**.

Внесение изменений может занять до 15 минут.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Введите идентификатор ресурса Azure или сведения о подписке Azure во вложении учетной записи хранения в аналитике аудитории

Вы можете прикрепить учетную запись Data Lake Storage в аналитике аудитории для [хранения выходных данных](manage-environments.md) или [использования ее как источника данных](connect-common-data-service-lake.md). Этот параметр позволяет вам выбирать между подходом на основе ресурсов или подходом на основе подписки. В зависимости от выбранного вами подхода следуйте процедуре, описанной в одном из следующих разделов.

### <a name="resource-based-storage-account-connection"></a>Подключение к учетной записи хранения на основе ресурса

1. Перейдите на [Портал администрирования Azure](https://portal.azure.com), войдите в свою подписку и откройте учетную запись хранения.

1. На левой панели перейдите к **Параметры** > **Свойства**.

1. Скопируйте значение идентификатора ресурса учетной записи хранения.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Скопируйте идентификатор ресурса учетной записи хранения.":::

1. В аналитике аудитории вставьте идентификатор ресурса в поле ресурса, отображаемое на экране подключения к учетной записи хранения.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Введите сведения идентификатора ресурса учетной записи хранения.":::   

1. Выполните оставшиеся шаги в аналитике аудитории, чтобы подключить учетную запись хранения.

### <a name="subscription-based-storage-account-connection"></a>Подключение к учетной записи хранения на основе подписки

1. Перейдите на [Портал администрирования Azure](https://portal.azure.com), войдите в свою подписку и откройте учетную запись хранения.

1. На левой панели перейдите к **Параметры** > **Свойства**.

1. Просмотрите **Подписка**, **Группа ресурсов** и **Имя** учетной записи хранения, чтобы убедиться, что вы выбрали правильные значения в аналитике аудитории.

1. В аналитике аудитории выберите значения для соответствующих полей при подключении учетной записи хранения.

1. Выполните оставшиеся шаги в аналитике аудитории, чтобы подключить учетную запись хранения.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
