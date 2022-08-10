---
title: Экспорт сегментов в Adobe Experience Platform (предварительная версия)
description: Узнайте, как использовать сегменты Customer Insights в Adobe Experience Platform.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195306"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Экспорт сегментов в Adobe Experience Platform (предварительная версия)

Экспортируйте сегменты, ориентированные на релевантную аудиторию, в Adobe Experience Platform.

:::image type="content" source="media/AEP-flow.png" alt-text="Схема процесса изложена в этой статье.":::

## <a name="prerequisites"></a>Предварительные условия

- Лицензия Adobe Experience Platform.
- Лицензия Adobe Campaign Standard.
- Имя и ключ учетной записи [Учетная запись хранилища BLOB-объектов Azure](/azure/storage/blobs/create-data-lake-storage-account). Чтобы найти имя и ключ, см. раздел [Управление параметрами учетной записи хранения на портале Azure](/azure/storage/common/storage-account-manage).
- [Контейнер хранилища BLOB-объектов Azure](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Обзор кампании

Чтобы лучше понять, как можно использовать сегменты из Customer Insights в Adobe Experience Platform, давайте рассмотрим вымышленный пример кампании.

Предположим, ваша компания предлагает ежемесячную услугу по подписке для ваших клиентов в США. Вы хотите определить клиентов, чьи подписки должны быть продлены в течение следующих восьми дней, но подписка пока не продлена. Чтобы удержать этих клиентов, вы хотите отправить им рекламное предложение по электронной почте, используя Adobe Experience Platform.

В этом примере мы хотим запустить промоакцию по электронной почте один раз. В этой статье не рассматривается вариант многократного запуска промоакции.

## <a name="identify-your-target-audience"></a>Определите свою целевую аудиторию

В нашем сценарии мы предполагаем, что адреса электронной почты клиентов доступны в Customer Insights и их рекламные предпочтения были проанализированы для определения членов сегмента.

[Сегмент, который вы определили в Customer Insights](segments.md), называется **ChurnProneCustomers**, и вы планируете отправить этим клиентам рекламную рассылку по электронной почте.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Снимок экрана страницы сегментов с созданным сегментом ChurnProneCustomers.":::

Письмо с предложением, которое вы хотите отправить, будет содержать имя, фамилию и дату окончания подписки клиента. Он информирует клиентов о скидке, которую они получат, если продлят подписку до ее окончания.

## <a name="export-your-target-audience"></a>Экспортируйте свою целевую аудиторию

Мы настроим экспорт из Customer Insights в учетную запись хранилища BLOB-объектов Azure.

### <a name="set-up-connection-to-azure-blob-storage"></a>Настройка подключения к хранилищу BLOB-объектов Azure

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Перейти в раздел **Администрирование** > **Подключения**.

1. Выбирать **Добавить подключение** и выбрать **Хранилище BLOB-объектов Azure**.

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. Укажите, кто может использовать это подключение. По умолчанию это только администраторы. Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введите **Имя учетной записи**, **Ключ учетной записи** и **Контейнер** для вашей учетной записи хранилища BLOB-объектов, в которую вы хотите экспортировать сегмент.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Снимок экрана конфигурации учетной записи хранилища. ":::

1. Ознакомьтесь с положениями [Соответствие и конфиденциальность данных](connections.md#data-privacy-and-compliance) и выберите **Принимаю**.

1. Выберите **Сохранить**, чтобы завершить подключение.

### <a name="configure-an-export"></a>Настройка экспорта

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Выберите **Добавить экспорт**.

1. В поле **Подключение для экспорта** выберите подключение из раздела "Хранилище BLOB-объектов Azure". Свяжитесь с администратором, если подключение недоступно.

1. Введите имя экспорта.

1. Выберите сегмент, которые вы хотите экспортировать. В этом примере это **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Снимок экрана пользовательского интерфейса выбора сегмента с выбранным сегментом ChurnProneCustomers.":::

1. Выберите **Сохранить**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Убедитесь, что количество записей в экспортируемом сегменте находится в пределах допустимого лимита вашей лицензии Adobe Campaign Standard.

Экспортированные данные хранятся в настроенном вами контейнере хранилища BLOB-объектов Azure. Следующие пути к папкам автоматически создаются в вашем контейнере:

- Для исходных сущностей и сущностей, созданных системой:  

  *%ContainerName%/ CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- Файл *model.json* для экспортируемых сущностей находится на уровне *%ExportDestinationName%*.

  Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Определение модели данных опыта (XDM) в Adobe Experience Platform

Прежде чем экспортированные данные из Customer Insights можно будет использовать в Adobe Experience Platform, нам нужно определить схему модели данных взаимодействия и [настроить данные для профиля клиента в реальном времени](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Узнайте, [что такое XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) и изучите [основы построения схемы](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Импорт данных в Adobe Experience Platform

Импортируйте подготовленные данные аудитории из Customer Insights в Adobe Experience Platform.

1. [Создайте подключение к источнику хранилища BLOB-объектов Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).

1. [Настройте поток данных](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) для пакетного подключения к облачному хранилищу, чтобы импортировать выходные данные сегмента из Customer Insights в Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Создание аудитории в Adobe Campaign Standard

Чтобы отправить электронное письмо для этой кампании, мы будем использовать Adobe Campaign Standard.

1. [Создайте аудиторию](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) в Adobe Campaign Standard с использованием данных в Adobe Experience Platform.

1. [Используйте конструктор сегментов](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) в Adobe Campaign Standard для определения аудитории на основе данных в Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Создание и отправка сообщения электронной почты с помощью Adobe Campaign Standard

Создайте текст сообщения электронной почты, а затем [протестируйте и отправьте](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) ваше сообщение.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Образец сообщения электронной почты с предложением продления из Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
