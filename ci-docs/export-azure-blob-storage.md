---
title: Экспорт данных Customer Insights в хранилище BLOB-объектов Azure
description: Узнайте, как настроить подключение и экспорт в хранилище BLOB-объектов.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3d573a6c83b7f0b0c33e656eb383e20a96856b0b
ms.sourcegitcommit: d45c00a5f6cb106714366af81e8070e7f53654b3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2022
ms.locfileid: "8757402"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Экспорт списка сегментов и других данных в хранилище BLOB-объектов Azure (предварительная версия)

Сохраняйте данные Customer Insights в хранилище BLOB-объектов или переносите их в другие приложения.

## <a name="known-limitations"></a>Известные ограничения

1. Для хранилища BLOB-объектов Azure вы можете выбрать между [уровнем производительности Стандарт и Премиум](/azure/storage/blobs/storage-blob-performance-tiers). Если вы выбрали уровень производительности Премиум, выберите [блочный BLOB-объект Премиум как тип организации](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-blob-storage"></a>Настройка подключения к хранилищу BLOB-объектов

1. Перейти в раздел **Администрирование** > **Подключения**.

1. Выберите **Добавить подключение** и выберите **Хранилище BLOB-объектов Azure** для настройки подключения.

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. Укажите, кто может использовать это подключение. Если вы не предпримете никаких действий, по умолчанию это будут администраторы. Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введите **Имя учетной записи**, **Ключ учетной записи** и **Контейнер** для вашей учетной записи хранилища BLOB-объектов.
    - Чтобы узнать больше о том, как найти имя учетной записи хранилища BLOB-объектов и ключ учетной записи, см. раздел [Управление параметрами учетной записи хранения на портале Azure](/azure/storage/common/storage-account-manage).
    - Чтобы узнать, как создать контейнер, см. раздел [Создание контейнера](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Выберите **Сохранить**, чтобы завершить подключение. 

## <a name="configure-an-export"></a>Настройка экспорта

Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа. Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> Если вы включили параметр мягкого удаления для учетной записи хранилища BLOB-объектов Azure, экспорт завершится ошибкой. Отключите мягкое удаление, чтобы экспортировать данные в BLOB-объекты. Дополнительные сведения см. в разделе [Включение мягкого удаления BLOB-объектов](/azure/storage/blobs/soft-delete-blob-enable)

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.

1. В поле **Подключение для экспорта** выберите подключение из раздела "Хранилище BLOB-объектов Azure". Если вы не видите название этого раздела, значит, вам недоступны соединения этого типа.

1. Установите флажок рядом с каждой сущностью, которую вы хотите экспортировать в этот пункт назначения.

1. Нажмите кнопку **Сохранить**.

Сохранение экспорта не запускает экспорт сразу.

Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab).     

Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand). 

Экспортированные данные хранятся в настроенном вами контейнере хранилища BLOB-объектов. Следующие пути к папкам автоматически создаются в вашем контейнере:

- Для исходных сущностей и сущностей, созданных системой:   
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - Пример: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
 
- Файл model.json для экспортируемых сущностей будет на уровне %ExportDestinationName%.  
  - Пример: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE [footer-include](includes/footer-banner.md)]