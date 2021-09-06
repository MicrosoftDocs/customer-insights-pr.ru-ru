---
title: Экспорт данных Customer Insights в Adobe Campaign Standard
description: Узнайте, как использовать сегменты аналитики аудитории в Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d301b4f0cb875303fb3d373b77177acd1c1f5219cd6f23c2a1d29ce67a222eab
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032179"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Использование сегментов Customer Insights в Adobe Campaign Standard (предварительная версия)

Как пользователь аналитики аудитории в Dynamics 365 Customer Insights, возможно, вы создали сегменты, чтобы сделать свои маркетинговые кампании более эффективными за счет нацеливания на релевантную аудиторию. Чтобы использовать сегмент из аналитики аудитории в Adobe Experience Platform и таких приложениях, как Adobe Campaign Standard, вам нужно выполнить несколько шагов, описанных в этой статье.

:::image type="content" source="media/ACS-flow.png" alt-text="Схема процесса изложена в этой статье.":::

## <a name="prerequisites"></a>Предварительные условия

-   Лицензия Dynamics 365 Customer Insights
-   Лицензия Adobe Campaign Standard
-   Учетная запись хранилища BLOB-объектов Azure

## <a name="campaign-overview"></a>Обзор кампании

Чтобы лучше понять, как можно использовать сегменты из аналитики аудитории в Adobe Experience Platform, давайте посмотрим на вымышленный образец кампании.

Предположим, ваша компания предлагает ежемесячную услугу по подписке для ваших клиентов в США. Вы хотите определить клиентов, чьи подписки должны быть продлены в течение следующих восьми дней, но подписка пока не продлена. Чтобы удержать этих клиентов, вы хотите отправить им рекламное предложение по электронной почте, используя Adobe Campaign Standard.

В этом примере мы хотим запустить промоакцию по электронной почте один раз. В этой статье не рассматривается вариант многократного запуска промоакции. Однако аналитика аудитории и Adobe Campaign Standard также можно настроить для работы со сценарием повторяющейся кампании.

## <a name="identify-your-target-audience"></a>Определите свою целевую аудиторию

В нашем сценарии мы предполагаем, что адреса электронной почты клиентов доступны в аналитике аудитории, а их рекламные предпочтения были проанализированы для идентификации участников сегмента.

[Сегмент, который вы определили в аналитике аудитории,](segments.md) называется **ChurnProneCustomers** и вы планируете направлять этим клиентам рекламную рассылку по электронной почте.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Снимок экрана страницы сегментов с созданным сегментом ChurnProneCustomers.":::

Письмо с предложением, которое вы хотите отправить, будет содержать имя, фамилию и дату окончания подписки клиента. Он информирует клиентов о скидке, которую они получат, если продлят подписку до ее окончания.

## <a name="export-your-target-audience"></a>Экспортируйте свою целевую аудиторию

### <a name="configure-a-connection"></a>Настройка подключения

Определив свою целевую аудиторию, мы можем настроить экспорт из аналитики аудитории в учетную запись хранилища BLOB-объектов Azure.

1. В аналитике аудитории перейдите по ссылке **Администрирование** > **Подключения**.

1. Выберите **Добавить подключение** и выберите **Adobe Campaign** для настройки подключения или выберите **Настройка** на плитке **Adobe Campaign**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Плитка конфигурации для Adobe Campaign Standard.":::

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. Укажите, кто может использовать это подключение. Если вы не предпримете никаких действий, по умолчанию это будут администраторы. Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).

1. Введите **Имя учетной записи**, **Ключ учетной записи** и **Контейнер** вашей учетной записи хранилища BLOB-объектов Azure, в которую вы хотите экспортировать сегмент.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Снимок экрана конфигурации учетной записи хранилища. "::: 

   - Подробнее о том, как найти имя учетной записи хранилища BLOB-объектов Azure и ключ учетной записи, см. в разделе [Управление настройками учетной записи хранения на портале Azure](/azure/storage/common/storage-account-manage).

   - Чтобы узнать, как создать контейнер, см. раздел [Создание контейнера](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Выберите **Сохранить**, чтобы завершить подключение.

### <a name="configure-an-export"></a>Настройка экспорта

Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа. Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Чтобы создать новый экспорт, выберите **Добавить экспорт**.

1. В поле **Подключение для экспорта** выберите подключение в разделе Adobe Campaign. Если вы не видите название этого раздела, значит, вам недоступны соединения этого типа.

1. Выберите сегмент, которые вы хотите экспортировать. В этом примере это **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Снимок экрана пользовательского интерфейса выбора сегмента с выбранным сегментом ChurnProneCustomers.":::

1. Выберите **Далее**.

1. Теперь сопоставим поля **Источник** из сегмента аналитики аудитории с именами полей **Цель** в схеме профиля Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Сопоставление полей для соединителя Adobe Campaign Standard.":::

   Если вы хотите добавить дополнительные атрибуты, выберите **Добавить атрибут**. Имя цели может отличаться от имени исходного поля, поэтому вы все равно можете сопоставить выходные данные сегмента из аналитики аудитории с Adobe Campaign Standard, если поля не имеют одинаковых имен в двух системах.

   > [!NOTE]
   > Адрес электронной почты используется в качестве поля идентификации, но вы можете использовать любой другой идентификатор из вашего профиля клиента аналитики аудитории для сопоставления данных с Adobe Campaign Standard.

1. Нажмите кнопку **Сохранить**.

После сохранения места назначения экспорта вы найдете его в разделе **Данные** > **Экспорты**.

Вы можете сейчас [экспортировать сегмент по запросу](export-destinations.md#run-exports-on-demand). Экспорт также будет выполняться с каждым [запланированным обновлением](system.md).

> [!NOTE]
> Убедитесь, что количество записей в экспортируемом сегменте находится в пределах допустимого лимита вашей лицензии Adobe Campaign Standard.

Экспортированные данные хранятся в контейнере хранилища BLOB-объектов Azure, который вы настроили выше. В вашем контейнере автоматически создан следующий путь к папке:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp% .csv*

Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Настройка Adobe Campaign Standard

Когда сегмент из аналитики аудитории экспортируется, он содержит столбцы, выбранные вами при определении места назначения экспорта на предыдущем шаге. Эти данные могут быть использованы для [создания профилей в Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Чтобы использовать сегмент в Adobe Campaign Standard, нам нужно расширить схему профиля в Adobe Campaign Standard, чтобы включить два дополнительных поля. Узнайте, как [расширить ресурс профиля](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) с новыми полями в Adobe Campaign Standard.

В нашем примере этими полями являются *название сегмента и дата сегмента (необязательно)*.

Мы будем использовать эти поля для идентификации профилей в Adobe Campaign Standard, на которые мы хотим нацелить эту кампанию.

Если в Adobe Campaign Standard нет других записей, кроме тех, что вы собираетесь импортировать, вы можете пропустить этот шаг.

## <a name="import-data-into-adobe-campaign-standard"></a>Импорт данных в Adobe Campaign Standard

Теперь, когда все готово, нам нужно импортировать подготовленные данные аудитории из аналитики аудитории в Adobe Campaign Standard для создания профилей. Узнайте, [как импортировать профили в Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences), используя рабочий процесс.

Рабочий процесс импорта на изображении ниже настроен для запуска каждые восемь часов и поиска экспортированных сегментов аналитики аудитории (CSV-файл в хранилище BLOB-объектов Azure). Бизнес-процесс извлекает содержимое CSV-файла в указанном порядке столбцов. Этот рабочий процесс был построен для выполнения базовой обработки ошибок и обеспечения того, чтобы каждая запись имела адрес электронной почты, прежде чем переносить данные в Adobe Campaign Standard. Рабочий процесс также извлекает имя сегмента из имени файла перед загрузкой в данные профиля Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Снимок экрана рабочего процесса импорта в пользовательский интерфейс Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Извлечение аудитории в Adobe Campaign Standard

Как только данные будут импортированы в Adobe Campaign Standard, вы [может создать рабочий процесс](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) и [запрашивать](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) клиентов на основе *названия сегмента* и *даты сегмента* для выбора профилей, которые были определены для нашей демонстрационной кампании.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Создание и отправка сообщения электронной почты с помощью Adobe Campaign Standard

Создайте текст сообщения электронной почты, а затем [протестируйте и отправьте](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) ваше сообщение.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Образец сообщения электронной почты с предложением продления из Adobe Campaign Standard.":::
