---
title: Экспорт данных Customer Insights в хранилище BLOB-объектов Azure
description: Узнайте, как настроить подключение к хранилищу BLOB-объектов Azure.
ms.date: 09/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0986ee5caf5fa079994ca584fb2c4d9294ddb80b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596193"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Соединитель для хранилища BLOB-объектов Azure (предварительная версия)

Храните свои данные Customer Insights в хранилище BLOB-объектов Azure или используйте их для переноса своих данных в другие приложения.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Настройка соединителя для хранилища BLOB-объектов Azure

1. В аналитике аудитории перейдите **Администрирование** > **Экспорт пунктов назначения**.

1. В пункте **Хранилище BLOB-объектов Azure** выберите **Настроить**.

1. Введите **Имя учетной записи**, **Ключ учетной записи** и **Контейнер** для вашей учетной записи хранилища BLOB-объектов Azure.
    - Подробнее о том, как найти имя учетной записи хранилища BLOB-объектов Azure и ключ учетной записи, см. в разделе [Управление настройками учетной записи хранения на портале Azure](/azure/storage/common/storage-account-manage).
    - Чтобы узнать, как создать контейнер, см. раздел [Создание контейнера](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Дайте вашему месту назначения узнаваемое имя в поле **Отображаемое имя**.

1. Выберите **Далее**.

1. Установите флажок рядом с каждой сущностью, которую вы хотите экспортировать в этот пункт назначения.

1. Нажмите кнопку **Сохранить**.

Экспортированные данные хранятся в настроенном вами контейнере хранилища BLOB-объектов Azure. Следующие пути к папкам автоматически создаются в вашем контейнере:

- Для исходных сущностей и сущностей, созданных системой: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Пример: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Файл model.json для экспортируемых сущностей будет находиться на уровне %ExportDestinationName%
  - Пример: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Экспорт данных

Вы можете [экспортировать данных по требованию](export-destinations.md#export-data-on-demand). Экспорт также будет выполняться с каждым [запланированным обновлением](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]