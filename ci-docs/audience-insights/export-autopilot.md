---
title: Экспорт данных Customer Insights в Autopilot
description: Узнайте, как настроить подключение и экспорт в Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760159"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="f11dc-103">Экспорт сегментов в Autopilot (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="f11dc-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="f11dc-104">Экспортируйте сегменты единых профилей клиентов в Autopilot и используйте их для маркетинга по электронной почте в Autopilot.</span><span class="sxs-lookup"><span data-stu-id="f11dc-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="f11dc-105">Предварительные требования для подключения</span><span class="sxs-lookup"><span data-stu-id="f11dc-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="f11dc-106">У вас есть [учетная запись Autopilot](https://www.autopilothq.com/) и соответствующие учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="f11dc-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f11dc-107">У вас есть [настроенные сегменты](segments.md) в аналитике аудитории.</span><span class="sxs-lookup"><span data-stu-id="f11dc-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="f11dc-108">Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f11dc-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f11dc-109">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="f11dc-109">Known limitations</span></span>

- <span data-ttu-id="f11dc-110">Всего в Autopilot можно экспортировать до 100 000 профилей.</span><span class="sxs-lookup"><span data-stu-id="f11dc-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="f11dc-111">Экспорт в Autopilot ограничен сегментами.</span><span class="sxs-lookup"><span data-stu-id="f11dc-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="f11dc-112">Экспорт до 100 000 профилей в Autopilot может занять до нескольких часов.</span><span class="sxs-lookup"><span data-stu-id="f11dc-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="f11dc-113">Количество профилей, которые вы можете экспортировать в Autopilot, зависит и ограничивается вашим контрактом с Autopilot.</span><span class="sxs-lookup"><span data-stu-id="f11dc-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="f11dc-114">Настройка подключения к Autopilot</span><span class="sxs-lookup"><span data-stu-id="f11dc-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="f11dc-115">Перейти в раздел **Администрирование** > **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="f11dc-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f11dc-116">Выберите **Добавить подключение** и выберите **Mailchimp** для настройки подключения.</span><span class="sxs-lookup"><span data-stu-id="f11dc-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="f11dc-117">Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="f11dc-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f11dc-118">Имя и тип подключения описывают это подключение.</span><span class="sxs-lookup"><span data-stu-id="f11dc-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f11dc-119">Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.</span><span class="sxs-lookup"><span data-stu-id="f11dc-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f11dc-120">Укажите, кто может использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="f11dc-120">Choose who can use this connection.</span></span> <span data-ttu-id="f11dc-121">Если вы не предпримете никаких действий, по умолчанию это будут администраторы.</span><span class="sxs-lookup"><span data-stu-id="f11dc-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f11dc-122">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f11dc-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="f11dc-123">Введите [ключ API Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="f11dc-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="f11dc-124">Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.</span><span class="sxs-lookup"><span data-stu-id="f11dc-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f11dc-125">Выберите **Подключиться** для инициализации подключения к Autopilot.</span><span class="sxs-lookup"><span data-stu-id="f11dc-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="f11dc-126">Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f11dc-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f11dc-127">Выберите **Сохранить**, чтобы завершить подключение.</span><span class="sxs-lookup"><span data-stu-id="f11dc-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="f11dc-128">Настройка экспорта</span><span class="sxs-lookup"><span data-stu-id="f11dc-128">Configure an export</span></span>

<span data-ttu-id="f11dc-129">Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа.</span><span class="sxs-lookup"><span data-stu-id="f11dc-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f11dc-130">Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f11dc-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f11dc-131">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="f11dc-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f11dc-132">Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.</span><span class="sxs-lookup"><span data-stu-id="f11dc-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f11dc-133">В поле **Подключение для экспорта** выберите подключение из раздела Autopilot.</span><span class="sxs-lookup"><span data-stu-id="f11dc-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="f11dc-134">Если вы не видите название этого раздела, вам не доступны подключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="f11dc-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="f11dc-135">В разделе **Сопоставление данных** в поле **Электронная почта** выберите унифицированный профиль клиента, который представляет адрес электронной почты клиента.</span><span class="sxs-lookup"><span data-stu-id="f11dc-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f11dc-136">Повторите те же шаги для других необязательных полей, таких как **Имя**, **Фамилия**.</span><span class="sxs-lookup"><span data-stu-id="f11dc-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="f11dc-137">Выберите сегменты, которые нужно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="f11dc-137">Select the segments you want to export.</span></span> <span data-ttu-id="f11dc-138">Мы настоятельно **рекомендуем не экспортировать в общей сложности более 100 000 профилей клиентов** в Autopilot.</span><span class="sxs-lookup"><span data-stu-id="f11dc-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="f11dc-139">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f11dc-139">Select **Save**.</span></span>

<span data-ttu-id="f11dc-140">Сохранение экспорта не запускает экспорт сразу.</span><span class="sxs-lookup"><span data-stu-id="f11dc-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f11dc-141">Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f11dc-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f11dc-142">Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f11dc-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f11dc-143">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="f11dc-143">Data privacy and compliance</span></span>

<span data-ttu-id="f11dc-144">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в Autopilot, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="f11dc-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f11dc-145">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией Autopilot любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть.</span><span class="sxs-lookup"><span data-stu-id="f11dc-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="f11dc-146">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f11dc-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f11dc-147">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="f11dc-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
