---
title: Работа с API-интерфейсами
description: Использование API и понимание ограничений.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 7201ed9e5315d73e6b9c25b4bc4c4e4ed839a215
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732280"
---
# <a name="work-with-customer-insights-apis"></a>Работа с API Customer Insights

Dynamics 365 Customer Insights предоставляет API-интерфейсы для создания ваших собственных приложений на основе ваших данных в Customer Insights.

> [!IMPORTANT]
> Подробная информация об этих API приведена в разделе [Справочник по API Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Они включают дополнительную информацию об операциях, параметрах и ответах.

В этой статье описывается, как получить доступ к API-интерфейсам Customer Insights, как создать регистрацию приложения Azure и начать работу с доступными библиотеками клиента.

## <a name="get-started-trying-the-customer-insights-apis"></a>Начните работу с API Customer Insights

1. [Выполните вход](https://home.ci.ai.dynamics.com) в Customer Insights. Если у вас еще нет подписки, [зарегистрируйтесь и получите пробную версию Customer Insights](https://aka.ms/tryci).

1. Чтобы включить API в среде Customer Insights, перейдите **Администрирование** > **Разрешения**. Для этого вам потребуются права администратора.

1. Перейдите на вкладку **API** и выберите кнопку **Включить**.    
 
   Включение API создает первичный и вторичный ключ подписки для вашего экземпляра, который используется в запросах API. Вы можете восстановить ключи, выбрав **Повторно создать первичный** или **Повторно создать вторичный** в разделе **Администрирование** > **Разрешения** > **API**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Включение API Customer Insights.":::

1. Выберите **Посмотреть наши API** чтобы [попробовать API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Выберите операцию API и выберите **Попробовать**.

1. На боковой панели установите значение в раскрывающемся меню **Авторизация** как **неявная**. Заголовок `Authorization` добавляется с токеном носителя. Ваш ключ подписки будет заполнен автоматически.
  
1. При желании добавьте все необходимые параметры запроса.

1. Прокрутите до нижней части боковой панели и выберите **Отправить**.

Ответ HTTP скоро появится ниже.

   :::image type="content" source="media/try-apis.gif" alt-text="Как протестировать API.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Создание регистрации нового приложения на портале Azure

Эти шаги помогут вам начать работу с API-интерфейсами Customer Insights в приложении Azure с использованием делегированных разрешений. Обязательно сначала заполните [Раздел начала работы](#get-started-trying-the-customer-insights-apis).

1. Войдите на [портал Azure](https://portal.azure.com) с учетной записью, у которой есть доступ к данным Customer Insights.

1. Слева выберите **Регистрация приложений**.

1. Выберите **Новая регистрация** и укажите имя приложения, выберите тип учетной записи.
 
   Также можно добавить URL-адрес перенаправления. http://localhost достаточно для разработки приложения на вашем локальном компьютере.

1. При регистрации нового приложения перейдите к **Разрешения API**.

   :::image type="content" source="media/app-registration-1.gif" alt-text="Как установить разрешения API при регистрации приложения.":::

1. Выберите **Добавить разрешение** и выберите **Customer Insights** на боковой панели.

1. Для **Тип разрешения** выберите **Делегированные разрешения**, а затем выберите разрешение **user_impersonation**.

1. Выберите **Добавить разрешения**. Если вам нужно получить доступ к API без входа пользователя в систему, просмотрите раздел [Разрешения приложения "сервер-сервер"](#server-to-server-application-permissions).

1. Выберите **Предоставить согласие администратора для…**, чтобы завершить регистрацию приложения.

Вы можете использовать идентификатор приложения/клиента для регистрации этого приложения в библиотеке проверки подлинности Microsoft (MSAL), чтобы получить токен носителя для отправки с вашим запросом в API.

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Как предоставить согласие администратора.":::

Для получения дополнительной информации о MSAL см. [Обзор библиотеки проверки подлинности Microsoft (MSAL)](/azure/active-directory/develop/msal-overview).

Дополнительные сведения о регистрации приложения в Azure см. в разделе [Регистрация приложения](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).

Для получения информации об использовании API в наших клиентских библиотеках см. [Клиентские библиотеки Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Разрешения приложения "сервер-сервер"

В [разделе регистрации приложения](#create-a-new-app-registration-in-the-azure-portal) описано, как зарегистрировать приложение, которое требует от пользователя входа в систему для аутентификации. Узнайте, как создать регистрацию приложения, которая не требует взаимодействия с пользователем и может быть запущена на сервере.

1. При регистрации приложения на портале Azure перейдите в **Разрешения API**.

1. Выберите **Добавить разрешение**. 

1. Выберите вкладку **API-интерфейсы, которые использует моя организация** и выберите **Dynamics 365 AI для Customer Insights** из списка. 

1. Для **Тип разрешения** выберите **Разрешения приложения**, а затем выберите разрешение **CustomerInsights.Api.All**.

1. Выберите **Добавить разрешения**.

1. При регистрации нового приложения вернитесь в **Разрешения API**.

1. Выберите **Предоставить согласие администратора для…**, чтобы завершить регистрацию приложения.

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Как предоставить согласие администратора.":::

1. В заключение, мы должны добавить имя приложения для регистрации в качестве пользователя в Customer Insights.  
   
   Откройте Customer Insights, перейдите **Администрирование** > **Разрешения** и выберите **Добавить пользователя**.

1. Найдите имя регистрации вашего приложения, выберите его в результатах поиска и выберите **Сохранить**.

## <a name="customer-insights-client-libraries"></a>Клиентские библиотеки Customer Insights

Этот раздел поможет вам начать работу с клиентскими библиотеками, доступными для API Customer Insights. Весь исходный код библиотеки и примеры приложений можно найти на [странице Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Узнайте, как начать использовать клиентские библиотеки C# с NuGet.org. Для получения дополнительной информации о пакете NuGet см. [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). В настоящее время этот пакет предназначен для платформ netstandard2.0 и netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Добавление клиентской библиотеки C# в проект C#

1. В Visual Studio откройте **NuGet Package Manager (Диспетчер пакетов)** для вашего проекта.

1. Найдите **Microsoft.Dynamics.CustomerInsights.Api**.

1. Выберите **Установить**, чтобы добавить пакет в проект.
 
   Также можно запустить эту команду в **консоли диспетчера пакетов NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Добавление пакета NuGet в проект Visual Studio.":::

#### <a name="use-the-c-client-library"></a>Использование клиентской библиотеки C#

1. Используйте [библиотеку проверки подлинности Microsoft (MSAL)](/azure/active-directory/develop/msal-overview), чтобы получить `AccessToken`, используя вашу существующую [регистрацию приложения Azure](#create-a-new-app-registration-in-the-azure-portal).

1. После успешной аутентификации и получения токена создайте новый или используйте существующий `HttpClient` с дополнительным параметром **DefaultRequestHeaders "Авторизация"**, установленным на **Носитель "маркер доступа"**, и **Ocp-Apim-Subscription-Key**, установленным на [**ключ подписки** из вашей среды Customer Insights](#get-started-trying-the-customer-insights-apis).   
 
   Сбросьте заголовок **Авторизация**, когда это необходимо. Например, когда срок действия токена истек.

1. Передайте этот `HttpClient` в создание клиента `CustomerInsights`.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Пример httpclient.":::

1. Совершайте вызовы с клиентом в "методы расширения", например, `GetAllInstancesAsync`. Если доступ к базовому `Microsoft.Rest.HttpOperationResponse` является предпочтительным, используйте "методы сообщений http", например `GetAllInstancesWithHttpMessagesAsync`.

1. Ответ, скорее всего, будет `object`, потому что метод может возвращать несколько типов (например, `IList<InstanceInfo>` и `ApiErrorResult`). Чтобы проверить тип возвращаемого значения, вы можете безопасно преобразовать объекты в типы ответов, указанные на [странице сведений API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) для этой операции.    
   
   Если требуется дополнительная информация по запросу, используйте **методы сообщений http** для доступа к необработанному объекту ответа.

### <a name="nodejs-package"></a>Пакет NodeJS

Используйте клиентские библиотеки NodeJS, доступные через NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Пакет Python

Используйте клиентские библиотеки Python, доступные через PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE[footer-include](../includes/footer-banner.md)]
