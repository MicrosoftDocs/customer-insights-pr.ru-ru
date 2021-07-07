---
title: Экспорт данных Customer Insights в Sendinblue
description: Узнайте, как настроить подключение и экспорт в Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314664"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="49488-103">Экспорт сегментов в Sendinblue (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="49488-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="49488-104">Экспортируйте сегменты единых профилей клиентов для создания кампаний, проведения маркетинга по электронной почте и работы с определенными группами клиентов в Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="49488-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="49488-105">Предварительные требования для подключения</span><span class="sxs-lookup"><span data-stu-id="49488-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="49488-106">У вас есть [учетная запись Sendinblue](https://www.sendinblue.com/) и соответствующие учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="49488-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="49488-107">В Sendinblue есть существующие списки и соответствующие идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="49488-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="49488-108">У вас есть [настроенные сегменты](segments.md).</span><span class="sxs-lookup"><span data-stu-id="49488-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="49488-109">Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="49488-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="49488-110">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="49488-110">Known limitations</span></span>

- <span data-ttu-id="49488-111">До 1 миллиона профилей на экспорт в Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="49488-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="49488-112">Экспорт в Sendinblue ограничен сегментами.</span><span class="sxs-lookup"><span data-stu-id="49488-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="49488-113">Экспорт сегментов с общим количеством профилей 1 миллион может занять до 90 минут.</span><span class="sxs-lookup"><span data-stu-id="49488-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="49488-114">Количество профилей, которые вы можете экспортировать в Sendinblue, зависит и ограничено вашим контрактом с Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="49488-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="49488-115">Настройка подключения к Sendinblue</span><span class="sxs-lookup"><span data-stu-id="49488-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="49488-116">Перейти в раздел **Администрирование** > **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="49488-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="49488-117">Выберите **Добавить подключение** и выберите **Sendinblue** для настройки подключения.</span><span class="sxs-lookup"><span data-stu-id="49488-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="49488-118">Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="49488-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="49488-119">Имя и тип подключения описывают это подключение.</span><span class="sxs-lookup"><span data-stu-id="49488-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="49488-120">Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.</span><span class="sxs-lookup"><span data-stu-id="49488-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="49488-121">Укажите, кто может использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="49488-121">Choose who can use this connection.</span></span> <span data-ttu-id="49488-122">По умолчанию это только администраторы.</span><span class="sxs-lookup"><span data-stu-id="49488-122">By default it's only administrators.</span></span> <span data-ttu-id="49488-123">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="49488-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="49488-124">Введите свой **[ключ API SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="49488-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="49488-125">Выберите **Принимаю**, чтобы подтвердить **Конфиденциальность и соответствие данных** и выберите **Подключить** для инициализации подключения к Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="49488-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="49488-126">Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="49488-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="49488-127">Выберите **Сохранить**, чтобы завершить подключение.</span><span class="sxs-lookup"><span data-stu-id="49488-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="49488-128">Настройка экспорта</span><span class="sxs-lookup"><span data-stu-id="49488-128">Configure an export</span></span>

<span data-ttu-id="49488-129">Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа.</span><span class="sxs-lookup"><span data-stu-id="49488-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="49488-130">Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="49488-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="49488-131">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="49488-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="49488-132">Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.</span><span class="sxs-lookup"><span data-stu-id="49488-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="49488-133">В поле **Подключение для экспорта** выберите подключение в разделе Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="49488-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="49488-134">Если вы не видите название этого раздела, вам не доступны подключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="49488-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="49488-135">Введите ваш **Идентификатор списка Sendinblue**.</span><span class="sxs-lookup"><span data-stu-id="49488-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="49488-136">В разделе **Сопоставление данных** в поле **Электронная почта** выберите унифицированный профиль клиента, который представляет адрес электронной почты клиента.</span><span class="sxs-lookup"><span data-stu-id="49488-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="49488-137">При желании вы можете экспортировать **имя**, **фамилию** и **телефон**, чтобы создавать более персонализированные электронные письма.</span><span class="sxs-lookup"><span data-stu-id="49488-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="49488-138">Выберите **Добавить атрибут**, чтобы сопоставить эти поля.</span><span class="sxs-lookup"><span data-stu-id="49488-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="49488-139">Выберите сегменты, которые нужно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="49488-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="49488-140">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="49488-140">Select **Save**.</span></span>

<span data-ttu-id="49488-141">Сохранение экспорта не запускает экспорт сразу.</span><span class="sxs-lookup"><span data-stu-id="49488-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="49488-142">Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="49488-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="49488-143">Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="49488-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="49488-144">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="49488-144">Data privacy and compliance</span></span>

<span data-ttu-id="49488-145">Когда вы разрешаете для Dynamics 365 Customer Insights передавать данные в Sendinblue, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="49488-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="49488-146">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за обеспечение того, что Sendinblue отвечает всем вашим обязательствам по обеспечению конфиденциальности и безопасности.</span><span class="sxs-lookup"><span data-stu-id="49488-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="49488-147">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="49488-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="49488-148">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="49488-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
