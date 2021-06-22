---
title: Экспорт данных Customer Insights в Campaign Monitor
description: Узнайте, как настроить подключение и экспорт в Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 091a3197dc0c19ff78f0419fb4e88868e0f78359
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124197"
---
# <a name="export-segments-to-campaign-monitor-preview"></a><span data-ttu-id="7e209-103">Экспорт сегментов в Campaign Monitor (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="7e209-103">Export segments to Campaign Monitor (preview)</span></span>

<span data-ttu-id="7e209-104">Экспортируйте сегменты унифицированных профилей клиентов в Campaign Monitor и используйте их для маркетинговых действий.</span><span class="sxs-lookup"><span data-stu-id="7e209-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7e209-105">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="7e209-105">Prerequisites</span></span>

-   <span data-ttu-id="7e209-106">У вас есть [учетная запись Campaign Monitor](https://www.campaignmonitor.com/) и соответствующие учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="7e209-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="7e209-107">У вас есть [настроенные сегменты](segments.md) в аналитике аудитории.</span><span class="sxs-lookup"><span data-stu-id="7e209-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="7e209-108">Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="7e209-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="7e209-109">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="7e209-109">Known limitations</span></span>

- <span data-ttu-id="7e209-110">Вы можете экспортировать до 1 миллиона профилей за один экспорт в Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="7e209-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="7e209-111">Экспорт в Campaign Monitor ограничен сегментами.</span><span class="sxs-lookup"><span data-stu-id="7e209-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="7e209-112">Экспорт до 1 миллиона профилей в Campaign Monitor может занять до 20 минут.</span><span class="sxs-lookup"><span data-stu-id="7e209-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="7e209-113">Количество профилей, которые вы можете экспортировать в Campaign Monitor, определяется и ограничивается вашим контрактом с Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="7e209-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="7e209-114">Настройка подключения к Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="7e209-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="7e209-115">Перейти в раздел **Администрирование** > **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="7e209-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="7e209-116">Выберите **Добавить подключение** и выберите **Campaign Monitor** для настройки подключения.</span><span class="sxs-lookup"><span data-stu-id="7e209-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="7e209-117">Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="7e209-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="7e209-118">Имя и тип подключения описывают это подключение.</span><span class="sxs-lookup"><span data-stu-id="7e209-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="7e209-119">Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.</span><span class="sxs-lookup"><span data-stu-id="7e209-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="7e209-120">Укажите, кто может использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="7e209-120">Choose who can use this connection.</span></span> <span data-ttu-id="7e209-121">Если вы не предпримете никаких действий, по умолчанию это будут администраторы.</span><span class="sxs-lookup"><span data-stu-id="7e209-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="7e209-122">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="7e209-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="7e209-123">Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.</span><span class="sxs-lookup"><span data-stu-id="7e209-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="7e209-124">Выберите **Подключить** для инициализации подключения к Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="7e209-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="7e209-125">Выберите **Проверка подлинности в Campaign Monitor** и укажите свои учетные данные администратора для Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="7e209-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="7e209-126">Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7e209-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="7e209-127">Выберите **Сохранить**, чтобы завершить подключение.</span><span class="sxs-lookup"><span data-stu-id="7e209-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="7e209-128">Настройка экспорта</span><span class="sxs-lookup"><span data-stu-id="7e209-128">Configure an export</span></span>

<span data-ttu-id="7e209-129">Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа.</span><span class="sxs-lookup"><span data-stu-id="7e209-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="7e209-130">Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="7e209-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="7e209-131">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="7e209-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7e209-132">Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.</span><span class="sxs-lookup"><span data-stu-id="7e209-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="7e209-133">В поле **Подключение для экспорта** выберите подключение из раздела Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="7e209-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="7e209-134">Если вы не видите название этого раздела, вам не доступны подключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="7e209-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="7e209-135">Введите свой [**ИД списка Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="7e209-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="7e209-136">[Сгенерируйте ключ API](https://www.campaignmonitor.com/api/getting-started/) из пункта **Параметры учетной записи** в Campaign Monitor сначала, чтобы просмотреть идентификатор списка API.</span><span class="sxs-lookup"><span data-stu-id="7e209-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="7e209-137">В разделе **Сопоставление данных** в поле **Электронная почта** выберите унифицированный профиль клиента, который представляет адрес электронной почты клиента.</span><span class="sxs-lookup"><span data-stu-id="7e209-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="7e209-138">Необходимо экспортировать сегменты в Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="7e209-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="7e209-139">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7e209-139">Select **Save**.</span></span>

<span data-ttu-id="7e209-140">Сохранение экспорта не запускает экспорт сразу.</span><span class="sxs-lookup"><span data-stu-id="7e209-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="7e209-141">Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7e209-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7e209-142">Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="7e209-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7e209-143">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="7e209-143">Data privacy and compliance</span></span>

<span data-ttu-id="7e209-144">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в Campaign Monitor, вы разрешаете передачу данных за пределы границ соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="7e209-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7e209-145">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за то, чтобы Campaign Monitor выполнял любые обязательства в отношении конфиденциальности или безопасности, которые могут иметься у вас.</span><span class="sxs-lookup"><span data-stu-id="7e209-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="7e209-146">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="7e209-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="7e209-147">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="7e209-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
