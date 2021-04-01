---
title: Экспорт данных Customer Insights в Google Ads
description: Узнайте, как настроить подключение к Google Ads.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d9a25af3913e755cccec745c532b35aef3cccf9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598263"
---
# <a name="connector-for-google-ads-preview"></a>Соединитель для Google Ads (предварительная версия)

Экспортируйте сегменты унифицированных профилей клиентов в список аудитории Google Ads и используйте их для рекламы в поиске Google, Gmail, YouTube и Google Display Network. 

## <a name="prerequisites"></a>Предварительные условия

-   У вас есть [учетная запись Google Ads](https://ads.google.com/) и соответствующие учетные данные администратора.
-   В Google Ads уже есть аудитории и соответствующие идентификаторы. Для получения дополнительной информации см. [Аудитории Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   У вас есть [настроенные сегменты](segments.md)
-   Унифицированные профили клиентов в экспортированных сегментах содержат поля, представляющие адрес электронной почты, имя и фамилию

## <a name="connect-to-google-ads"></a>Подключиться к Google Рекламе

1. Откройте **Администратор** > **Пункты назначения экспорта**.

1. Под **Google Ads** выберите **Настроить**.

1. Дайте вашему пункту назначения экспорта узнаваемое имя в поле **Отображаемое имя**.

1. Введите ваш **[Идентификатор клиента Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Введите ваш **[одобренный токен разработчика Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.

1. Введите ваш **[Идентификатор аудитории Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** и выберите **Подключиться** для инициализации подключения к Google Ads.

1. Выберите **Авторизоваться в Google Ads** и укажите свои учетные данные Google Ads.

1. Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Снимок экрана экспорта подключения Google Ads":::

1. Выберите **Далее**, чтобы настроить экспорт.

## <a name="configure-the-connector"></a>Настройка соединителя

1. В разделе **Сопоставление данных** в поле **Электронная почта** выберите унифицированный профиль клиента, который представляет адрес электронной почты клиента. Повторите те же шаги для полей **Имя** и **Фамилия**.

1. Выберите сегменты, которые нужно экспортировать. Всего в Google Ads можно экспортировать до 1 миллиона профилей клиентов.

1. Нажмите кнопку **Сохранить**.

## <a name="export-the-data"></a>Экспорт данных

Вы можете [экспортировать данных по требованию](export-destinations.md). Экспорт также будет выполняться с каждым [запланированным обновлением](system.md#schedule-tab). Теперь в Google Ads вы можете найти свои сегменты в [Аудитории Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>Известные ограничения

- До 1 миллиона профилей на экспорт в Google Ads.
- Экспорт в Google Ads ограничен сегментами.
- Экспорт сегментов с общим количеством профилей 1 миллион может занять до 5 минут из-за ограничений со стороны провайдера. 
- Сопоставление в Google Ads может занять до 48 часов.

## <a name="data-privacy-and-compliance"></a>Соответствие и конфиденциальность данных

Когда вы включаете Dynamics 365 Customer Insights для передачи данных в Google Ads, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные. Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией Google Ads любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть. Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).
Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.


[!INCLUDE[footer-include](../includes/footer-banner.md)]