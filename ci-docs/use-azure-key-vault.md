---
title: Используйте собственное Azure Key Vault для управления секретами
description: Узнайте, как настроить Customer Insights для использования собственного Azure Key Vault.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 9eb06a1190fe4e8012ecd3d6742b8b3f5f4d6349
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653493"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Использовать свое Azure Key Vault (предварительная версия)

Связывание выделенного [Azure Key Vault](/azure/key-vault/general/basic-concepts) со средой Customer Insights помогает организациям соответствовать требованиям.
Выделенное хранилище ключей можно использовать для подготовки и использования секретов в рамках соответствия организации. Customer Insights может использовать секреты в Azure Key Vault для [установки подключения](connections.md) к сторонним системам.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Свяжите хранилище ключей со средой Customer Insights

### <a name="prerequisites"></a>Предварительные условия

Чтобы настроить хранилище ключей в Customer Insights, должны быть выполнены следующие предварительные условия:

- Необходимо иметь активную подписку Azure.

- Необходимо иметь роль [администратора](permissions.md#admin) в Customer Insights. Узнать больше о [разрешениях пользователей в Customer Insights](permissions.md#assign-roles-and-permissions).

- У вас роли [участник](/azure/role-based-access-control/built-in-roles#contributor) и [администратор доступа пользователя](/azure/role-based-access-control/built-in-roles#user-access-administrator) в хранилище ключей или группе ресурсов, которой принадлежит хранилище ключей. Для получения дополнительной информации см. [Добавление или удаление назначений ролей Azure с помощью портала Azure](/azure/role-based-access-control/role-assignments-portal). Если у вас нет роли администратора доступа пользователя в хранилище ключей, необходимо настроить разрешения на управление доступом на основе ролей для субъекта-службы Azure для Dynamics 365 Customer Insights отдельно. Следуйте инструкциям, чтобы [использовать субъект-службу Azure](connect-service-principal.md) для связываемого хранилища ключей.

- В хранилище ключей должен быть **отключен** брандмауэр Key Vault.

- Хранилище ключей находится в том же [расположении в Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview), что и среда Customer Insights. Регион среды в Customer Insights в **Администрирование** > **Система** > **Сведения** > **Регион**.

### <a name="link-a-key-vault-to-the-environment"></a>Свяжите хранилище ключей со средой

1. Перейдите **Администрирование** > **Безопасность**, затем выберите вкладку **Key Vault**.
1. На плитке **Key Vault** выберите **Настройка**.
1. Выберите **Подписка**.
1. Выберите хранилище ключей в раскрывающемся списке **Key Vault**. Если отображается слишком много хранилищ ключей, выберите группу ресурсов, чтобы ограничить результаты поиска.
1. Примите соглашение **Соответствие и конфиденциальность данных**.
1. Выберите **Сохранить**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Шаги по настройке связанного хранилища ключей см. в Customer Insights.":::

Плитка **Key Vault** теперь показывает имя связанного хранилища ключей, группу ресурсов и подписку. Готово к использованию при настройке подключения.
Чтобы узнать, какие разрешения в хранилище ключей предоставлены Customer Insights, перейдите по ссылке [Разрешения, предоставленные в хранилище ключей](#permissions-granted-on-the-key-vault), далее в этой статье.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Используйте хранилище ключей в настройке подключения

Когда [выполняется настройка подключений](connections.md) для сторонних систем, секреты из связанного Key Vault можно использовать для настройки подключений.

1. Перейти в раздел **Администрирование** > **Подключения**.
1. Выберите **Добавить подключение**.
1. Для поддерживаемых типов подключения доступен переключатель **Использовать Key Vault**, если вы связали хранилище ключей.
1. Вместо того, чтобы вводить секрет вручную, вы можете выбрать секретное имя, которое указывает на секретное значение в хранилище ключей.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Панель подключения с SFTP-подключением, использующим секрет Key Vault.":::

## <a name="supported-connection-types"></a>Поддерживаемые типы подключения

Поддерживаются следующие подключения [экспорта](export-destinations.md):

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>Разрешения, предоставленные в хранилище ключей

Следующие разрешения предоставляются Customer Insights в связанном хранилище ключей, если [Политика доступа Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) или [Управление доступом на основе ролей](/azure/key-vault/general/rbac-guide?tabs=azure-cli) включены.

### <a name="key-vault-access-policy"></a>Политики доступа Key Vault

| Тип        | Разрешения          |
| ----------- | -------------------- |
| Ключ.         | [Получить ключи](/rest/api/keyvault/get-keys), [Получить ключ](/rest/api/keyvault/get-key)                                 |
| Секретный      | [Получить секреты](/rest/api/keyvault/get-secrets), [Получить секрет](/rest/api/keyvault/get-secret)                     |
| Сертификат | [Получить сертификаты](/rest/api/keyvault/get-certificates), [Получить сертификат](/rest/api/keyvault/get-certificate) |

Предыдущие значения — это минимум для перечисления и чтения во время выполнения.

### <a name="azure-role-based-access-control"></a>Управление доступом на основе ролей Azure

Роли пользователя читателя Key Vault и секрета Key Vault будут добавлены для Customer Insights. Подробнее об этих ролях см. в [Встроенные роли Azure для операций плоскости данных Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Рекомендации

- Используйте отдельное или выделенное хранилище ключей, которое содержит только секреты, необходимые для Customer Insights. Узнайте больше о том, почему [рекомендуется отдельное хранилище ключей](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Следуйте [рекомендациям по использованию Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) для контроля доступа, резервного копирования, аудита и восстановления.

## <a name="frequently-asked-questions"></a>Вопросы и ответы

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Может ли Customer Insights записывать секреты или перезаписывать секреты в хранилище ключей?

№ Только разрешения на чтение и список, указанные в разделе [предоставленные разрешения](#permissions-granted-on-the-key-vault) ранее в этой статье предоставлены Customer Insights. Система не может добавлять, удалять или перезаписывать секреты в хранилище ключей. Также именно поэтому вы не можете ввести учетные данные, когда соединение использует Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Могу ли я изменить соединение с использованием секретов Key Vault на аутентификацию по умолчанию?

№ Вы не можете вернуться к подключению по умолчанию после того, как настроили его с помощью секрета из связанного хранилища ключей. Создайте отдельное соединение и удалите старое, если оно вам больше не нужно.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Как я могу отозвать доступ к хранилищу ключей для Customer Insights?

В зависимости от того, что включено: [Политика доступа Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) или [Управление доступом на основе ролей Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli), вам необходимо удалить разрешения для субъекта-службы `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` с именем `Dynamics 365 AI for Customer Insights`. Все подключения, использующие хранилище ключей, перестанут работать.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Секрет, используемый в соединении, был удален из хранилища ключей. Что я могу сделать?

Уведомление появляется в Customer Insights, когда настроенный секрет из хранилища ключей больше не доступен. Включите [обратимое удаление](/azure/key-vault/general/soft-delete-overview) в хранилище ключей, чтобы восстановить секреты, если они случайно удалены.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Соединение не работает, но мой секрет находится в хранилище ключей. В чем может быть причина?

Уведомление появляется в Customer Insights, когда он не может получить доступ к хранилищу ключей. Возможная причина:

- Разрешения для субъекта-службы Customer Insights были удалены. Их нужно восстанавливать вручную.

- Брандмауэр в хранилище ключей включен. Чтобы хранилище ключей снова стало доступным для Customer Insights, необходимо отключить брандмауэр.
