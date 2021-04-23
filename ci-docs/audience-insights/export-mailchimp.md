---
title: Экспорт данных Customer Insights в Mailchimp
description: Узнайте, как настроить подключение к Mailchimp.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598217"
---
# <a name="connector-for-mailchimp-preview"></a>Соединитель для Mailchimp (предварительная версия)

Экспортируйте сегменты унифицированных профилей клиентов в Mailchimp для создания информационных бюллетеней и кампаний по электронной почте.

## <a name="prerequisites"></a>Предварительные условия

-   У вас есть [учетная запись Mailchimp](https://mailchimp.com/) и соответствующие учетные данные администратора.
-   В Mailchimp уже есть аудитории и соответствующие идентификаторы. Для получения дополнительной информации см. [Аудитории Mailchimp](https://mailchimp.com/help/create-audience/).
-   У вас есть [настроенные сегменты](segments.md)
-   Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.

## <a name="connect-to-mailchimp"></a>Подключиться к Mailchimp

1. Откройте **Администратор** > **Пункты назначения экспорта**.

1. Под **Mailchimp** выберите **Настроить**.

1. Дайте вашему пункту назначения экспорта узнаваемое имя в поле **Отображаемое имя**.

1. Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.

1. Введите ваш **[Идентификатор аудитории Mailchimp](https://mailchimp.com/help/find-audience-id/)** и выберите **Подключиться** для инициализации подключения к Mailchimp.

1. Выберите **Авторизоваться в Mailchimp** и укажите свои учетные данные Mailchimp.

1. Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Снимок экрана экспорта подключения Mailchimp":::

1. Выберите **Далее**, чтобы настроить экспорт.

## <a name="configure-the-connector"></a>Настройка соединителя

1. В разделе **Сопоставление данных** в поле **Электронная почта** выберите унифицированный профиль клиента, который представляет адрес электронной почты клиента. 

1. По желанию вы можете экспортировать **Имя** и **Фамилия** в качестве дополнительных полей для создания более персонализированных писем. Выберите **Добавить атрибут**, чтобы сопоставить эти поля.

1. Выберите сегменты, которые нужно экспортировать. Всего в Mailchimp можно экспортировать до 1 миллиона профилей клиентов.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Выберите поля и сегменты для экспорта в Mailchimp":::

1. Нажмите кнопку **Сохранить**.

## <a name="export-the-data"></a>Экспорт данных

Вы можете [экспортировать данных по требованию](export-destinations.md). Экспорт также будет выполняться с каждым [запланированным обновлением](system.md#schedule-tab). Теперь в Mailchimp вы можете найти свои сегменты в [Аудитории Mailchimp](https://mailchimp.com/help/create-audience/).

## <a name="known-limitations"></a>Известные ограничения

- До 1 миллиона профилей на экспорт в Mailchimp.
- Экспорт в Mailchimp ограничен сегментами.
- Экспорт сегментов с общим количеством профилей 1 миллион может занять до трех часов из-за ограничений со стороны провайдера. 
- Количество профилей, которые вы можете экспортировать в Mailchimp, зависит и ограничивается вашим контрактом с Mailchimp.

## <a name="data-privacy-and-compliance"></a>Соответствие и конфиденциальность данных

Когда вы включаете Dynamics 365 Customer Insights для передачи данных в Mailchimp, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные. Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией Mailchimp любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть. Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).
Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.


[!INCLUDE[footer-include](../includes/footer-banner.md)]