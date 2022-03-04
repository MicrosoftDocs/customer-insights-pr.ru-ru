---
title: Управление файлами cookie и согласием пользователя на хранение пользовательских данных в Dynamics 365 Customer Insights
description: Узнайте, как файлы cookie и согласие пользователя используются для идентификации посетителей веб-сайта.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 018263220d4628690e9f0beb8453e58b0356d099
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229001"
---
# <a name="manage-cookies-and-user-consent"></a>Управление файлами cookie и согласием пользователя

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Возможность аналитики взаимодействия в Dynamics 365 Customer Insights использует файлы cookie и ключи (`localStorage`) для идентификации посетителей сайта.

Файлы cookie — это небольшие файлы, в которых хранится информация о взаимодействиях пользователя с веб-сайтом. Они хранятся в веб-браузерах. Когда пользователи посещают веб-сайт, для которого ваши пользователи сохранили файлы cookie, браузер отправляет эту информацию на сервер, который возвращает информацию, уникальную для пользователя. Это технология, которая позволяет, например, корзине в интернет-магазине сохранять выбранные товары, даже если пользователь уходит с веб-сайта.

## <a name="user-consent"></a>Согласие пользователя

[Общий регламент по защите данных (GDPR)](/dynamics365/get-started/gdpr/) — это нормативный акт Европейского союза (ЕС), который предписывает организациям обеспечивать конфиденциальность и безопасность своих пользователей. Файлы cookie часто хранят или собирают «личные данные», такие как интернет-идентификатор, на который распространяется GDPR. Если ваш бизнес работает и/или продает субъектам данных из ЕС, GDPR повлияет на вас. [Подробнее о том, как Microsoft может помочь вам соблюдать GDPR](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Чтобы SDK аналитики вовлеченности могли хранить файлы cookie или другую конфиденциальную информацию, вы должны указать, дали ли ваши пользователи согласие. Это происходит при инициализации пакета SDK путем установки поля `userConsent` в конфигурации.

Если вы укажете, что согласия пользователя нет, SDK не будет хранить никаких данных и не будет отправлять события, которые можно использовать для отслеживания поведения пользователя. Любые ранее сохраненные данные будут удалены из браузера.

Если значение согласия пользователя не указано, SDK будет считать, что пользователь дал согласие. Это означает, что если вы (как наш клиент) не укажете значение согласия пользователя в SDK, данные будут собраны. Однако, если вы укажете, что значение для согласия пользователя должно быть «истинным», данные не будут собираться, если пользователь откажется или не предоставит явное согласие.

Ниже приведен фрагмент кода для инициализации пакета веб-SDK с согласием пользователя:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Хранение данных о посетителях в возможности аналитики вовлеченности

### <a name="cookies"></a>Файлы cookie

- _msei
    - Хранит ИД анонимного пользователя. Этот файл cookie устанавливается в домене клиента и истекает через 365 дней.

### <a name="local-storage"></a>Локальное хранилище

Возможность анализа взаимодействия также использует ключи (`localStorage`) для отслеживания данных, не являющихся конфиденциальными. Эти данные полностью хранятся в самом браузере, и трафик на ваши серверы и с них не отправляется.

- *EISession.Id*
    - Хранит информацию о текущем сеансе пользователя, такую как ИД сеанса, когда он начался и когда истечет.
- *EISession.Previous*
    - Сохраняет URL-адрес ранее посещенной страницы в текущем сеансе.

Срок действия ключей в локальном хранилище не истекает автоматически, и они будут сброшены во время следующего сеанса пакета SDK.

## <a name="deleting-cookies"></a>Удаление файлов cookie

Ваши клиенты могут вручную удалить файлы cookie и ключи локального хранилища в любое время в настройках своих браузеров.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
