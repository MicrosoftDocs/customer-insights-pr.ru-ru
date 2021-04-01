---
title: Экспорт данных Customer Insights в Adobe Campaign Standard
description: Узнайте, как использовать сегменты аналитики аудитории в Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596331"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Используйте сегменты Customer Insights в Adobe Campaign Standard (предварительная версия)

Как пользователь аналитики аудитории для Dynamics 365 Customer Insights, возможно, вы создали сегменты, чтобы сделать свои маркетинговые кампании более эффективными за счет настройки таргетинга на нужные аудитории. Чтобы использовать сегмент из аналитики аудитории на платформе Adobe Experience и в таких приложениях, как Adobe Campaign Standard, вам необходимо выполнить несколько шагов, описанных в этой статье.

:::image type="content" source="media/ACS-flow.png" alt-text="Схема процесса изложена в этой статье.":::

## <a name="prerequisites"></a>Предварительные условия

-   Лицензия Dynamics 365 Customer Insights
-   Лицензия Adobe Campaign Standard
-   Учетная запись хранилища BLOB-объектов Azure

## <a name="campaign-overview"></a>Обзор кампании

Чтобы лучше понять, как можно использовать сегменты из аналитики аудитории на платформе Adobe Experience, давайте рассмотрим вымышленный пример кампании.

Предположим, ваша компания предлагает ежемесячную услугу по подписке для ваших клиентов в США. Вы хотите определить клиентов, чьи подписки должны быть продлены в течение следующих восьми дней, но подписка пока не продлена. Чтобы удержать этих клиентов, вы хотите отправить им рекламное предложение по электронной почте, используя Adobe Campaign Standard.

В этом примере мы хотим запустить промоакцию по электронной почте один раз. В этой статье не рассматривается вариант многократного запуска промоакции. Однако аналитика аудитории и Adobe Campaign Standard можно также настроить для работы со сценарием повторяющейся кампании.

## <a name="identify-your-target-audience"></a>Определите свою целевую аудиторию

В нашем сценарии мы предполагаем, что адреса электронной почты клиентов доступны в аналитике аудитории, а их рекламные предпочтения были проанализированы для идентификации участников сегмента.

[Сегмент, который вы определили в аналитике аудитории,](segments.md) называется **ChurnProneCustomers** и вы планируете направлять этим клиентам рекламную рассылку по электронной почте.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Снимок экрана страницы сегментов с созданным сегментом ChurnProneCustomers.":::

Письмо с предложением, которое вы хотите отправить, будет содержать имя, фамилию и дату окончания подписки клиента. Он информирует клиентов о скидке, которую они получат, если продлят подписку до ее окончания.

## <a name="export-your-target-audience"></a>Экспортируйте свою целевую аудиторию

Определив свою целевую аудиторию, мы можем настроить экспорт из аналитики аудитории в учетную запись хранилища BLOB-объектов Azure.

1. В аналитике аудитории перейдите **Администрирование** > **Экспорт пунктов назначения**.

1. На плитке **Adobe Campaign** выберите **Настройка**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Плитка конфигурации для Adobe Campaign Standard.":::

1. Укажите **Отображаемое имя** для этого нового пункта назначения экспорта, а затем введите **Имя учетной записи**, **Ключ учетной записи**, и **Контейнер** для учетной записи хранилища BLOB-объектов Azure, в которую вы хотите экспортировать сегмент.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Снимок экрана конфигурации учетной записи хранилища. "::: 

   - Подробнее о том, как найти имя учетной записи хранилища BLOB-объектов Azure и ключ учетной записи, см. в разделе [Управление настройками учетной записи хранения на портале Azure](/azure/storage/common/storage-account-manage).

   - Чтобы узнать, как создать контейнер, см. раздел [Создание контейнера](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Выберите **Далее**.

1. Выберите сегмент, которые вы хотите экспортировать. В этом примере это **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Снимок экрана пользовательского интерфейса выбора сегмента с выбранным сегментом ChurnProneCustomers.":::

1. Выберите **Далее**.

1. Теперь сопоставим **Исходные** поля из сегмента аналитики аудитории с именами **Целевых** полей в схеме профиля Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Сопоставление полей для соединителя Adobe Campaign Standard.":::

   Если вы хотите добавить дополнительные атрибуты, выберите **Добавить атрибут**. Целевое имя может отличаться от имени исходного поля, но вы все равно можете сопоставить выходные данные сегмента из аналитики аудитории с Adobe Campaign Standard, если поля имеют разные имена в двух системах.

   > [!NOTE]
   > Адрес электронной почты используется в качестве поля идентификации, но вы можете использовать любой другой идентификатор из вашего профиля клиента аналитики аудитории для сопоставления данных с Adobe Campaign Standard.

1. Нажмите кнопку **Сохранить**.

После сохранения места назначения экспорта вы найдете его по следующему пути: **Администратор** > **Экспорты** > **Мои пункты назначения экспорта**.

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Снимок экрана со списком экспортов и выделенным примером сегмента.":::

Вы можете сейчас [экспортировать сегмент по запросу](export-destinations.md#export-data-on-demand). Экспорт также будет выполняться с каждым [запланированным обновлением](system.md).

> [!NOTE]
> Убедитесь, что количество записей в экспортируемом сегменте находится в пределах допустимого лимита вашей лицензии Adobe Campaign Standard.

Экспортированные данные хранятся в контейнере хранилища BLOB-объектов Azure, который вы настроили выше. В вашем контейнере автоматически создан следующий путь к папке:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp% .csv*

Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Настройка Adobe Campaign Standard

Когда сегмент из аналитики аудитории экспортируется, он содержит столбцы, выбранные вами при определении места назначения экспорта на предыдущем шаге. Эти данные могут быть использованы для [создания профилей в Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Чтобы использовать сегмент в Adobe Campaign Standard, нам необходимо расширить схему профиля в Adobe Campaign Standard, включив в нее два дополнительных поля. Подробнее о том, как [расширить ресурс профиля](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) новыми полями в Adobe Campaign Standard.

В нашем примере этими полями являются *название сегмента и дата сегмента (необязательно).*

Мы будем использовать эти поля для определения профилей в Adobe Campaign Standard, на которые мы хотим настроить таргетинг для этой кампании.

Если в Adobe Campaign Standard нет других записей, кроме тех, которые вы собираетесь импортировать, вы можете пропустить этот шаг.

## <a name="import-data-into-adobe-campaign-standard"></a>Импортировать данные в Adobe Campaign Standard

Теперь, когда все готово, нам нужно импортировать подготовленные данные аудитории из аналитики аудитории в Adobe Campaign Standard для создания профилей. Научитесь [импортировать профили в Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) используя бизнес-процесс.

Бизнес-процесс импорта на изображении ниже настроен на запуск каждые 8 часов. Он ищет экспортированные сегменты аналитики аудитории (CSV-файл в хранилище BLOB-объектов Azure). Бизнес-процесс извлекает содержимое CSV-файла в указанном порядке столбцов. Этот бизнес-процесс был создан для того, чтобы выполнять базовую обработку ошибок и обеспечивать наличие адреса электронной почты в каждой записи перед переносом данных в Adobe Campaign Standard. Бизнес-процесс также извлекает имя сегмента из имени файла перед его загрузкой в данные профиля ACS.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Снимок экрана бизнес-процесса импорта в пользовательском интерфейсе Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Получите аудиторию в Adobe Campaign Standard

После импорта данных в Adobe Campaign Standard вы [может есоздать бизнес-процесс](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) и [запрос](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) клиентов на основе *Названия сегмента* и *Даты сегмента* для выбора профилей, которые были определены для нашего примера кампании.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Создайте и отправьте электронное письмо с помощью Adobe Campaign Standard

Создайте текст сообщения электронной почты, а затем [протестируйте и отправьте](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) ваше сообщение.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Образец сообщения электронной почты с предложением о продлении от Adobe Campaign Standard.":::