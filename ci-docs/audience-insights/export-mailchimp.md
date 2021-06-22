---
title: Экспорт данных Customer Insights в Mailchimp
description: Узнайте, как настроить подключение и экспорт в Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7922a6a69f863caae5401549ed6f88a61aa77d39
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124243"
---
# <a name="export-segments-to-mailchimp-preview"></a><span data-ttu-id="db834-103">Экспорт сегментов в Mailchimp (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="db834-103">Export segments to Mailchimp (preview)</span></span>

<span data-ttu-id="db834-104">Экспортируйте сегменты унифицированных профилей клиентов в Mailchimp для создания информационных бюллетеней и кампаний по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="db834-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="db834-105">Предварительные требования для подключения</span><span class="sxs-lookup"><span data-stu-id="db834-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="db834-106">У вас есть [учетная запись Mailchimp](https://mailchimp.com/) и соответствующие учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="db834-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="db834-107">В Mailchimp уже есть аудитории и соответствующие идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="db834-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="db834-108">Для получения дополнительной информации см. [Аудитории Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="db834-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="db834-109">У вас есть [настроенные сегменты](segments.md)</span><span class="sxs-lookup"><span data-stu-id="db834-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="db834-110">Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="db834-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="db834-111">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="db834-111">Known limitations</span></span>

- <span data-ttu-id="db834-112">До 1 миллиона профилей на экспорт в Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="db834-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="db834-113">Экспорт в Mailchimp ограничен сегментами.</span><span class="sxs-lookup"><span data-stu-id="db834-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="db834-114">Экспорт сегментов с 1 миллионом профилей может занять до трех часов.</span><span class="sxs-lookup"><span data-stu-id="db834-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="db834-115">Количество профилей, которые вы можете экспортировать в Mailchimp, зависит и ограничивается вашим контрактом с Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="db834-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="db834-116">Настройка подключения к Mailchimp</span><span class="sxs-lookup"><span data-stu-id="db834-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="db834-117">Перейти в раздел **Администрирование** > **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="db834-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="db834-118">Выберите **Добавить подключение** и выберите **Mailchimp** для настройки подключения.</span><span class="sxs-lookup"><span data-stu-id="db834-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="db834-119">Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="db834-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="db834-120">Имя и тип подключения описывают это подключение.</span><span class="sxs-lookup"><span data-stu-id="db834-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="db834-121">Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.</span><span class="sxs-lookup"><span data-stu-id="db834-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="db834-122">Укажите, кто может использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="db834-122">Choose who can use this connection.</span></span> <span data-ttu-id="db834-123">Если вы не предпримете никаких действий, по умолчанию это будут администраторы.</span><span class="sxs-lookup"><span data-stu-id="db834-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="db834-124">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="db834-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="db834-125">Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.</span><span class="sxs-lookup"><span data-stu-id="db834-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="db834-126">Выберите **Подключить** для инициализации подключения к Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="db834-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="db834-127">Выберите **Авторизоваться в Mailchimp** и укажите свои учетные данные Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="db834-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="db834-128">Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="db834-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="db834-129">Выберите **Сохранить**, чтобы завершить подключение.</span><span class="sxs-lookup"><span data-stu-id="db834-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="db834-130">Настройка соединителя</span><span class="sxs-lookup"><span data-stu-id="db834-130">Configure the connector</span></span>

<span data-ttu-id="db834-131">Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа.</span><span class="sxs-lookup"><span data-stu-id="db834-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="db834-132">Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="db834-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="db834-133">Перейдите в раздел **Данные**> **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="db834-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="db834-134">Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.</span><span class="sxs-lookup"><span data-stu-id="db834-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="db834-135">В поле **Подключение для экспорта** выберите подключение из раздела Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="db834-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="db834-136">Если вы не видите название этого раздела, вам не доступны подключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="db834-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="db834-137">Введите свой **[ИД аудитории Mailchimp](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="db834-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="db834-138">В разделе **Сопоставление данных** в поле **Электронная почта** выберите унифицированный профиль клиента, который представляет адрес электронной почты клиента.</span><span class="sxs-lookup"><span data-stu-id="db834-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="db834-139">При желании вы можете экспортировать поля **Имя** и **Фамилия** для создания более персонализированных сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="db834-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="db834-140">Выберите **Добавить атрибут**, чтобы сопоставить эти поля.</span><span class="sxs-lookup"><span data-stu-id="db834-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="db834-141">Выберите сегменты, которые нужно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="db834-141">Select the segments you want to export.</span></span> <span data-ttu-id="db834-142">Всего в Mailchimp можно экспортировать до 1 миллиона профилей клиентов.</span><span class="sxs-lookup"><span data-stu-id="db834-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="db834-143">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="db834-143">Select **Save**.</span></span>

<span data-ttu-id="db834-144">Сохранение экспорта не запускает экспорт сразу.</span><span class="sxs-lookup"><span data-stu-id="db834-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="db834-145">Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="db834-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="db834-146">Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="db834-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="db834-147">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="db834-147">Data privacy and compliance</span></span>

<span data-ttu-id="db834-148">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в Mailchimp, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="db834-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="db834-149">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией Mailchimp любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть.</span><span class="sxs-lookup"><span data-stu-id="db834-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="db834-150">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="db834-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="db834-151">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="db834-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
