---
title: Экспорт данных Customer Insights в Adobe Experience Platform
description: Узнайте, как использовать сегменты аналитики аудитории в Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 884f4d30f354bed29909d57be84dce4c8e46965a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760117"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Используйте сегменты Customer Insights в Adobe Experience Platform (предварительная версия)

Как пользователь аналитики аудитории для Dynamics 365 Customer Insights, возможно, вы создали сегменты, чтобы сделать свои маркетинговые кампании более эффективными за счет настройки таргетинга на нужные аудитории. Чтобы использовать сегмент из аналитики аудитории на платформе Adobe Experience и в таких приложениях, как Adobe Campaign Standard, вам необходимо выполнить несколько шагов, описанных в этой статье.

:::image type="content" source="media/AEP-flow.png" alt-text="Схема процесса изложена в этой статье.":::

## <a name="prerequisites"></a>Предварительные условия

-   Лицензия Dynamics 365 Customer Insights
-   Лицензия Adobe Experience Platform
-   Лицензия Adobe Campaign Standard
-   Учетная запись хранилища BLOB-объектов Azure

## <a name="campaign-overview"></a>Обзор кампании

Чтобы лучше понять, как можно использовать сегменты из аналитики аудитории на платформе Adobe Experience, давайте рассмотрим вымышленный пример кампании.

Предположим, ваша компания предлагает ежемесячную услугу по подписке для ваших клиентов в США. Вы хотите определить клиентов, чьи подписки должны быть продлены в течение следующих восьми дней, но подписка пока не продлена. Чтобы удержать этих клиентов, вы хотите отправить им рекламное предложение по электронной почте, используя Adobe Experience Platform.

В этом примере мы хотим запустить промоакцию по электронной почте один раз. В этой статье не рассматривается вариант многократного запуска промоакции.

## <a name="identify-your-target-audience"></a>Определите свою целевую аудиторию

В нашем сценарии мы предполагаем, что адреса электронной почты клиентов доступны в аналитике аудитории, а их рекламные предпочтения были проанализированы для идентификации участников сегмента.

[Сегмент, который вы определили в аналитике аудитории,](segments.md) называется **ChurnProneCustomers** и вы планируете направлять этим клиентам рекламную рассылку по электронной почте.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Снимок экрана страницы сегментов с созданным сегментом ChurnProneCustomers.":::

Письмо с предложением, которое вы хотите отправить, будет содержать имя, фамилию и дату окончания подписки клиента. Он информирует клиентов о скидке, которую они получат, если продлят подписку до ее окончания.

## <a name="export-your-target-audience"></a>Экспортируйте свою целевую аудиторию

Определив свою целевую аудиторию, мы можем настроить экспорт из аналитики аудитории в учетную запись хранилища BLOB-объектов Azure.

### <a name="configure-a-connection"></a>Настройка подключения

1. Перейти в раздел **Администрирование** > **Подключения**.

1. Выберите **Добавить подключение** и выберите **Хранилище BLOB-объектов Azure** или выберите **Настройка** на плитке **Хранилище BLOB-объектов Azure**:

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Плитка конфигурации для хранилища BLOB-объектов Azure."::: чтобы настроить подключение.

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. Укажите, кто может использовать это подключение. Если вы не предпримете никаких действий, по умолчанию это будут администраторы. Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введите **Имя учетной записи**, **Ключ учетной записи** и **Контейнер** для вашей учетной записи хранилища BLOB-объектов, в которую вы хотите экспортировать сегмент.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Снимок экрана конфигурации учетной записи хранилища. "::: 
   
    - Чтобы узнать больше о том, как найти имя учетной записи хранилища BLOB-объектов и ключ учетной записи, см. раздел [Управление параметрами учетной записи хранения на портале Azure](/azure/storage/common/storage-account-manage).
    - Чтобы узнать, как создать контейнер, см. раздел [Создание контейнера](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Выберите **Сохранить**, чтобы завершить подключение. 

### <a name="configure-an-export"></a>Настройка экспорта

Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа. Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Чтобы создать новый экспорт, выберите **Добавить экспорт**.

1. В поле **Подключение для экспорта** выберите подключение из раздела "Хранилище BLOB-объектов Azure". Если вы не видите название этого раздела, вам не доступны подключения этого типа.

1. Выберите сегмент, которые вы хотите экспортировать. В этом примере это **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Снимок экрана пользовательского интерфейса выбора сегмента с выбранным сегментом ChurnProneCustomers.":::

1. Нажмите кнопку **Сохранить**.

После сохранения места назначения экспорта вы найдете его в разделе **Данные** > **Экспорты**.

Вы можете сейчас [экспортировать сегмент по запросу](export-destinations.md#run-exports-on-demand). Экспорт также будет выполняться с каждым [запланированным обновлением](system.md).

> [!NOTE]
> Убедитесь, что количество записей в экспортируемом сегменте находится в пределах допустимого лимита вашей лицензии Adobe Campaign Standard.

Экспортированные данные хранятся в контейнере хранилища BLOB-объектов Azure, который вы настроили выше. В вашем контейнере автоматически создан следующий путь к папке:

*%ContainerName%/ CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

Файл *model.json* для экспортируемых сущностей находится на уровне *%ExportDestinationName%*.

Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Определение модели данных о взаимодействиях (XDM) в Adobe Experience Platform

Чтобы использовать экспортированные данные из аналитики аудитории в рамках Adobe Experience Platform, нам необходимо определить схему модели данных о взаимодействиях и [настроить данные для профиля клиента в реальном времени](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Узнайте, [что такое XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) и изучите [основы построения схемы](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Импорт данных в Adobe Experience Platform

Теперь, когда все готово, нам нужно импортировать подготовленные данные аудитории из аналитики аудитории в Adobe Experience Platform.

Сначала, [создайте подключение к источнику хранилища BLOB-объектов Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

После определения подключения к источнику [настройте поток данных](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) для пакетного подключения к облачному хранилищу для импорта выходных данных сегмента из аналитики аудитории в Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Создайте аудиторию в Adobe Campaign Standard

Чтобы отправить сообщение электронной почты для этой кампании, мы будем использовать Adobe Campaign Standard. После импорта данных в Adobe Experience Platform нам необходимо [создать аудиторию](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) в Adobe Campaign Standard с использованием данных в Adobe Experience Platform.

Узнайте, как [использовать конструктор сегментов](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) в Adobe Campaign Standard, чтобы определить аудиторию на основе данных в Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Создайте и отправьте электронное письмо с помощью Adobe Campaign Standard

Создайте текст сообщения электронной почты, а затем [протестируйте и отправьте](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) ваше сообщение.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Образец сообщения электронной почты с предложением о продлении от Adobe Campaign Standard.":::
