---
title: Параметры безопасности Customer Insights
description: Узнайте о настройках безопасности в Dynamics 365 Customer Insights.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947431"
---
# <a name="security-settings-in-customer-insights"></a>Параметры безопасности Customer Insights

На странице **Безопасность** перечислены параметры для настройки разрешений пользователей и функций, которые помогают сделать Dynamics 365 Customer Insights более безопасным. Только администраторы могут получить доступ к этой странице.

Перейдите в **Администратор** > **Безопасность** для настройки параметров.

Страница **Безопасность** содержит следующие вкладки:

- [Пользователи](#users-tab)
- [API](#apis-tab)
- [Частные ссылки](#private-links-tab)
- [Хранилище ключей ](#key-vault-tab)
- [Безопасный доступ к данным клиентов с помощью защищенного хранилища (предварительная версия)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>Вкладка Пользователи

Доступ к Customer Insights предоставлен только пользователям вашей организации, которые были добавлены в приложение администратором. Вкладка **Пользователи** позволяет управлять доступом пользователей и их разрешениями. Дополнительные сведения см. статье о [разрешениях пользователей](permissions.md).

## <a name="apis-tab"></a>Вкладка API

Просмотр и управление ключами для использования [API Customer Insights](apis.md) с данными вашей среды.

Вы можете создать первичные и вторичные ключи, выбрав **Повторно создать первичный** или **Повторно создать вторичный**. 

Чтобы заблокировать доступ API к среде, выберите **Отключить**. Если API отключены, вы можете выбрать **Включить**, чтобы снова предоставить доступ.

## <a name="private-links-tab"></a>Вкладка "Приватный канал"

[Приватный канал Azure](/azure/private-link/private-link-overview) позволяет Customer Insights подключиться к вашей учетной записи Azure Data Lake Storage через частную конечную точку в вашей виртуальной сети. Для данных в учетной записи хранения, которые недоступны в общедоступном Интернете, приватный канал обеспечивает подключение к этой сети с ограниченным доступом.

> [!IMPORTANT]
> Минимальные требования к роли для настройки подключения по приватному каналу:
>
> - Customer Insights: Администратор
> - Встроенная роль Azure: [Участник учетной записи хранения](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Разрешения для пользовательской роли Azure: [Microsoft.Storage/storageAccounts/read и Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

Настройка приватного канала в Customer Insights — это двухэтапный процесс. Сначала вы инициируете создание приватного канала из раздела **Администрирование** > **Безопасность** > **Приватные каналы** в Customer Insights. На панели **Добавить приватный канал** перечислены учетные записи хранения вашего клиента, на просмотр которых у вас есть разрешения. Выберите учетную запись хранения и дайте согласие на создание приватного канала.

Затем вам необходимо одобрить приватный канал на стороне учетной записи Data Lake Storage. Откройте ссылку, представленную на экране, чтобы утвердить новый приватный канал.

## <a name="key-vault-tab"></a>Вкладка Key Vault

Вкладка **Key Vault** позволяет связывать и управлять вашим собственным [хранилищем Azure Key Vault](/azure/key-vault/general/basic-concepts) в среде.
Выделенное хранилище ключей можно использовать для подготовки и использования секретов в рамках соответствия организации. Customer Insights может использовать секреты в Azure Key Vault для [установки подключения](connections.md) к сторонним системам.

Дополнительные сведения см. в разделе [Использование собственного хранилища Azure Key Vault](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Безопасный доступ к данным клиентов с помощью защищенного хранилища (предварительная версия)

Customer Insights использует возможность защищенного хранилища Power Platform. Защищенное хранилище предоставляет интерфейс для просмотра и утверждения (или отклонения) запросов на доступ к данным. Эти запросы возникают, когда для разрешения обращения в службу поддержки требуется доступ к данным клиента. Чтобы использовать эту функцию, Customer Insights должен иметь существующее подключение к среде Microsoft Dataverse в вашем клиенте.

Дополнительные сведения о защищенном хранилище см. в [сводке](/power-platform/admin/about-lockbox#summary) по защищенному хранилищу Power Platform. В статье также описывается [рабочий процесс](/power-platform/admin/about-lockbox#workflow) и требуемая [настройка](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) для включения защищенного хранилища.

> [!IMPORTANT]
> Глобальные администраторы для Power Platform или администраторы Power Platform могут одобрять запросы на защищенное хранилище, созданные для Customer Insights.

[!INCLUDE [footer-include](includes/footer-banner.md)]
