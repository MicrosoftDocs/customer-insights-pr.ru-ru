---
title: Экспорт данных Customer Insights в AdRoll
description: Узнайте, как настроить подключение к AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697090"
---
# <a name="connector-for-adroll-preview"></a>Соединитель для AdRoll (предварительная версия)

Экспортируйте сегменты унифицированных профилей клиентов в AdRoll и используйте их для рекламы. 

## <a name="prerequisites"></a>Предварительные условия

-   У вас есть [учетная запись AdRoll](https://www.adroll.com/) и соответствующие учетные данные администратора.
-   У вас есть [настроенные сегменты](segments.md) в аналитике аудитории.
-   Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.

## <a name="connect-to-adroll"></a>Подключение к AdRoll

1. Откройте **Администратор** > **Пункты назначения экспорта**.

1. В разделе **AdRoll** выберите **Настройка**.

1. Дайте вашему пункту назначения экспорта узнаваемое имя в поле **Отображаемое имя**.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Панель конфигурации для подключения AdRoll.":::

1. Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.

1. Выберите **Подключиться** для инициализации подключения к AdRoll.

1. Выберите **Авторизоваться в AdRoll** и укажите свои учетные данные AdRoll. 

1. Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.

1. Введите ваш **Идентификатор рекламодателя AdRoll** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).

1. Выберите **Далее**, чтобы настроить экспорт.

## <a name="configure-the-connector"></a>Настройка соединителя

1. В разделе **Сопоставление данных** в поле **Электронная почта** выберите унифицированный профиль клиента, который представляет адрес электронной почты клиента. Требуется экспортировать сегменты в AdRoll.

1. Выберите сегменты, которые нужно экспортировать. Выберите сегмент, в котором не менее 100 участников. Вы не можете экспортировать меньшие сегменты. Кроме того, максимальный размер экспортируемого сегмента составляет 250 000 участников для каждого экспорта. 

1. Нажмите кнопку **Сохранить**.

## <a name="export-the-data"></a>Экспорт данных

Вы можете [экспортировать данных по требованию](export-destinations.md). Экспорт также будет выполняться с каждым [запланированным обновлением](system.md#schedule-tab).

## <a name="known-limitations"></a>Известные ограничения

- Всего в AdRoll можно экспортировать до 250 000 профилей.
- Вы не можете экспортировать сегменты с менее чем 100 профилями в AdRoll. 
- Экспорт в AdRoll ограничен сегментами.
- Экспорт до 250 000 профилей в AdRoll может занять до 10 минут. 
- Количество профилей, которые вы можете экспортировать в AdRoll ограничен вашим контрактом с AdRoll.

## <a name="data-privacy-and-compliance"></a>Соответствие и конфиденциальность данных

Когда вы включаете Dynamics 365 Customer Insights для передачи данных в AdRoll, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные. Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение AdRoll любых обязательств в отношении конфиденциальности или безопасности. Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).

Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.