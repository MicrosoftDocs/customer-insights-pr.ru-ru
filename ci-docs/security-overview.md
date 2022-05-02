---
title: Параметры безопасности в Dynamics 365 Customer Insights
description: Узнайте о настройках безопасности в Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653734"
---
# <a name="security-overview-page"></a>Страница обзора безопасности

На странице **Безопасность** перечислены параметры для настройки разрешений пользователей и функций, которые помогают сделать Dynamics 365 Customer Insights более безопасным. Только администраторы могут получить доступ к этой странице. 

Перейдите в **Администратор** > **Безопасность** для настройки параметров.

Страница **Безопасность** содержит следующие вкладки:
- [Пользователи](#users-tab)
- [API](#apis-tab)
- [Хранилище ключей ](#key-vault-tab)

## <a name="users-tab"></a>Вкладка Пользователи

Доступ к Customer Insights предоставлен только пользователям вашей организации, которые были добавлены в приложение администратором. Вкладка **Пользователи** позволяет управлять доступом пользователей и их разрешениями. Дополнительные сведения см. статье о [разрешениях пользователей](permissions.md).

## <a name="apis-tab"></a>Вкладка API

Просмотр и управление ключами для использования [API Customer Insights](apis.md) с данными вашей среды.

Вы можете создать первичные и вторичные ключи, выбрав **Повторно создать первичный** или **Повторно создать вторичный**. 

Чтобы заблокировать доступ API к среде, выберите **Отключить**. Если API отключены, вы можете выбрать **Включить**, чтобы снова предоставить доступ.

## <a name="key-vault-tab"></a>Вкладка Key Vault

Вкладка **Key Vault** позволяет связывать и управлять вашим собственным [хранилищем Azure Key Vault](/azure/key-vault/general/basic-concepts) в среде.
Выделенное хранилище ключей можно использовать для подготовки и использования секретов в рамках соответствия организации. Customer Insights может использовать секреты в Azure Key Vault для [установки подключения](connections.md) к сторонним системам.

Дополнительные сведения см. в разделе [Использование собственного хранилища Azure Key Vault](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
