---
title: Экспорт данных Customer Insights в Sendinblue
description: Узнайте, как настроить подключение и экспорт в Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: be52554763b57e1c1ef2f960d52bbae79ac9827913c97ac73b429f66bbf4db37
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036071"
---
# <a name="export-segments-to-sendinblue-preview"></a>Экспорт сегментов в Sendinblue (предварительная версия)

Экспортируйте сегменты единых профилей клиентов для создания кампаний, проведения маркетинга по электронной почте и работы с определенными группами клиентов в Sendinblue.

## <a name="prerequisites-for-connection"></a>Предварительные требования для подключения

-   У вас есть [учетная запись Sendinblue](https://www.sendinblue.com/) и соответствующие учетные данные администратора.
-   В Sendinblue есть существующие списки и соответствующие идентификаторы.
-   У вас есть [настроенные сегменты](segments.md).
-   Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.

## <a name="known-limitations"></a>Известные ограничения

- До 1 миллиона профилей на экспорт в Sendinblue.
- Экспорт в Sendinblue ограничен сегментами.
- Экспорт сегментов с общим количеством профилей 1 миллион может занять до 90 минут. 
- Количество профилей, которые вы можете экспортировать в Sendinblue, зависит и ограничено вашим контрактом с Sendinblue.

## <a name="set-up-connection-to-sendinblue"></a>Настройка подключения к Sendinblue

1. Перейти в раздел **Администрирование** > **Подключения**.

1. Выберите **Добавить подключение** и выберите **Sendinblue** для настройки подключения.

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. Укажите, кто может использовать это подключение. По умолчанию это только администраторы. Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введите свой **[ключ API SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.

1. Выберите **Принимаю**, чтобы подтвердить **Конфиденциальность и соответствие данных** и выберите **Подключить** для инициализации подключения к Sendinblue.

1. Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.

1. Выберите **Сохранить**, чтобы завершить подключение.

## <a name="configure-an-export"></a>Настройка экспорта

Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа. Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.

1. В поле **Подключение для экспорта** выберите подключение в разделе Sendinblue. Если вы не видите название этого раздела, вам не доступны подключения этого типа.

1. Введите ваш **Идентификатор списка Sendinblue**. 

1. В разделе **Сопоставление данных** в поле **Электронная почта** выберите унифицированный профиль клиента, который представляет адрес электронной почты клиента. 

1. При желании вы можете экспортировать **имя**, **фамилию** и **телефон**, чтобы создавать более персонализированные электронные письма. Выберите **Добавить атрибут**, чтобы сопоставить эти поля.

1. Выберите сегменты, которые нужно экспортировать. 

1. Нажмите кнопку **Сохранить**.

Сохранение экспорта не запускает экспорт сразу.

Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab). Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Соответствие и конфиденциальность данных

Когда вы разрешаете для Dynamics 365 Customer Insights передавать данные в Sendinblue, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные. Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за обеспечение того, что Sendinblue отвечает всем вашим обязательствам по обеспечению конфиденциальности и безопасности. Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).
Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.


[!INCLUDE[footer-include](../includes/footer-banner.md)]