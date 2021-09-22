---
title: Выполнение примера iOS SDK
description: Пример проекта, чтобы узнать о iOS SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 053e626d06d3e17b39b448987410058e45e8ae0385f3ecdef40314cb46ae4bf4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036844"
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
