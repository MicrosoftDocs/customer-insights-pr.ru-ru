---
title: Экспорт данных Customer Insights в ActiveCampaign
description: Узнайте, как настроить подключение и экспорт в ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314665"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="f7767-103">Экспорт сегментов в ActiveCampaign (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="f7767-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="f7767-104">Экспортируйте сегменты единых профилей клиентов в ActiveCampaign и используйте их для маркетинговой деятельности.</span><span class="sxs-lookup"><span data-stu-id="f7767-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f7767-105">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="f7767-105">Prerequisites</span></span>

-   <span data-ttu-id="f7767-106">У вас есть [учетная запись ActiveCampaign](https://www.activecampaign.com/) и соответствующие учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="f7767-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f7767-107">У вас есть [настроенные сегменты](segments.md) в аналитике аудитории.</span><span class="sxs-lookup"><span data-stu-id="f7767-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="f7767-108">Единые профили клиентов в экспортированных сегментах содержат поле с адресом электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f7767-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f7767-109">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="f7767-109">Known limitations</span></span>

- <span data-ttu-id="f7767-110">Вы можете экспортировать до 1 миллиона профилей за один экспорт в ActiveCampaign, и это может занять до 90 минут.</span><span class="sxs-lookup"><span data-stu-id="f7767-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="f7767-111">Экспорт в ActiveCampaign ограничен сегментами.</span><span class="sxs-lookup"><span data-stu-id="f7767-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="f7767-112">Количество профилей, которые вы можете экспортировать в ActiveCampaign, зависит от вашего контракта с ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="f7767-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="f7767-113">Настройте подключение к ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="f7767-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="f7767-114">Перейти в раздел **Администрирование** > **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="f7767-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f7767-115">Выберите **Добавить подключение** и выберите **ActiveCampaign** для настройки подключения.</span><span class="sxs-lookup"><span data-stu-id="f7767-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="f7767-116">Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="f7767-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f7767-117">Имя и тип подключения описывают это подключение.</span><span class="sxs-lookup"><span data-stu-id="f7767-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f7767-118">Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.</span><span class="sxs-lookup"><span data-stu-id="f7767-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f7767-119">Укажите, кто может использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="f7767-119">Choose who can use this connection.</span></span> <span data-ttu-id="f7767-120">По умолчанию это только администраторы.</span><span class="sxs-lookup"><span data-stu-id="f7767-120">By default, it's only administrators.</span></span> <span data-ttu-id="f7767-121">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f7767-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f7767-122">Введите ваш [Ключ API ActiveCampaign и имя узла конечной точки REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="f7767-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="f7767-123">Имя узла конечной точки REST — это только имя хоста, без https://.</span><span class="sxs-lookup"><span data-stu-id="f7767-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="f7767-124">Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.</span><span class="sxs-lookup"><span data-stu-id="f7767-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f7767-125">Выберите **Подключиться** для инициализации подключения к ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="f7767-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="f7767-126">Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f7767-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f7767-127">Выберите **Сохранить**, чтобы завершить подключение.</span><span class="sxs-lookup"><span data-stu-id="f7767-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="f7767-128">Настройка экспорта</span><span class="sxs-lookup"><span data-stu-id="f7767-128">Configure an export</span></span>

<span data-ttu-id="f7767-129">Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа.</span><span class="sxs-lookup"><span data-stu-id="f7767-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="f7767-130">Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f7767-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f7767-131">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="f7767-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f7767-132">Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.</span><span class="sxs-lookup"><span data-stu-id="f7767-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f7767-133">В поле **Подключение для экспорта** выберите подключение в разделе ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="f7767-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="f7767-134">Если вы не видите название этого раздела, вам не доступны подключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="f7767-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f7767-135">Введите ваш [**Идентификатор списка ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="f7767-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="f7767-136">В разделе **Сопоставление данных** в поле **Электронная почта** выберите унифицированный профиль клиента, который представляет адрес электронной почты клиента.</span><span class="sxs-lookup"><span data-stu-id="f7767-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f7767-137">Это требуется для экспорта сегментов в ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="f7767-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="f7767-138">При желании вы можете экспортировать имя, фамилию и телефон, чтобы создавать более персонализированные электронные письма.</span><span class="sxs-lookup"><span data-stu-id="f7767-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="f7767-139">Выберите Добавить атрибут, чтобы сопоставить эти поля.</span><span class="sxs-lookup"><span data-stu-id="f7767-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="f7767-140">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f7767-140">Select **Save**.</span></span>

<span data-ttu-id="f7767-141">Сохранение экспорта не запускает экспорт сразу.</span><span class="sxs-lookup"><span data-stu-id="f7767-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f7767-142">Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f7767-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f7767-143">Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f7767-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f7767-144">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="f7767-144">Data privacy and compliance</span></span>

<span data-ttu-id="f7767-145">Когда вы разрешаете для Dynamics 365 Customer Insights передавать данные в ActiveCampaign, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="f7767-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f7767-146">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за обеспечение того, что ActiveCampaign отвечает всем вашим обязательствам по обеспечению конфиденциальности и безопасности.</span><span class="sxs-lookup"><span data-stu-id="f7767-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f7767-147">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f7767-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="f7767-148">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="f7767-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
