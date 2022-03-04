---
title: Выполнение примера iOS SDK
description: Пример проекта, чтобы узнать о iOS SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bbe4ba648952a8081af4c8f2610276809fa5efeb
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232858"
---
# <a name="run-the-ios-sdk-sample"></a>Выполнение примера iOS SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Этот пример проекта iOS поможет вам понять, как SDK работает в приложении. Создание кода не требуется. Просто добавьте свой ключ приема, и вы сразу сможете видеть события в своей рабочей области.

## <a name="prerequisites"></a>Предварительные условия

- [Xcode версии 9+](https://developer.apple.com/xcode/downloads/)
- [Ключ приема](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>Скачивание примера iOS SDK

1. [Загрузите аналитику взаимодействия примера iOS SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. Распаковка сжатый файл `ei-ios-sample.zip`.
1. Откройте пример проекта приложения в Xcode.
1. В файле `EIConfig.plist` замените строку `“YOUR-INGESTION-KEY”` в поле `ingestionKey` на ключ приема вашей рабочей области из аналитики взаимодействия в разделе **Администратор** > **Рабочая область** > **Руководство по установке**.
1. Выберите **Выполнить**, чтобы запустить демонстрационный проект.
1. Просматривайте события в своем рабочем пространстве.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
