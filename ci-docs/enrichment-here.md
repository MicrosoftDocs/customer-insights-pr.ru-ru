---
title: Обогащение сторонним обогащением HERE Technologies
description: Общие сведения о стороннем обогащении HERE Technologies.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 171ead92427924083a13e2a3d52e7a7da417c801
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953689"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Обогащение профилей клиентов с помощью HERE Technologies (предварительная версия)

HERE Technologies — компания, занимающаяся платформой определения местоположения, которая предоставляет данные и услуги, ориентированные на местоположение. Служба по обогащению данных HERE Technologies повышают точность информации о местоположении ваших клиентов. Она обеспечивает нормализацию адресов, извлечение широты и долготы и многое другое.

## <a name="prerequisites"></a>Предварительные условия

- Активная подписка HERE Technologies. Чтобы получить подписку, [зарегистрируйтесь здесь](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) или [свяжитесь с HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) напрямую. [Узнайте больше об обогащении на основе местоположения от HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- [Подключение](connections.md) HERE [настроено](#configure-the-connection-for-here-technologies) администратором.

## <a name="configure-the-connection-for-here-technologies"></a>Настройка подключения для HERE Technologies

Вы должны быть [администратором](permissions.md#admin) в Customer Insights и иметь активный ключ API HERE Technologies.

1. Выберите **Добавить подключение** при настройке обогащения или перейдите в раздел **Администрирование** > **Подключения** и выберите **Настроить** на плитке HERE technologies.

1. Введите имя для подключения и действительный ключ API HERE Technologies.

1. Проверьте и дайте свое согласие для [Конфиденциальность и соответствие данных](#data-privacy-and-compliance), выбрав **Принимаю**.

1. Выберите **Проверить** для проверки конфигурации, затем выберите **Сохранить**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Страница настройки подключения HERE technologies.":::

### <a name="data-privacy-and-compliance"></a>Соответствие и конфиденциальность данных

Когда вы включаете Dynamics 365 Customer Insights для передачи данных в HERE Technologies, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные. Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией HERE Technologies любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть. Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).
Ваш администратор Dynamics 365 Customer Insights может удалить это обогащение в любое время, чтобы прекратить использование этой функции.

## <a name="configure-the-enrichment"></a>Настройка обогащения

1. Перейдите в раздел **Данные** > **Обогащение** и выберите вкладку **Обнаружить**.

1. Выберите **Обогатить данные** на пункте **Расположение** из плитки HERE Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="Плитка HERE Technologies.":::

1. Просмотрите обзор и выберите **Далее**.

1. Выберите подключение. Свяжитесь с администратором, если оно недоступно.

1. Выберите **Далее**.

1. Выберите **Набор данных клиента** и выберите профиль или сегмент, который вы хотите обогатить данными от HERE Technologies. Сущность *Клиент* обогащает все ваши профили клиентов, в том время как сегмент обогащает только профили клиентов, содержащиеся в этом сегменте.

1. Определите, какой тип полей из ваших объединенных профилей использовать для сопоставления: основной и/или дополнительный адрес. Вы можете указать сопоставление полей для обоих адресов и обогатить профили для обоих адресов по отдельности. Например, для домашнего адреса и рабочего адреса. Выберите **Далее**.

1. Сопоставьте свои поля с данными от HERE Technologies. Поля **Улица 1** и **Почтовый индекс** обязательны для выбранного основного и/или дополнительного адреса. Для более точного сопоставления добавьте больше полей.

1. Выберите **Далее**, чтобы завершить сопоставление полей.

1. Укажите **Имя** для обогащения и **Имя выходной сущности**.

1. Выберите **Сохранить обогащение** после просмотра вашего выбора.

1. Выберите **Выполнить**, чтобы начать процесс обогащения, или закройте, чтобы вернуться на страницу **Обогащения**.

## <a name="enrichment-results"></a>Результаты обогащения

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

В поле **Количество клиентов, обогащенных по значению поля** дана детализация охвата каждого обогащенного поля.

## <a name="next-steps"></a>Следующие шаги

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
