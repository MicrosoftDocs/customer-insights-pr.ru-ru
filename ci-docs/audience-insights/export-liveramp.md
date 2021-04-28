---
title: Соединитель LiveRamp
description: Узнайте, как настроить подключение и экспорт в LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760343"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="497c7-103">Экспорт сегментов в LiveRamp&reg; (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="497c7-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="497c7-104">Активируйте свои данные в LiveRamp для подключения к более чем 500 платформам в цифровых и социальных сетях, а также на телевидении.</span><span class="sxs-lookup"><span data-stu-id="497c7-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="497c7-105">Работайте со своими данными в LiveRamp для нацеливания, подавления и персонализации рекламных кампаний.</span><span class="sxs-lookup"><span data-stu-id="497c7-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="497c7-106">Предварительные требования для подключения</span><span class="sxs-lookup"><span data-stu-id="497c7-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="497c7-107">Вам нужна подписка LiveRamp, чтобы использовать этот соединитель.</span><span class="sxs-lookup"><span data-stu-id="497c7-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="497c7-108">Чтобы получить подписку, [обратитесь в LiveRamp](https://liveramp.com/contact/) непосредственно.</span><span class="sxs-lookup"><span data-stu-id="497c7-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="497c7-109">[Дополнительные сведения о LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="497c7-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="497c7-110">Настройка подключения к LiveRamp</span><span class="sxs-lookup"><span data-stu-id="497c7-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="497c7-111">Перейти в раздел **Администрирование** > **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="497c7-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="497c7-112">Выберите **Добавить подключение** и выберите **LiveRamp** для настройки подключения.</span><span class="sxs-lookup"><span data-stu-id="497c7-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="497c7-113">Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="497c7-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="497c7-114">Имя и тип подключения описывают это подключение.</span><span class="sxs-lookup"><span data-stu-id="497c7-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="497c7-115">Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.</span><span class="sxs-lookup"><span data-stu-id="497c7-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="497c7-116">Укажите, кто может использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="497c7-116">Choose who can use this connection.</span></span> <span data-ttu-id="497c7-117">Если вы не предпримете никаких действий, по умолчанию это будут администраторы.</span><span class="sxs-lookup"><span data-stu-id="497c7-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="497c7-118">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="497c7-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="497c7-119">Укажите **Имя пользователя** и **Пароль** для вашей учетной записи LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="497c7-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="497c7-120">Эти учетные данные могут отличаться от ваших учетных данных LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="497c7-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="497c7-121">Выберите **Проверить** ,чтобы проверить подключение к LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="497c7-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="497c7-122">После успешной проверки предоставьте свое согласие на **Конфиденциальность данных и соответствие**, установив флажок **Принимаю**.</span><span class="sxs-lookup"><span data-stu-id="497c7-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="497c7-123">Выберите **Сохранить**, чтобы завершить подключение.</span><span class="sxs-lookup"><span data-stu-id="497c7-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="497c7-124">Настройка экспорта</span><span class="sxs-lookup"><span data-stu-id="497c7-124">Configure an export</span></span>

<span data-ttu-id="497c7-125">Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа.</span><span class="sxs-lookup"><span data-stu-id="497c7-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="497c7-126">Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="497c7-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="497c7-127">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="497c7-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="497c7-128">Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.</span><span class="sxs-lookup"><span data-stu-id="497c7-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="497c7-129">В поле **Подключение для экспорта** выберите подключение из раздела LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="497c7-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="497c7-130">Если вы не видите название этого раздела, вам не доступны подключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="497c7-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="497c7-131">В поле **Выберите ваш ключевой идентификатор** выберите **Электронная почта**, **Имя и адрес** или **Телефон**, чтобы отправить в LiveRamp для разрешения личности.</span><span class="sxs-lookup"><span data-stu-id="497c7-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="497c7-132">![Соединитель LiveRamp с сопоставлением атрибутов](media/export-liveramp-segments.png "Соединитель LiveRamp с сопоставлением атрибутов")</span><span class="sxs-lookup"><span data-stu-id="497c7-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="497c7-133">Сопоставьте соответствующие атрибуты из вашей унифицированной сущности клиента с выбранным ключевым идентификатором.</span><span class="sxs-lookup"><span data-stu-id="497c7-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="497c7-134">Выберите **Добавить атрибут** для отображения дополнительных атрибутов для отправки в LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="497c7-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="497c7-135">Отправка большего количества атрибутов ключевых идентификаторов в LiveRamp, вероятно, даст вам более высокий уровень соответствия.</span><span class="sxs-lookup"><span data-stu-id="497c7-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="497c7-136">Выберите сегменты, которые вы хотите экспортировать в LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="497c7-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="497c7-137">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="497c7-137">Select **Save**.</span></span>

<span data-ttu-id="497c7-138">Сохранение экспорта не запускает экспорт сразу.</span><span class="sxs-lookup"><span data-stu-id="497c7-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="497c7-139">Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="497c7-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="497c7-140">Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="497c7-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="497c7-141">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="497c7-141">Data privacy and compliance</span></span>

<span data-ttu-id="497c7-142">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в Liveramp, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="497c7-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="497c7-143">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией Liveramp любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть.</span><span class="sxs-lookup"><span data-stu-id="497c7-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="497c7-144">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="497c7-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="497c7-145">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="497c7-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
