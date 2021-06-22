---
title: Экспорт данных Customer Insights в AdRoll
description: Узнайте, как настроить подключение и экспорт в AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dbebc3ee3978ca6ee9d1ad1c15c226479876709f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124381"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="5b197-103">Экспорт сегментов в AdRoll (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="5b197-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="5b197-104">Экспортируйте сегменты унифицированных профилей клиентов в AdRoll и используйте их для рекламы.</span><span class="sxs-lookup"><span data-stu-id="5b197-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="5b197-105">Предварительные требования для подключения</span><span class="sxs-lookup"><span data-stu-id="5b197-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="5b197-106">У вас есть [учетная запись AdRoll](https://www.adroll.com/) и соответствующие учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="5b197-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="5b197-107">У вас есть [настроенные сегменты](segments.md) в аналитике аудитории.</span><span class="sxs-lookup"><span data-stu-id="5b197-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="5b197-108">Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="5b197-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5b197-109">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="5b197-109">Known limitations</span></span>

- <span data-ttu-id="5b197-110">Всего в AdRoll можно экспортировать до 250 000 профилей.</span><span class="sxs-lookup"><span data-stu-id="5b197-110">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="5b197-111">Вы не можете экспортировать сегменты с менее чем 100 профилями в AdRoll.</span><span class="sxs-lookup"><span data-stu-id="5b197-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="5b197-112">Экспорт в AdRoll ограничен сегментами.</span><span class="sxs-lookup"><span data-stu-id="5b197-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="5b197-113">Экспорт до 250 000 профилей в AdRoll может занять до 10 минут.</span><span class="sxs-lookup"><span data-stu-id="5b197-113">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="5b197-114">Количество профилей, которые вы можете экспортировать в AdRoll ограничен вашим контрактом с AdRoll.</span><span class="sxs-lookup"><span data-stu-id="5b197-114">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="5b197-115">Настройка подключения к AdRoll</span><span class="sxs-lookup"><span data-stu-id="5b197-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="5b197-116">Перейти в раздел **Администрирование** > **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="5b197-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="5b197-117">Выберите **Добавить подключение** и выберите **AdRoll** для настройки подключения.</span><span class="sxs-lookup"><span data-stu-id="5b197-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="5b197-118">Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="5b197-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="5b197-119">Имя и тип подключения описывают это подключение.</span><span class="sxs-lookup"><span data-stu-id="5b197-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="5b197-120">Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.</span><span class="sxs-lookup"><span data-stu-id="5b197-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="5b197-121">Укажите, кто может использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="5b197-121">Choose who can use this connection.</span></span> <span data-ttu-id="5b197-122">Если вы не предпримете никаких действий, по умолчанию это будут администраторы.</span><span class="sxs-lookup"><span data-stu-id="5b197-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="5b197-123">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="5b197-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="5b197-124">Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.</span><span class="sxs-lookup"><span data-stu-id="5b197-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="5b197-125">Выберите **Подключиться** для инициализации подключения к AdRoll.</span><span class="sxs-lookup"><span data-stu-id="5b197-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="5b197-126">Выберите **Авторизоваться в AdRoll** и укажите свои учетные данные AdRoll.</span><span class="sxs-lookup"><span data-stu-id="5b197-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="5b197-127">Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5b197-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="5b197-128">Выберите **Сохранить**, чтобы завершить подключение.</span><span class="sxs-lookup"><span data-stu-id="5b197-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="5b197-129">Настройка экспорта</span><span class="sxs-lookup"><span data-stu-id="5b197-129">Configure an export</span></span>

<span data-ttu-id="5b197-130">Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа.</span><span class="sxs-lookup"><span data-stu-id="5b197-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="5b197-131">Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="5b197-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5b197-132">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="5b197-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5b197-133">Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.</span><span class="sxs-lookup"><span data-stu-id="5b197-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="5b197-134">В поле **Подключение для экспорта** выберите подключение из раздела AdRoll.</span><span class="sxs-lookup"><span data-stu-id="5b197-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="5b197-135">Если вы не видите название этого раздела, вам не доступны подключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="5b197-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="5b197-136">Введите ваш **Идентификатор рекламодателя AdRoll**. Для получения дополнительной информации см. раздел [Профили рекламодателей AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="5b197-136">Enter your **AdRoll Advertiser ID** For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="5b197-137">В разделе **Сопоставление данных** в поле **Электронная почта** выберите унифицированный профиль клиента, который представляет адрес электронной почты клиента.</span><span class="sxs-lookup"><span data-stu-id="5b197-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="5b197-138">Требуется экспортировать сегменты в AdRoll.</span><span class="sxs-lookup"><span data-stu-id="5b197-138">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="5b197-139">Выберите сегменты, которые нужно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="5b197-139">Select the segments you want to export.</span></span> <span data-ttu-id="5b197-140">Выберите сегмент, в котором не менее 100 участников.</span><span class="sxs-lookup"><span data-stu-id="5b197-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="5b197-141">Вы не можете экспортировать меньшие сегменты.</span><span class="sxs-lookup"><span data-stu-id="5b197-141">You can't export smaller segments.</span></span> <span data-ttu-id="5b197-142">Кроме того, максимальный размер экспортируемого сегмента составляет 250 000 участников для каждого экспорта.</span><span class="sxs-lookup"><span data-stu-id="5b197-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="5b197-143">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5b197-143">Select **Save**.</span></span>

<span data-ttu-id="5b197-144">Сохранение экспорта не запускает экспорт сразу.</span><span class="sxs-lookup"><span data-stu-id="5b197-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="5b197-145">Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5b197-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5b197-146">Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="5b197-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5b197-147">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="5b197-147">Data privacy and compliance</span></span>

<span data-ttu-id="5b197-148">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в AdRoll, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="5b197-148">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5b197-149">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение AdRoll любых обязательств в отношении конфиденциальности или безопасности.</span><span class="sxs-lookup"><span data-stu-id="5b197-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="5b197-150">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="5b197-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="5b197-151">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="5b197-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
