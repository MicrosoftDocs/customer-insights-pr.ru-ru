---
title: Используйте собственную учетную запись Azure Data Lake Storage второго поколения
author: mukeshpo
description: Узнайте о требованиях, предъявляемых к использованию собственной учетной записи Azure Data Lake Storage, для хранения данных Customer Insights.
ms.author: mukeshpo
ms.date: 08/15/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 5e4b9348f06d4e5e10b4499ad86b38c9d52da1f5
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304397"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Используйте собственную учетную запись Azure Data Lake Storage второго поколения

Dynamics 365 Customer Insights позволяет хранить все ваши данные в [Azure Data Lake Storage второго поколения](/azure/storage/blobs/data-lake-storage-introduction). Сохраняя данные в Data Lake Storage, вы соглашаетесь с тем, что данные будут передаваться и храниться в соответствующем географическом местоположении для этой учетной записи хранения Azure. Дополнительные сведения см. в [Центре управления безопасностью Microsoft](https://www.microsoft.com/trust-center).

Администраторы в Customer Insights могут [создавать среды](create-environment.md), а также [указывать способ хранения данных](create-environment.md#step-2-configure-data-storage) в процессе.

## <a name="prerequisites"></a>Предварительные условия

- Учетные записи Azure Data Lake Storage должны быть из того же региона Azure, который вы выбрали при создании среды Customer Insights. Чтобы узнать регион среды, перейдите на страницу **Администратор** > **Система** > **Сведения** в Customer Insights.
- Учетная запись Data Lake Storage должна быть Gen2. Учетные записи хранения Azure Data Lake Gen1 не поддерживаются.
- Учетная запись Data Lake Storage должна иметь [включенное иерархическое пространство имен](/azure/storage/blobs/data-lake-storage-namespace).
- Контейнер с именем `customerinsights` должен существовать в учетной записи хранения. Создайте его, прежде чем использовать собственный репозиторий Data Lake Storage в Customer Insights.
- У администратора, выполняющего настройку среды Customer Insights, должна быть роль "Участник данных BLOB-объектов хранилища" или "Владелец данных BLOB-объектов хранилища" в учетной записи хранения или контейнере `customerinsights`. Дополнительные сведения о назначении разрешений в учетной записи хранения см. в разделе [Создание учетной записи хранения](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>Подключение Customer Insights к учетной записи хранения

При создании новой среды убедитесь, что учетная запись Data Lake Storage существует и соблюдены все необходимые условия.

1. На этапе **Хранилище данных** при создании среды в качестве места сохранения для параметра **Сохранять выходные данные** выберите **Azure Data Lake Storage 2-го поколения**.
1. Выберите, как требуется **Подключить хранилище**. Можно выбрать один из двух вариантов: проверка подлинности на основе ресурсов и проверка подлинности на основе подписки. Для получения дополнительной информации см. раздел [Подключение к учетной записи Azure Data Lake Storage с помощью субъекта-службы Azure](connect-service-principal.md).
   - Для параметра **Подписка Azure** выберите **Подписку**, **Группу ресурсов** и **Учетную запись хранения**, содержащую контейнер `customerinsights`.
   - Для параметра **Ключ учетной записи** укажите **Имя учетной записи** и **Ключ учетной записи** для учетной записи Data Lake Storage. Использование этого способа проверки подлинности подразумевает, что вы будете проинформированы, если ваша организация изменит ключи. При смене ключа вам будет необходимо [обновить конфигурацию среды](manage-environments.md#edit-an-existing-environment), используя новый ключ.
1. Выберите, хотите ли вы использовать приватный канал Azure для подключения к учетной записи хранения, и [создайте подключение к приватному каналу](security-overview.md#set-up-an-azure-private-link).

Когда системные процессы, такие как прием данных, завершены, система создает соответствующие папки в учетной записи хранения. Файлы данных и файлы model.json создаются и добавляются в папки на основе имени процесса.

Если вы создаете несколько сред Customer Insights и выбираете сохранение выходных сущностей из этих сред в свою учетную запись хранения, Customer Insights создает отдельные папки для каждой среды с `ci_environmentID` в контейнере.
