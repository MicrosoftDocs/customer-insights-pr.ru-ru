---
title: Экспорт сегментов Customer Insights в Adobe Campaign Standard (предварительная версия)
description: Узнайте, как использовать сегменты Customer Insights в Adobe Campaign Standard.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195536"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Экспорт сегментов Customer Insights в Adobe Campaign Standard (предварительная версия)

Экспортируйте сегменты, ориентированные на релевантную аудиторию, в Adobe Campaign Standard.

:::image type="content" source="media/ACS-flow.png" alt-text="Схема процесса изложена в этой статье.":::

## <a name="prerequisites"></a>Предварительные условия

- Лицензия Adobe Campaign Standard.
- Имя и ключ учетной записи [Учетная запись хранилища BLOB-объектов Azure](/azure/storage/blobs/create-data-lake-storage-account). Чтобы найти имя и ключ, см. раздел [Управление параметрами учетной записи хранения на портале Azure](/azure/storage/common/storage-account-manage).
- [Контейнер хранилища BLOB-объектов Azure](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Обзор кампании

Чтобы лучше понять, как можно использовать сегменты из Customer Insights в Adobe Experience Platform, давайте рассмотрим вымышленный пример кампании.

Предположим, ваша компания предлагает ежемесячную услугу по подписке для ваших клиентов в США. Вы хотите определить клиентов, чьи подписки должны быть продлены в течение следующих восьми дней, но подписка пока не продлена. Чтобы удержать этих клиентов, вы хотите отправить им рекламное предложение по электронной почте, используя Adobe Campaign Standard.

В этом примере мы хотим запустить промоакцию по электронной почте один раз. В этой статье не рассматривается вариант многократного запуска промоакции. Тем не менее, Customer Insights и Adobe Campaign Standard также можно настроить для работы в повторяющемся сценарии кампании.

## <a name="identify-your-target-audience"></a>Определите свою целевую аудиторию

В нашем сценарии мы предполагаем, что адреса электронной почты клиентов доступны в Customer Insights и их рекламные предпочтения были проанализированы для определения членов сегмента.

[Сегмент, который вы определили в Customer Insights](segments.md), называется **ChurnProneCustomers**, и вы планируете отправить этим клиентам рекламную рассылку по электронной почте.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Снимок экрана страницы сегментов с созданным сегментом ChurnProneCustomers.":::

Письмо с предложением, которое вы хотите отправить, будет содержать имя, фамилию и дату окончания подписки клиента. Он информирует клиентов о скидке, которую они получат, если продлят подписку до ее окончания.

## <a name="export-your-target-audience"></a>Экспортируйте свою целевую аудиторию

### <a name="set-up-connection-to-adobe-campaign"></a>Настройка подключения к Adobe Campaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Перейти в раздел **Администрирование** > **Подключения**.

1. Выберите **Добавить подключение** и выберите **Adobe Campaign**.

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. Укажите, кто может использовать это подключение. По умолчанию это только администраторы. Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введите **Имя учетной записи**, **Ключ учетной записи** и **Контейнер** для вашей учетной записи хранилища BLOB-объектов.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Снимок экрана конфигурации учетной записи хранилища. ":::

1. Ознакомьтесь с положениями [Соответствие и конфиденциальность данных](connections.md#data-privacy-and-compliance) и выберите **Принимаю**.

1. Выберите **Сохранить**, чтобы завершить подключение.

### <a name="configure-an-export"></a>Настройка экспорта

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Выберите **Добавить экспорт**.

1. В поле **Подключение для экспорта** выберите подключение в разделе Adobe Campaign. Свяжитесь с администратором, если подключение недоступно.

1. Введите имя экспорта.

1. Выберите сегмент, которые вы хотите экспортировать. В этом примере это **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Снимок экрана пользовательского интерфейса выбора сегмента с выбранным сегментом ChurnProneCustomers.":::

1. Выберите **Далее**.

1. Сопоставьте поля **Источник** из сегмента Customer Insights с именами полей **Цель** в схеме профилей Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Сопоставление полей для соединителя Adobe Campaign Standard.":::

   Если вы хотите добавить дополнительные атрибуты, выберите **Добавить атрибут**. Целевое имя может отличаться от имени исходного поля, чтобы можно было сопоставить выходные данные сегмента из Customer Insights с Adobe Campaign Standard, если поля не имеют одинаковых имен в двух системах.

   > [!NOTE]
   > Адрес электронной почты используется в качестве поля идентификации, но вы можете использовать любой другой идентификатор из профиля клиента для сопоставления данных с Adobe Campaign Standard.

1. Выберите **Сохранить**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Убедитесь, что количество записей в экспортируемом сегменте находится в пределах допустимого лимита вашей лицензии Adobe Campaign Standard.

Экспортированные данные хранятся в контейнере хранилища BLOB-объектов Azure, который вы настроили выше. В вашем контейнере автоматически создается следующий путь к папке: *%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Настройка Adobe Campaign Standard

Экспортированные сегменты содержат столбцы, выбранные вами при настройке экспорта. Эти данные могут быть использованы для [создания профилей в Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Чтобы использовать сегмент в Adobe Campaign Standard, [расширьте схему профиля](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) в Adobe Campaign Standard, чтобы включить два дополнительных поля.

В нашем примере этими полями являются название сегмента и дата сегмента. Мы будем использовать эти поля для идентификации профилей в Adobe Campaign Standard, на которые мы хотим нацелить эту кампанию.

Если в Adobe Campaign Standard нет других записей, кроме тех, что вы собираетесь импортировать, пропустите этот шаг.

## <a name="import-data-into-adobe-campaign-standard"></a>Импорт данных в Adobe Campaign Standard

Импортируйте подготовленные данные аудитории из Customer Insights в Adobe Campaign Standard для [создания профилей](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).

Рабочий процесс импорта на изображении ниже настроен на запуск каждые восемь часов и ищет экспортированные сегменты Customer Insights (CSV-файл в хранилище BLOB-объектов Azure). Бизнес-процесс извлекает содержимое CSV-файла в указанном порядке столбцов. Этот рабочий процесс был построен для выполнения базовой обработки ошибок и обеспечения того, чтобы каждая запись имела адрес электронной почты, прежде чем переносить данные в Adobe Campaign Standard. Рабочий процесс также извлекает имя сегмента из имени файла перед загрузкой в данные профиля Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Снимок экрана рабочего процесса импорта в пользовательский интерфейс Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Извлечение аудитории в Adobe Campaign Standard

Как только данные будут импортированы в Adobe Campaign Standard, [создайте рабочий процесс](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) и [запросите](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) клиентов на основе имени и даты сегмента для выбора профилей, которые были определены для нашей демонстрационной кампании.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Создание и отправка сообщения электронной почты с помощью Adobe Campaign Standard

Создайте текст сообщения электронной почты, а затем [протестируйте и отправьте](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) ваше сообщение.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Образец сообщения электронной почты с предложением продления из Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
