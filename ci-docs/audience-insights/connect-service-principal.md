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
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="b6ea6-103">Подключение учетной записи Azure Data Lake Storage Gen2 с помощью субъекта-службы Azure для аналитики аудитории</span><span class="sxs-lookup"><span data-stu-id="b6ea6-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="b6ea6-104">У автоматизированных инструментов, использующих службы Azure, всегда должны быть ограниченные разрешения.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="b6ea6-105">Вместо того, чтобы приложения входили в систему как полностью привилегированный пользователь, Azure предлагает субъекты-службы.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="b6ea6-106">Прочтите, чтобы узнать, как связать аналитику аудитории с учетной записи Azure Data Lake Storage Gen2 с использованием субъекта-службы Azure вместо ключей учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="b6ea6-107">Вы можете использовать субъект-службу для безопасного [добавления или редактирования папки Common Data Model как источника данных](connect-common-data-model.md) или [создания новой или обновления существующей среды](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="b6ea6-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="b6ea6-108">Для учетной записи хранения Azure Data Lake Gen2, которая планирует использовать субъект-службу, должно быть [включено иерархическое пространство имен (HNS)](/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="b6ea6-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="b6ea6-109">Для создания субъекта-службы вам потребуются разрешения администратора для вашей подписки Azure.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="b6ea6-110">Создание субъекта-службы Azure для аналитики аудитории</span><span class="sxs-lookup"><span data-stu-id="b6ea6-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="b6ea6-111">Перед созданием нового субъекта-службы для аналитики аудитории проверьте, существует ли он в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="b6ea6-112">Поиск существующего субъекта-службы</span><span class="sxs-lookup"><span data-stu-id="b6ea6-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="b6ea6-113">Перейдите на [Портал администрирования Azure](https://portal.azure.com) и войдите в свою организацию.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="b6ea6-114">Выберите **Azure Active Directory** в службах Azure.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="b6ea6-115">В **Управление** выберите **Корпоративные приложения**.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="b6ea6-116">Найдите идентификатор основного приложения аналитики аудитории `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` или имя `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="b6ea6-117">Если вы найдете соответствующую запись, это означает, что субъект-служба для аналитики аудитории уже существует.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="b6ea6-118">Создавать ее не требуется.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Снимок экрана, показывающий существующий субъект-службу.":::
   
6. <span data-ttu-id="b6ea6-120">Если результаты не возвращаются, создайте новый субъект-службу.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="b6ea6-121">Создание субъекта-службы</span><span class="sxs-lookup"><span data-stu-id="b6ea6-121">Create a new service principal</span></span>

1. <span data-ttu-id="b6ea6-122">Установите последнюю версию **Azure Active Directory PowerShell для Graph**.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="b6ea6-123">Для получения дополнительной информации см. [Установка Azure Active Directory PowerShell для Graph](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="b6ea6-123">For more information, see [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="b6ea6-124">На вашем компьютере нажмите клавишу Windows на клавиатуре и выполните поиск **Windows PowerShell** и **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="b6ea6-125">В открывшемся окне PowerShell введите `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="b6ea6-126">Создайте субъект-службу для аналитики аудитории с помощью модуля Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="b6ea6-127">В окне PowerShell введите `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="b6ea6-128">Замените "ваш идентификатор клиента" фактическим идентификатором вашего клиента, для которого вы хотите создать субъект-службу.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="b6ea6-129">Параметр имени среды `AzureEnvironmentName` является необязательным.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="b6ea6-130">Введите `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="b6ea6-131">Эта команда создает субъект-службу для аналитики аудитории для выбранного клиента.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="b6ea6-132">Предоставление разрешений субъекту-службе для доступа к учетной записи хранения</span><span class="sxs-lookup"><span data-stu-id="b6ea6-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="b6ea6-133">Перейдите на портал Azure, чтобы предоставить субъекту-службе разрешения для учетной записи хранения, которую вы хотите использовать в аналитике аудитории.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="b6ea6-134">Перейдите на [Портал администрирования Azure](https://portal.azure.com) и войдите в свою организацию.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="b6ea6-135">Откройте учетную запись хранения, к которой у субъекта-службы должен быть доступ для аналитики аудитории.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="b6ea6-136">Выберите **Контроль доступа (IAM)** на панели навигации и выберите **Добавить** > **Добавить назначение роли**.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Снимок экрана, показывающий портал Azure при добавлении назначения роли.":::
   
1. <span data-ttu-id="b6ea6-138">В области **Добавить назначение роли** задайте следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="b6ea6-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="b6ea6-139">Роль: *Участник данных хранилища BLOB-объектов*</span><span class="sxs-lookup"><span data-stu-id="b6ea6-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="b6ea6-140">Назначьте доступ: *Пользователь, группа или субъект-служба*</span><span class="sxs-lookup"><span data-stu-id="b6ea6-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="b6ea6-141">Выберите: *ИИ Dynamics 365 для Customer Insights* ([субъект-служба, которую вы создали](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="b6ea6-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="b6ea6-142">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-142">Select **Save**.</span></span>

<span data-ttu-id="b6ea6-143">Внесение изменений может занять до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="b6ea6-144">Введите идентификатор ресурса Azure или сведения о подписке Azure во вложении учетной записи хранения в аналитике аудитории.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="b6ea6-145">Прикрепите учетную запись хранения Azure Data Lake в аналитике аудитории как [хранить выходные данные](manage-environments.md) или [использовать как источник данных](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="b6ea6-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="b6ea6-146">Выбор варианта Azure Data Lake позволяет выбирать между подходом на основе ресурсов или на основе подписки.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="b6ea6-147">Выполните следующие шаги, чтобы предоставить необходимую информацию о выбранном подходе.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="b6ea6-148">Подключение к учетной записи хранения на основе ресурса</span><span class="sxs-lookup"><span data-stu-id="b6ea6-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="b6ea6-149">Перейдите на [Портал администрирования Azure](https://portal.azure.com), войдите в свою подписку и откройте учетную запись хранения.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="b6ea6-150">Перейдите **Параметры** > **Свойства** на панели навигации.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="b6ea6-151">Скопируйте значение идентификатора ресурса учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Скопируйте идентификатор ресурса учетной записи хранения.":::

1. <span data-ttu-id="b6ea6-153">В аналитике аудитории вставьте идентификатор ресурса в поле ресурса, отображаемое на экране подключения к учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Введите сведения идентификатора ресурса учетной записи хранения.":::   
   
1. <span data-ttu-id="b6ea6-155">Выполните оставшиеся шаги в аналитике аудитории, чтобы подключить учетную запись хранения.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="b6ea6-156">Подключение к учетной записи хранения на основе подписки</span><span class="sxs-lookup"><span data-stu-id="b6ea6-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="b6ea6-157">Перейдите на [Портал администрирования Azure](https://portal.azure.com), войдите в свою подписку и откройте учетную запись хранения.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="b6ea6-158">Перейдите **Параметры** > **Свойства** на панели навигации.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="b6ea6-159">Просмотрите **Подписка**, **Группа ресурсов** и **Имя** учетной записи хранения, чтобы убедиться, что вы выбрали правильные значения в аналитике аудитории.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="b6ea6-160">В аналитике аудитории выберите значения или для соответствующих полей при подключении учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="b6ea6-161">Выполните оставшиеся шаги в аналитике аудитории, чтобы подключить учетную запись хранения.</span><span class="sxs-lookup"><span data-stu-id="b6ea6-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]