---
title: Начало работы с Android SDK
description: Узнайте, как персонализировать и запускать Android SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 77e63929bbcc7ecff34a3839af525b76ec3c7f21173ddc5f8f2d69f11c25c441
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036934"
---
# <a name="get-started-with-the-android-sdk"></a>Начало работы с Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Это руководство поможет вам инструментировать ваше приложение Android с помощью SDK аналитики взаимодействий Dynamics 365 Customer Insights. Вы начнете видеть события на своем портале через пять минут или раньше.

## <a name="configuration-options"></a>Параметры конфигурации
В SDK можно передать следующие параметры конфигурации:

- **ingestionKey**: ключ приема используется для отправки событий в вашу рабочую область.

## <a name="prerequisites"></a>Предварительные условия

- Android Studio

- Минимальный уровень Android API: 16 (Jelly Bean)

- Ключ приема (инструкции по получению см. ниже)

## <a name="step-1-integrate-the-sdk-into-your-application"></a>Шаг 1. Интеграция SDK в ваше приложение
Начните процесс, выбрав рабочее пространство, выбрав мобильную платформу Android и загрузив Android SDK.

- Используйте переключатель рабочего пространства на левой панели навигации, чтобы выбрать рабочее пространство.

- Если у вас нет существующей рабочей области, выберите **Создать рабочую область** и следуйте инструкциям по созданию [новой рабочей области](create-workspace.md).

## <a name="step-2-configure-the-sdk"></a>Шаг 2. Настройка SDK

1. После создания рабочей области перейдите в **Администрирование** > **Рабочая область**, а затем выберите **Руководство по установке**. 

1. Загрузите [SDK аналитики взаимодействия Android SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip), и поместите файл `eiandroidsdk-debug.aar` в папку `libs`.

1. Откройте проектный файл `build.gradle` и добавьте следующие фрагменты:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

1. Настройте конфигурацию SDK аналитики взаимодействия с помощью файла `AndroidManifest.xml`, расположенного в папке `manifests`. 
1. Скопируйте XML фрагмент кода из **Руководство по установке**. `Your-Ingestion-Key` должны быть автоматически заполнены.

   > [!NOTE]
   > Вам не нужно заменять раздел `${applicationId}`. Он заполняется автоматически.
   

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Включите или отключите автоматический сбор событий `View`, установив для вышеуказанного поля `autoCapture` параметр `true` или `false`.

1. (Необязательно) Другие конфигурации включают настройку URL-адреса сборщика конечной точки. Их можно добавить в метаданные ключа приема в `AndroidManifest.xml`:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="step-3-initialize-the-sdk-from-mainactivity"></a>Шаг 3. Инициализируйте пакет SDK из MainActivity 

После инициализации SDK вы можете работать с событиями и их свойствами в среде MainActivity.

    
Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Установить свойство для всех событий (необязательно)
    
Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

Для свойств событий контекста поддерживаются следующие типы:
- String
- Дата
- Двойной
- Long
- Логическое значение
- UUID

### <a name="track-an-event"></a>Отслеживать событие

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

### <a name="set-user-details-for-your-event-optional"></a>Укажите сведения о пользователе для вашего события (необязательно)

SDK позволяет вам определять сведения о пользователе, которые можно отправлять с каждым событием. Вы можете уточнить информацию о пользователе, вызвав `setUser(user: User)` API на уровне `Analytics`.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

Класс данных `User` содержит следующие строковые свойства:

- **localId**: локальный ИД пользователя.
- **authId**: ИД аутентифицированного пользователя.
- **authType**: тип аутентификации, используемый для получения идентификатора аутентифицированного пользователя.
- **имя**: имя пользователя.
- **электронная почта**: адрес электронной почты пользователя.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
