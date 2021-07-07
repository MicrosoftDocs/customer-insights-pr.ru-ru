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
ms.openlocfilehash: 1045d0e373fd5ea8987684e51bd9a07b7b535ee3
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305540"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="aca97-103">Используйте сегменты Customer Insights в Adobe Experience Platform (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="aca97-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="aca97-104">Как пользователь аналитики аудитории в Dynamics 365 Customer Insights, возможно, вы создали сегменты, чтобы сделать свои маркетинговые кампании более эффективными за счет нацеливания на релевантную аудиторию.</span><span class="sxs-lookup"><span data-stu-id="aca97-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="aca97-105">Чтобы использовать сегмент из аналитики аудитории на платформе Adobe Experience и в таких приложениях, как Adobe Campaign Standard, вам необходимо выполнить несколько шагов, описанных в этой статье.</span><span class="sxs-lookup"><span data-stu-id="aca97-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Схема процесса изложена в этой статье.":::

## <a name="prerequisites"></a><span data-ttu-id="aca97-107">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="aca97-107">Prerequisites</span></span>

-   <span data-ttu-id="aca97-108">Лицензия Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="aca97-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="aca97-109">Лицензия Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="aca97-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="aca97-110">Лицензия Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="aca97-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="aca97-111">Учетная запись хранилища BLOB-объектов Azure</span><span class="sxs-lookup"><span data-stu-id="aca97-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="aca97-112">Обзор кампании</span><span class="sxs-lookup"><span data-stu-id="aca97-112">Campaign Overview</span></span>

<span data-ttu-id="aca97-113">Чтобы лучше понять, как можно использовать сегменты из аналитики аудитории на платформе Adobe Experience, давайте рассмотрим вымышленный пример кампании.</span><span class="sxs-lookup"><span data-stu-id="aca97-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="aca97-114">Предположим, ваша компания предлагает ежемесячную услугу по подписке для ваших клиентов в США.</span><span class="sxs-lookup"><span data-stu-id="aca97-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="aca97-115">Вы хотите определить клиентов, чьи подписки должны быть продлены в течение следующих восьми дней, но подписка пока не продлена.</span><span class="sxs-lookup"><span data-stu-id="aca97-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="aca97-116">Чтобы удержать этих клиентов, вы хотите отправить им рекламное предложение по электронной почте, используя Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="aca97-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="aca97-117">В этом примере мы хотим запустить промоакцию по электронной почте один раз.</span><span class="sxs-lookup"><span data-stu-id="aca97-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="aca97-118">В этой статье не рассматривается вариант многократного запуска промоакции.</span><span class="sxs-lookup"><span data-stu-id="aca97-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="aca97-119">Определите свою целевую аудиторию</span><span class="sxs-lookup"><span data-stu-id="aca97-119">Identify your target audience</span></span>

<span data-ttu-id="aca97-120">В нашем сценарии мы предполагаем, что адреса электронной почты клиентов доступны в аналитике аудитории, а их рекламные предпочтения были проанализированы для идентификации участников сегмента.</span><span class="sxs-lookup"><span data-stu-id="aca97-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="aca97-121">[Сегмент, который вы определили в аналитике аудитории,](segments.md) называется **ChurnProneCustomers** и вы планируете направлять этим клиентам рекламную рассылку по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="aca97-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Снимок экрана страницы сегментов с созданным сегментом ChurnProneCustomers.":::

<span data-ttu-id="aca97-123">Письмо с предложением, которое вы хотите отправить, будет содержать имя, фамилию и дату окончания подписки клиента.</span><span class="sxs-lookup"><span data-stu-id="aca97-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="aca97-124">Он информирует клиентов о скидке, которую они получат, если продлят подписку до ее окончания.</span><span class="sxs-lookup"><span data-stu-id="aca97-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="aca97-125">Экспортируйте свою целевую аудиторию</span><span class="sxs-lookup"><span data-stu-id="aca97-125">Export your target audience</span></span>

<span data-ttu-id="aca97-126">Определив свою целевую аудиторию, мы можем настроить экспорт из аналитики аудитории в учетную запись хранилища BLOB-объектов Azure.</span><span class="sxs-lookup"><span data-stu-id="aca97-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="aca97-127">Настройка подключения</span><span class="sxs-lookup"><span data-stu-id="aca97-127">Configure a connection</span></span>

1. <span data-ttu-id="aca97-128">Перейти в раздел **Администрирование** > **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="aca97-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="aca97-129">Выберите **Добавить подключение** и выберите **Хранилище BLOB-объектов Azure** для настройки подключения или выберите **Настройка** на плитке **Хранилище BLOB-объектов Azure**.</span><span class="sxs-lookup"><span data-stu-id="aca97-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile to configure the connection.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Плитка конфигурации для хранилища BLOB-объектов Azure."::: 

1. <span data-ttu-id="aca97-131">Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="aca97-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="aca97-132">Имя и тип подключения описывают это подключение.</span><span class="sxs-lookup"><span data-stu-id="aca97-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="aca97-133">Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.</span><span class="sxs-lookup"><span data-stu-id="aca97-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="aca97-134">Укажите, кто может использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="aca97-134">Choose who can use this connection.</span></span> <span data-ttu-id="aca97-135">Если вы не предпримете никаких действий, по умолчанию это будут администраторы.</span><span class="sxs-lookup"><span data-stu-id="aca97-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="aca97-136">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="aca97-136">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="aca97-137">Введите **Имя учетной записи**, **Ключ учетной записи** и **Контейнер** для вашей учетной записи хранилища BLOB-объектов, в которую вы хотите экспортировать сегмент.</span><span class="sxs-lookup"><span data-stu-id="aca97-137">Enter **Account name**, **Account key**, and **Container** for your Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Снимок экрана конфигурации учетной записи хранилища. "::: 
   
    - <span data-ttu-id="aca97-139">Чтобы узнать больше о том, как найти имя учетной записи хранилища BLOB-объектов и ключ учетной записи, см. раздел [Управление параметрами учетной записи хранения на портале Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="aca97-139">To learn more about how to find the Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="aca97-140">Чтобы узнать, как создать контейнер, см. раздел [Создание контейнера](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="aca97-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="aca97-141">Выберите **Сохранить**, чтобы завершить подключение.</span><span class="sxs-lookup"><span data-stu-id="aca97-141">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="aca97-142">Настройка экспорта</span><span class="sxs-lookup"><span data-stu-id="aca97-142">Configure an export</span></span>

<span data-ttu-id="aca97-143">Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа.</span><span class="sxs-lookup"><span data-stu-id="aca97-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="aca97-144">Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="aca97-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="aca97-145">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="aca97-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="aca97-146">Чтобы создать новый экспорт, выберите **Добавить экспорт**.</span><span class="sxs-lookup"><span data-stu-id="aca97-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="aca97-147">В поле **Подключение для экспорта** выберите подключение из раздела "Хранилище BLOB-объектов Azure".</span><span class="sxs-lookup"><span data-stu-id="aca97-147">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="aca97-148">Если вы не видите название этого раздела, значит, вам недоступны соединения этого типа.</span><span class="sxs-lookup"><span data-stu-id="aca97-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="aca97-149">Выберите сегмент, которые вы хотите экспортировать.</span><span class="sxs-lookup"><span data-stu-id="aca97-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="aca97-150">В этом примере это **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="aca97-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Снимок экрана пользовательского интерфейса выбора сегмента с выбранным сегментом ChurnProneCustomers.":::

1. <span data-ttu-id="aca97-152">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="aca97-152">Select **Save**.</span></span>

<span data-ttu-id="aca97-153">После сохранения места назначения экспорта вы найдете его в разделе **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="aca97-153">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="aca97-154">Вы можете сейчас [экспортировать сегмент по запросу](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="aca97-154">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="aca97-155">Экспорт также будет выполняться с каждым [запланированным обновлением](system.md).</span><span class="sxs-lookup"><span data-stu-id="aca97-155">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="aca97-156">Убедитесь, что количество записей в экспортируемом сегменте находится в пределах допустимого лимита вашей лицензии Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="aca97-156">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="aca97-157">Экспортированные данные хранятся в контейнере хранилища BLOB-объектов Azure, который вы настроили выше.</span><span class="sxs-lookup"><span data-stu-id="aca97-157">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="aca97-158">В вашем контейнере автоматически создан следующий путь к папке:</span><span class="sxs-lookup"><span data-stu-id="aca97-158">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="aca97-159">*%ContainerName%/ CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="aca97-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="aca97-160">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="aca97-160">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="aca97-161">Файл *model.json* для экспортируемых сущностей находится на уровне *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="aca97-161">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="aca97-162">Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="aca97-162">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="aca97-163">Определение модели данных о взаимодействиях (XDM) в Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="aca97-163">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="aca97-164">Чтобы использовать экспортированные данные из аналитики аудитории в рамках Adobe Experience Platform, нам необходимо определить схему модели данных о взаимодействиях и [настроить данные для профиля клиента в реальном времени](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="aca97-164">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="aca97-165">Узнайте, [что такое XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) и изучите [основы построения схемы](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="aca97-165">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="aca97-166">Импорт данных в Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="aca97-166">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="aca97-167">Теперь, когда все готово, нам нужно импортировать подготовленные данные аудитории из аналитики аудитории в Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="aca97-167">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="aca97-168">Сначала, [создайте подключение к источнику хранилища BLOB-объектов Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="aca97-168">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="aca97-169">После определения подключения к источнику [настройте поток данных](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) для пакетного подключения к облачному хранилищу для импорта выходных данных сегмента из аналитики аудитории в Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="aca97-169">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="aca97-170">Создайте аудиторию в Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="aca97-170">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="aca97-171">Чтобы отправить электронное письмо для этой кампании, мы будем использовать Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="aca97-171">To send the email for this campaign, we'll use Adobe Campaign Standard.</span></span> <span data-ttu-id="aca97-172">После импорта данных в Adobe Experience Platform нам необходимо [создать аудиторию](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) в Adobe Campaign Standard с использованием данных в Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="aca97-172">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>


<span data-ttu-id="aca97-173">Узнайте, как [использовать конструктор сегментов](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) в Adobe Campaign Standard, чтобы определить аудиторию на основе данных в Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="aca97-173">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="aca97-174">Создайте и отправьте электронное письмо с помощью Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="aca97-174">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="aca97-175">Создайте текст сообщения электронной почты, а затем [протестируйте и отправьте](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) ваше сообщение.</span><span class="sxs-lookup"><span data-stu-id="aca97-175">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Образец сообщения электронной почты с предложением о продлении от Adobe Campaign Standard.":::
