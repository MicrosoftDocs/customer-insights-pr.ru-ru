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
ms.openlocfilehash: 917ab9559416f3ee0ffd66e471e590e8da3faffc
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305402"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="9d8fe-103">Используйте сегменты Customer Insights в Adobe Campaign Standard (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="9d8fe-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="9d8fe-104">Как пользователь аналитики аудитории в Dynamics 365 Customer Insights, возможно, вы создали сегменты, чтобы сделать свои маркетинговые кампании более эффективными за счет нацеливания на релевантную аудиторию.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="9d8fe-105">Чтобы использовать сегмент из аналитики аудитории на платформе Adobe Experience и в таких приложениях, как Adobe Campaign Standard, вам необходимо выполнить несколько шагов, описанных в этой статье.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Схема процесса изложена в этой статье.":::

## <a name="prerequisites"></a><span data-ttu-id="9d8fe-107">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="9d8fe-107">Prerequisites</span></span>

-   <span data-ttu-id="9d8fe-108">Лицензия Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="9d8fe-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="9d8fe-109">Лицензия Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="9d8fe-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="9d8fe-110">Учетная запись хранилища BLOB-объектов Azure</span><span class="sxs-lookup"><span data-stu-id="9d8fe-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="9d8fe-111">Обзор кампании</span><span class="sxs-lookup"><span data-stu-id="9d8fe-111">Campaign overview</span></span>

<span data-ttu-id="9d8fe-112">Чтобы лучше понять, как можно использовать сегменты из аналитики аудитории на платформе Adobe Experience, давайте рассмотрим вымышленный пример кампании.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="9d8fe-113">Предположим, ваша компания предлагает ежемесячную услугу по подписке для ваших клиентов в США.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="9d8fe-114">Вы хотите определить клиентов, чьи подписки должны быть продлены в течение следующих восьми дней, но подписка пока не продлена.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="9d8fe-115">Чтобы удержать этих клиентов, вы хотите отправить им рекламное предложение по электронной почте, используя Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="9d8fe-116">В этом примере мы хотим запустить промоакцию по электронной почте один раз.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="9d8fe-117">В этой статье не рассматривается вариант многократного запуска промоакции.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="9d8fe-118">Однако аналитика аудитории и Adobe Campaign Standard можно также настроить для работы со сценарием повторяющейся кампании.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="9d8fe-119">Определите свою целевую аудиторию</span><span class="sxs-lookup"><span data-stu-id="9d8fe-119">Identify your target audience</span></span>

<span data-ttu-id="9d8fe-120">В нашем сценарии мы предполагаем, что адреса электронной почты клиентов доступны в аналитике аудитории, а их рекламные предпочтения были проанализированы для идентификации участников сегмента.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="9d8fe-121">[Сегмент, который вы определили в аналитике аудитории,](segments.md) называется **ChurnProneCustomers** и вы планируете направлять этим клиентам рекламную рассылку по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Снимок экрана страницы сегментов с созданным сегментом ChurnProneCustomers.":::

<span data-ttu-id="9d8fe-123">Письмо с предложением, которое вы хотите отправить, будет содержать имя, фамилию и дату окончания подписки клиента.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="9d8fe-124">Он информирует клиентов о скидке, которую они получат, если продлят подписку до ее окончания.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="9d8fe-125">Экспортируйте свою целевую аудиторию</span><span class="sxs-lookup"><span data-stu-id="9d8fe-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="9d8fe-126">Настройка подключения</span><span class="sxs-lookup"><span data-stu-id="9d8fe-126">Configure a connection</span></span>

<span data-ttu-id="9d8fe-127">Определив свою целевую аудиторию, мы можем настроить экспорт из аналитики аудитории в учетную запись хранилища BLOB-объектов Azure.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="9d8fe-128">В аналитике аудитории перейдите по ссылке **Администрирование** > **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="9d8fe-129">Выберите **Добавить подключение** и выберите **Adobe Campaign** для настройки подключения или выберите **Настройка** на плитке **Adobe Campaign**.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Плитка конфигурации для Adobe Campaign Standard.":::

1. <span data-ttu-id="9d8fe-131">Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="9d8fe-132">Имя и тип подключения описывают это подключение.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="9d8fe-133">Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="9d8fe-134">Укажите, кто может использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-134">Choose who can use this connection.</span></span> <span data-ttu-id="9d8fe-135">Если вы не предпримете никаких действий, по умолчанию это будут администраторы.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="9d8fe-136">Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="9d8fe-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="9d8fe-137">Введите **Имя учетной записи**, **Ключ учетной записи** и **Контейнер** вашей учетной записи хранилища BLOB-объектов Azure, в которую вы хотите экспортировать сегмент.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Снимок экрана конфигурации учетной записи хранилища. "::: 

   - <span data-ttu-id="9d8fe-139">Подробнее о том, как найти имя учетной записи хранилища BLOB-объектов Azure и ключ учетной записи, см. в разделе [Управление настройками учетной записи хранения на портале Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="9d8fe-139">To learn more about how to find the Azure Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="9d8fe-140">Чтобы узнать, как создать контейнер, см. раздел [Создание контейнера](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="9d8fe-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="9d8fe-141">Выберите **Сохранить**, чтобы завершить подключение.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="9d8fe-142">Настройка экспорта</span><span class="sxs-lookup"><span data-stu-id="9d8fe-142">Configure an export</span></span>

<span data-ttu-id="9d8fe-143">Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="9d8fe-144">Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="9d8fe-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="9d8fe-145">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9d8fe-146">Чтобы создать новый экспорт, выберите **Добавить экспорт**.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="9d8fe-147">В поле **Подключение для экспорта** выберите подключение из раздела Adobe Campaign.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="9d8fe-148">Если вы не видите название этого раздела, значит, вам недоступны соединения этого типа.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="9d8fe-149">Выберите сегмент, которые вы хотите экспортировать.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="9d8fe-150">В этом примере это **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Снимок экрана пользовательского интерфейса выбора сегмента с выбранным сегментом ChurnProneCustomers.":::

1. <span data-ttu-id="9d8fe-152">Выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-152">Select **Next**.</span></span>

1. <span data-ttu-id="9d8fe-153">Теперь сопоставим **Исходные** поля из сегмента аналитики аудитории с именами **Целевых** полей в схеме профиля Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Сопоставление полей для соединителя Adobe Campaign Standard.":::

   <span data-ttu-id="9d8fe-155">Если вы хотите добавить дополнительные атрибуты, выберите **Добавить атрибут**.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="9d8fe-156">Целевое имя может отличаться от имени исходного поля, но вы все равно можете сопоставить выходные данные сегмента из аналитики аудитории с Adobe Campaign Standard, если поля имеют разные имена в двух системах.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9d8fe-157">Адрес электронной почты используется в качестве поля идентификации, но вы можете использовать любой другой идентификатор из вашего профиля клиента аналитики аудитории для сопоставления данных с Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="9d8fe-158">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-158">Select **Save**.</span></span>

<span data-ttu-id="9d8fe-159">После сохранения места назначения экспорта вы найдете его в разделе **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="9d8fe-160">Вы можете сейчас [экспортировать сегмент по запросу](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="9d8fe-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="9d8fe-161">Экспорт также будет выполняться с каждым [запланированным обновлением](system.md).</span><span class="sxs-lookup"><span data-stu-id="9d8fe-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9d8fe-162">Убедитесь, что количество записей в экспортируемом сегменте находится в пределах допустимого лимита вашей лицензии Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="9d8fe-163">Экспортированные данные хранятся в контейнере хранилища BLOB-объектов Azure, который вы настроили выше.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-163">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="9d8fe-164">В вашем контейнере автоматически создан следующий путь к папке:</span><span class="sxs-lookup"><span data-stu-id="9d8fe-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="9d8fe-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp% .csv*</span><span class="sxs-lookup"><span data-stu-id="9d8fe-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="9d8fe-166">Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="9d8fe-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="9d8fe-167">Настройка Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="9d8fe-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="9d8fe-168">Когда сегмент из аналитики аудитории экспортируется, он содержит столбцы, выбранные вами при определении места назначения экспорта на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="9d8fe-169">Эти данные могут быть использованы для [создания профилей в Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="9d8fe-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="9d8fe-170">Чтобы использовать сегмент в Adobe Campaign Standard, нам необходимо расширить схему профиля в Adobe Campaign Standard, включив в нее два дополнительных поля.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="9d8fe-171">Подробнее о том, как [расширить ресурс профиля](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) новыми полями в Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="9d8fe-172">В нашем примере этими полями являются *название сегмента и дата сегмента (необязательно)*.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-172">In our example, these fields are *Segment Name and Segment Date (optional)*.</span></span>

<span data-ttu-id="9d8fe-173">Мы будем использовать эти поля для определения профилей в Adobe Campaign Standard, на которые мы хотим настроить таргетинг для этой кампании.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="9d8fe-174">Если в Adobe Campaign Standard нет других записей, кроме тех, которые вы собираетесь импортировать, вы можете пропустить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="9d8fe-175">Импортировать данные в Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="9d8fe-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="9d8fe-176">Теперь, когда все готово, нам нужно импортировать подготовленные данные аудитории из аналитики аудитории в Adobe Campaign Standard для создания профилей.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="9d8fe-177">Научитесь [импортировать профили в Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) используя бизнес-процесс.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="9d8fe-178">Рабочий процесс импорта на изображении ниже настроен для запуска каждые восемь часов и поиска экспортированных сегментов аналитики аудитории (CSV-файл в хранилище BLOB-объектов Azure).</span><span class="sxs-lookup"><span data-stu-id="9d8fe-178">The import workflow in the image below has been configured to run every eight hours and look for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="9d8fe-179">Бизнес-процесс извлекает содержимое CSV-файла в указанном порядке столбцов.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="9d8fe-180">Этот бизнес-процесс был создан для того, чтобы выполнять базовую обработку ошибок и обеспечивать наличие адреса электронной почты в каждой записи перед переносом данных в Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="9d8fe-181">Рабочий процесс также извлекает имя сегмента из имени файла перед загрузкой в данные профиля Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-181">The workflow also extracts the segment name from the filename before upserting into Adobe Campaign Standard profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Снимок экрана бизнес-процесса импорта в пользовательском интерфейсе Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="9d8fe-183">Получите аудиторию в Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="9d8fe-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="9d8fe-184">После импорта данных в Adobe Campaign Standard вы [может есоздать бизнес-процесс](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) и [запрос](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) клиентов на основе *Названия сегмента* и *Даты сегмента* для выбора профилей, которые были определены для нашего примера кампании.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="9d8fe-185">Создайте и отправьте электронное письмо с помощью Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="9d8fe-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="9d8fe-186">Создайте текст сообщения электронной почты, а затем [протестируйте и отправьте](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) ваше сообщение.</span><span class="sxs-lookup"><span data-stu-id="9d8fe-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Образец сообщения электронной почты с предложением о продлении от Adobe Campaign Standard.":::
