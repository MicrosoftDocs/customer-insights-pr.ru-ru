---
title: Пример Android SDK
description: Пример проекта, чтобы узнать о Android SDK
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 2ee29a98192bb53bd92241d71c1a76ec2b7bf846
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229934"
---
# <a name="run-the-android-sdk-sample"></a>Выполнение примера Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Этот пример проекта Android поможет вам понять, как SDK работает в приложении. Создание кода не требуется. Просто добавьте свой ключ приема, и вы сразу сможете видеть события в своей рабочей области.

## <a name="prerequisites"></a>Предварительные условия

- [Android Studio](https://developer.android.com/studio)
- [Ключ приема](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Скачивание примера Android SDK

1. [Загрузите аналитику взаимодействия примера Android SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Распаковка сжатый файл `ei-android-sample.zip`.
1. Откройте распакованную папку в Android Studio.
1. В файле `AndroidManifest.xml` замените строку `"Your-Ingestion-Key"` на ключ приема вашей рабочей области из аналитики взаимодействия в разделе **Администратор** > **Рабочая область** > **Руководство по установке**. 

   > [!NOTE]
   > Вам не нужно заменять раздел `${applicationId}`. Он заполняется автоматически.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Выберите **Выполнить**, чтобы запустить демонстрационный проект.
1. Просматривайте события в своем рабочем пространстве.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
