---
title: Используйте собственную учетную запись Azure Data Lake Storage второго поколения
author: mukeshpo
description: Узнайте о требованиях, предъявляемых к использованию собственной учетной записи Azure Data Lake Storage, для хранения данных Customer Insights.
ms.author: mukeshpo
ms.date: 06/08/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: d2ff49c324c5c5c28213f362ff330d441fcb6052
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246217"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Используйте собственную учетную запись Azure Data Lake Storage второго поколения

Dynamics 365 Customer Insights позволяет хранить все ваши данные в [Azure Data Lake Storage второго поколения](/azure/storage/blobs/data-lake-storage-introduction).

Сохраняя данные в Data Lake Storage, вы соглашаетесь с тем, что данные будут передаваться и храниться в соответствующем географическом местоположении для этой учетной записи хранения Azure. Дополнительные сведения см. в [Центре управления безопасностью Microsoft](https://www.microsoft.com/trust-center).

Администраторы в Customer Insights могут [создавать среды](create-environment.md), а также [указывать способ хранения данных](create-environment.md#step-2-configure-data-storage) в процессе.

## <a name="prerequisites-to-use-your-storage-account"></a>Необходимые условия для использования вашей учетной записи хранения

- Учетные записи Azure Data Lake Storage должны быть из того же региона Azure, который вы выбрали при создании среды Customer Insights. Регион среды Customer Insights можно проверить в разделе **Администрирование** > **Система** > **Сведения**.
- Репозиторий Data Lake Storage должен быть второго поколения и иметь [включенное иерархическое пространство имен](/azure/storage/blobs/create-data-lake-storage-account). Учетные записи хранения 1-го поколения не поддерживаются.
- Контейнер с именем `customerinsights` должен существовать в учетной записи хранения. Его необходимо создать, прежде чем можно будет использовать собственный репозиторий Data Lake Storage в Customer Insights. У администратора, выполняющего настройку среды Customer Insights, должна быть роль "Участник данных BLOB-объектов хранилища" или "Владелец данных BLOB-объектов хранилища" в учетной записи хранения или контейнере `customerinsights`. Дополнительные сведения о назначении разрешений в учетной записи хранения см. в разделе [Создание учетной записи хранения](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>Подключение Customer Insights к учетной записи хранения

При создании новой среды убедитесь, что учетная запись Data Lake Storage существует и соблюдены все необходимые условия.

1. На этапе **Хранилище данных** при создании среды в качестве места сохранения для параметра **Сохранять выходные данные** выберите **Azure Data Lake Storage 2-го поколения**.
1. Выберите, как требуется **Подключить хранилище**. Можно выбрать один из двух вариантов: проверка подлинности на основе ресурсов и проверка подлинности на основе подписки. Для получения дополнительной информации см. раздел [Подключение к учетной записи Azure Data Lake Storage с помощью субъекта-службы Azure](connect-service-principal.md).
   - Для параметра **Подписка Azure** выберите **Подписку**, **Группу ресурсов** и **Учетную запись хранения**, содержащую контейнер `customerinsights`.
   - Для параметра **Ключ учетной записи** укажите **Имя учетной записи** и **Ключ учетной записи** для учетной записи Data Lake Storage. Использование этого способа проверки подлинности подразумевает, что вы будете проинформированы, если ваша организация изменит ключи. При смене ключа вам будет необходимо [обновить конфигурацию среды](manage-environments.md#edit-an-existing-environment), используя новый ключ.
1. Выберите, хотите ли вы использовать приватный канал Azure для подключения к учетной записи хранения, и [создайте подключение к приватному каналу](security-overview.md#set-up-an-azure-private-link) с двухэтапным процессом.

Когда системные процессы, такие как прием данных, завершены, система создает соответствующие папки в учетной записи хранения. Файлы данных и файлы *model.json* создаются и добавляются в папки на основе имени процесса.

Если вы создаете несколько сред Customer Insights и выбираете сохранение выходных сущностей из этих сред в свою учетную запись хранения, Customer Insights создает отдельные папки для каждой среды с `ci_environmentID` в контейнере.
