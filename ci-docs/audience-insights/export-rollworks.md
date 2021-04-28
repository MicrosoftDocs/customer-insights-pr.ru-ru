---
title: Экспорт данных Customer Insights в RollWorks
description: Узнайте, как настроить подключение и экспорт в RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4979f0147dea2270f11342c1bb6b0693f3c24aea
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760618"
---
# <a name="export-segment-lists-to-rollworks-preview"></a><span data-ttu-id="ef744-103">Экспорт списков сегментов в RollWorks (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="ef744-103">Export segment lists to RollWorks (preview)</span></span>

<span data-ttu-id="ef744-104">Экспортируйте сегменты унифицированных профилей клиентов в RollWorks и используйте их для рекламы.</span><span class="sxs-lookup"><span data-stu-id="ef744-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="ef744-105">Предварительные требования для подключения</span><span class="sxs-lookup"><span data-stu-id="ef744-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="ef744-106">У вас есть [учетная запись RollWorks](https://www.rollworks.com/) и соответствующие учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="ef744-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ef744-107">У вас есть [настроенные сегменты](segments.md) в аналитике аудитории.</span><span class="sxs-lookup"><span data-stu-id="ef744-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ef744-108">Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ef744-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ef744-109">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="ef744-109">Known limitations</span></span>

- <span data-ttu-id="ef744-110">Вы можете экспортировать до 250 000 миллиона профилей за один экспорт в RollWorks.</span><span class="sxs-lookup"><span data-stu-id="ef744-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="ef744-111">Вы не можете экспортировать сегменты с менее чем 100 профилями в RollWorks.</span><span class="sxs-lookup"><span data-stu-id="ef744-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="ef744-112">Экспорт в RollWorks ограничен сегментами.</span><span class="sxs-lookup"><span data-stu-id="ef744-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="ef744-113">Экспорт до 250 000 профилей в RollWorks может занять до 10 минут.</span><span class="sxs-lookup"><span data-stu-id="ef744-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="ef744-114">Количество профилей, которые вы можете экспортировать в RollWorks, определяется и ограничивается вашим контрактом с RollWorks.</span><span class="sxs-lookup"><span data-stu-id="ef744-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="ef744-115">Настройка подключения к RollWorks</span><span class="sxs-lookup"><span data-stu-id="ef744-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="ef744-116">Перейти в раздел **Администрирование** > **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="ef744-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ef744-117">Выберите **Добавить подключение** и выберите **RollWorks** для настройки подключения.</span><span class="sxs-lookup"><span data-stu-id="ef744-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="ef744-118">Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="ef744-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ef744-119">Имя и тип подключения описывают это подключение.</span><span class="sxs-lookup"><span data-stu-id="ef744-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ef744-120">Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.</span><span class="sxs-lookup"><span data-stu-id="ef744-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ef744-121">Укажите, кто может использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="ef744-121">Choose who can use this connection.</span></span> <span data-ttu-id="ef744-122">Если вы не предпримете никаких действий, по умолчанию это будут администраторы.</span><span class="sxs-lookup"><span data-stu-id="ef744-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ef744-123">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ef744-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ef744-124">Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.</span><span class="sxs-lookup"><span data-stu-id="ef744-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ef744-125">Выберите **Подключить** для инициализации подключения к RollWorks.</span><span class="sxs-lookup"><span data-stu-id="ef744-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="ef744-126">Выберите **Проверка подлинности в RollWorks** и укажите свои учетные данные администратора для RollWorks.</span><span class="sxs-lookup"><span data-stu-id="ef744-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="ef744-127">Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ef744-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ef744-128">Выберите **Сохранить**, чтобы завершить подключение.</span><span class="sxs-lookup"><span data-stu-id="ef744-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ef744-129">Настройка экспорта</span><span class="sxs-lookup"><span data-stu-id="ef744-129">Configure an export</span></span>

<span data-ttu-id="ef744-130">Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа.</span><span class="sxs-lookup"><span data-stu-id="ef744-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ef744-131">Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ef744-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ef744-132">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="ef744-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ef744-133">Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.</span><span class="sxs-lookup"><span data-stu-id="ef744-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ef744-134">В поле **Подключение для экспорта** выберите подключение из раздела RollWorks.</span><span class="sxs-lookup"><span data-stu-id="ef744-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="ef744-135">Если вы не видите название этого раздела, вам не доступны подключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="ef744-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ef744-136">Введите ваш **ИД рекламодателя RollWorks** [рекламодателя RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="ef744-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="ef744-137">В разделе **Сопоставление данных** в поле **Электронная почта** выберите унифицированный профиль клиента, который представляет адрес электронной почты клиента.</span><span class="sxs-lookup"><span data-stu-id="ef744-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ef744-138">Необходимо экспортировать сегменты в RollWorks.</span><span class="sxs-lookup"><span data-stu-id="ef744-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="ef744-139">Выберите сегменты, которые нужно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="ef744-139">Select the segments you want to export.</span></span> <span data-ttu-id="ef744-140">Выберите сегмент, в котором не менее 100 участников.</span><span class="sxs-lookup"><span data-stu-id="ef744-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="ef744-141">Вы не можете экспортировать меньшие сегменты.</span><span class="sxs-lookup"><span data-stu-id="ef744-141">You can't export smaller segments.</span></span> <span data-ttu-id="ef744-142">Кроме того, максимальный размер экспортируемого сегмента составляет 250 000 участников для каждого экспорта.</span><span class="sxs-lookup"><span data-stu-id="ef744-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="ef744-143">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ef744-143">Select **Save**.</span></span>

<span data-ttu-id="ef744-144">Сохранение экспорта не запускает экспорт сразу.</span><span class="sxs-lookup"><span data-stu-id="ef744-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ef744-145">Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ef744-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ef744-146">Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ef744-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ef744-147">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="ef744-147">Data privacy and compliance</span></span>

<span data-ttu-id="ef744-148">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в RollWorks, вы разрешаете передачу данных за пределы границ соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="ef744-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ef744-149">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за то, чтобы RollWorks выполнял любые обязательства в отношении конфиденциальности или безопасности, которые могут иметься у вас.</span><span class="sxs-lookup"><span data-stu-id="ef744-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ef744-150">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ef744-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="ef744-151">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="ef744-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
