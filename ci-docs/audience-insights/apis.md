---
title: Работа с API-интерфейсами
description: Использование API и понимание ограничений.
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 966db1a22e7dece1bcd89733880bce059151157f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267540"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="af0be-103">Работа с API Customer Insights</span><span class="sxs-lookup"><span data-stu-id="af0be-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="af0be-104">Dynamics 365 Customer Insights предоставляет API-интерфейсы для создания ваших собственных приложений на основе ваших данных в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="af0be-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="af0be-105">Подробная информация об этих API приведена в разделе [Справочник по API Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="af0be-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="af0be-106">Они включают дополнительную информацию об операциях, параметрах и ответах.</span><span class="sxs-lookup"><span data-stu-id="af0be-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="af0be-107">В этой статье вы узнаете, как получить доступ к API-интерфейсам Customer Insights, как создать регистрацию приложения Azure и начать работу с доступными клиентскими библиотеками.</span><span class="sxs-lookup"><span data-stu-id="af0be-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="af0be-108">Начните работу с API Customer Insights</span><span class="sxs-lookup"><span data-stu-id="af0be-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="af0be-109">[Выполните вход](https://home.ci.ai.dynamics.com) в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="af0be-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="af0be-110">Если у вас еще нет подписки, [зарегистрируйтесь и получите пробную версию Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="af0be-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="af0be-111">Чтобы включить API в среде Customer Insights, перейдите **Администрирование** > **Разрешения**.</span><span class="sxs-lookup"><span data-stu-id="af0be-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="af0be-112">Для этого вам потребуются права администратора.</span><span class="sxs-lookup"><span data-stu-id="af0be-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="af0be-113">Перейдите на вкладку **API** и выберите кнопку **Включить**.</span><span class="sxs-lookup"><span data-stu-id="af0be-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="af0be-114">Включение API создает первичный и вторичный ключ подписки для вашего экземпляра, который используется в запросах API.</span><span class="sxs-lookup"><span data-stu-id="af0be-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="af0be-115">Вы можете восстановить ключи, выбрав **Повторно создать первичный** или **Повторно создать вторичный** в разделе **Администрирование** > **Разрешения** > **API**.</span><span class="sxs-lookup"><span data-stu-id="af0be-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Включение API Customer Insights":::

1. <span data-ttu-id="af0be-117">Выберите **Просмотреть наши API**, чтобы попробовать API.</span><span class="sxs-lookup"><span data-stu-id="af0be-117">Select **Explore our APIs** to try out the APIs.</span></span>

1. <span data-ttu-id="af0be-118">Выберите операцию API и выберите **Попробовать**.</span><span class="sxs-lookup"><span data-stu-id="af0be-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="af0be-119">На боковой панели установите значение в раскрывающееся меню **Авторизация** как **неявная**.</span><span class="sxs-lookup"><span data-stu-id="af0be-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="af0be-120">Заголовок `Authorization` получается с добавленным токеном носителя.</span><span class="sxs-lookup"><span data-stu-id="af0be-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="af0be-121">Ваш ключ подписки будет заполнен автоматически.</span><span class="sxs-lookup"><span data-stu-id="af0be-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="af0be-122">При желании добавьте все необходимые параметры запроса.</span><span class="sxs-lookup"><span data-stu-id="af0be-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="af0be-123">Прокрутите до нижней части боковой панели и выберите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="af0be-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="af0be-124">Ответ HTTP скоро появится ниже.</span><span class="sxs-lookup"><span data-stu-id="af0be-124">The HTTP response will soon appear below.</span></span>

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="af0be-125">Создание регистрации нового приложения на портале Azure</span><span class="sxs-lookup"><span data-stu-id="af0be-125">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="af0be-126">Эти шаги помогут вам начать использование API Customer Insights в приложении Azure с использованием делегированных разрешений.</span><span class="sxs-lookup"><span data-stu-id="af0be-126">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="af0be-127">Обязательно сначала заполните [раздел начала работы](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="af0be-127">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="af0be-128">Войдите на [портал Azure](https://portal.azure.com) с учетной записью, у которой есть доступ к данным Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="af0be-128">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="af0be-129">Слева выберите **Регистрация приложений**.</span><span class="sxs-lookup"><span data-stu-id="af0be-129">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="af0be-130">Выберите **Новая регистрация** и укажите имя приложения, выберите тип учетной записи.</span><span class="sxs-lookup"><span data-stu-id="af0be-130">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="af0be-131">Также можно добавить URL-адрес перенаправления.</span><span class="sxs-lookup"><span data-stu-id="af0be-131">Optionally, add a redirect URL.</span></span> <span data-ttu-id="af0be-132">http://localhost достаточно для разработки приложения на вашем локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="af0be-132">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="af0be-133">При регистрации нового приложения перейдите к **Разрешения API**.</span><span class="sxs-lookup"><span data-stu-id="af0be-133">On your new App registration, go to **API permissions**.</span></span>

1. <span data-ttu-id="af0be-134">Выберите **Добавить разрешение** и выберите **Customer Insights** на боковой панели.</span><span class="sxs-lookup"><span data-stu-id="af0be-134">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="af0be-135">Для **Тип разрешения** выберите **Делегированные разрешения** и выберите разрешение **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="af0be-135">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="af0be-136">Выберите **Добавить разрешения**.</span><span class="sxs-lookup"><span data-stu-id="af0be-136">Select **Add permissions**.</span></span> <span data-ttu-id="af0be-137">Если вам нужно получить доступ к API без входа пользователя в систему, просмотрите раздел [Разрешения приложения "сервер-сервер"](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="af0be-137">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="af0be-138">Выберите **Предоставить согласие администратора для…**, чтобы завершить регистрацию приложения.</span><span class="sxs-lookup"><span data-stu-id="af0be-138">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="af0be-139">Вы можете использовать идентификатор приложения/клиента для регистрации этого приложения в библиотеке проверки подлинности Microsoft (MSAL), чтобы получить токен носителя для отправки с вашим запросом в API.</span><span class="sxs-lookup"><span data-stu-id="af0be-139">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

<span data-ttu-id="af0be-140">Для получения дополнительной информации о MSAL см. [Обзор библиотеки проверки подлинности Microsoft (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="af0be-140">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="af0be-141">Дополнительные сведения о регистрации приложения в Azure см. в разделе [Новый способ регистрации приложения на портале Azure](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="af0be-141">For more information about app registration in Azure, see [The new Azure portal app registration experience](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="af0be-142">Для получения информации об использовании API наших клиентских библиотек см. [Клиентские библиотеки Customer Insights](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="af0be-142">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="af0be-143">Разрешения приложения "сервер-сервер"</span><span class="sxs-lookup"><span data-stu-id="af0be-143">Server-to-server application permissions</span></span>

<span data-ttu-id="af0be-144">В [разделе регистрации приложения](#create-a-new-app-registration-in-the-azure-portal) описано, как зарегистрировать приложение, которое требует от пользователя входа в систему для аутентификации.</span><span class="sxs-lookup"><span data-stu-id="af0be-144">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="af0be-145">Узнайте, как создать регистрацию приложения, которая не требует взаимодействия с пользователем и может быть запущена на сервере.</span><span class="sxs-lookup"><span data-stu-id="af0be-145">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="af0be-146">При регистрации приложения на портале Azure перейдите в **Разрешения API**.</span><span class="sxs-lookup"><span data-stu-id="af0be-146">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="af0be-147">Выберите **Добавить разрешение** и выберите **Customer Insights** на боковой панели.</span><span class="sxs-lookup"><span data-stu-id="af0be-147">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="af0be-148">Для **Тип разрешения** выберите **Разрешения приложения** и выберите разрешение **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="af0be-148">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="af0be-149">Выберите **Добавить разрешения**.</span><span class="sxs-lookup"><span data-stu-id="af0be-149">Select **Add permissions**.</span></span>

1. <span data-ttu-id="af0be-150">Чтобы дать согласие администратора на это разрешение приложения, вам необходимо добавить субъект-службу.</span><span class="sxs-lookup"><span data-stu-id="af0be-150">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="af0be-151">Установите модуль Azure Active Directory (AD) PowerShell: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="af0be-151">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="af0be-152">Подключитесь к своей учетной записи AD: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="af0be-152">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="af0be-153">Вы можете найти свой идентификатор клиента в **Обзор** > **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="af0be-153">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="af0be-154">Выполните следующую команду, чтобы добавить субъект-службу Azure AD: параметр AppId `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` относится к приложению API Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="af0be-154">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Пример субъекта-службы":::

1. <span data-ttu-id="af0be-156">При регистрации нового приложения вернитесь в **Разрешения API**.</span><span class="sxs-lookup"><span data-stu-id="af0be-156">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="af0be-157">Выберите **Предоставить согласие администратора для…**, чтобы завершить регистрацию приложения.</span><span class="sxs-lookup"><span data-stu-id="af0be-157">Select **Grant admin consent for...** to complete the app registration.</span></span>

1. <span data-ttu-id="af0be-158">В заключение, мы должны добавить имя приложения для регистрации в качестве пользователя в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="af0be-158">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="af0be-159">Откройте Customer Insights, перейдите **Администрирование** > **Разрешения** и выберите **Добавить пользователя**.</span><span class="sxs-lookup"><span data-stu-id="af0be-159">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="af0be-160">Найдите имя регистрации вашего приложения, выберите его в результатах поиска и выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="af0be-160">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="af0be-161">Клиентские библиотеки Customer Insights</span><span class="sxs-lookup"><span data-stu-id="af0be-161">Customer Insights client libraries</span></span>

<span data-ttu-id="af0be-162">Этот раздел поможет вам начать работу с клиентскими библиотеками, доступными для API Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="af0be-162">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span>

### <a name="c-nuget"></a><span data-ttu-id="af0be-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="af0be-163">C# NuGet</span></span>

<span data-ttu-id="af0be-164">Узнайте, как начать использовать клиентские библиотеки C# с NuGet.org. Для получения дополнительной информации о пакете NuGet см. [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="af0be-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="af0be-165">В настоящее время этот пакет предназначен для платформ netstandard2.0 и netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="af0be-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="af0be-166">Добавление клиентской библиотеки C# в проект C#</span><span class="sxs-lookup"><span data-stu-id="af0be-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="af0be-167">В Visual Studio откройте **Диспетчер пакетов NuGet** для вашего проекта.</span><span class="sxs-lookup"><span data-stu-id="af0be-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="af0be-168">Найдите **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="af0be-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="af0be-169">Выберите **Установить**, чтобы добавить пакет в проект.</span><span class="sxs-lookup"><span data-stu-id="af0be-169">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="af0be-170">Также можно запустить эту команду в **консоли диспетчера пакетов NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="af0be-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Добавление пакета NuGet в проект Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="af0be-172">Использование клиентской библиотеки C#</span><span class="sxs-lookup"><span data-stu-id="af0be-172">Use the C# client library</span></span>

1. <span data-ttu-id="af0be-173">Используйте [библиотеку проверки подлинности Microsoft (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview), чтобы получить `AccessToken`, используя вашу существующую [регистрацию приложения Azure](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="af0be-173">Use the [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="af0be-174">После успешной аутентификации и получения токена создайте новый или используйте существующий `HttpClient` с дополнительным **DefaultRequestHeaders "Authorization"** как **Носитель <access token>**, **Ocp-Apim-Subscription-Key** как [**ключ подписки** из вашей среды Customer Insights](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="af0be-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="af0be-175">Сбросьте заголовок **Авторизация**, когда это необходимо.</span><span class="sxs-lookup"><span data-stu-id="af0be-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="af0be-176">Например, когда срок действия токена истек.</span><span class="sxs-lookup"><span data-stu-id="af0be-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="af0be-177">Передайте этот `HttpClient` в создание клиента `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="af0be-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Пример httpclient":::

1. <span data-ttu-id="af0be-179">Совершайте вызовы с клиентом в "методы расширения", например, `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="af0be-179">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="af0be-180">Если доступ к базовому `Microsoft.Rest.HttpOperationResponse` является предпочтительным, используйте "методы сообщений http", например `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="af0be-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="af0be-181">Ответ, скорее всего, будет `object`, потому что метод может возвращать несколько типов (например, `IList<InstanceInfo>` и `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="af0be-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="af0be-182">Чтобы проверить тип возвращаемого значения, вы можете безопасно преобразовать объекты в типы ответов, указанные на [странице сведений API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) для этой операции.</span><span class="sxs-lookup"><span data-stu-id="af0be-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="af0be-183">Если требуется дополнительная информация по запросу, используйте **методы сообщений http** для доступа к необработанному объекту ответа.</span><span class="sxs-lookup"><span data-stu-id="af0be-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]