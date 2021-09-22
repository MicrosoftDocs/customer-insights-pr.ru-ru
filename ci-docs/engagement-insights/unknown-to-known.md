---
title: Распознавание веб-событий от ранее аутентифицированных посетителей с функцией от неизвестного к известному
description: Функция от неизвестного к известному позволяет связывать события на веб-сайте с посетителями, прошедшими аутентификацию ранее.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: d1bbc3315b55e2ee233dc672456e0c27e4ad0fbd5937af09cc790c96ee274000
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036799"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Распознавание веб-событий от ранее аутентифицированных посетителей

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Функция **От неизвестному к известному** в возможности анализа взаимодействия позволяет связывать события на веб-сайте с посетителями, прошедшими аутентификацию ранее. Если эта функция отключена, посетители, которые прошли аутентификацию во время предыдущего посещения, а затем ушли, не идентифицируются, если они не аутентифицируются снова при возвращении. 

Например, человек посетил веб-сайт на прошлой неделе, вошел в свою учетную запись на сайте и просмотрел каталог продуктов. Человек возвращается на следующей неделе, чтобы просмотреть другие продукты, не входя в свою учетную запись. Владелец сайта, использующий функцию **От неизвестному к известному**, будет знать, что тот же человек вернулся и что он сделал на сайте. Это позволяет более точно составлять отчеты и анализировать действия на веб-сайте.

## <a name="enable-unknown-to-known"></a>Включение функции "От неизвестного к известному"

Для включения этой функции необходимо быть [администратором рабочей области](user-roles.md). 

1. В аналитике взаимодействия перейдите в раздел **Администрирование** > **Рабочая область**. 
2. Выберите вкладку **Параметры**.
3. В разделе **От неизвестному к известному** установите переключатель в положение **Включено**.

![Включение функции «От неизвестного к известному»](media/U2Ktoggle.png "Включение функции &quot;От неизвестного к известному&quot;")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>Добавление кода JavaScript во фрагмент кода отслеживания вашего сайта

Веб-сайт может захватывать **user authId** с помощью следующего примера кода JavaScript с использованием [веб-SDK анализа взаимодействия](advanced-SDK-implementation.md). Для того, чтобы функция **От неизвестному к известному** работала, вам нужно захватить authId *и* включить userMapping:True во фрагмент кода JavaScript, как в примере ниже.

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
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
