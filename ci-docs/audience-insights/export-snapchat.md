---
title: Экспорт данных Customer Insights в Snapchat
description: Узнайте, как настроить подключение и экспорт в Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d3dae7f0fef1fc3792c90c8ac0d3b037f5c0923d
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760615"
---
# <a name="export-segment-lists-to-snapchat-preview"></a>Экспорт списков сегментов в Snapchat (предварительная версия)

Экспортируйте сегменты унифицированных профилей клиентов в Snapchat и используйте их для рекламы. 

## <a name="prerequisites-for-a-connection"></a>Предварительные требования для подключения

-   У вас есть [учетная запись Snapchat Business](https://business.snapchat.com/), [учетная запись Snapchat Ads](https://ads.snapchat.com/) и соответствующие учетные данные администратора.
-   У вас есть [настроенные сегменты](segments.md) в аналитике аудитории.
-   Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.

## <a name="known-limitations"></a>Известные ограничения

- Экспорт в Snapchat ограничен сегментами.
- Экспорт до 1 миллиона профилей в Snapchat может занять до 15 минут. 

## <a name="set-up-connection-to-snapchat"></a>Настройка подключения к Snapchat

1. Перейти в раздел **Администрирование** > **Подключения**.

1. Выберите **Добавить подключение** и выберите **Snapchat** для настройки подключения.

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. Укажите, кто может использовать это подключение. Если вы не предпримете никаких действий, по умолчанию это будут администраторы. Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.

1. Выберите **Подключить** для инициализации подключения к Snapchat.

1. Выберите **Проверка подлинности в Snapchat** и укажите свои учетные данные администратора для Snapchat. 

1. Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.

1. Выберите **Сохранить**, чтобы завершить подключение.

## <a name="configure-an-export"></a>Настройка экспорта

Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа. Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.

1. В поле **Подключение для экспорта** выберите подключение из раздела Snapchat. Если вы не видите название этого раздела, вам не доступны подключения этого типа.

1. Введите [**ИД аудитории Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).

1. В разделе **Сопоставление данных** в поле **Электронная почта** выберите унифицированный профиль клиента, который представляет адрес электронной почты клиента. Необходимо экспортировать сегменты в Snapchat.

1. Выберите сегменты, которые нужно экспортировать. 

1. Нажмите кнопку **Сохранить**.

Сохранение экспорта не запускает экспорт сразу.

Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab). Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Соответствие и конфиденциальность данных

Когда вы включаете Dynamics 365 Customer Insights для передачи данных в Snapchat, вы разрешаете передачу данных за пределы границ соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные. Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за то, чтобы Snapchat выполнял любые обязательства в отношении конфиденциальности или безопасности, которые могут иметься у вас. Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).

Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.