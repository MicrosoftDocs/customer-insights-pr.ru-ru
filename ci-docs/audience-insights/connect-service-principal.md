---
title: Подключение к учетной записи Azure Data Lake Storage Gen2 с помощью субъекта службы
description: Используйте субъект-службу Azure для аналитики аудитории, чтобы подключиться к собственному озеру данных при его подключении к аналитике аудитории.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644104"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="0bf70-103">Подключение учетной записи Azure Data Lake Storage Gen2 с помощью субъекта-службы Azure для аналитики аудитории</span><span class="sxs-lookup"><span data-stu-id="0bf70-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="0bf70-104">У автоматизированных инструментов, использующих службы Azure, всегда должны быть ограниченные разрешения.</span><span class="sxs-lookup"><span data-stu-id="0bf70-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="0bf70-105">Вместо того, чтобы приложения входили в систему как полностью привилегированный пользователь, Azure предлагает субъекты-службы.</span><span class="sxs-lookup"><span data-stu-id="0bf70-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="0bf70-106">Прочтите, чтобы узнать, как связать аналитику аудитории с учетной записи Azure Data Lake Storage Gen2 с использованием субъекта-службы Azure вместо ключей учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="0bf70-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="0bf70-107">Вы можете использовать субъект-службу для безопасного [добавления или редактирования папки Common Data Model как источника данных](connect-common-data-model.md) или [создания новой или обновления существующей среды](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="0bf70-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

<span data-ttu-id="0bf70-108">Для создания субъекта-службы вам потребуются разрешения администратора для вашей подписки Azure.</span><span class="sxs-lookup"><span data-stu-id="0bf70-108">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="0bf70-109">Создание субъекта-службы Azure для аналитики аудитории</span><span class="sxs-lookup"><span data-stu-id="0bf70-109">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="0bf70-110">Перед созданием нового субъекта-службы для аналитики аудитории проверьте, существует ли он в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="0bf70-110">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="0bf70-111">Поиск существующего субъекта-службы</span><span class="sxs-lookup"><span data-stu-id="0bf70-111">Look for an existing service principal</span></span>

1. <span data-ttu-id="0bf70-112">Перейдите на [Портал администрирования Azure](https://portal.azure.com) и войдите в свою организацию.</span><span class="sxs-lookup"><span data-stu-id="0bf70-112">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="0bf70-113">Выберите **Azure Active Directory** в службах Azure.</span><span class="sxs-lookup"><span data-stu-id="0bf70-113">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="0bf70-114">В **Управление** выберите **Корпоративные приложения**.</span><span class="sxs-lookup"><span data-stu-id="0bf70-114">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="0bf70-115">Найдите идентификатор основного приложения аналитики аудитории `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` или имя `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="0bf70-115">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="0bf70-116">Если вы найдете соответствующую запись, это означает, что субъект-служба для аналитики аудитории уже существует.</span><span class="sxs-lookup"><span data-stu-id="0bf70-116">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="0bf70-117">Создавать ее не требуется.</span><span class="sxs-lookup"><span data-stu-id="0bf70-117">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Снимок экрана, показывающий существующий субъект-службу.":::
   
6. <span data-ttu-id="0bf70-119">Если результаты не возвращаются, создайте новый субъект-службу.</span><span class="sxs-lookup"><span data-stu-id="0bf70-119">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="0bf70-120">Создание субъекта-службы</span><span class="sxs-lookup"><span data-stu-id="0bf70-120">Create a new service principal</span></span>

1. <span data-ttu-id="0bf70-121">Установите последнюю версию **Azure Active Directory PowerShell для Graph**.</span><span class="sxs-lookup"><span data-stu-id="0bf70-121">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="0bf70-122">Для получения дополнительной информации см. [Установка Azure Active Directory PowerShell для Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="0bf70-122">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="0bf70-123">На вашем компьютере нажмите клавишу Windows на клавиатуре и выполните поиск **Windows PowerShell** и **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="0bf70-123">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="0bf70-124">В открывшемся окне PowerShell введите `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="0bf70-124">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="0bf70-125">Создайте субъект-службу для аналитики аудитории с помощью модуля Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0bf70-125">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="0bf70-126">В окне PowerShell введите `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="0bf70-126">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="0bf70-127">Замените "ваш идентификатор клиента" фактическим идентификатором вашего клиента, для которого вы хотите создать субъект-службу.</span><span class="sxs-lookup"><span data-stu-id="0bf70-127">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="0bf70-128">Параметр имени среды `AzureEnvironmentName` является необязательным.</span><span class="sxs-lookup"><span data-stu-id="0bf70-128">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="0bf70-129">Введите `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="0bf70-129">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="0bf70-130">Эта команда создает субъект-службу для аналитики аудитории для выбранного клиента.</span><span class="sxs-lookup"><span data-stu-id="0bf70-130">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="0bf70-131">Предоставление разрешений субъекту-службе для доступа к учетной записи хранения</span><span class="sxs-lookup"><span data-stu-id="0bf70-131">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="0bf70-132">Перейдите на портал Azure, чтобы предоставить субъекту-службе разрешения для учетной записи хранения, которую вы хотите использовать в аналитике аудитории.</span><span class="sxs-lookup"><span data-stu-id="0bf70-132">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="0bf70-133">Перейдите на [Портал администрирования Azure](https://portal.azure.com) и войдите в свою организацию.</span><span class="sxs-lookup"><span data-stu-id="0bf70-133">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="0bf70-134">Откройте учетную запись хранения, к которой у субъекта-службы должен быть доступ для аналитики аудитории.</span><span class="sxs-lookup"><span data-stu-id="0bf70-134">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="0bf70-135">Выберите **Контроль доступа (IAM)** на панели навигации и выберите **Добавить** > **Добавить назначение роли**.</span><span class="sxs-lookup"><span data-stu-id="0bf70-135">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Снимок экрана, показывающий портал Azure при добавлении назначения роли.":::
   
1. <span data-ttu-id="0bf70-137">В области **Добавить назначение роли** задайте следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="0bf70-137">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="0bf70-138">Роль: *Участник данных хранилища BLOB-объектов*</span><span class="sxs-lookup"><span data-stu-id="0bf70-138">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="0bf70-139">Назначьте доступ: *Пользователь, группа или субъект-служба*</span><span class="sxs-lookup"><span data-stu-id="0bf70-139">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="0bf70-140">Выберите: *ИИ Dynamics 365 для Customer Insights* ([субъект-служба, которую вы создали](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="0bf70-140">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="0bf70-141">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0bf70-141">Select **Save**.</span></span>

<span data-ttu-id="0bf70-142">Внесение изменений может занять до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="0bf70-142">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="0bf70-143">Введите идентификатор ресурса Azure или сведения о подписке Azure во вложении учетной записи хранения в аналитике аудитории.</span><span class="sxs-lookup"><span data-stu-id="0bf70-143">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="0bf70-144">Прикрепите учетную запись хранения Azure Data Lake в аналитике аудитории как [хранить выходные данные](manage-environments.md) или [использовать как источник данных](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="0bf70-144">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="0bf70-145">Выбор варианта Azure Data Lake позволяет выбирать между подходом на основе ресурсов или на основе подписки.</span><span class="sxs-lookup"><span data-stu-id="0bf70-145">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="0bf70-146">Выполните следующие шаги, чтобы предоставить необходимую информацию о выбранном подходе.</span><span class="sxs-lookup"><span data-stu-id="0bf70-146">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resounce-based-storage-account-connection"></a><span data-ttu-id="0bf70-147">Подключение к учетной записи хранения на основе ресурса</span><span class="sxs-lookup"><span data-stu-id="0bf70-147">Resounce-based storage account connection</span></span>

1. <span data-ttu-id="0bf70-148">Перейдите на [Портал администрирования Azure](https://portal.azure.com), войдите в свою подписку и откройте учетную запись хранения.</span><span class="sxs-lookup"><span data-stu-id="0bf70-148">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="0bf70-149">Перейдите **Параметры** > **Свойства** на панели навигации.</span><span class="sxs-lookup"><span data-stu-id="0bf70-149">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="0bf70-150">Скопируйте значение идентификатора ресурса учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="0bf70-150">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Скопируйте идентификатор ресурса учетной записи хранения.":::

1. <span data-ttu-id="0bf70-152">В аналитике аудитории вставьте идентификатор ресурса в поле ресурса, отображаемое на экране подключения к учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="0bf70-152">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Введите сведения идентификатора ресурса учетной записи хранения.":::   
   
1. <span data-ttu-id="0bf70-154">Выполните оставшиеся шаги в аналитике аудитории, чтобы подключить учетную запись хранения.</span><span class="sxs-lookup"><span data-stu-id="0bf70-154">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="0bf70-155">Подключение к учетной записи хранения на основе подписки</span><span class="sxs-lookup"><span data-stu-id="0bf70-155">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="0bf70-156">Перейдите на [Портал администрирования Azure](https://portal.azure.com), войдите в свою подписку и откройте учетную запись хранения.</span><span class="sxs-lookup"><span data-stu-id="0bf70-156">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="0bf70-157">Перейдите **Параметры** > **Свойства** на панели навигации.</span><span class="sxs-lookup"><span data-stu-id="0bf70-157">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="0bf70-158">Просмотрите **Подписка**, **Группа ресурсов** и **Имя** учетной записи хранения, чтобы убедиться, что вы выбрали правильные значения в аналитике аудитории.</span><span class="sxs-lookup"><span data-stu-id="0bf70-158">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="0bf70-159">В аналитике аудитории выберите значения или для соответствующих полей при подключении учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="0bf70-159">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Введите сведения идентификатора ресурса учетной записи хранения.":::
   
1. <span data-ttu-id="0bf70-161">Выполните оставшиеся шаги в аналитике аудитории, чтобы подключить учетную запись хранения.</span><span class="sxs-lookup"><span data-stu-id="0bf70-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>
