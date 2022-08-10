---
title: Экспорт данных в хранилище BLOB-объектов Azure (предварительная версия)
description: Узнайте, как настроить подключение и экспорт в хранилище BLOB-объектов.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195720"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Экспорт данных в хранилище BLOB-объектов Azure (предварительная версия)

Сохраняйте данные Customer Insights в хранилище BLOB-объектов или переносите их в другие приложения.

## <a name="prerequisites"></a>Предварительные условия

- Имя и ключ учетной записи [Учетная запись хранилища BLOB-объектов Azure](/azure/storage/blobs/create-data-lake-storage-account). Чтобы найти имя и ключ, см. раздел [Управление параметрами учетной записи хранения на портале Azure](/azure/storage/common/storage-account-manage).
- [Контейнер хранилища BLOB-объектов Azure](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Известные ограничения

- Для хранилища BLOB-объектов Azure выберите между [уровнем производительности Стандарт и Премиум](/azure/storage/blobs/storage-blob-performance-tiers). Если вы выбрали уровень производительности Премиум, выберите [блочный BLOB-объект Премиум как тип организации](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>Настройка подключения к хранилищу BLOB-объектов

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Перейти в раздел **Администрирование** > **Подключения**.

1. Выбирать **Добавить подключение** и выбрать **Хранилище BLOB-объектов Azure**.

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. Укажите, кто может использовать это подключение. По умолчанию это только администраторы. Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введите **Имя учетной записи**, **Ключ учетной записи** и **Контейнер** для вашей учетной записи хранилища BLOB-объектов.

1. Ознакомьтесь с положениями [Соответствие и конфиденциальность данных](connections.md#data-privacy-and-compliance) и выберите **Принимаю**.

1. Выберите **Сохранить**, чтобы завершить подключение.

## <a name="configure-an-export"></a>Настройка экспорта

Чтобы настроить этот экспорт, вы должны иметь [разрешение](export-destinations.md#set-up-a-new-export) для этого типа соединения.

> [!IMPORTANT]
> Если вы включили [параметр мягкого удаления](/azure/storage/blobs/soft-delete-blob-enable) для учетной записи хранилища BLOB-объектов Azure, экспорт завершится ошибкой. Отключите мягкое удаление, чтобы экспортировать данные в BLOB-объекты.

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Выберите **Добавить экспорт**.

1. В поле **Подключение для экспорта** выберите подключение из раздела "Хранилище BLOB-объектов Azure". Свяжитесь с администратором, если подключение недоступно.

1. Введите имя экспорта.

1. Введите имя папки для хранилища BLOB-объектов.

1. Установите флажок рядом с каждой сущностью, которую вы хотите экспортировать в этот пункт назначения.

1. Выберите **Сохранить**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Экспортированные данные хранятся в настроенном вами контейнере хранилища BLOB-объектов. Следующие пути к папкам автоматически создаются в вашем контейнере:

- Для исходных сущностей и сущностей, созданных системой:   
  *%ContainerName%/ CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > Экспорт сущностей, содержащих большой объем данных, может привести к созданию нескольких файлов CSV в одной папке для каждого экспорта. Разделение экспорта происходит по соображениям производительности, чтобы минимизировать время, необходимое для завершения экспорта.

- Файл model.json для экспортируемых сущностей находится на уровне *%ExportDestinationName%*.  
  
  Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
