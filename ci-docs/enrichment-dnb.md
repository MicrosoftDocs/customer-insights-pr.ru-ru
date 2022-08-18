---
title: Обогащение профилей компаний с помощью Dun & Bradstreet (предварительная версия)
description: Общая информация о стороннем обогащении Dun & Bradstreet.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: e89b64774dcb519a071dd3d403473807a50e7f33
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237920"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>Обогащение профилей компаний с помощью Dun & Bradstreet (предварительная версия)

Dun & Bradstreet предоставляет коммерческие данные, аналитику и идеи для бизнеса. Это позволяет клиентам с унифицированными профилями клиентов для компаний обогащать свои данные. Обогащение включает атрибуты, такие как DUNS, размер компании, местонахождение, отрасль и так далее.

## <a name="prerequisites"></a>Предварительные условия

- Активная лицензия [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights).
- [Единые профили клиентов Unified customer profile](customer-profiles.md) для компаний.
- Натсроен [проект](#set-up-your-dun--bradstreet-project) Dun & Bradstreet.
- [Подключение](connections.md) Dun & Bradstreet [настроено](#configure-a-connection-for-dun--bradstreet) администратором.

## <a name="set-up-your-dun--bradstreet-project"></a>Настройка вашего проекта Dun & Bradstreet

Как лицензированный пользователь Dun & Bradstreet, вы можете создать проект в [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Войдите в [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Чтобы получить учетные данные, [восстановите пароль](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Загрузите [наш файл шаблона CSV](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv), который будет использоваться для сопоставления полей Customer Insights с соответствующими полями Dun & Bradstreet.

1. Отправьте файл на шаге **Отправить данные** во время создания проекта Dun & Bradstreet.

1. Выберите горизонтальные точки под соответствующим **источником** в недавно созданном проекте Dun & Bradstreet, чтобы увидеть доступные варианты.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Снимок экрана точек в проекте Dun & Bradstreet.":::

1. Выберите **Получить сведения S3**. Сохраните эту информацию в надежном месте. Вам это понадобится, чтобы [настроить соединение для обогащения](#configure-a-connection-for-dun--bradstreet) в Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Снимок экрана выбора информации s3 в проекте Dun & Bradstreet.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Настройте соединение для Dun & Bradstreet

Вы должны быть [администратором](permissions.md#admin) в Customer Insights и иметь учетные данные от Dun & Bradstreet Connect.

1. Выберите **Добавить подключение** при настройке обогащения или перейдите в раздел **Администратор** > **Подключения** и выберите **Настройка** на плитке Dun & Bradstreet.

1. Введите имя для подключения.

1. Предоставьте действительные учетные данные Dun & Bradstreet и сведения о проекте Dun & Bradstreet *Регион, Путь к папке для сброса, Имя папки для сброса*. [Эта информация](#set-up-your-dun--bradstreet-project) берется из проекта Dun & Bradstreet.

1. Ознакомьтесь с положениями [Соответствие и конфиденциальность данных](connections.md#data-privacy-and-compliance) и выберите **Принимаю**.

1. Выберите **Проверить** для проверки конфигурации, затем выберите **Сохранить**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Страница настройки соединения Dun & Bradstreet.":::

## <a name="supported-countries-or-regions"></a>Поддерживаемые страны или регионы

В настоящее время мы поддерживаем следующие варианты страны/региона: Канада (английский) или США (английский).

## <a name="configure-the-enrichment"></a>Настройка обогащения

1. Перейдите в раздел **Данные** > **Обогащение** и выберите вкладку **Обнаружить**.

1. Выберите **Обогатить данные** на плитке **Данные о компании** для Dun & Bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Снимок экрана плитки Dun & Bradstreet.":::

1. Просмотрите обзор и выберите **Далее**.

1. Выберите подключение и подтвердите. Свяжитесь с администратором, если подключение недоступно.

1. Выберите **Далее**.

1. Выберите **Набор данных клиента** и выберите профиль или сегмент, который вы хотите обогатить данными компании из Dun & Bradstreet. Сущность *Клиент* обогащает все ваши профили клиентов, в том время как сегмент обогащает только профили клиентов, содержащиеся в этом сегменте.

1. Определите, какие типы полей из ваших унифицированных профилей должны использоваться для сопоставления данных компании из Dun & Bradstreet. Хотя бы одно из полей **Имя и адрес**, **Телефон** или **Электронная почта** является обязательным.

1. Выберите **Далее**

1. Сопоставьте свои поля с данными компании от Dun & Bradstreet. Поля **Номер DUNS** или **Название компании** и **Страна** обязательны.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Панель сопоставления полей Dun & Bradstreet.":::

1. Выберите **Далее**, чтобы завершить сопоставление полей.

1. Укажите **Имя** для обогащения и **Имя выходной сущности**.

1. Выберите **Сохранить обогащение** после просмотра вашего выбора.

1. Выберите **Выполнить**, чтобы начать процесс обогащения, или закройте, чтобы вернуться на страницу **Обогащения**.

## <a name="view-enrichment-results"></a>Просмотр результатов обогащения

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Следующие шаги

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
