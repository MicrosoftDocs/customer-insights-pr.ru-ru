---
title: Экспорт данных Customer Insights в RollWorks
description: Узнайте, как настроить подключение и экспорт в RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4979f0147dea2270f11342c1bb6b0693f3c24aea
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760618"
---
# <a name="export-segment-lists-to-rollworks-preview"></a>Экспорт списков сегментов в RollWorks (предварительная версия)

Экспортируйте сегменты унифицированных профилей клиентов в RollWorks и используйте их для рекламы. 

## <a name="prerequisites-for-a-connection"></a>Предварительные требования для подключения

-   У вас есть [учетная запись RollWorks](https://www.rollworks.com/) и соответствующие учетные данные администратора.
-   У вас есть [настроенные сегменты](segments.md) в аналитике аудитории.
-   Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.

## <a name="known-limitations"></a>Известные ограничения

- Вы можете экспортировать до 250 000 миллиона профилей за один экспорт в RollWorks.
- Вы не можете экспортировать сегменты с менее чем 100 профилями в RollWorks. 
- Экспорт в RollWorks ограничен сегментами.
- Экспорт до 250 000 профилей в RollWorks может занять до 10 минут. 
- Количество профилей, которые вы можете экспортировать в RollWorks, определяется и ограничивается вашим контрактом с RollWorks.

## <a name="set-up-connection-to-rollworks"></a>Настройка подключения к RollWorks

1. Перейти в раздел **Администрирование** > **Подключения**.

1. Выберите **Добавить подключение** и выберите **RollWorks** для настройки подключения.

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. Укажите, кто может использовать это подключение. Если вы не предпримете никаких действий, по умолчанию это будут администраторы. Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.

1. Выберите **Подключить** для инициализации подключения к RollWorks.

1. Выберите **Проверка подлинности в RollWorks** и укажите свои учетные данные администратора для RollWorks.

1. Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.

1. Выберите **Сохранить**, чтобы завершить подключение.

## <a name="configure-an-export"></a>Настройка экспорта

Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа. Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.

1. В поле **Подключение для экспорта** выберите подключение из раздела RollWorks. Если вы не видите название этого раздела, вам не доступны подключения этого типа.

1. Введите ваш **ИД рекламодателя RollWorks** [рекламодателя RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. В разделе **Сопоставление данных** в поле **Электронная почта** выберите унифицированный профиль клиента, который представляет адрес электронной почты клиента. Необходимо экспортировать сегменты в RollWorks.

1. Выберите сегменты, которые нужно экспортировать. Выберите сегмент, в котором не менее 100 участников. Вы не можете экспортировать меньшие сегменты. Кроме того, максимальный размер экспортируемого сегмента составляет 250 000 участников для каждого экспорта. 

1. Нажмите кнопку **Сохранить**.

Сохранение экспорта не запускает экспорт сразу.

Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab). Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Соответствие и конфиденциальность данных

Когда вы включаете Dynamics 365 Customer Insights для передачи данных в RollWorks, вы разрешаете передачу данных за пределы границ соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные. Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за то, чтобы RollWorks выполнял любые обязательства в отношении конфиденциальности или безопасности, которые могут иметься у вас. Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).

Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.