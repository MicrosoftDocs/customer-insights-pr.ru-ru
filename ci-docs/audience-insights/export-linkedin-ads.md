---
title: Экспорт данных Customer Insights в LinkedIn Ads
description: Узнайте, как настроить подключение и экспорт в LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124542"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="8382d-103">Экспорт сегментов в LinkedIn Ads (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="8382d-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="8382d-104">Экспортируйте сегменты единых профилей клиентов в LinkedIn Ads для создания сопоставленных аудиторий.</span><span class="sxs-lookup"><span data-stu-id="8382d-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="8382d-105">Используйте сопоставленные аудитории для таргетинга на компании и контакты.</span><span class="sxs-lookup"><span data-stu-id="8382d-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8382d-106">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="8382d-106">Prerequisites</span></span>

-   <span data-ttu-id="8382d-107">У вас есть [учетная запись LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) и соответствующие учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="8382d-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="8382d-108">У вас есть [настроенные сегменты](segments.md) в аналитике аудитории.</span><span class="sxs-lookup"><span data-stu-id="8382d-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="8382d-109">Профили клиентов в экспортированных сегментах содержат поле с адресом электронной почты.</span><span class="sxs-lookup"><span data-stu-id="8382d-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8382d-110">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="8382d-110">Known limitations</span></span>

- <span data-ttu-id="8382d-111">Вы можете экспортировать до 100 тыс профилей за один экспорт в LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="8382d-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="8382d-112">Экспорт в LinkedIn Ads ограничен сегментами.</span><span class="sxs-lookup"><span data-stu-id="8382d-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="8382d-113">Экспорт до 100 тыс профилей в LinkedIn Ads может занять до 10 минут.</span><span class="sxs-lookup"><span data-stu-id="8382d-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="8382d-114">Настройка подключения к LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="8382d-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="8382d-115">В аналитике аудитории перейдите по ссылке **Администрирование** > **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="8382d-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="8382d-116">Выберите **Добавить подключение** и выберите **LinkedIn Ads** для настройки подключения.</span><span class="sxs-lookup"><span data-stu-id="8382d-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="8382d-117">Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="8382d-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="8382d-118">Имя и тип подключения описывают это подключение.</span><span class="sxs-lookup"><span data-stu-id="8382d-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="8382d-119">Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.</span><span class="sxs-lookup"><span data-stu-id="8382d-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="8382d-120">Укажите, кто может использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="8382d-120">Choose who can use this connection.</span></span> <span data-ttu-id="8382d-121">Если вы не предпримете никаких действий, по умолчанию это администраторы.</span><span class="sxs-lookup"><span data-stu-id="8382d-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="8382d-122">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="8382d-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="8382d-123">Предоставьте свой [идентификатор учетной записи LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).</span><span class="sxs-lookup"><span data-stu-id="8382d-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="8382d-124">Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.</span><span class="sxs-lookup"><span data-stu-id="8382d-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8382d-125">Выберите **Подключить** для инициализации подключения к Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="8382d-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="8382d-126">Выберите **Проверка подлинности в LinkedIn** и укажите свои учетные данные администратора для LinkedIn Campaign Manager.</span><span class="sxs-lookup"><span data-stu-id="8382d-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="8382d-127">Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8382d-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="8382d-128">Выберите **Сохранить**, чтобы завершить подключение.</span><span class="sxs-lookup"><span data-stu-id="8382d-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="8382d-129">Настройка экспорта</span><span class="sxs-lookup"><span data-stu-id="8382d-129">Configure an export</span></span>

<span data-ttu-id="8382d-130">Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа.</span><span class="sxs-lookup"><span data-stu-id="8382d-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="8382d-131">Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="8382d-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="8382d-132">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="8382d-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8382d-133">Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.</span><span class="sxs-lookup"><span data-stu-id="8382d-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="8382d-134">В поле **Подключение для экспорта** выберите подключение из раздела LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="8382d-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="8382d-135">Если вы не видите название этого раздела, вам не доступны подключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="8382d-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="8382d-136">Выберите, хотите ли вы экспортировать данные для выполнения [таргетинг на контакты](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) или [таргетинг на компании](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) в LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="8382d-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="8382d-137">В разделе **Сопоставление данных** единого профиля клиента выберите поле, которое представляет адрес электронной почты клиента.</span><span class="sxs-lookup"><span data-stu-id="8382d-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="8382d-138">Необходимо экспортировать сегменты в LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="8382d-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="8382d-139">Выберите сегменты, которые нужно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="8382d-139">Select the segments you want to export.</span></span> <span data-ttu-id="8382d-140">Сопоставленные аудитории в LinkedIn Campaign Manager будет автоматически созданы с именем сегментов, которые вы выбрали для экспорта.</span><span class="sxs-lookup"><span data-stu-id="8382d-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="8382d-141">Каждый сегмент приведет к отдельному сопоставленной аудитории.</span><span class="sxs-lookup"><span data-stu-id="8382d-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="8382d-142">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8382d-142">Select **Save**.</span></span>

<span data-ttu-id="8382d-143">Сохранение экспорта не запускает экспорт сразу.</span><span class="sxs-lookup"><span data-stu-id="8382d-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="8382d-144">Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8382d-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8382d-145">Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="8382d-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8382d-146">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="8382d-146">Data privacy and compliance</span></span>

<span data-ttu-id="8382d-147">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в LinkedIn Ads, вы разрешаете передачу данных за пределы границ соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="8382d-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8382d-148">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за то, чтобы LinkedIn Ads выполнял любые обязательства в отношении конфиденциальности или безопасности, которые могут иметься у вас.</span><span class="sxs-lookup"><span data-stu-id="8382d-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="8382d-149">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8382d-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="8382d-150">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="8382d-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
