---
title: Запустите образец веб-пакета SDK
description: Узнайте, как персонализировать и запустить образец веб-пакета SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a50a10db784ec7c1943c94e74000713309787e5c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225347"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Запустите образец веб-пакета SDK для возможность аналитики вовлеченности Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Библиотека веб-пакета SDK для возможностей аналитики вовлеченности — это библиотека JavaScript с образцом кода, который вы можете использовать на вашем веб-сайте.

## <a name="prerequisites"></a>Предварительные условия

- Установка [Кода Visual Studio](https://code.visualstudio.com/).
- [Установите расширение Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) в Visual Studio Code и узнайте, как запустить Live Server.
- Вы должны иметь [рабочую область аналитики взаимодействия](create-workspace.md).

## <a name="run-sample"></a>Выполнить образец

1. [Скачать пример веб-пакета SDK](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Распаковка сжатый файл `ei_websdk_sample.zip`.

1. Откройте распакованную папку в Visual Studio Code.

1. Перейдите на портал аналитики взаимодействия для вашей рабочей области. Выберите **Администрирование** > **Рабочая область** и **Руководство по установке**. Следуйте первому варианту и выберите **Скопировать код**, чтобы скопировать фрагмент кода JavaScript.

1. В файле `ei_websdk_sample.html` вставьте фрагмент кода, который вы только что скопировали, под этой строкой:

   - <-- ВСТАВЬТЕ ФРАГМЕНТ КОДА JAVASCRIPT С ПОРТАЛА АНАЛИТИКИ ВЗАИМОДЕЙСТВИЯ ПОД ЭТОЙ СТРОКОЙ -->

1. Откройте файл `ei_websdk_sample.html` с помощью Live Server в Visual Studio Code, выбрав **Ввести в действие** из строки состояния.

1. При открытии страницы должно быть автоматически отправлено событие просмотра. Нажатие на любую из кнопок на странице отправит события действия. Кнопка **Отслеживать события** также отправит настраиваемые события. Выбор кнопки **Перейти в Bing** отправит событие действия перед переходом на веб-сайт Bing.

1. Посмотрите на события, происходящие, когда вы переходите к вашей рабочей области. Эта рабочая область связана с ключом приема, введенным на шаге 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
