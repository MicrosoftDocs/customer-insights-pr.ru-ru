---
title: Расширенные сценарии веб-пакета SDK
description: Расширенные сценарии, которые следует учитывать при оснащении вашего веб-сайта с SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 11/12/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7455d276035bfaf1f8a93d0e3b0b0884353a4010715c05d1d696309f7eb4b233
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036344"
---
# <a name="advanced-web-sdk-instrumentation"></a>Расширенный инструментарий веб-пакета SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Эта статья проведет вас через расширенные сценарии, чтобы рассмотреть, когда [оснащение вашего веб-сайта](instrument-website.md) с SDK возможностей аналитики вовлеченности Dynamics 365 Customer Insights.

## <a name="setting-user-details-for-your-event"></a>Настройка сведений о пользователе для вашего события

SDK позволяет вам определять сведения о пользователе, которые можно отправлять с каждым событием. Вы можете указать сведения о пользователе в свойстве с именем `user` (ожидаемые данные для этого свойства — это объект `IUser`), аналогичный `src`, `name`, а также `cfg` в конфигурации фрагмента кода.

Объект `IUser` содержит следующие строковые свойства:

- **localId**: локальный ИД пользователя.
- **authId**: ИД аутентифицированного пользователя.
- **authType**: тип аутентификации, используемый для получения ИД аутентифицированного пользователя.
- **имя**: имя пользователя.
- **электронная почта**: адрес электронной почты пользователя.
    
В следующем примере показан фрагмент кода, отправляющий сведения о пользователе. Там, где вы видите функции, обозначенные символом *, замените его своей реализацией вызова этих значений:  

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
    name:"myproject",      
    cfg:{ 
      ingestionKey:<paste your ingestion key>", 
      autoCapture:{ 
        view:true, 
        click:true 
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

Вы также можете указать информацию о пользователе, вызвав API `setUser(user: IUser)` в SDK. Телеметрия, отправленная после вызова `setUser API`, будет содержать сведения о пользователе.

## <a name="adding-custom-properties-for-each-event"></a>Добавление настраиваемых свойств для каждого события

SDK позволяет вам определять настраиваемые свойства, которые можно отправлять с каждым событием. Вы можете указать настраиваемые свойства как объект, содержащий пары ключ-значение (значение может иметь тип `string | number | boolean`). Объект можно добавить в свойство, называемое `props`, похожий на `src`, `name`, а также `cfg` в конфигурации фрагмент кода. 

В следующем примере показан фрагмент кода, отправляющий настраиваемые свойства:

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
    name:"myproject",      
    cfg:{ 
      ingestionKey:<paste your ingestion key>", 
      autoCapture:{ 
        view:true, 
        click:true 
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

Вы также можете указать настраиваемые свойства индивидуально, вызвав API `setProperty(name: string, value: string | number | boolean)` в SDK.

## <a name="sending-custom-events"></a>Отправка настраиваемых событий

Вы можете использовать SDK для отправки настраиваемых событий. Вы должны указать имя для события и свойства, которые будут отправлены с событием.

В следующем примере показан фрагмент кода, отслеживающий настраиваемое событие. "ИМЯ" — это значение в ключе `name` в конфигурации фрагмента кода. Это также имя переменной в объекте окна, куда загружается SDK.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]