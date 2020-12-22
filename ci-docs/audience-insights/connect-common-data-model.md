---
title: Подключение данных Common Data Model к учетной записи Azure Data Lake
description: Работа с данными Common Data Model с помощью Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643474"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="0eda3-103">Подключение к папке Common Data Model с помощью учетной записи Azure Data Lake</span><span class="sxs-lookup"><span data-stu-id="0eda3-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="0eda3-104">В этой статье содержится информация о том, как принимать данные из папки Common Data Model с помощью вашей учетной записи Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="0eda3-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="0eda3-105">Важные замечания</span><span class="sxs-lookup"><span data-stu-id="0eda3-105">Important considerations</span></span>

- <span data-ttu-id="0eda3-106">Данные в Azure Data Lake должны соответствовать стандарту Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="0eda3-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="0eda3-107">Другие форматы в настоящее время не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="0eda3-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="0eda3-108">Прием данных поддерживает исключительно учетные записи хранения Azure Data Lake *Gen2*.</span><span class="sxs-lookup"><span data-stu-id="0eda3-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="0eda3-109">Вы не можете использовать учетные записи хранения Azure Data Lake Gen1 для приема данных.</span><span class="sxs-lookup"><span data-stu-id="0eda3-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="0eda3-110">Чтобы пройти аутентификацию с помощью субъекта-службы Azure, убедитесь, что она настроена в вашем клиенте.</span><span class="sxs-lookup"><span data-stu-id="0eda3-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="0eda3-111">Для получения дополнительной информации см. [Подключение аналитики аудитории к учетной записи Azure Data Lake Storage Gen2 с помощью субъекта-службы Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="0eda3-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="0eda3-112">Azure Data Lake, которое вы хотите подключить и из которого нужно принимать данные, должно находиться в том же регионе Azure, что и среда Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0eda3-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="0eda3-113">Подключения к папке Common Data Model из озера данных в другом регионе Azure не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="0eda3-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="0eda3-114">Чтобы узнать регион Azure среды, перейдите **Администрирование** > **Система** > **О системе** в аналитике аудитории.</span><span class="sxs-lookup"><span data-stu-id="0eda3-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="0eda3-115">Данные, хранящиеся в веб-службах, могут храниться в другом месте, отличном от того, где данные обрабатываются или хранятся в Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0eda3-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="0eda3-116"> Импортируя данные или подключаясь к данным, хранящимся в онлайн-сервисах, вы соглашаетесь с тем, что данные могут быть переданы и сохранены в Dynamics 365 Customer Insights.  [Подробнее см. в центре обеспечения безопасности Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="0eda3-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="0eda3-117">Подключение к папке Common Data Model</span><span class="sxs-lookup"><span data-stu-id="0eda3-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="0eda3-118">В аналитике аудитории перейдите **Данные** > **Источники данных**.</span><span class="sxs-lookup"><span data-stu-id="0eda3-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="0eda3-119">Выберите **Добавить источник данных**.</span><span class="sxs-lookup"><span data-stu-id="0eda3-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="0eda3-120">Выберите **Подключиться к папке Common Data Model**, введите **Имя** для источника данных и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0eda3-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span>

1. <span data-ttu-id="0eda3-121">Вы можете выбрать между использованием варианта на основе ресурсов и варианта на основе подписки для аутентификации.</span><span class="sxs-lookup"><span data-stu-id="0eda3-121">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="0eda3-122">Для получения дополнительной информации см. [Подключение аналитики аудитории к учетной записи Azure Data Lake Storage Gen2 с помощью субъекта-службы Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="0eda3-122">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="0eda3-123">Введите сведения **Контейнер** и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0eda3-123">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0eda3-124">![Диалоговое окно для ввода сведений о соединении для Azure Data Lake](media/enter-new-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="0eda3-124">![Dialog box to enter connection details for Azure Data Lake](media/enter-new-storage-details.png)</span></span>

1. <span data-ttu-id="0eda3-125">В диалоговом окне **Папка Common Data Model** выберите файл model.json, из которого нужно импортировать данные, и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0eda3-125">In the **Select a Common Data Model folder** dialog, select the model.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="0eda3-126">Любой файл model.json, связанный с другим источником данных в среде, не будет отображаться в списке.</span><span class="sxs-lookup"><span data-stu-id="0eda3-126">Any model.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="0eda3-127">Вы получите список доступных сущностей в выбранном файле model.json.</span><span class="sxs-lookup"><span data-stu-id="0eda3-127">You'll get a list of available entities in the selected model.json file.</span></span> <span data-ttu-id="0eda3-128">Вы можете просмотреть и выбрать из списка доступных сущностей и выбрать **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0eda3-128">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="0eda3-129">Все выбранные сущности будут загружены из нового источника данных.</span><span class="sxs-lookup"><span data-stu-id="0eda3-129">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0eda3-130">![Диалоговое окно со списком сущностей из файла model.json](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="0eda3-130">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="0eda3-131">Укажите, для каких сущностей вы хотите включить профилирование данных и выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0eda3-131">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="0eda3-132">Профилирование данных включает аналитику и другие возможности.</span><span class="sxs-lookup"><span data-stu-id="0eda3-132">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="0eda3-133">Вы можете выбрать всю сущность, которая выбирает все атрибуты из сущности, или выбрать определенные атрибуты по своему выбору.</span><span class="sxs-lookup"><span data-stu-id="0eda3-133">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="0eda3-134">По умолчанию ни одна сущность не включена для профилирования данных.</span><span class="sxs-lookup"><span data-stu-id="0eda3-134">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0eda3-135">![Диалоговое окно с профилированием данных](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="0eda3-135">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="0eda3-136">После сохранения вашего выбора открывается страница **Источники данных**.</span><span class="sxs-lookup"><span data-stu-id="0eda3-136">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="0eda3-137">Теперь вы должны увидеть соединение с папкой Common Data Model как с источником данных.</span><span class="sxs-lookup"><span data-stu-id="0eda3-137">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="0eda3-138">Файл model.json может быть связан только с одним источником данных в той же среде.</span><span class="sxs-lookup"><span data-stu-id="0eda3-138">A model.json file can only associate with one data source in the same environment.</span></span> <span data-ttu-id="0eda3-139">Однако один и тот же файл model.json можно использовать для источников данных в нескольких средах.</span><span class="sxs-lookup"><span data-stu-id="0eda3-139">However, the same model.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="0eda3-140">Изменение источника данных папки Common Data Model</span><span class="sxs-lookup"><span data-stu-id="0eda3-140">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="0eda3-141">Вы можете обновить ключ доступа для учетной записи хранения, содержащей папку Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="0eda3-141">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="0eda3-142">Вы также можете изменить файл model.json.</span><span class="sxs-lookup"><span data-stu-id="0eda3-142">You may also change the model.json file.</span></span> <span data-ttu-id="0eda3-143">Чтобы подключиться к другому контейнеру из своей учетной записи хранилища или изменить имя учетной записи, [создайте новое соединение источника данных](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="0eda3-143">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="0eda3-144">В аналитике аудитории перейдите **Данные** > **Источники данных**.</span><span class="sxs-lookup"><span data-stu-id="0eda3-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="0eda3-145">Рядом с источником данных, который вы хотите обновить, выберите многоточие.</span><span class="sxs-lookup"><span data-stu-id="0eda3-145">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="0eda3-146">Выберите вариант **Изменить** из списка.</span><span class="sxs-lookup"><span data-stu-id="0eda3-146">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="0eda3-147">При желании обновите **Ключ доступа** и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0eda3-147">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Диалог для редактирования и обновления ключа доступа для существующего источника данных](media/edit-access-key.png)

5. <span data-ttu-id="0eda3-149">При желании вы можете выполнить обновление из подключения ключа учетной записи на подключение на основе ресурса или подписки.</span><span class="sxs-lookup"><span data-stu-id="0eda3-149">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="0eda3-150">Для получения дополнительной информации см. [Подключение аналитики аудитории к учетной записи Azure Data Lake Storage Gen2 с помощью субъекта-службы Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="0eda3-150">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="0eda3-151">Невозможно изменить сведения **Контейнер** при обновлении соединения.</span><span class="sxs-lookup"><span data-stu-id="0eda3-151">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0eda3-152">![Диалоговое окно для ввода сведений о соединении для Azure Data Lake](media/enter-existing-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="0eda3-152">![Dialog box to enter connection details for Azure Data Lake](media/enter-existing-storage-details.png)</span></span>

6. <span data-ttu-id="0eda3-153">При желании выберите другой файл model.json с другим набором сущностей из контейнера.</span><span class="sxs-lookup"><span data-stu-id="0eda3-153">Optionally, choose a different model.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="0eda3-154">При желании вы можете выбрать дополнительные сущности для приема.</span><span class="sxs-lookup"><span data-stu-id="0eda3-154">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="0eda3-155">Вы также можете удалить любые уже выбранные сущности, если нет никаких зависимостей.</span><span class="sxs-lookup"><span data-stu-id="0eda3-155">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="0eda3-156">Если существуют зависимости от существующего файла model.json и набора сущностей, вы увидите сообщение об ошибке и не сможете выбрать другой файл model.json.</span><span class="sxs-lookup"><span data-stu-id="0eda3-156">If there are dependencies on the existing model.json file and the set of entities, you'll see an error message and can't select a different model.json file.</span></span> <span data-ttu-id="0eda3-157">Удалите эти зависимости перед изменением файла model.json или создайте новый источник данных с файлом model.json, который вы хотите использовать, чтобы избежать удаления зависимостей.</span><span class="sxs-lookup"><span data-stu-id="0eda3-157">Remove those dependencies before changing the model.json file or create a new data source with the model.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="0eda3-158">При желании вы можете выбрать дополнительные атрибуты или сущности, чтобы включить профилирование данных или отключить уже выбранные.</span><span class="sxs-lookup"><span data-stu-id="0eda3-158">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   
