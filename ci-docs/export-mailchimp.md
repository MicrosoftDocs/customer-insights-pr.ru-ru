---
title: Экспорт данных Customer Insights в Mailchimp
description: Узнайте, как настроить подключение и экспорт в Mailchimp.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 394287f861df69a88209aae9d857e795d3528cd7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647482"
---
# <a name="export-segments-to-mailchimp-preview"></a>Экспорт сегментов в Mailchimp (предварительная версия)

Экспортируйте сегменты унифицированных профилей клиентов в Mailchimp для создания информационных бюллетеней и кампаний по электронной почте.

## <a name="prerequisites-for-connection"></a>Предварительные требования для подключения

-   У вас есть [учетная запись Mailchimp](https://mailchimp.com/) и соответствующие учетные данные администратора.
-   В Mailchimp уже есть аудитории и соответствующие идентификаторы. Для получения дополнительной информации см. [Аудитории Mailchimp](https://mailchimp.com/help/create-audience/).
-   У вас есть [настроенные сегменты](segments.md)
-   Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.

## <a name="known-limitations"></a>Известные ограничения

- До 1 миллиона профилей клиентов за один экспорт в Mailchimp.
- Экспорт в Mailchimp ограничен сегментами.
- Экспорт сегментов с 1 млн профилей клиентов может занять до трех часов. 
- Количество профилей клиентов, которые вы можете экспортировать в Mailchimp, зависит от вашего контракта с Mailchimp и ограничен им.

## <a name="set-up-connection-to-mailchimp"></a>Настройка подключения к Mailchimp

1. Перейти в раздел **Администрирование** > **Подключения**.

1. Выберите **Добавить подключение** и выберите **Mailchimp**, чтобы настроить подключение.

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. Укажите, кто может использовать это подключение. Если вы не предпримете никаких действий, по умолчанию это будут администраторы. Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.

1. Выберите **Подключить** для инициализации подключения к Mailchimp.

1. Выберите **Авторизоваться в Mailchimp** и укажите свои учетные данные Mailchimp.

1. Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.

1. Выберите **Сохранить**, чтобы завершить подключение. 

## <a name="configure-the-connector"></a>Настройка соединителя

Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа. Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).

1. Перейдите в раздел **Данные**> **Экспорты**.

1. Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.

1. В поле **Подключение для экспорта** выберите подключение из раздела Mailchimp. Если вы не видите название этого раздела, вам не доступны подключения этого типа.

1. Введите свой **[ИД аудитории Mailchimp](https://mailchimp.com/help/find-audience-id/)**

1. В разделе **Сопоставление данных** в поле **Эл. почта** выберите поле, которое представляет адрес электронной почты клиента. 

1. При желании вы можете экспортировать поля **Имя** и **Фамилия** для создания более персонализированных сообщений электронной почты. Выберите **Добавить атрибут**, чтобы сопоставить эти поля.

1. Выберите сегменты, которые нужно экспортировать. Всего в Mailchimp можно экспортировать до 1 миллиона профилей клиентов.

1. Нажмите кнопку **Сохранить**.

Сохранение экспорта не запускает экспорт сразу.

Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab). Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Соответствие и конфиденциальность данных

Когда вы включаете Dynamics 365 Customer Insights для передачи данных в Mailchimp, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные. Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией Mailchimp любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть. Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).
Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.

[!INCLUDE [footer-include](includes/footer-banner.md)]