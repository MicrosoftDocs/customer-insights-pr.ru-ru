---
title: Экспорт данных Customer Insights в Constant Contact
description: Узнайте, как настроить подключение и экспорт в Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29f4320c798db62609283e3c48f0b47a4f0b982f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124289"
---
# <a name="export-segments-to-constant-contact-preview"></a><span data-ttu-id="67ca0-103">Экспорт сегментов в Constant Contact (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="67ca0-103">Export segments to Constant Contact (preview)</span></span>

<span data-ttu-id="67ca0-104">Экспортируйте сегменты унифицированных профилей клиентов в Constant Contact и используйте их для маркетинговых действий.</span><span class="sxs-lookup"><span data-stu-id="67ca0-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="67ca0-105">Предварительные требования для подключения</span><span class="sxs-lookup"><span data-stu-id="67ca0-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="67ca0-106">У вас есть [учетная запись Constant Contact](https://www.constantcontact.com/account-home) и соответствующие учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="67ca0-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="67ca0-107">У вас есть [настроенные сегменты](segments.md) в аналитике аудитории.</span><span class="sxs-lookup"><span data-stu-id="67ca0-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="67ca0-108">Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="67ca0-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="67ca0-109">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="67ca0-109">Known limitations</span></span>

- <span data-ttu-id="67ca0-110">Вы можете экспортировать до 1 миллиона профилей за один экспорт в Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="67ca0-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="67ca0-111">Экспорт в Constant Contact ограничен сегментами.</span><span class="sxs-lookup"><span data-stu-id="67ca0-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="67ca0-112">Экспорт до 1 миллиона профилей в Constant Contact может занять до 1 часа.</span><span class="sxs-lookup"><span data-stu-id="67ca0-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="67ca0-113">Количество профилей, которые вы можете экспортировать в Constant Contact, определяется и ограничивается вашим контрактом с Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="67ca0-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="67ca0-114">Настройка подключения к Constant Contact</span><span class="sxs-lookup"><span data-stu-id="67ca0-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="67ca0-115">Перейти в раздел **Администрирование** > **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="67ca0-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="67ca0-116">Выберите **Добавить подключение** и выберите **Constant Contact** для настройки подключения.</span><span class="sxs-lookup"><span data-stu-id="67ca0-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="67ca0-117">Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="67ca0-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="67ca0-118">Имя и тип подключения описывают это подключение.</span><span class="sxs-lookup"><span data-stu-id="67ca0-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="67ca0-119">Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.</span><span class="sxs-lookup"><span data-stu-id="67ca0-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="67ca0-120">Укажите, кто может использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="67ca0-120">Choose who can use this connection.</span></span> <span data-ttu-id="67ca0-121">Если вы не предпримете никаких действий, по умолчанию это будут администраторы.</span><span class="sxs-lookup"><span data-stu-id="67ca0-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="67ca0-122">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="67ca0-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="67ca0-123">Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.</span><span class="sxs-lookup"><span data-stu-id="67ca0-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="67ca0-124">Выберите **Подключить** для инициализации подключения к Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="67ca0-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="67ca0-125">Выберите **Аутентификация в AdRoll** и укажите свои учетные данные администратора для Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="67ca0-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="67ca0-126">Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="67ca0-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="67ca0-127">Выберите **Сохранить**, чтобы завершить подключение.</span><span class="sxs-lookup"><span data-stu-id="67ca0-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="67ca0-128">Настройка экспорта</span><span class="sxs-lookup"><span data-stu-id="67ca0-128">Configure an export</span></span>

<span data-ttu-id="67ca0-129">Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа.</span><span class="sxs-lookup"><span data-stu-id="67ca0-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="67ca0-130">Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="67ca0-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="67ca0-131">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="67ca0-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="67ca0-132">Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.</span><span class="sxs-lookup"><span data-stu-id="67ca0-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="67ca0-133">В поле **Подключение для экспорта** выберите подключение из раздела Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="67ca0-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="67ca0-134">Если вы не видите название этого раздела, вам не доступны подключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="67ca0-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="67ca0-135">Введите свой [**ИД списка Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists).</span><span class="sxs-lookup"><span data-stu-id="67ca0-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="67ca0-136">Откройте список в Constant Contact, чтобы найти идентификатор списка в URL-адресе.</span><span class="sxs-lookup"><span data-stu-id="67ca0-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="67ca0-137">В разделе **Сопоставление данных** в поле **Электронная почта** выберите унифицированный профиль клиента, который представляет адрес электронной почты клиента.</span><span class="sxs-lookup"><span data-stu-id="67ca0-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="67ca0-138">Необходимо экспортировать сегменты в Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="67ca0-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="67ca0-139">По желанию вы можете экспортировать Имя и Фамилия в качестве дополнительных полей для создания более персонализированных писем.</span><span class="sxs-lookup"><span data-stu-id="67ca0-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="67ca0-140">Выберите **Добавить атрибут**, чтобы сопоставить эти поля.</span><span class="sxs-lookup"><span data-stu-id="67ca0-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="67ca0-141">Выберите сегменты, которые нужно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="67ca0-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="67ca0-142">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="67ca0-142">Select **Save**.</span></span>

<span data-ttu-id="67ca0-143">Сохранение экспорта не запускает экспорт сразу.</span><span class="sxs-lookup"><span data-stu-id="67ca0-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="67ca0-144">Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="67ca0-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="67ca0-145">Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="67ca0-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="67ca0-146">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="67ca0-146">Data privacy and compliance</span></span>

<span data-ttu-id="67ca0-147">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в Constant Contact, вы разрешаете передачу данных за пределы границ соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="67ca0-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="67ca0-148">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за то, чтобы Constant Contact выполнял любые обязательства в отношении конфиденциальности или безопасности, которые могут иметься у вас.</span><span class="sxs-lookup"><span data-stu-id="67ca0-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="67ca0-149">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="67ca0-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="67ca0-150">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="67ca0-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
