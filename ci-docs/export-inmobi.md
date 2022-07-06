---
title: Экспорт данных Customer Insights в InMobi
description: Узнайте, как настроить подключение к Criteo и экспорт в InMobi.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2022
ms.locfileid: "9056550"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Экспорт списка сегментов и других данных в InMobi (предварительная версия)

Экспортируйте списки сегментов или другие данные из экземпляра Customer Insights в [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Предварительные условия

1. У вас есть [учетная запись InMobi](https://www.inmobi.com/) и учетные данные администратора.
1. У вас есть имя учетной записи хранилища BLOB-объектов Azure и соответствующий ключ учетной записи. Дополнительные сведения см. в разделе [Управление параметрами учетной записи хранения на портале Azure](/azure/storage/common/storage-account-manage). В учетной записи хранения есть контейнер, в который можно экспортировать данные inMobi. Дополнительные сведения см. в разделе [Создание контейнера](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. InMobi создаст прямое подключение к вашему хранилищу BLOB-объектов и настроит автоматический импорт ваших данных в InMobi. Свяжитесь с представителем InMobi, чтобы инициировать процесс.

## <a name="known-limitations"></a>Известные ограничения

1. Для хранилища BLOB-объектов Azure вы можете выбрать между [уровнем производительности Стандарт и Премиум](/azure/storage/blobs/storage-blob-performance-tiers). Если вы выбрали уровень производительности Премиум, выберите [блочный BLOB-объект Премиум как тип организации](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Настройка подключения к хранилищу BLOB-объектов Azure и настройка экспорта

1. Следуйте инструкциям, чтобы [настроить подключение к хранилищу BLOB-объектов Azure](export-azure-blob-storage.md).
2. Следуйте инструкциям, чтобы [настроить экспорт](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
