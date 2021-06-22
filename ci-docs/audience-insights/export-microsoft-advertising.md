---
title: Экспорт данных Customer Insights в Microsoft Advertising
description: Узнайте, как настроить подключение и экспорт в Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124540"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="a2465-103">Экспорт сегментов в Microsoft Advertising (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="a2465-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="a2465-104">Экспортируйте сегменты Customer Insights в Microsoft Advertising для создания аудиторий Customer Match.</span><span class="sxs-lookup"><span data-stu-id="a2465-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="a2465-105">Используйте эти аудитории для своих рекламных кампаний.</span><span class="sxs-lookup"><span data-stu-id="a2465-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a2465-106">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="a2465-106">Prerequisites</span></span>

-   <span data-ttu-id="a2465-107">У вас есть [учетная запись Microsoft Advertising](https://ads.microsoft.com/) и соответствующие учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="a2465-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a2465-108">Вы приняли условия использования Customer Match.</span><span class="sxs-lookup"><span data-stu-id="a2465-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="a2465-109">[Настроенные сегменты](segments.md) в аналитиках аудитории.</span><span class="sxs-lookup"><span data-stu-id="a2465-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="a2465-110">Единые профили клиентов в экспортированных сегментах содержат поле с адресом электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a2465-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a2465-111">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="a2465-111">Known limitations</span></span>

- <span data-ttu-id="a2465-112">Вы можете экспортировать до 500 тыс профилей за один экспорт в Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="a2465-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="a2465-113">Экспорт в Microsoft Advertising ограничен сегментами.</span><span class="sxs-lookup"><span data-stu-id="a2465-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="a2465-114">Экспорт до 500 тыс профилей в Microsoft Advertising может занять до 10 минут.</span><span class="sxs-lookup"><span data-stu-id="a2465-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="a2465-115">Настройка подключения к Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="a2465-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="a2465-116">Перейти в раздел **Администрирование** > **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="a2465-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a2465-117">Выберите **Добавить подключение** и выберите **Microsoft Advertising** для настройки подключения.</span><span class="sxs-lookup"><span data-stu-id="a2465-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="a2465-118">Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="a2465-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a2465-119">Имя и тип подключения описывают это подключение.</span><span class="sxs-lookup"><span data-stu-id="a2465-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a2465-120">Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.</span><span class="sxs-lookup"><span data-stu-id="a2465-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a2465-121">Укажите, кто может использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="a2465-121">Choose who can use this connection.</span></span> <span data-ttu-id="a2465-122">По умолчанию это администраторы.</span><span class="sxs-lookup"><span data-stu-id="a2465-122">The default is administrators.</span></span> <span data-ttu-id="a2465-123">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a2465-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a2465-124">Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.</span><span class="sxs-lookup"><span data-stu-id="a2465-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a2465-125">Выберите **Подключить** для инициализации подключения к Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="a2465-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="a2465-126">Выберите **Проверка подлинности в Microsoft Advertising** и укажите свои учетные данные администратора для Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="a2465-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="a2465-127">Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a2465-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a2465-128">Выберите **Сохранить**, чтобы завершить подключение.</span><span class="sxs-lookup"><span data-stu-id="a2465-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a2465-129">Настройка экспорта</span><span class="sxs-lookup"><span data-stu-id="a2465-129">Configure an export</span></span>

<span data-ttu-id="a2465-130">Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа.</span><span class="sxs-lookup"><span data-stu-id="a2465-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a2465-131">Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a2465-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a2465-132">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="a2465-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a2465-133">Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.</span><span class="sxs-lookup"><span data-stu-id="a2465-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a2465-134">В поле **Подключение для экспорта** выберите подключение из раздела Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="a2465-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="a2465-135">Если вы не видите название этого раздела, вам не доступны подключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="a2465-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a2465-136">Выберите сегменты для экспорта.</span><span class="sxs-lookup"><span data-stu-id="a2465-136">Select the segments to export.</span></span> <span data-ttu-id="a2465-137">Аудитории Customer Match в Microsoft Advertising создаются автоматически с именами сегментов, выбранных для экспорта.</span><span class="sxs-lookup"><span data-stu-id="a2465-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="a2465-138">Каждый сегмент приведет к отдельной аудитории Customer Match.</span><span class="sxs-lookup"><span data-stu-id="a2465-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="a2465-139">Введите ваш **Идентификатор клиента Microsoft Advertising и идентификатор учетной записи**.</span><span class="sxs-lookup"><span data-stu-id="a2465-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="a2465-140">Вы можете найти идентификатор клиента (`cid`) и идентификатор учетной записи (`aid`) в параметрах URL-адреса при входе в Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="a2465-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="a2465-141">В разделе **Сопоставление данных** в поле **Электронная почта** выберите поле в едином профиле клиента с адресом электронной почты клиента.</span><span class="sxs-lookup"><span data-stu-id="a2465-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="a2465-142">Необходимо экспортировать сегменты в Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="a2465-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="a2465-143">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a2465-143">Select **Save**.</span></span>

<span data-ttu-id="a2465-144">Сохранение экспорта не запускает экспорт сразу.</span><span class="sxs-lookup"><span data-stu-id="a2465-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a2465-145">Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a2465-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a2465-146">Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a2465-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a2465-147">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="a2465-147">Data privacy and compliance</span></span>

<span data-ttu-id="a2465-148">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в Microsoft Advertising, вы разрешаете передачу данных за пределы границ соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="a2465-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a2465-149">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за то, чтобы Microsoft Advertising выполнял любые обязательства в отношении конфиденциальности или безопасности, которые могут иметься у вас.</span><span class="sxs-lookup"><span data-stu-id="a2465-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a2465-150">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a2465-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="a2465-151">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="a2465-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
