---
title: Начало работы с iOS SDK
description: Узнайте, как персонализировать и запускать iOS SDK
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 09/15/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e4d0555d2fc377fae62ff5db64c032fcebcb04
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226231"
---
# <a name="get-started-with-the-ios-sdk"></a>Начало работы с iOS SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Это руководство поможет вам инструментировать ваше приложение iOS с помощью SDK аналитики взаимодействий Dynamics 365 Customer Insights. Вы начнете видеть события на своем портале через пять минут или раньше.

## <a name="configuration-options"></a>Параметры конфигурации

Следующие параметры конфигурации можно передать в SDK через предоставленный файл `EIConfig.plist`:

- **ingestionKey**: ключ приема используется для отправки событий в ваш проект.
- **autocollectAction**: логическое значение для включения или отключения автоматического инструментирования событий действия.
- **autocollectView**: логическое значение для включения или отключения автоматического инструментирования событий представления.
- **endpointUrl**: URL-адрес конечной точки, в которую будут направляться события.

## <a name="prerequisites"></a>Предварительные условия

- Xcode версии 9+
- iOS версии 8.2+
- Ключ приема (инструкции по получению см. ниже)

## <a name="integrate-the-sdk-into-your-application"></a>Интеграция SDK в ваше приложение

Начните процесс, выбрав рабочее пространство, выбрав мобильную платформу iOS и загрузив SDK.

- Используйте переключатель рабочего пространства на левой панели навигации, чтобы выбрать рабочее пространство.

- Если у вас нет существующей рабочей области, выберите **Создать рабочую область** и следуйте инструкциям по созданию [новой рабочей области](create-workspace.md).

- После создания рабочей области перейдите в **Администрирование** > **Рабочая область**, а затем выберите **Руководство по установке**.

## <a name="configure-the-sdk"></a>Настройка SDK

После загрузки SDK вы можете работать с ним в Xcode, чтобы включить и определить события. Сделать это можно двумя способами

### <a name="option-1-using-cocoapods-recommended"></a>Вариант 1. Использование CocoaPods (рекомендуется)
CocoaPods является менеджером зависимостей для проектов Swift и Objective-C Cocoa. Его использование упрощает интеграцию SDK анализа взаимодействия для iOS. CocoaPods также позволяет обновиться до последней версии SDK анализа взаимодействия. Вот как использовать CocoaPods для интеграции SDK анализа взаимодействия в ваш проект Xcode. 

1. Установите CocoaPods. 

1. Создайте новый файл с именем Podfile в корневом каталоге вашего проекта и добавьте в него следующие операторы. Замените YOUR_TARGET_PROJECT_NAME именем вашего проекта Xcode. 
```objectivec
platform :ios, '9.0'  

 target '${YOUR_TARGET_PROJECT_NAME}' do 

     use_frameworks!   

     pod 'EIObjC.framework.debug' 

     pod 'EIObjC.framework.release' 

 end 
```
Приведенная выше конфигурация модуля содержит как отладочную, так и выпускную версию пакета SDK. Выберите ту, которая лучше всего подходит для вашего проекта.

1. Установите модуль, выполнив следующую команду:  `pod install --repo-update `

### <a name="option-2-using-download-link"></a>Вариант 2. Использование ссылки для скачивания

1. Загрузите [SDK аналитики взаимодействия iOS SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip) и поместите файл `EIObjC.xcframework` в папку `Frameworks`.

1. Если папка `Frameworks` не существует, создайте ее в папке проекта.

## <a name="enable-auto-instrumentation"></a>Включить автоматическое инструментирование
 
Вы можете легко включить автоматическое инструментирование без программирования. Когда проект запускается, он автоматически отслеживает события `view` и `action` с использованием настроенного ключа приема. 

1. Обновите и включите предоставленный файл `EIConfig.plist` в папке каталога вашего проекта для следующих полей:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = ДА
    - autocollectAction = ДА

2. Затем добавьте файл `EIConfig.plist` в свой проект в Xcode. 



Чтобы отключить автоматическое инструментирование, обновите следующие поля во включенном файле `EIConfig.plist` в папке каталога вашего проекта. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Реализуйте настраиваемые события

1. Откройте свой проект в Xcode и перейдите к параметрам **Общие**. 
1. Добавьте `EIObjC.xcframework` в проект в разделе "Платформы, библиотеки и встроенный контент".

1. Импортируйте файл заголовка платформы в AppDelegate.m со следующим фрагментом:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Инициализируйте SDK аналитики взаимодействия из приложения: didFinishLaunchingWithOptions.
1. Скопируйте XML фрагмент кода из **Руководство по установке**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Отслеживать событие:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Укажите сведения о пользователе для вашего события

SDK позволяет вам определять сведения о пользователе, которые можно отправлять с каждым событием. Вы можете уточнить информацию о пользователе, вызвав `setUser:(nonnull EIUser *)user` API в SDK.

Указание сведений о пользователе на уровне `Analytics` означает, что вся телеметрия будет иметь эту информацию. Однако, если вы укажете на уровне события, вызвав `setUser:(nonnull EIUser *)user` API для сущности EIEvent, информацию будет содержать только это конкретное событие.

Класс данных `EIUser` содержит следующие свойства NSString:

- **localId**: локальный ИД пользователя.
- **authId**: ИД аутентифицированного пользователя.
- **authType**: тип аутентификации, используемый для получения ИД аутентифицированного пользователя.
- **имя**: имя пользователя.
- **электронная почта**: адрес электронной почты пользователя.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
