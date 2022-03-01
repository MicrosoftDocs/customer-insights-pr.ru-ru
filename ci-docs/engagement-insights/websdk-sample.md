---
title: Запустите образец веб-пакета SDK
description: Узнайте, как персонализировать и запустить образец веб-пакета SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036619"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Запустите образец веб-пакета SDK для возможность аналитики вовлеченности Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Библиотека веб-пакета SDK для возможностей аналитики вовлеченности — это библиотека JavaScript с образцом кода, который вы можете использовать на вашем веб-сайте.

## <a name="prerequisites"></a>Предварительные условия

- Установка [Кода Visual Studio](https://code.visualstudio.com/).
- [Установите расширение Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) в Visual Studio Code и узнайте, как запустить Live Server.
- Вы должны иметь [ключ приема](instrument-website.md).

## <a name="run-sample"></a>Выполнить образец

1. [Скачать пример веб-пакета SDK](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Распаковка сжатый файл `ei_websdk_sample.zip`.

1. Откройте распакованную папку в Visual Studio Code.

1. В файле `ei_websdk_sample.html` замените строку «INGESTION_KEY» на свой ключ приема с портала возможностей аналитики вовлеченности, а строку «NAME» — на глобальное имя, в котором вы хотите создать экземпляр SDK. Убедитесь, что вы заменили все вхождения.

1. Откройте файл `ei_websdk_sample.html` с помощью Live Server в Visual Studio Code, выбрав **Ввести в действие** из строки состояния.

1. При открытии страницы должно быть автоматически отправлено событие просмотра. Нажатие на любую из кнопок на странице отправит события действия. Кнопка **Отслеживать события** также отправит настраиваемые события. Выбор кнопки **Перейти в Bing** отправит событие действия перед переходом на веб-сайт Bing.

1. Посмотрите на события, происходящие, когда вы переходите к вашей рабочей области. Эта рабочая область связана с ключом приема, введенным на шаге 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]