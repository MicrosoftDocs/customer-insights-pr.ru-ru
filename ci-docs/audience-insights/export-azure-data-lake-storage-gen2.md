---
title: Экспорт данных Customer Insights в Azure Data Lake Storage Gen2
description: Узнайте, как настроить подключение к Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477195"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Соединитель для Azure Data Lake Storage Gen2 (предварительная версия)

Сохраняйте данные Customer Insights в Azure Data Lake Storage Gen2 или переносите их в другие приложения.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Настройка соединителя для Azure Data Lake Storage Gen2

1. В аналитике аудитории перейдите **Администрирование** > **Экспорт пунктов назначения**.

1. В **Azure Data Lake Storage Gen2** выберите **Настроить**.

1. Дайте вашему месту назначения узнаваемое имя в поле **Отображаемое имя**.

1. Введите **Имя учетной записи**, **Ключ учетной записи** и **Контейнер** для своего Azure Data Lake Storage Gen2.
    - Чтобы узнать, как создать учетную запись хранения для использования с Azure Data Lake Storage Gen2, см. [Создать учетную запись хранения](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account). 
    - Чтобы узнать больше о том, как найти имя учетной записи хранения Azure Data Lake Gen2 и ключ учетной записи, см. [Управление параметрами учетной записи хранения на портале Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).

1. Выберите **Далее**.

1. Установите флажок рядом с каждой сущностью, которую вы хотите экспортировать в этот пункт назначения.

1. Нажмите кнопку **Сохранить**.

## <a name="export-the-data"></a>Экспорт данных

Вы можете [экспортировать данных по требованию](export-destinations.md#export-data-on-demand). Экспорт также будет выполняться с каждым [запланированным обновлением](system.md#schedule-tab).
