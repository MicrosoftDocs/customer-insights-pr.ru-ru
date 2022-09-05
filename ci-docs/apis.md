---
title: Работа с API Customer Insights
description: Использование API и понимание ограничений.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387356"
---
# <a name="work-with-customer-insights-apis"></a>Работа с API Customer Insights

Dynamics 365 Customer Insights предоставляет API-интерфейсы для создания ваших собственных приложений на основе ваших данных в Customer Insights.

> [!IMPORTANT]
> Подробная информация об этих API приведена в разделе [Справочник по API Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Они включают дополнительную информацию об операциях, параметрах и ответах.

Попробуйте API-интерфейсы Customer Insights, создайте регистрацию приложения Azure и начните работу с клиентскими библиотеками.

## <a name="get-started-trying-the-customer-insights-apis"></a>Начните работу с API Customer Insights

Включите API-интерфейсы Customer Insights и попробуйте их. Администратор Customer Insights должен включить API-доступ к Customer Insights. После включения доступа любой пользователь может использовать API-интерфейс с ключом подписки.

1. [Выполните вход](https://home.ci.ai.dynamics.com) в Customer Insights. Если у вас еще нет подписки, [зарегистрируйтесь и получите пробную версию Customer Insights](https://aka.ms/tryci).

1. Перейдите в раздел **Администрирование** > **Безопасность** и выберите вкладку **API-интерфейсы**.

1. Если API-доступ к среде не настроен, выберите **Включить**.

   Включение API создает первичный и вторичный ключ подписки для вашего экземпляра, который используется в запросах API. Чтобы создать ключи, выберите **Повторно создать первичный** или **Повторно создать вторичный** на вкладке **API-интерфейсы**.

1. Выберите [**Ознакомьтесь с нашими API-интерфейсами**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances), чтобы попробовать API-интерфейсы.

1. Найдите и выберите операцию API-интерфейса и выберите **Попробовать**.

   :::image type="content" source="media/try-api.png" alt-text="Как протестировать API.":::

1. На боковой панели установите значение в раскрывающемся меню **Авторизация** как **неявная**. Заголовок `Authorization` добавляется с токеном носителя. Ваш ключ подписки заполняется автоматически.
  
1. При желании добавьте все необходимые параметры запроса.

1. Прокрутите до нижней части боковой панели и выберите **Отправить**.

   Ответ HTTP отображается в нижней части области.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Создание регистрации нового приложения на портале Azure

Создайте новую [регистрацию приложения](/graph/auth-register-app-v2) для использования API-интерфейсов Customer Insights в приложении Azure с использованием делегированных разрешений.

1. Заполните [раздел начала работы](#get-started-trying-the-customer-insights-apis).

1. Войдите на [портал Azure](https://portal.azure.com) с учетной записью, у которой есть доступ к данным Customer Insights.

1. Выполните поиск, затем выберите **Регистрации приложений**.

1. Выберите **Новая регистрация** и укажите имя приложения, выберите тип учетной записи.

   Также можно добавить URL-адрес перенаправления. http://localhost достаточно для разработки приложения на вашем локальном компьютере.

1. Выберите **Зарегистрировать**.

1. При регистрации нового приложения перейдите к **Разрешения API**.

1. Выберите пункт **Добавить разрешение**, а затем — **Dynamics 365 AI для Customer Insights** в боковой области.

1. Для **Тип разрешения** выберите **Делегированные разрешения**, а затем выберите разрешение **user_impersonation**.

1. Выберите **Добавить разрешения**.

1. Выберите **Предоставить согласие администратора для…**, чтобы завершить регистрацию приложения.

1. Чтобы получить доступ к API-интерфейсу без входа пользователя в систему, перейдите в раздел [Разрешения приложения "сервер-сервер"](#server-to-server-application-permissions).

Вы можете использовать идентификатор приложения/клиента для регистрации этого приложения в [библиотеке проверки подлинности Microsoft (MSAL)](/azure/active-directory/develop/msal-overview), чтобы получить токен носителя для отправки с вашим запросом в API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Для получения информации об использовании API в наших клиентских библиотеках см. [Клиентские библиотеки Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Разрешения приложения "сервер-сервер"

Создайте регистрацию приложения, которая не требует взаимодействия с пользователем и может выполняться на сервере.

1. При регистрации приложения на портале Azure перейдите в **Разрешения API**.

1. Выберите **Добавить разрешение**.

1. Выберите вкладку **API-интерфейсы, которые использует моя организация** и выберите **Dynamics 365 AI для Customer Insights** из списка.

1. Для **Тип разрешения** выберите **Разрешения приложения**, а затем выберите разрешение **CustomerInsights.Api.All**.

1. Выберите **Добавить разрешения**.

1. При регистрации нового приложения вернитесь в **Разрешения API**.

1. Выберите **Предоставить согласие администратора для…**, чтобы завершить регистрацию приложения.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Добавьте имя регистрации приложения в качестве пользователя в Customer Insights.

   1. Откройте Customer Insights, перейдите в раздел **Администрирование** > **Безопасность** и выберите пункт **Добавить пользователей**.

   1. Найдите имя регистрации вашего приложения, выберите его в результатах поиска и выберите **Сохранить**.

## <a name="sample-queries"></a>Примеры запросов

Краткий список примеров запросов OData для работы с API-интерфейсами см. в разделе [Примеры запросов OData](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Клиентские библиотеки Customer Insights

Начните работу с клиентскими библиотеками, доступными для API-интерфейсов Customer Insights. Весь исходный код библиотеки и примеры приложений можно найти на [странице Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).

### <a name="c-nuget"></a>C# NuGet

Используйте клиентские библиотеки C# с NuGet.org. В настоящее время этот пакет предназначен для платформ netstandard2.0 и netcoreapp2.0. Для получения дополнительной информации о пакете NuGet, см. раздел [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).

#### <a name="add-the-c-client-library-to-a-c-project"></a>Добавление клиентской библиотеки C# в проект C#

1. В Visual Studio откройте **NuGet Package Manager (Диспетчер пакетов)** для вашего проекта.

1. Найдите **Microsoft.Dynamics.CustomerInsights.Api**.

1. Выберите **Установить**, чтобы добавить пакет в проект.

   Также можно запустить эту команду в **консоли диспетчера пакетов NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Использование клиентской библиотеки C#

1. Используйте [библиотеку проверки подлинности Microsoft (MSAL)](/azure/active-directory/develop/msal-overview), чтобы получить `AccessToken`, используя вашу существующую [регистрацию приложения Azure](#create-a-new-app-registration-in-the-azure-portal).

1. После успешной аутентификации и получения токена создайте новый или используйте существующий клиент `HttpClient` с параметром **DefaultRequestHeaders "Авторизация"**, для которого установлено значение **Носитель "маркер доступа"**, и параметром **Ocp-Apim-Subscription-Key**, для которого установлено значение [**ключ подписки** из вашей среды Customer Insights](#get-started-trying-the-customer-insights-apis).   

   Сбросьте заголовок **Авторизация**, когда это необходимо. Например, когда срок действия токена истек.

1. Передайте этот `HttpClient` в создание клиента `CustomerInsights`.

   <!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Совершайте вызовы с клиентом в "методы расширения", например, `GetAllInstancesAsync`. Если доступ к базовому `Microsoft.Rest.HttpOperationResponse` является предпочтительным, используйте "методы сообщений http", например `GetAllInstancesWithHttpMessagesAsync`.

1. Ответ, скорее всего, будет типа `object`, потому что метод может возвращать несколько типов (например, `IList<InstanceInfo>` и `ApiErrorResult`). Чтобы проверить тип возврата, используйте объекты в типах ответов, указанных на [странице сведений об API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) для этой операции.

   Если требуется дополнительная информация по запросу, используйте **методы сообщений http** для доступа к необработанному объекту ответа.

### <a name="nodejs-package"></a>Пакет NodeJS

Используйте клиентские библиотеки NodeJS, доступные через NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Пакет Python

Используйте клиентские библиотеки Python, доступные через PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
