---
title: Подключение к объектам в управляемом озере Common Data Service
description: Импортируйте данные из управляемого Data Lake Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596975"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="d6b80-103">Подключение к данным в озере данных, управляемом Common Data Service</span><span class="sxs-lookup"><span data-stu-id="d6b80-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="d6b80-104">В этой статье представлена информация о том, как существующие клиенты Dynamics 365 могут быстро подключиться к своим аналитическим сущностям в управляемом озере Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d6b80-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="d6b80-105">Вы должны быть администратором организации Common Data Service, чтобы продолжить и просмотреть список сущностей, доступных в управляемом озере.</span><span class="sxs-lookup"><span data-stu-id="d6b80-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="d6b80-106">Важные замечания</span><span class="sxs-lookup"><span data-stu-id="d6b80-106">Important considerations</span></span>

<span data-ttu-id="d6b80-107">Данные, хранящиеся в онлайн-сервисах, например Azure Data Lake Storage, могут храниться в другом месте, отличном от места, где данные обрабатываются или хранятся в Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d6b80-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="d6b80-108"> Импортируя данные или подключаясь к данным, хранящимся в онлайн-сервисах, вы соглашаетесь с тем, что данные могут быть переданы и сохранены в Dynamics 365 Customer Insights.  [Подробнее см. в центре обеспечения безопасности Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="d6b80-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="d6b80-109">Подключение к озеру, управляемому Common Data Service</span><span class="sxs-lookup"><span data-stu-id="d6b80-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="d6b80-110">В аналитике аудитории перейдите **Данные** > **Источники данных**.</span><span class="sxs-lookup"><span data-stu-id="d6b80-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="d6b80-111">Выберите **Добавить источник данных**.</span><span class="sxs-lookup"><span data-stu-id="d6b80-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="d6b80-112">Выберите **Подключиться к Common Data Service** и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d6b80-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="d6b80-113">Введите **Имя** для источника данных, затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d6b80-113">Enter a **Name** for the data source and select **Next**.</span></span> <span data-ttu-id="d6b80-114">Рекомендации по названию:</span><span class="sxs-lookup"><span data-stu-id="d6b80-114">Name guidelines:</span></span> 
   - <span data-ttu-id="d6b80-115">Начните с буквы.</span><span class="sxs-lookup"><span data-stu-id="d6b80-115">Start with a letter.</span></span>
   - <span data-ttu-id="d6b80-116">Используйте только буквы и цифры.</span><span class="sxs-lookup"><span data-stu-id="d6b80-116">Use letters and numbers only.</span></span> <span data-ttu-id="d6b80-117">Использовать специальные символы и пробелы не разрешается.</span><span class="sxs-lookup"><span data-stu-id="d6b80-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="d6b80-118">Используйте от 3 до 64 символов.</span><span class="sxs-lookup"><span data-stu-id="d6b80-118">Use between 3 and 64 characters.</span></span>

5. <span data-ttu-id="d6b80-119">Укажите **Адрес сервера** для вашей организации Common Data Service и выберите **Войти**.</span><span class="sxs-lookup"><span data-stu-id="d6b80-119">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d6b80-120">![Диалоговое окно для ввода адреса сервера Common Data Service](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="d6b80-120">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="d6b80-121">Выберите сущности, которые нужно принимать, в доступном списке.</span><span class="sxs-lookup"><span data-stu-id="d6b80-121">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="d6b80-122">Если некоторые сущности уже выбраны, они могут использоваться другими приложениями Dynamics 365 (например, Dynamics 365 Sales Insights или Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="d6b80-122">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="d6b80-123">Вы не можете изменить выбор.</span><span class="sxs-lookup"><span data-stu-id="d6b80-123">You can't change the selection.</span></span> <span data-ttu-id="d6b80-124">Эти сущности будут доступны после создания источника данных.</span><span class="sxs-lookup"><span data-stu-id="d6b80-124">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d6b80-125">![Диалоговое окно со списком сущностей в организации Common Data Service](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="d6b80-125">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="d6b80-126">Сохраните свой выбор, чтобы начать синхронизацию выбранных сущностей с озером, управляемым Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d6b80-126">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="d6b80-127">Вы найдете недавно добавленное соединение на странице **Источники данных**.</span><span class="sxs-lookup"><span data-stu-id="d6b80-127">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="d6b80-128">Оно будет поставлено в очередь для обновления и покажет количество сущностей равным 0, пока все сущности не будут синхронизированы.</span><span class="sxs-lookup"><span data-stu-id="d6b80-128">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="d6b80-129">Только один источник данных среды может одновременно использовать это и то же управляемое озеро Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d6b80-129">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="d6b80-130">Изменение источника данных озера, управляемого Common Data Service</span><span class="sxs-lookup"><span data-stu-id="d6b80-130">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="d6b80-131">Вы редактируете выбор сущности только после создания источника данных.</span><span class="sxs-lookup"><span data-stu-id="d6b80-131">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="d6b80-132">Например, если дополнительные сущности были добавлены в Common Data Service и вы тоже хотите их импортировать.</span><span class="sxs-lookup"><span data-stu-id="d6b80-132">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="d6b80-133">Чтобы подключиться к другому Common Data Service, [создайте новый источник данных](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="d6b80-133">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="d6b80-134">В аналитике аудитории перейдите **Данные** > **Источники данных**.</span><span class="sxs-lookup"><span data-stu-id="d6b80-134">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="d6b80-135">Рядом с источником данных, который вы хотите обновить, выберите многоточие.</span><span class="sxs-lookup"><span data-stu-id="d6b80-135">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="d6b80-136">Выберите вариант **Изменить** из списка.</span><span class="sxs-lookup"><span data-stu-id="d6b80-136">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="d6b80-137">Выберите дополнительные сущности из доступного списка сущностей и выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d6b80-137">Select additional entities from the available list of entities and select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]