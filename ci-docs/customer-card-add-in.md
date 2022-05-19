---
title: Надстройка карточек клиентов для приложений Dynamics 365 (содержит видео)
description: Покажите данные профиля клиента из Customer Insights в приложениях Dynamics 365 с помощью этой надстройки.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-search-filter
- ci-customer-card
- customerInsights
ms.openlocfilehash: 8508880bb3274bb491a314a043a5222d4d381073
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755652"
---
# <a name="customer-card-add-in-preview"></a>Надстройка карточек клиентов (предварительная версия)

Получите полный обзор своих клиентов прямо в приложениях Dynamics 365. Установив надстройку «Карточка клиента» в поддерживаемом приложении Dynamics 365, вы можете выбрать отображение полей профиля клиента, аналитических данных и временной шкалы действий. Надстройка будет извлекать данные из Customer Insights, не влияя на данные в подключенном приложении Dynamics 365.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Предварительные условия

- Надстройка работает только с приложениями на основе модели Dynamics 365, такими как Sales или Customer Service версии 9.0 и новее.
- Чтобы ваши данные Dynamics 365 сопоставлялись профилям клиентов Customer Insights, рекомендуется, чтобы они были [приняты из приложения Dynamics 365 с помощью соединителя Microsoft Dataverse](connect-power-query.md). Если вы используете другой метод для приема контактов (или организаций) Dynamics 365, вам необходимо убедиться, что поле `contactid` (или `accountid`) задано как [первичный ключ для этого источник данных на этапе сопоставления процесса объединения данных](map-entities.md#select-primary-key-and-semantic-type-for-attributes).
- Все пользователи Dynamics 365 надстройки Карточка клиента должны быть [добавлены как пользователи](permissions.md) в Customer Insights, чтобы просмотреть данные.
- [Настроенные возможности поиска и фильтрации](search-filter-index.md) в Customer Insights необходимы для работы поиска данных.
- Каждый элемент управления надстройки основан на определенных данных в Customer Insights. Некоторые данные и элементы управления доступны только в средах определенных типов. Конфигурация надстройки сообщит вам, если элемент управления недоступен из-за выбранного типа среды. Подробнее о [вариантах использования среды](work-with-business-accounts.md).
  - **Контроль мер**: требует [настроенных мер](measures.md) атрибутов типа клиента.
  - **Интеллектуальный контроль**: требуются данные, созданные с использованием [прогнозов или пользовательских моделей](predictions-overview.md).
  - **Контроль информации о клиенте**: все поля из профиля доступны в едином профиле клиента.
  - **Контроль обогащения**: требуется активное [обогащение](enrichment-hub.md), примененное к профилям клиентов. Надстройка карточек поддерживает следующие расширения: [Бренды](enrichment-microsoft.md) от Майкрософт, [Интересы](enrichment-microsoft.md) от Майкрософт, а также[Данные о взаимодействии с Office](enrichment-office.md) от Майкрософт.
  - **Контроль контактов**: требуется определение семантической сущности контактов типа.
  - **Контроль временной шкалы**: требуются [настроенные действия](activities.md).

## <a name="install-the-customer-card-add-in"></a>Установка надстройки карточек клиентов

Надстройка карточки клиента — это решение для приложений Customer Engagement в Dynamics 365. Чтобы установить решение, перейдите в AppSource и найдите **Карточка клиента Dynamics**. Выберите [Настройка карточек клиента в AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) и выберите **Получить**.

Вам может потребоваться войти в систему с учетными данными администратора для приложения Dynamics 365, чтобы установить решение. Установка решения в вашей среде может занять некоторое время.

## <a name="configure-the-customer-card-add-in"></a>Настройка надстройки карточки клиента

1. В качестве администратора перейдите в раздел **Настройки** в Dynamics 365 и выберите **Решения**.

1. Выберите ссылку **Отображаемое имя** для решения **Надстройка карточки клиента Dynamics 365 Customer Insights (предварительная версия)**.

   > [!div class="mx-imgBorder"]
   > ![Выберите отображаемое имя.](media/select-display-name.png "Выберите отображаемое имя.")

1. Выберите **Войти** и введите учетные данные для учетной записи администратора, которую вы используете для настройки Customer Insights.

   > [!NOTE]
   > Убедитесь, что блокировщик всплывающих окон браузера не блокирует окно аутентификации при выборе кнопки **Войти**.

1. Выберите среду Customer Insights, из которой вы хотите получить данные.

1. Определите сопоставление полей с записями в приложении Dynamics 365. В зависимости от ваших данных в Customer Insights вы можете выбрать отображение следующих параметров:
   - Для сопоставления с контактом выберите поле в сущности "Клиент", которое соответствует идентификатору сущности вашего контакта.
   - Для сопоставления с учетной записью выберите поле в сущности "Клиент", которое соответствует идентификатору сущности вашей учетной записи.

   > [!div class="mx-imgBorder"]
   > ![Поле идентификатора контакта.](media/contact-id-field.png "Поле идентификатора контакта.")

1. Выберите **Сохранить конфигурацию**, чтобы сохранить настройки.

1. Затем необходимо назначить роли безопасности в Dynamics 365, чтобы пользователи могли настраивать и просматривать карточку клиента. В Dynamics 365 перейдите в раздел **Параметры** > **Безопасность** > **Пользователи**. Выберите пользователей для редактирования ролей пользователей и выберите **Управление ролями**.

1. Назначьте роль **Настройщик карточек Customer Insights** для пользователей, которые будут настраивать содержимое, отображаемое на карточке, для всей организации.

## <a name="add-customer-card-controls-to-forms"></a>Добавление элементов управления карточкой клиента в формы

В зависимости от вашего сценария вы можете добавить элементы управления либо в форме **Контакт**, либо в форме **Организация**. Если ваша среда Customer Insights предназначена для организаций, мы рекомендуем добавить элементы управления в форму организации. В этом случае замените «контакт» в приведенных ниже шагах на «организация».

1. Чтобы добавить элементы управления карточки клиента в свою форму контакта, перейдите к пункту **Параметры** > **Настройки** в Dynamics 365.

1. Выберите **Настройка системы**.

1. Перейдите к сущности **Контакт**, разверните ее и выберите **Формы**.

1. Выберите форму контакта, к которой вы хотели бы добавить элементы управления карточки клиента.

    > [!div class="mx-imgBorder"]
    > ![Выберите форму контакта.](media/contact-active-forms.png "Выберите форму контакта.")

1. Чтобы добавить элемент управления, в редакторе форм перетащите любое поле из **Обозревателя полей** в место, где вы хотите разместить этот элемент управления.

1. Выберите только что добавленное поле в форме, затем выберите **Изменить свойства**.

1. Перейдите на вкладку **Элементы управления** и выберите **Добавить элемент управления**. Выберите один из доступных пользовательских элементов управления и выберите **Добавить**.

1. В диалоговом окне **Свойства поля** снимите флажок **Отображать метку в форме**.

1. Выберите параметр **Интернет** для элемента управления. Для элемента управления обогащением выберите тип обогащения, который вы хотите отобразить, настроив поле **enrichmentType**. Добавьте отдельный элемент управления обогащения для каждого типа обогащения.

1. Выбрать **Сохранить** и **Опубликовать**, чтобы опубликовать обновленную форму контакта.

1. Перейдите к опубликованной форме контакта. Вы увидите недавно добавленный элемент управления. Возможно, вам придется войти в систему при первом использовании.

1. Чтобы настроить то, что вы хотите отображаться в пользовательском элементе управления, выберите кнопку редактирования в правом верхнем углу.

## <a name="upgrade-customer-card-add-in"></a>Обновление надстройки карточек клиентов

Надстройка карточки клиента не обновляется автоматически. Чтобы выполнить обновление до последней версии, выполните следующие действия в приложении Dynamics 365, в котором установлена надстройка.

1. В приложении Dynamics 365 перейдите **Параметры** > **Настройка** и выберите **Решения**.

1. В таблице надстроек найдите **CustomerInsightsCustomerCard** и выберите строку.

1. Выберите **Применить обновление решения** на панели действий.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Обновите решение в области настройки приложений Dynamics 365.":::

1. После запуска процесса обновления будет показан индикатор загрузки, пока обновление не будет завершено. Если более новой версии нет, при обновлении будет отображаться сообщение об ошибке.

## <a name="troubleshooting"></a>Устранение неполадок

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>Элементы управления из надстройки карточки клиентов не находят данные

**Проблема:**

Даже при правильно настроенных полях идентификаторов элементы управления не могут найти данные ни для одного клиента.  

**Решение:**

1. Убедитесь, что вы настроили надстройку карточки в соответствии с инструкциями: [Настройка надстройки карточки клиента](#configure-the-customer-card-add-in)

1. Проверьте конфигурацию приема данных. Отредактируйте источник данных для системы Dynamics 365, который содержит GUID идентификатора контакта. Если GUID идентификатора контакта отображается прописными буквами в редакторе Power Query, попробуйте выполнить следующие шаги:
    1. Отредактируйте источник данных, чтобы открыть источник данных в редакторе Power Query.
    1. Выберите столбец идентификатора контакта.
    1. Выберите **Преобразовать** в строке заголовка, чтобы увидеть доступные действия.
    1. Выберите **нижний регистр**. Убедитесь, что GUID в таблице теперь в нижнем регистре.
    1. Сохраните источник данных.
    1. Запустите прием данных, объединение и последующие процессы для распространения изменений в GUID.

После завершения системой полного обновления элементы управления надстройки карточки клиента должны отображать ожидаемые данные.

[!INCLUDE [footer-include](includes/footer-banner.md)]