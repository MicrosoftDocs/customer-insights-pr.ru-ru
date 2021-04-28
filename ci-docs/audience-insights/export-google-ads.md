---
title: Экспорт данных Customer Insights в Google Ads
description: Узнайте, как настроить подключение и экспорт в Google Реклама.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f4c094e486577d00d8c0c64e8527829820b335f6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759709"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="74985-103">Экспорт сегментов в Google Рекламу (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="74985-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="74985-104">Экспортируйте сегменты унифицированных профилей клиентов в список аудитории Google Ads и используйте их для рекламы в поиске Google, Gmail, YouTube и Google Display Network.</span><span class="sxs-lookup"><span data-stu-id="74985-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="74985-105">Предварительные требования для подключения</span><span class="sxs-lookup"><span data-stu-id="74985-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="74985-106">У вас есть [учетная запись Google Ads](https://ads.google.com/) и соответствующие учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="74985-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="74985-107">У вас есть [одобренный токен разработчика Google Рекламы](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="74985-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="74985-108">Вы выполняете требования [правил в отношении списков электронных адресов](https://support.google.com/adspolicy/answer/6299717)</span><span class="sxs-lookup"><span data-stu-id="74985-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="74985-109">Вы выполняете требования к [размерам списков ремаркетинга](https://support.google.com/google-ads/answer/7558048)</span><span class="sxs-lookup"><span data-stu-id="74985-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="74985-110">В Google Ads уже есть аудитории и соответствующие идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="74985-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="74985-111">Для получения дополнительной информации см. [Аудитории Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="74985-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="74985-112">У вас есть [настроенные сегменты](segments.md)</span><span class="sxs-lookup"><span data-stu-id="74985-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="74985-113">Унифицированные профили клиентов в экспортированных сегментах содержат поля, представляющие адрес электронной почты, имя и фамилию</span><span class="sxs-lookup"><span data-stu-id="74985-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="74985-114">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="74985-114">Known limitations</span></span>

- <span data-ttu-id="74985-115">До 1 миллиона профилей на экспорт в Google Ads.</span><span class="sxs-lookup"><span data-stu-id="74985-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="74985-116">Экспорт в Google Ads ограничен сегментами.</span><span class="sxs-lookup"><span data-stu-id="74985-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="74985-117">Экспорт сегментов с общим количеством профилей 1 миллион может занять до 5 минут из-за ограничений со стороны провайдера.</span><span class="sxs-lookup"><span data-stu-id="74985-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="74985-118">Сопоставление в Google Ads может занять до 48 часов.</span><span class="sxs-lookup"><span data-stu-id="74985-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="74985-119">Настройка подключения к Google Реклама</span><span class="sxs-lookup"><span data-stu-id="74985-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="74985-120">Перейти в раздел **Администрирование** > **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="74985-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="74985-121">Выберите **Добавить подключение** и выберите **Google Реклама** для настройки подключения.</span><span class="sxs-lookup"><span data-stu-id="74985-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="74985-122">Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="74985-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="74985-123">Имя и тип подключения описывают это подключение.</span><span class="sxs-lookup"><span data-stu-id="74985-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="74985-124">Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.</span><span class="sxs-lookup"><span data-stu-id="74985-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="74985-125">Укажите, кто может использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="74985-125">Choose who can use this connection.</span></span> <span data-ttu-id="74985-126">Если вы не предпримете никаких действий, по умолчанию это будут администраторы.</span><span class="sxs-lookup"><span data-stu-id="74985-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="74985-127">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="74985-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="74985-128">Введите ваш **[Идентификатор клиента Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="74985-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="74985-129">Введите ваш **[одобренный токен разработчика Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="74985-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="74985-130">Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.</span><span class="sxs-lookup"><span data-stu-id="74985-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="74985-131">Выберите **Авторизоваться в Google Ads** и укажите свои учетные данные Google Ads.</span><span class="sxs-lookup"><span data-stu-id="74985-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="74985-132">Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="74985-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="74985-133">Выберите **Сохранить**, чтобы завершить подключение.</span><span class="sxs-lookup"><span data-stu-id="74985-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="74985-134">Настройка экспорта</span><span class="sxs-lookup"><span data-stu-id="74985-134">Configure an export</span></span>

<span data-ttu-id="74985-135">Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа.</span><span class="sxs-lookup"><span data-stu-id="74985-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="74985-136">Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="74985-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="74985-137">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="74985-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="74985-138">Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.</span><span class="sxs-lookup"><span data-stu-id="74985-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="74985-139">В поле **Подключение для экспорта** выберите подключение из раздела Google Реклама.</span><span class="sxs-lookup"><span data-stu-id="74985-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="74985-140">Если вы не видите название этого раздела, вам не доступны подключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="74985-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="74985-141">Введите ваш **[Идентификатор аудитории Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** и выберите **Подключиться** для инициализации подключения к Google Ads.</span><span class="sxs-lookup"><span data-stu-id="74985-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="74985-142">В разделе **Сопоставление данных** в поле **Электронная почта** выберите унифицированный профиль клиента, который представляет адрес электронной почты клиента.</span><span class="sxs-lookup"><span data-stu-id="74985-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="74985-143">Повторите те же шаги для полей **Имя** и **Фамилия**.</span><span class="sxs-lookup"><span data-stu-id="74985-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="74985-144">Выберите сегменты, которые нужно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="74985-144">Select the segments you want to export.</span></span> <span data-ttu-id="74985-145">Всего в Google Ads можно экспортировать до 1 миллиона профилей клиентов.</span><span class="sxs-lookup"><span data-stu-id="74985-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="74985-146">Сохранение экспорта не запускает экспорт сразу.</span><span class="sxs-lookup"><span data-stu-id="74985-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="74985-147">Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="74985-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="74985-148">Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="74985-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="74985-149">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="74985-149">Data privacy and compliance</span></span>

<span data-ttu-id="74985-150">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в Google Ads, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="74985-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="74985-151">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией Google Ads любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть.</span><span class="sxs-lookup"><span data-stu-id="74985-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="74985-152">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="74985-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="74985-153">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="74985-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
