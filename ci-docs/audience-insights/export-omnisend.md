---
title: Экспорт данных Customer Insights в Omnisend
description: Узнайте, как настроить подключение и экспорт в Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124541"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="7f531-103">Экспорт сегментов в Omnisend (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="7f531-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="7f531-104">Экспортируйте сегменты унифицированных профилей клиентов в Omnisend и используйте их для маркетинговых действий.</span><span class="sxs-lookup"><span data-stu-id="7f531-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7f531-105">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="7f531-105">Prerequisites</span></span>

-   <span data-ttu-id="7f531-106">У вас есть [учетная запись Omnisend](https://www.omnisend.com/) и соответствующие учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="7f531-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="7f531-107">У вас есть [настроенные сегменты](segments.md) в аналитике аудитории.</span><span class="sxs-lookup"><span data-stu-id="7f531-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="7f531-108">Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="7f531-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="7f531-109">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="7f531-109">Known limitations</span></span>

- <span data-ttu-id="7f531-110">Вы можете экспортировать до 1 миллиона профилей за один экспорт в Omnisend, и это может занять до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="7f531-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="7f531-111">Экспорт в Omnisend ограничен сегментами.</span><span class="sxs-lookup"><span data-stu-id="7f531-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="7f531-112">Количество профилей, которые вы можете экспортировать в Omnisend, зависит от вашего контракта с Omnisend.</span><span class="sxs-lookup"><span data-stu-id="7f531-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="7f531-113">Настройка подключения к Omnisend</span><span class="sxs-lookup"><span data-stu-id="7f531-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="7f531-114">Перейти в раздел **Администрирование** > **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="7f531-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="7f531-115">Выберите **Добавить подключение** и выберите **Omnisend** для настройки подключения.</span><span class="sxs-lookup"><span data-stu-id="7f531-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="7f531-116">Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="7f531-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="7f531-117">Имя и тип подключения описывают это подключение.</span><span class="sxs-lookup"><span data-stu-id="7f531-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="7f531-118">Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.</span><span class="sxs-lookup"><span data-stu-id="7f531-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="7f531-119">Укажите, кто может использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="7f531-119">Choose who can use this connection.</span></span> <span data-ttu-id="7f531-120">По умолчанию это только администраторы.</span><span class="sxs-lookup"><span data-stu-id="7f531-120">By default it's only administrators.</span></span> <span data-ttu-id="7f531-121">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="7f531-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="7f531-122">Введите [ключ API Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span><span class="sxs-lookup"><span data-stu-id="7f531-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="7f531-123">Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.</span><span class="sxs-lookup"><span data-stu-id="7f531-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="7f531-124">Выберите **Подключить** для инициализации подключения к Omnisend.</span><span class="sxs-lookup"><span data-stu-id="7f531-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="7f531-125">Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7f531-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="7f531-126">Выберите **Сохранить**, чтобы завершить подключение.</span><span class="sxs-lookup"><span data-stu-id="7f531-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="7f531-127">Настройка экспорта</span><span class="sxs-lookup"><span data-stu-id="7f531-127">Configure an export</span></span>

<span data-ttu-id="7f531-128">Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа.</span><span class="sxs-lookup"><span data-stu-id="7f531-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="7f531-129">Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="7f531-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="7f531-130">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="7f531-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7f531-131">Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.</span><span class="sxs-lookup"><span data-stu-id="7f531-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="7f531-132">В поле **Подключение для экспорта** выберите подключение из раздела Omnisend.</span><span class="sxs-lookup"><span data-stu-id="7f531-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="7f531-133">Если вы не видите название этого раздела, вам не доступны подключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="7f531-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="7f531-134">В разделе **Сопоставление данных** в поле **Электронная почта** выберите унифицированный профиль клиента, который представляет адрес электронной почты клиента.</span><span class="sxs-lookup"><span data-stu-id="7f531-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="7f531-135">Необходимо экспортировать сегменты в Omnisend.</span><span class="sxs-lookup"><span data-stu-id="7f531-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="7f531-136">При желании вы можете экспортировать поля Имя, Фамилия, Адрес, Страна/регион и почтовый индекс для создания более персонализированных сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="7f531-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="7f531-137">Выберите **Добавить атрибут**, чтобы сопоставить эти поля.</span><span class="sxs-lookup"><span data-stu-id="7f531-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="7f531-138">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7f531-138">Select **Save**.</span></span>

<span data-ttu-id="7f531-139">Сохранение экспорта не запускает экспорт сразу.</span><span class="sxs-lookup"><span data-stu-id="7f531-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="7f531-140">Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7f531-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7f531-141">Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="7f531-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7f531-142">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="7f531-142">Data privacy and compliance</span></span>

<span data-ttu-id="7f531-143">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в Omnisend, вы разрешаете передачу данных за пределы границ соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="7f531-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7f531-144">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за то, чтобы Omnisend выполнял любые обязательства в отношении конфиденциальности или безопасности, которые могут иметься у вас.</span><span class="sxs-lookup"><span data-stu-id="7f531-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="7f531-145">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="7f531-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="7f531-146">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="7f531-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
