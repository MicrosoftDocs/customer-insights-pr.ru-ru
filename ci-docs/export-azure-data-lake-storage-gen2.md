---
title: Экспорт данных в Azure Data Lake Storage 2-го поколения (предварительная версия)
description: Узнайте, как настроить подключение к Azure Data Lake Storage Gen2.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196456"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Экспорт данных в Azure Data Lake Storage 2-го поколения (предварительная версия)

Сохраняйте данные Customer Insights в учетной записи Azure Data Lake Storage 2-го поколения или используйте эту службу для передачи данных в другие приложения.

## <a name="prerequisites"></a>Предварительные условия

- [Учетная запись хранения для использования с Azure Data Lake 2-го поколения](/azure/storage/blobs/create-data-lake-storage-account). Чтобы найти имя учетной записи хранения и ключ учетной записи, см. раздел [Управление параметрами учетной записи хранения на портале Azure](/azure/storage/common/storage-account-manage).
- [Контейнер хранилища BLOB-объектов Azure](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Известные ограничения

- Для Azure Data Lake Storage 2-го поколения выберите между [уровнем производительности Стандарт и Премиум](/azure/storage/blobs/create-data-lake-storage-account). Если вы выбрали уровень производительности Премиум, выберите [блочный BLOB-объект Премиум как тип организации](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Настройте подключение к Azure Data Lake Storage Gen2

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Перейти в раздел **Администрирование** > **Подключения**.

1. Выбирать **Добавить соединение** и выбрать **Azure Data Lake 2-го поколения**.

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. Укажите, кто может использовать это подключение. По умолчанию это только администраторы. Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введите **Имя учетной записи**, **Ключ учетной записи** и **Контейнер** для своего Azure Data Lake Storage Gen2.

1. Ознакомьтесь с положениями [Соответствие и конфиденциальность данных](connections.md#data-privacy-and-compliance) и выберите **Принимаю**.

1. Выберите **Сохранить**, чтобы завершить подключение.

## <a name="configure-an-export"></a>Настройка экспорта

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Выберите **Добавить экспорт**.

1. В поле **Подключение для экспорта** выберите подключение из раздела Azure Data Lake. Свяжитесь с администратором, если подключение недоступно.

1. Введите имя экспорта.

1. Введите имя папки для хранилища Azure Data Lake Storage 2-го поколения.

1. Установите флажок рядом с каждой сущностью, которую вы хотите экспортировать в этот пункт назначения.

1. Выберите **Сохранить**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Экспортированные данные хранятся в настроенном вами контейнере хранилища Azure Data Lake 2-го поколения.

> [!TIP]
> Экспорт сущностей, содержащих большой объем данных, может привести к созданию нескольких файлов CSV в одной папке для каждого экспорта. Разделение экспорта происходит по соображениям производительности, чтобы минимизировать время, необходимое для завершения экспорта.

[!INCLUDE [footer-include](includes/footer-banner.md)]
