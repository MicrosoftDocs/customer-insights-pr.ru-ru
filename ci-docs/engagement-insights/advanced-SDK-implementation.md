---
title: Расширенные сценарии веб-пакета SDK
description: Расширенные сценарии, которые следует учитывать при оснащении вашего веб-сайта с SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a083d8215f295af0884257a016b62b8c7e4ab2c7
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227214"
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

В следующем примере показан фрагмент кода, отправляющий сведения о пользователе. Если вы видите функции, перед которыми стоит символ звездочки *, замените функцию своей собственной реализацией:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
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

Вы также можете указать информацию о пользователе, вызвав API `setUser(user: IUser)`. Телеметрия, отправленная после вызова API `setUser`, будет содержать сведения о пользователе.

## <a name="adding-custom-properties-for-each-event"></a>Добавление настраиваемых свойств для каждого события

SDK позволяет вам определять настраиваемые свойства, которые можно отправлять с каждым событием. Вы можете указать настраиваемые свойства как объект, содержащий пары ключ-значение (значение может иметь тип `string | number | boolean`). Вы можете добавить объект в свойство под названием `props`, аналогично `src`, `name` и `cfg`, в конфигурации фрагмента кода.

В следующем примере показан фрагмент кода, отправляющий настраиваемые свойства:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
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

Вы также можете указать пользовательские свойства индивидуально, вызвав API `setProperty(name: string, value: string | number | boolean)`.

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
