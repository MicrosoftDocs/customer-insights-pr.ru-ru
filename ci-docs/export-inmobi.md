---
title: Экспорт данных Customer Insights в InMobi
description: Узнайте, как настроить подключение к Criteo и экспорт в InMobi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195904"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Экспорт данных Customer Insights в InMobi (предварительная версия)

Экспортируйте списки сегментов или другие данные из экземпляра Customer Insights в [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Предварительные условия

- [Учетная запись InMobi](https://www.inmobi.com/) и учетные данные администратора.
- Имя и ключ учетной записи [Учетная запись хранилища BLOB-объектов Azure](/azure/storage/blobs/create-data-lake-storage-account). Чтобы найти имя и ключ, см. раздел [Управление параметрами учетной записи хранения на портале Azure](/azure/storage/common/storage-account-manage).
- [Контейнер хранилища BLOB-объектов Azure](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container), в который можно экспортировать данные InMobi.
- InMobi создаст прямое подключение к вашему хранилищу BLOB-объектов и настроит автоматический импорт ваших данных в InMobi. Свяжитесь с представителем InMobi, чтобы инициировать процесс.

## <a name="known-limitations"></a>Известные ограничения

- Для хранилища BLOB-объектов Azure выберите между [уровнем производительности Стандарт и Премиум](/azure/storage/blobs/storage-blob-performance-tiers). Если вы выбрали уровень производительности Премиум, выберите [блочный BLOB-объект Премиум как тип организации](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>Настройка подключения к хранилищу BLOB-объектов Azure

[Настройка подключения к вашему хранилищу BLOB-объектов Azure](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>Настройка экспорта

[Настройка экспорта](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
