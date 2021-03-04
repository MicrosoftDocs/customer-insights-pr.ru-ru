---
title: Создание сред и управление ими
description: Узнайте, как зарегистрироваться для службы и как управлять средами.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 744f0bcbf5d2700363180f44e38d6dee9bf5df63
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270128"
---
# <a name="manage-environments"></a><span data-ttu-id="38460-103">Управление средами</span><span class="sxs-lookup"><span data-stu-id="38460-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="38460-104">В этой статье объясняется, как создать новую организацию и как подготовить среду.</span><span class="sxs-lookup"><span data-stu-id="38460-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="38460-105">Зарегистрируйтесь и создайте организацию</span><span class="sxs-lookup"><span data-stu-id="38460-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="38460-106">Перейдите на веб-сайт [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="38460-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="38460-107">Выберите **Приступая к работе**.</span><span class="sxs-lookup"><span data-stu-id="38460-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="38460-108">Выберите предпочитаемый сценарий регистрации и выберите соответствующую ссылку.</span><span class="sxs-lookup"><span data-stu-id="38460-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="38460-109">Примите условия и выберите **Продолжить**, чтобы начать создание организации.</span><span class="sxs-lookup"><span data-stu-id="38460-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="38460-110">После создания среды вы будете перенаправлены в [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="38460-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="38460-111">Используйте демонстрационную среду, чтобы изучить приложение, или создайте новую среду, следуя инструкциям в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="38460-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="38460-112">После указания параметров среды выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="38460-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="38460-113">Вы войдете в систему после успешного создания среды.</span><span class="sxs-lookup"><span data-stu-id="38460-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="38460-114">Создание среды в существующей организации</span><span class="sxs-lookup"><span data-stu-id="38460-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="38460-115">Существует два способа для создания новой среды.</span><span class="sxs-lookup"><span data-stu-id="38460-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="38460-116">Вы можете указать совершенно новую конфигурацию или скопировать некоторые параметры конфигурации из существующей среды.</span><span class="sxs-lookup"><span data-stu-id="38460-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="38460-117">Чтобы создать среду:</span><span class="sxs-lookup"><span data-stu-id="38460-117">To create an environment:</span></span>

1. <span data-ttu-id="38460-118">Выберите **Среда** в заголовке приложения.</span><span class="sxs-lookup"><span data-stu-id="38460-118">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="38460-119">Выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="38460-119">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="38460-120">![Параметры среды](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="38460-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="38460-121">В диалоге **Создание новой среды** выберите **Создать среду**.</span><span class="sxs-lookup"><span data-stu-id="38460-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="38460-122">Если вы хотите [копировать данные из текущей среды](#additional-considerations-for-copy-configuration-preview), выберите **Копировать из существующей среды**.</span><span class="sxs-lookup"><span data-stu-id="38460-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="38460-123">Вы увидите список всех доступных сред в вашей организации, откуда вы можете копировать данные.</span><span class="sxs-lookup"><span data-stu-id="38460-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="38460-124">Укажите следующие данные:</span><span class="sxs-lookup"><span data-stu-id="38460-124">Provide the following details:</span></span>
   - <span data-ttu-id="38460-125">**Имя**: имя этой среды.</span><span class="sxs-lookup"><span data-stu-id="38460-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="38460-126">Это поле уже заполнено, если вы скопировали существующую среду, но вы можете изменить его.</span><span class="sxs-lookup"><span data-stu-id="38460-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="38460-127">**Регион**: регион, в котором служба развернута и размещена.</span><span class="sxs-lookup"><span data-stu-id="38460-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="38460-128">**Тип**: выберите, хотите ли вы создать рабочую среду или среду песочницы.</span><span class="sxs-lookup"><span data-stu-id="38460-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="38460-129">По желанию можно выбрать **Дополнительные параметры**:</span><span class="sxs-lookup"><span data-stu-id="38460-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="38460-130">**Сохранить все данные в**: указывает, где вы хотите сохранить выходные данные, сгенерированные в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="38460-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="38460-131">Предусмотрено два варианта: **Хранилище Customer Insights** (Azure Data Lake, управляемое рабочей группой Customer Insights) и **Azure Data Lake Storage 2-го поколения** (ваше собственное хранилище Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="38460-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="38460-132">По умолчанию выбран вариант хранилища Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="38460-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="38460-133">Сохраняя данные в хранилище Azure Data Lake Storage, вы даете согласие на передачу данных в регион, соответствующий учетной записи этой службы хранилища Azure, который может отличаться от региона, где хранятся данные Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="38460-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="38460-134">Подробнее можно узнать в центре управления безопасностью Microsoft.</span><span class="sxs-lookup"><span data-stu-id="38460-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="38460-135">В настоящее время принятые сущности всегда хранятся в Data Lake, управляемом Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="38460-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="38460-136">Мы поддерживаем только учетные записи хранения Azure Data Lake Gen2 из того же региона Azure, который вы выбрали при создании среды.</span><span class="sxs-lookup"><span data-stu-id="38460-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="38460-137">Мы поддерживаем только учетные записи хранилищ с поддержкой иерархического пространства имен (HNS) Azure Data Lake 2-го поколения.</span><span class="sxs-lookup"><span data-stu-id="38460-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="38460-138">Для варианта Azure Data Lake Storage Gen2 вы можете выбрать между использованием варианта на основе ресурсов и варианта на основе подписки для аутентификации.</span><span class="sxs-lookup"><span data-stu-id="38460-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="38460-139">Для получения дополнительной информации см. [Подключение аналитики аудитории к учетной записи Azure Data Lake Storage Gen2 с помощью субъекта-службы Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="38460-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="38460-140">Имя **Контейнер** не может быть изменено и будет "customerinsights".</span><span class="sxs-lookup"><span data-stu-id="38460-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="38460-141">Если вы хотите использовать [прогнозы](predictions.md) или настроить совместное использование данных с приложениями и решениями на основе Microsoft Dataverse, укажите URL среды Microsoft Dataverse в **Настройка передачи данных в Microsoft Dataverse и включение дополнительных функций**.</span><span class="sxs-lookup"><span data-stu-id="38460-141">If you want to use [predictions](predictions.md) or configure data sharing with applications and solutions based on Microsoft Dataverse, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="38460-142">Выберите **Включить обмен данными**, чтобы поделиться выходными данными Customer Insights с Microsoft Dataverse Managed Data Lake.</span><span class="sxs-lookup"><span data-stu-id="38460-142">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="38460-143">Обмен данными с Microsoft Dataverse Managed Data Lake в настоящее время не поддерживается, если вы сохраняете все данные в свои собственные Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="38460-143">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="38460-144">[Прогноз отсутствующих значений в сущности](predictions.md) в настоящее время не поддерживается, если вы включаете обмен данными с Microsoft Dataverse Managed Data Lake.</span><span class="sxs-lookup"><span data-stu-id="38460-144">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="38460-145">![Параметры конфигурации для включения обмена данными с Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="38460-145">![Configuration options to enable data sharing with Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="38460-146">Когда вы запускаете процессы, такие как прием данных или создание сегментов, соответствующие папки будут созданы в учетной записи хранения, которую вы указали выше.</span><span class="sxs-lookup"><span data-stu-id="38460-146">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="38460-147">Файлы данных и файлы model.json будут созданы и добавлены в соответствующие вложенные папки в зависимости от выполняемого вами процесса.</span><span class="sxs-lookup"><span data-stu-id="38460-147">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="38460-148">Если вы создаете несколько сред Customer Insights и выбираете сохранение выходных объектов из этих сред в своей учетной записи хранения, отдельные папки будут созданы для каждой среды с помощью ci_<environmentid> в контейнере.</span><span class="sxs-lookup"><span data-stu-id="38460-148">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="38460-149">Дополнительные рекомендации по копированию конфигурации (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="38460-149">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="38460-150">Копируются следующие параметры конфигурации:</span><span class="sxs-lookup"><span data-stu-id="38460-150">The following configuration settings are copied:</span></span>

- <span data-ttu-id="38460-151">Конфигурации функции</span><span class="sxs-lookup"><span data-stu-id="38460-151">Feature configurations</span></span>
- <span data-ttu-id="38460-152">Полученные/импортированные источники данных</span><span class="sxs-lookup"><span data-stu-id="38460-152">Ingested/imported data sources</span></span>
- <span data-ttu-id="38460-153">Конфигурация унификации данных (сопоставления/соответствия/слияния)</span><span class="sxs-lookup"><span data-stu-id="38460-153">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="38460-154">Сегменты</span><span class="sxs-lookup"><span data-stu-id="38460-154">Segments</span></span>
- <span data-ttu-id="38460-155">Мер</span><span class="sxs-lookup"><span data-stu-id="38460-155">Measures</span></span>
- <span data-ttu-id="38460-156">Отношения</span><span class="sxs-lookup"><span data-stu-id="38460-156">Relationships</span></span>
- <span data-ttu-id="38460-157">Действия</span><span class="sxs-lookup"><span data-stu-id="38460-157">Activities</span></span>
- <span data-ttu-id="38460-158">Индекс поиска и фильтра</span><span class="sxs-lookup"><span data-stu-id="38460-158">Search & filter Index</span></span>
- <span data-ttu-id="38460-159">Пункты назначения экспорта</span><span class="sxs-lookup"><span data-stu-id="38460-159">Export destinations</span></span>
- <span data-ttu-id="38460-160">Запланированное обновление</span><span class="sxs-lookup"><span data-stu-id="38460-160">Scheduled refresh</span></span>
- <span data-ttu-id="38460-161">Обогащение</span><span class="sxs-lookup"><span data-stu-id="38460-161">Enrichments</span></span>
- <span data-ttu-id="38460-162">Управление моделями</span><span class="sxs-lookup"><span data-stu-id="38460-162">Model management</span></span>
- <span data-ttu-id="38460-163">Назначения ролей</span><span class="sxs-lookup"><span data-stu-id="38460-163">Role assignments</span></span>

<span data-ttu-id="38460-164">Следующие параметры *не* копируются:</span><span class="sxs-lookup"><span data-stu-id="38460-164">The following settings are *not* copied:</span></span>

- <span data-ttu-id="38460-165">Профили клиентов.</span><span class="sxs-lookup"><span data-stu-id="38460-165">Customer profiles.</span></span>
- <span data-ttu-id="38460-166">Учетные данные источника данных.</span><span class="sxs-lookup"><span data-stu-id="38460-166">Data source credentials.</span></span> <span data-ttu-id="38460-167">Вам нужно будет предоставить учетные данные для каждого источник данных и обновить источники данных вручную.</span><span class="sxs-lookup"><span data-stu-id="38460-167">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="38460-168">Источники данных из папки Common Data Model и озера, управляемого Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="38460-168">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="38460-169">Вам нужно будет создать эти источники данных вручную с тем же именем, что и в исходной среде.</span><span class="sxs-lookup"><span data-stu-id="38460-169">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="38460-170">При копировании среды вы увидите подтверждающее сообщение о том, что новая среда была создана.</span><span class="sxs-lookup"><span data-stu-id="38460-170">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="38460-171">Выберите **Перейти к источникам данных**, чтобы увидеть список источников данных.</span><span class="sxs-lookup"><span data-stu-id="38460-171">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="38460-172">Все источники данных покажут состояние **Требуются учетные данные**.</span><span class="sxs-lookup"><span data-stu-id="38460-172">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="38460-173">Отредактируйте источники данных и введите учетные данные, чтобы обновить их.</span><span class="sxs-lookup"><span data-stu-id="38460-173">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="38460-174">![Источники данных скопированы](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="38460-174">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="38460-175">После обновления источников данных перейдите к **Данные** > **Унификация**.</span><span class="sxs-lookup"><span data-stu-id="38460-175">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="38460-176">Здесь вы найдете параметры из исходной среды.</span><span class="sxs-lookup"><span data-stu-id="38460-176">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="38460-177">Отредактируйте их по мере необходимости или выберите **Запустить**, чтобы начать процесс унификации данных и создать единую сущность клиента.</span><span class="sxs-lookup"><span data-stu-id="38460-177">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="38460-178">Когда унификация данных будет завершена, перейдите к пунктам **Меры** и **Сегменты**, чтобы обновить их тоже.</span><span class="sxs-lookup"><span data-stu-id="38460-178">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="38460-179">Изменение существующей среды</span><span class="sxs-lookup"><span data-stu-id="38460-179">Edit an existing environment</span></span>

<span data-ttu-id="38460-180">Вы можете редактировать некоторые сведения существующих сред.</span><span class="sxs-lookup"><span data-stu-id="38460-180">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="38460-181">Выберите **Среда** в заголовке приложения.</span><span class="sxs-lookup"><span data-stu-id="38460-181">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="38460-182">Выберите значок **Правка**.</span><span class="sxs-lookup"><span data-stu-id="38460-182">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="38460-183">В поле **Редактирование среды** вы можете обновить **Отображаемое имя** среды, но вы не можете изменить **Регион** или **Тип**.</span><span class="sxs-lookup"><span data-stu-id="38460-183">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="38460-184">Если среда настроена для хранения данных в Azure Data Lake Storage 2-го поколения, вы можете обновить **Ключ учетной записи**.</span><span class="sxs-lookup"><span data-stu-id="38460-184">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="38460-185">Тем не менее, вы не можете изменить **Имя учетной записи** или имя **Контейнер**.</span><span class="sxs-lookup"><span data-stu-id="38460-185">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="38460-186">При желании вы можете выполнить обновление из подключения ключа учетной записи на подключение на основе ресурса или подписки.</span><span class="sxs-lookup"><span data-stu-id="38460-186">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="38460-187">После обновления вы не сможете вернуться к ключу учетной записи после обновления.</span><span class="sxs-lookup"><span data-stu-id="38460-187">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="38460-188">Для получения дополнительной информации см. [Подключение аналитики аудитории к учетной записи Azure Data Lake Storage Gen2 с помощью субъекта-службы Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="38460-188">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="38460-189">Невозможно изменить сведения **Контейнер** при обновлении соединения.</span><span class="sxs-lookup"><span data-stu-id="38460-189">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="38460-190">Сбросить существующую среду</span><span class="sxs-lookup"><span data-stu-id="38460-190">Reset an existing environment</span></span>

<span data-ttu-id="38460-191">Как администратор вы можете сбросить среду до пустого состояния, если хотите удалить все конфигурации и удалить полученные данные.</span><span class="sxs-lookup"><span data-stu-id="38460-191">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="38460-192">Выберите **Среда** в заголовке приложения.</span><span class="sxs-lookup"><span data-stu-id="38460-192">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="38460-193">Выберите среду, которую вы хотите сбросить, и выберите многоточие **...**.</span><span class="sxs-lookup"><span data-stu-id="38460-193">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="38460-194">Выберите вариант **Сбросить**.</span><span class="sxs-lookup"><span data-stu-id="38460-194">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="38460-195">Чтобы подтвердить удаление, введите имя среды и выберите **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="38460-195">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="38460-196">Удалить существующую среду (доступно только для администраторов)</span><span class="sxs-lookup"><span data-stu-id="38460-196">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="38460-197">Как администратор вы можете удалить среду, которую вы администрируете.</span><span class="sxs-lookup"><span data-stu-id="38460-197">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="38460-198">Выберите **Среда** в заголовке приложения.</span><span class="sxs-lookup"><span data-stu-id="38460-198">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="38460-199">Выберите среду, которую вы хотите сбросить, и выберите многоточие **...**.</span><span class="sxs-lookup"><span data-stu-id="38460-199">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="38460-200">Выберите вариант **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="38460-200">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="38460-201">Чтобы подтвердить удаление, введите имя среды и выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="38460-201">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]