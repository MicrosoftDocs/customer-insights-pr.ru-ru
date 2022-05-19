---
title: Экспорт данных Customer Insights в LinkedIn Ads
description: Узнайте, как настроить подключение и экспорт в LinkedIn Ads.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bf1d12ffbd7a4cfd7d268fea8a1f90cc37589e00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647442"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Экспорт сегментов в LinkedIn Ads (предварительная версия)

Экспортируйте сегменты единых профилей клиентов в LinkedIn Ads для создания сопоставленных аудиторий. Используйте сопоставленные аудитории для таргетинга на компании и контакты.

## <a name="prerequisites"></a>Предварительные условия

-   У вас есть [учетная запись LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) и соответствующие учетные данные администратора.
-   У вас должны быть [настроенные сегменты](segments.md) в Customer Insights.
-   Профили клиентов в экспортированных сегментах содержат поле с адресом электронной почты.

## <a name="known-limitations"></a>Известные ограничения

- Ваш сегмент в Customer Insights должен содержать не менее 300 уникальных профилей. 
- Всего в LinkedIn Ads можно экспортировать до 100 000 профилей клиентов на один экспорт.
- Экспорт в LinkedIn Ads ограничен сегментами.
- Экспорт до 100 000 профилей клиентов в LinkedIn Ads может занять до 10 минут. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>Настройка подключения к LinkedIn Ads

1. Перейти в раздел **Администрирование** > **Подключения**.

1. Выберите **Добавить подключение** и выберите **LinkedIn Ads** для настройки подключения.

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. Укажите, кто может использовать это подключение. Если вы не предпримете никаких действий, по умолчанию это администраторы. Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Предоставьте свой [идентификатор учетной записи LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).

1. Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.

1. Выберите **Подключить** для инициализации подключения к Campaign Monitor.

1. Выберите **Проверка подлинности в LinkedIn** и укажите свои учетные данные администратора для LinkedIn Campaign Manager.

1. Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.

1. Выберите **Сохранить**, чтобы завершить подключение.

## <a name="configure-an-export"></a>Настройка экспорта

Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа. Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.

1. В поле **Подключение для экспорта** выберите подключение из раздела LinkedIn Ads. Если вы не видите название этого раздела, вам не доступны подключения этого типа.

1. Выберите, хотите ли вы экспортировать данные для выполнения [таргетинг на контакты](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) или [таргетинг на компании](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) в LinkedIn. 

1. В разделе **Сопоставление данных** для целевого контакта выберите хотя бы одно поле, которое представляет адрес электронной почты клиента, Apple Ad ID, Google Ad ID, Google User ID или имя и фамилия. Если вы выбираете цель на компанию, выберите хотя бы одно поле, которое представляет название компании, домен электронной почты, URL-адрес страницы LinkedIn, символ акций или веб-сайт. Можно выбрать дополнительные поля для дальнейшего определения вашего экспорта. 

1. Выберите сегменты, которые нужно экспортировать. Сопоставленные аудитории в LinkedIn Campaign Manager будет автоматически созданы с именем сегментов, которые вы выбрали для экспорта. Каждый сегмент приведет к отдельному сопоставленной аудитории. 

1. Нажмите кнопку **Сохранить**.

Сохранение экспорта не запускает экспорт сразу.

Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab). Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Соответствие и конфиденциальность данных

Когда вы включаете Dynamics 365 Customer Insights для передачи данных в LinkedIn Ads, вы разрешаете передачу данных за пределы границ соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные. Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за то, чтобы LinkedIn Ads выполнял любые обязательства в отношении конфиденциальности или безопасности, которые могут иметься у вас. Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).

Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.