---
title: Экспорт данных Customer Insights в Snapchat
description: Узнайте, как настроить подключение и экспорт в Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6565ab81599abcc0f94465e1153f08e0bc119839
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124059"
---
# <a name="export-segments-to-snapchat-preview"></a><span data-ttu-id="46ba3-103">Экспорт сегментов в Snapchat (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="46ba3-103">Export segments to Snapchat (preview)</span></span>

<span data-ttu-id="46ba3-104">Экспортируйте сегменты унифицированных профилей клиентов в Snapchat и используйте их для рекламы.</span><span class="sxs-lookup"><span data-stu-id="46ba3-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="46ba3-105">Предварительные требования для подключения</span><span class="sxs-lookup"><span data-stu-id="46ba3-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="46ba3-106">У вас есть [учетная запись Snapchat Business](https://business.snapchat.com/), [учетная запись Snapchat Ads](https://ads.snapchat.com/) и соответствующие учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="46ba3-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="46ba3-107">У вас есть [настроенные сегменты](segments.md) в аналитике аудитории.</span><span class="sxs-lookup"><span data-stu-id="46ba3-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="46ba3-108">Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="46ba3-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="46ba3-109">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="46ba3-109">Known limitations</span></span>

- <span data-ttu-id="46ba3-110">Экспорт в Snapchat ограничен сегментами.</span><span class="sxs-lookup"><span data-stu-id="46ba3-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="46ba3-111">Экспорт до 1 миллиона профилей в Snapchat может занять до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="46ba3-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="46ba3-112">Настройка подключения к Snapchat</span><span class="sxs-lookup"><span data-stu-id="46ba3-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="46ba3-113">Перейти в раздел **Администрирование** > **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="46ba3-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="46ba3-114">Выберите **Добавить подключение** и выберите **Snapchat** для настройки подключения.</span><span class="sxs-lookup"><span data-stu-id="46ba3-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="46ba3-115">Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="46ba3-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="46ba3-116">Имя и тип подключения описывают это подключение.</span><span class="sxs-lookup"><span data-stu-id="46ba3-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="46ba3-117">Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.</span><span class="sxs-lookup"><span data-stu-id="46ba3-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="46ba3-118">Укажите, кто может использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="46ba3-118">Choose who can use this connection.</span></span> <span data-ttu-id="46ba3-119">Если вы не предпримете никаких действий, по умолчанию это будут администраторы.</span><span class="sxs-lookup"><span data-stu-id="46ba3-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="46ba3-120">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="46ba3-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="46ba3-121">Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.</span><span class="sxs-lookup"><span data-stu-id="46ba3-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="46ba3-122">Выберите **Подключить** для инициализации подключения к Snapchat.</span><span class="sxs-lookup"><span data-stu-id="46ba3-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="46ba3-123">Выберите **Проверка подлинности в Snapchat** и укажите свои учетные данные администратора для Snapchat.</span><span class="sxs-lookup"><span data-stu-id="46ba3-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="46ba3-124">Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="46ba3-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="46ba3-125">Выберите **Сохранить**, чтобы завершить подключение.</span><span class="sxs-lookup"><span data-stu-id="46ba3-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="46ba3-126">Настройка экспорта</span><span class="sxs-lookup"><span data-stu-id="46ba3-126">Configure an export</span></span>

<span data-ttu-id="46ba3-127">Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа.</span><span class="sxs-lookup"><span data-stu-id="46ba3-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="46ba3-128">Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="46ba3-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="46ba3-129">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="46ba3-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="46ba3-130">Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.</span><span class="sxs-lookup"><span data-stu-id="46ba3-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="46ba3-131">В поле **Подключение для экспорта** выберите подключение из раздела Snapchat.</span><span class="sxs-lookup"><span data-stu-id="46ba3-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="46ba3-132">Если вы не видите название этого раздела, вам не доступны подключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="46ba3-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="46ba3-133">Введите [**ИД аудитории Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="46ba3-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="46ba3-134">В разделе **Сопоставление данных** в поле **Электронная почта** выберите унифицированный профиль клиента, который представляет адрес электронной почты клиента.</span><span class="sxs-lookup"><span data-stu-id="46ba3-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="46ba3-135">Необходимо экспортировать сегменты в Snapchat.</span><span class="sxs-lookup"><span data-stu-id="46ba3-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="46ba3-136">Выберите сегменты, которые нужно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="46ba3-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="46ba3-137">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="46ba3-137">Select **Save**.</span></span>

<span data-ttu-id="46ba3-138">Сохранение экспорта не запускает экспорт сразу.</span><span class="sxs-lookup"><span data-stu-id="46ba3-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="46ba3-139">Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="46ba3-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="46ba3-140">Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="46ba3-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="46ba3-141">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="46ba3-141">Data privacy and compliance</span></span>

<span data-ttu-id="46ba3-142">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в Snapchat, вы разрешаете передачу данных за пределы границ соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="46ba3-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="46ba3-143">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за то, чтобы Snapchat выполнял любые обязательства в отношении конфиденциальности или безопасности, которые могут иметься у вас.</span><span class="sxs-lookup"><span data-stu-id="46ba3-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="46ba3-144">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="46ba3-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="46ba3-145">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="46ba3-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
