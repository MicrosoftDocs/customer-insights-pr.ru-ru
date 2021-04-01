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
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="1cc0b-103">Используйте сегменты Customer Insights в Adobe Campaign Standard (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="1cc0b-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="1cc0b-104">Как пользователь аналитики аудитории для Dynamics 365 Customer Insights, возможно, вы создали сегменты, чтобы сделать свои маркетинговые кампании более эффективными за счет настройки таргетинга на нужные аудитории.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="1cc0b-105">Чтобы использовать сегмент из аналитики аудитории на платформе Adobe Experience и в таких приложениях, как Adobe Campaign Standard, вам необходимо выполнить несколько шагов, описанных в этой статье.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Схема процесса изложена в этой статье.":::

## <a name="prerequisites"></a><span data-ttu-id="1cc0b-107">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="1cc0b-107">Prerequisites</span></span>

-   <span data-ttu-id="1cc0b-108">Лицензия Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="1cc0b-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="1cc0b-109">Лицензия Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1cc0b-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="1cc0b-110">Учетная запись хранилища BLOB-объектов Azure</span><span class="sxs-lookup"><span data-stu-id="1cc0b-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="1cc0b-111">Обзор кампании</span><span class="sxs-lookup"><span data-stu-id="1cc0b-111">Campaign Overview</span></span>

<span data-ttu-id="1cc0b-112">Чтобы лучше понять, как можно использовать сегменты из аналитики аудитории на платформе Adobe Experience, давайте рассмотрим вымышленный пример кампании.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="1cc0b-113">Предположим, ваша компания предлагает ежемесячную услугу по подписке для ваших клиентов в США.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="1cc0b-114">Вы хотите определить клиентов, чьи подписки должны быть продлены в течение следующих восьми дней, но подписка пока не продлена.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="1cc0b-115">Чтобы удержать этих клиентов, вы хотите отправить им рекламное предложение по электронной почте, используя Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="1cc0b-116">В этом примере мы хотим запустить промоакцию по электронной почте один раз.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="1cc0b-117">В этой статье не рассматривается вариант многократного запуска промоакции.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="1cc0b-118">Однако аналитика аудитории и Adobe Campaign Standard можно также настроить для работы со сценарием повторяющейся кампании.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="1cc0b-119">Определите свою целевую аудиторию</span><span class="sxs-lookup"><span data-stu-id="1cc0b-119">Identify your target audience</span></span>

<span data-ttu-id="1cc0b-120">В нашем сценарии мы предполагаем, что адреса электронной почты клиентов доступны в аналитике аудитории, а их рекламные предпочтения были проанализированы для идентификации участников сегмента.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="1cc0b-121">[Сегмент, который вы определили в аналитике аудитории,](segments.md) называется **ChurnProneCustomers** и вы планируете направлять этим клиентам рекламную рассылку по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Снимок экрана страницы сегментов с созданным сегментом ChurnProneCustomers.":::

<span data-ttu-id="1cc0b-123">Письмо с предложением, которое вы хотите отправить, будет содержать имя, фамилию и дату окончания подписки клиента.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="1cc0b-124">Он информирует клиентов о скидке, которую они получат, если продлят подписку до ее окончания.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="1cc0b-125">Экспортируйте свою целевую аудиторию</span><span class="sxs-lookup"><span data-stu-id="1cc0b-125">Export your target audience</span></span>

<span data-ttu-id="1cc0b-126">Определив свою целевую аудиторию, мы можем настроить экспорт из аналитики аудитории в учетную запись хранилища BLOB-объектов Azure.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="1cc0b-127">В аналитике аудитории перейдите **Администрирование** > **Экспорт пунктов назначения**.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="1cc0b-128">На плитке **Adobe Campaign** выберите **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Плитка конфигурации для Adobe Campaign Standard.":::

1. <span data-ttu-id="1cc0b-130">Укажите **Отображаемое имя** для этого нового пункта назначения экспорта, а затем введите **Имя учетной записи**, **Ключ учетной записи**, и **Контейнер** для учетной записи хранилища BLOB-объектов Azure, в которую вы хотите экспортировать сегмент.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Снимок экрана конфигурации учетной записи хранилища. "::: 

   - <span data-ttu-id="1cc0b-132">Подробнее о том, как найти имя учетной записи хранилища BLOB-объектов Azure и ключ учетной записи, см. в разделе [Управление настройками учетной записи хранения на портале Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="1cc0b-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="1cc0b-133">Чтобы узнать, как создать контейнер, см. раздел [Создание контейнера](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="1cc0b-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="1cc0b-134">Выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-134">Select **Next**.</span></span>

1. <span data-ttu-id="1cc0b-135">Выберите сегмент, которые вы хотите экспортировать.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="1cc0b-136">В этом примере это **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Снимок экрана пользовательского интерфейса выбора сегмента с выбранным сегментом ChurnProneCustomers.":::

1. <span data-ttu-id="1cc0b-138">Выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-138">Select **Next**.</span></span>

1. <span data-ttu-id="1cc0b-139">Теперь сопоставим **Исходные** поля из сегмента аналитики аудитории с именами **Целевых** полей в схеме профиля Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Сопоставление полей для соединителя Adobe Campaign Standard.":::

   <span data-ttu-id="1cc0b-141">Если вы хотите добавить дополнительные атрибуты, выберите **Добавить атрибут**.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="1cc0b-142">Целевое имя может отличаться от имени исходного поля, но вы все равно можете сопоставить выходные данные сегмента из аналитики аудитории с Adobe Campaign Standard, если поля имеют разные имена в двух системах.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1cc0b-143">Адрес электронной почты используется в качестве поля идентификации, но вы можете использовать любой другой идентификатор из вашего профиля клиента аналитики аудитории для сопоставления данных с Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="1cc0b-144">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-144">Select **Save**.</span></span>

<span data-ttu-id="1cc0b-145">После сохранения места назначения экспорта вы найдете его по следующему пути: **Администратор** > **Экспорты** > **Мои пункты назначения экспорта**.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Снимок экрана со списком экспортов и выделенным примером сегмента.":::

<span data-ttu-id="1cc0b-147">Вы можете сейчас [экспортировать сегмент по запросу](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1cc0b-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="1cc0b-148">Экспорт также будет выполняться с каждым [запланированным обновлением](system.md).</span><span class="sxs-lookup"><span data-stu-id="1cc0b-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1cc0b-149">Убедитесь, что количество записей в экспортируемом сегменте находится в пределах допустимого лимита вашей лицензии Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="1cc0b-150">Экспортированные данные хранятся в контейнере хранилища BLOB-объектов Azure, который вы настроили выше.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="1cc0b-151">В вашем контейнере автоматически создан следующий путь к папке:</span><span class="sxs-lookup"><span data-stu-id="1cc0b-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="1cc0b-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp% .csv*</span><span class="sxs-lookup"><span data-stu-id="1cc0b-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="1cc0b-153">Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="1cc0b-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="1cc0b-154">Настройка Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1cc0b-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="1cc0b-155">Когда сегмент из аналитики аудитории экспортируется, он содержит столбцы, выбранные вами при определении места назначения экспорта на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="1cc0b-156">Эти данные могут быть использованы для [создания профилей в Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="1cc0b-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="1cc0b-157">Чтобы использовать сегмент в Adobe Campaign Standard, нам необходимо расширить схему профиля в Adobe Campaign Standard, включив в нее два дополнительных поля.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="1cc0b-158">Подробнее о том, как [расширить ресурс профиля](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) новыми полями в Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="1cc0b-159">В нашем примере этими полями являются *название сегмента и дата сегмента (необязательно).*</span><span class="sxs-lookup"><span data-stu-id="1cc0b-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="1cc0b-160">Мы будем использовать эти поля для определения профилей в Adobe Campaign Standard, на которые мы хотим настроить таргетинг для этой кампании.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="1cc0b-161">Если в Adobe Campaign Standard нет других записей, кроме тех, которые вы собираетесь импортировать, вы можете пропустить этот шаг.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="1cc0b-162">Импортировать данные в Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1cc0b-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="1cc0b-163">Теперь, когда все готово, нам нужно импортировать подготовленные данные аудитории из аналитики аудитории в Adobe Campaign Standard для создания профилей.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="1cc0b-164">Научитесь [импортировать профили в Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) используя бизнес-процесс.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="1cc0b-165">Бизнес-процесс импорта на изображении ниже настроен на запуск каждые 8 часов. Он ищет экспортированные сегменты аналитики аудитории (CSV-файл в хранилище BLOB-объектов Azure).</span><span class="sxs-lookup"><span data-stu-id="1cc0b-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="1cc0b-166">Бизнес-процесс извлекает содержимое CSV-файла в указанном порядке столбцов.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="1cc0b-167">Этот бизнес-процесс был создан для того, чтобы выполнять базовую обработку ошибок и обеспечивать наличие адреса электронной почты в каждой записи перед переносом данных в Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="1cc0b-168">Бизнес-процесс также извлекает имя сегмента из имени файла перед его загрузкой в данные профиля ACS.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Снимок экрана бизнес-процесса импорта в пользовательском интерфейсе Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="1cc0b-170">Получите аудиторию в Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1cc0b-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="1cc0b-171">После импорта данных в Adobe Campaign Standard вы [может есоздать бизнес-процесс](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) и [запрос](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) клиентов на основе *Названия сегмента* и *Даты сегмента* для выбора профилей, которые были определены для нашего примера кампании.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="1cc0b-172">Создайте и отправьте электронное письмо с помощью Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1cc0b-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="1cc0b-173">Создайте текст сообщения электронной почты, а затем [протестируйте и отправьте](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) ваше сообщение.</span><span class="sxs-lookup"><span data-stu-id="1cc0b-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Образец сообщения электронной почты с предложением о продлении от Adobe Campaign Standard.":::