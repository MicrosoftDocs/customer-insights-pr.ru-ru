---
title: Экспорт данных Customer Insights в Azure Data Lake Storage Gen2
description: Узнайте, как настроить подключение к Azure Data Lake Storage Gen2.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 934c396559d4c4be8e640917d2265805753eb62d
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2021
ms.locfileid: "7605919"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>Экспорт списка сегментов и других данных в Azure Data Lake Storage Gen2 (предварительная версия)

Сохраняйте данные Customer Insights в учетной записи Azure Data Lake Storage 2-го поколения или используйте эту службу для передачи данных в другие приложения.

## <a name="known-limitations"></a>Известные ограничения

1. Для Azure Data Lake Storage Gen2 вы можете выбирать между [уровнем производительности Стандарт и Премиум](/azure/storage/blobs/create-data-lake-storage-account) при создании учетной записи хранения для своего озера данных. Если вы выбрали уровень производительности Премиум, выберите блочный BLOB-объект Премиум как тип организации. 


## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Настройте подключение к Azure Data Lake Storage Gen2 


1. Перейти в раздел **Администрирование** > **Подключения**.

1. Выберите **Добавить подключение** и выберите **Azure Data Lake 2-го поколения** для настройки подключения.

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. Укажите, кто может использовать это подключение. Если вы не предпримете никаких действий, по умолчанию это будут администраторы. Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введите **Имя учетной записи**, **Ключ учетной записи** и **Контейнер** для своего Azure Data Lake Storage Gen2.
    - Чтобы узнать, как создать учетную запись хранения для использования с Azure Data Lake Storage Gen2, см. [Создать учетную запись хранения](/azure/storage/blobs/create-data-lake-storage-account). 
    - Чтобы узнать больше о том, как найти имя учетной записи хранения Azure Data Lake 2-го поколения и ключ учетной записи, см. раздел [Управление параметрами учетной записи хранения на портале Azure](/azure/storage/common/storage-account-manage).

1. Выберите **Сохранить**, чтобы завершить подключение. 

## <a name="configure-an-export"></a>Настройка экспорта

Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа. Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Чтобы создать новый экспорт, выберите **Добавить экспорт**.

1. В поле **Подключение для экспорта** выберите подключение из раздела **Azure Data Lake**. Если вы не видите название этого раздела, вам не доступны подключения этого типа.

1. Установите флажок рядом с каждой сущностью, которую вы хотите экспортировать в этот пункт назначения.

1. Нажмите кнопку **Сохранить**.

Сохранение экспорта не запускает экспорт сразу.

Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab). Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand). 

Экспортированные данные хранятся в настроенном вами контейнере хранилища Azure Data Lake 2-го поколения. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
