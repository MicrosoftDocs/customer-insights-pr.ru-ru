---
title: Обогащение сторонним обогащением HERE Technologies
description: Общие сведения о стороннем обогащении HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c131ffb230a62b76e123334ff3c6776c8f9aa06e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646823"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Обогащение профилей клиентов с помощью HERE Technologies (предварительная версия)

HERE Technologies — компания, занимающаяся платформой определения местоположения, которая предоставляет данные и услуги, ориентированные на местоположение. С помощью услуг по обогащению данных HERE Technologies вы можете получить более точное представление о местоположении ваших клиентов с помощью нормализации адресов, извлечения широты и долготы и т. д.

## <a name="prerequisites"></a>Предварительные условия

Для настройки обогащения HERE Technologies должны быть соблюдены следующие предварительные условия:

- Требуется активная подписка HERE Technologies. Чтобы получить подписку, вы можете [зарегистрироваться здесь](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) или [связаться с HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) напрямую. [Узнайте больше об обогащении на основе местоположения от HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Подключение [HERE](connections.md) доступно *или* у вас есть разрешения [администратора](permissions.md#admin) и ключ API HERE Technologies.

## <a name="configure-the-enrichment"></a>Настройка обогащения

1. Перейти к **Данные** > **Обогащение**. 

1. Выберите **Обогатить данные** на плитке HERE Technologies, затем выберите **Начать**.

   > [!div class="mx-imgBorder"]
   > ![Плитка HERE Technologies.](media/HERE-tile.png "Плитка HERE Technologies")

1. Выберите [подключение](connections.md) из раскрывающегося списка. Свяжитесь с администратором, если подключение недоступно. Если вы администратор, вы можете создать подключение, выбрав **Добавить подключение**. Выберите **HERE Technologies** из раскрывающегося списка. 

1. Выберите **Подключиться к HERE Technologies** для подтверждения выбора.

1.  Выберите **Далее** и выберите **Набор данных клиента**, который вы хотите обогатить данными о местоположении от HERE Technologies. Вы можете выбрать сущность **Клиент**, чтобы обогатить все ваши профили клиентов, или выбрать сущность сегмента, чтобы обогатить только профили клиентов, содержащиеся в этом сегменте.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Снимок экрана при выборе набора данных клиента.":::

1. Выберите, хотите ли вы сопоставить поля с основным и/или дополнительным адресом. Вы можете указать сопоставление полей для обоих адресов и обогатить профили для обоих адресов по отдельности. Например, если есть домашний и рабочий адреса. Выберите **Далее**.

1. Определите, какие поля из ваших унифицированных профилей следует использовать для поиска соответствия данные расположения от HERE Technologies. Поля **Улица 1** и **Почтовый индекс** обязательны для выбранного основного и/или дополнительного адреса. Для большей точности соответствия можно добавить больше полей.

   > [!div class="mx-imgBorder"]
   > ![Страница конфигурации обогащения HERE Technologies.](media/enrichment-HERE-configuration.png "Страница конфигурации обогащения HERE Technologies")

1. Выберите **Далее**, чтобы завершить сопоставление полей.

1. Задайте имя для обогащения. 

1. Выберите **Сохранить обогащение** после просмотра вашего выбора.

## <a name="configure-the-connection-for-here-technologies"></a>Настройка подключения для HERE Technologies 

Чтобы настраивать подключения, вы должны быть администратором. Выберите **Добавить подключение** при настройке обогащения *или* перейдите в раздел **Администрирование** > **Подключения** и выберите **Настроить** на плитке HERE technologies.

1. Введите имя для подключения в поле **Отображаемое имя**.

1. Предоставьте действующий ключ API-интерфейса HERE Technologies.

1. Проверьте и дайте свое согласие для **Конфиденциальность и соответствие данных**, выбрав **Принимаю**.

1. Выберите **Проверить** для проверки конфигурации.

1. После завершения проверки выберите **Сохранить**.

   > [!div class="mx-imgBorder"]
   > ![Страница настройки подключения HERE technologies.](media/enrichment-HERE-connection.png "Страница настройки подключения HERE technologies")

## <a name="enrichment-results"></a>Результаты обогащения

Чтобы начать процесс обогащения, выберите **Выполнить** на панели команд. Вы также можете позволить системе запускать обогащение автоматически как часть [запланированного обновления](system.md#schedule-tab). Время обработки будет зависеть от объема данных вашего клиента и времени ответа API от HERE Technologies.

После завершения процесса обогащения вы можете просмотреть недавно обогащенные данные профилей клиентов в разделе **Мои обогащения**. Кроме того, вы найдете время последнего обновления и количество обогащенных профилей.

Вы можете получить доступ к детализированному представлению каждого обогащенного профиля, выбрав **Просмотр обогащенных данных**.

## <a name="next-steps"></a>Дальнейшие действия

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Соответствие и конфиденциальность данных

Когда вы включаете Dynamics 365 Customer Insights для передачи данных в HERE Technologies, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные. Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией HERE Technologies любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть. Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).
Ваш администратор Dynamics 365 Customer Insights может удалить это обогащение в любое время, чтобы прекратить использование этой функции.


[!INCLUDE [footer-include](includes/footer-banner.md)]