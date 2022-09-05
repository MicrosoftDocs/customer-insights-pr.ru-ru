---
title: Настройка параметров безопасности
description: Узнайте о настройках безопасности в Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: d20d57e9b7724e9921f9341eeaa39141b4555ff1
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387265"
---
# <a name="configure-security-settings"></a>Настройка параметров безопасности

Управление ключами API, доступ к данным клиентов и настройка приватного канала Azure.

## <a name="manage-api-keys"></a>Управление ключами API

Просмотр и управление ключами для использования [API Customer Insights](apis.md) с данными в вашей среде.

1. Перейдите в раздел **Администрирование** > **Безопасность** и выберите вкладку **API-интерфейсы**.

1. Если API-доступ к среде не настроен, выберите **Включить**. Либо, чтобы заблокировать доступ API к среде, выберите **Отключить** и подтвердите свой выбор.

1. Управление первичными и вторичными ключами API:

   1. Чтобы отобразить первичный или вторичный ключ API, выберите значок **Показать**.

   1. Чтобы скопировать первичный или вторичный ключ API, выберите значок **Копировать**.

   1. Чтобы создать новые первичные или вторичные ключи API, выберите **Повторно создать первичный** или **Повторно создать вторичный**.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Безопасный доступ к данным клиентов с помощью защищенного хранилища (предварительная версия)

Customer Insights использует возможность защищенного хранилища Power Platform. Защищенное хранилище предоставляет интерфейс для просмотра и утверждения (или отклонения) запросов на доступ к данным. Эти запросы возникают, когда для разрешения обращения в службу поддержки требуется доступ к данным клиента. Чтобы использовать эту функцию, Customer Insights должен иметь существующее подключение к среде Microsoft Dataverse в вашем клиенте.

Дополнительные сведения о защищенном хранилище см. в [сводке](/power-platform/admin/about-lockbox#summary) по защищенному хранилищу Power Platform. В статье также описывается [рабочий процесс](/power-platform/admin/about-lockbox#workflow) и требуемая [настройка](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) для включения защищенного хранилища.

> [!IMPORTANT]
> Глобальные администраторы для Power Platform или администраторы Power Platform могут одобрять запросы на защищенное хранилище, созданные для Customer Insights.

## <a name="set-up-an-azure-private-link"></a>Настройка приватного канала Azure

[Приватный канал Azure](/azure/private-link/private-link-overview) позволяет Customer Insights подключиться к вашей учетной записи Azure Data Lake Storage через частную конечную точку в вашей виртуальной сети. Для данных в учетной записи хранения, которые недоступны в общедоступном Интернете, приватный канал обеспечивает подключение к этой сети с ограниченным доступом.

> [!IMPORTANT]
> Минимальные требования к роли для настройки подключения по приватному каналу:
>
> - Customer Insights: Администратор
> - Встроенная роль Azure: [Участник учетной записи хранения](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Разрешения для пользовательской роли Azure: [Microsoft.Storage/storageAccounts/read и Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. В Customer Insights выберите **Администратор** > **Безопасность** и выберите вкладку **Приватные каналы**.

1. Выберите **Добавить приватный канал**.

   На панели **Добавить приватный канал** перечислены учетные записи хранения вашего клиента, на просмотр которых у вас есть разрешения.

1. Выберите подписку, группу ресурсов и учетную запись хранения.

1. Ознакомьтесь с положениями [Соответствие и конфиденциальность данных](connections.md#data-privacy-and-compliance) и выберите **Принимаю**.

1. Выберите **Сохранить**.

1. Перейдите в свою учетную запись Data Lake Storage и откройте ссылку, представленную на экране.

1. Утвердите приватный канал.


[!INCLUDE [footer-include](includes/footer-banner.md)]
