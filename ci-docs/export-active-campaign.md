---
title: Экспорт сегментов в ActiveCampaign
description: Узнайте, как настроить подключение и экспорт в ActiveCampaign.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 178d2df8edf1abcec72664e19d73a88f2b97f12d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195583"
---
# <a name="export-segments-to-activecampaign-preview"></a>Экспорт сегментов в ActiveCampaign (предварительная версия)

Экспортируйте сегменты единых профилей клиентов в ActiveCampaign и используйте их для маркетинговой деятельности.

## <a name="prerequisites"></a>Предварительные условия

- [Учетная запись ActiveCampaign](https://www.activecampaign.com/) и соответствующие учетные данные администратора.
- [ИД списка ActiveCampaign](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).
- [Ключ API ActiveCampaign](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) и имя узла конечной точки REST.
- [Настроенные сегменты](segments.md) в Customer Insights.
- Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.

## <a name="known-limitations"></a>Известные ограничения

- До 1 млн профилей клиентов на экспорт в ActiveCampaign, что может занять до 90 минут. Количество профилей клиентов, которые вы можете экспортировать в ActiveCampaign, зависит от вашего контракта с ActiveCampaign.
- Только сегменты.

## <a name="set-up-connection-to-activecampaign"></a>Настройте подключение к ActiveCampaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Перейти в раздел **Администрирование** > **Подключения**.

1. Выберите **Добавить подключение** и выберите **ActiveCampaign**.

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. Укажите, кто может использовать это подключение. По умолчанию это только администраторы. Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введите ваш Ключ API ActiveCampaign и имя узла конечной точки REST. Имя узла конечной точки REST — это только имя хоста, без https://.

1. Ознакомьтесь с положениями [Соответствие и конфиденциальность данных](connections.md#data-privacy-and-compliance) и выберите **Принимаю**.

1. Выберите **Подключиться** для инициализации подключения.

1. Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.

1. Выберите **Сохранить**, чтобы завершить подключение.

## <a name="configure-an-export"></a>Настройка экспорта

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Выберите **Добавить экспорт**.

1. В поле **Подключение для экспорта** выберите подключение в разделе ActiveCampaign. Свяжитесь с администратором, если подключение недоступно.

1. Введите имя экспорта.

1. Введите ваш **ИД списка ActiveCampaign**.

1. В разделе **Сопоставление данных** в поле **Эл. почта** выберите поле, которое представляет адрес электронной почты клиента.

1. При желании экспортируйте **имя**, **фамилию** и **телефон**, чтобы создавать более персонализированные электронные письма. Выберите **Добавить атрибут**, чтобы сопоставить эти поля.

1. Выберите сегменты, которые нужно экспортировать.

1. Выберите **Сохранить**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
