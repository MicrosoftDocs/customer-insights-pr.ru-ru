---
title: Экспорт данных Customer Insights в Google Ads
description: Узнайте, как настроить подключение к Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568490"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="7e2e9-103">Соединитель для Google Ads (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="7e2e9-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="7e2e9-104">Экспортируйте сегменты унифицированных профилей клиентов в список аудитории Google Ads и используйте их для рекламы в поиске Google, Gmail, YouTube и Google Display Network.</span><span class="sxs-lookup"><span data-stu-id="7e2e9-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="7e2e9-105">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="7e2e9-105">Prerequisites</span></span>

-   <span data-ttu-id="7e2e9-106">У вас есть [учетная запись Google Ads](https://ads.google.com/) и соответствующие учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="7e2e9-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="7e2e9-107">В Google Ads уже есть аудитории и соответствующие идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="7e2e9-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="7e2e9-108">Для получения дополнительной информации см. [Аудитории Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="7e2e9-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="7e2e9-109">У вас есть [настроенные сегменты](segments.md)</span><span class="sxs-lookup"><span data-stu-id="7e2e9-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="7e2e9-110">Унифицированные профили клиентов в экспортированных сегментах содержат поля, представляющие адрес электронной почты, имя и фамилию</span><span class="sxs-lookup"><span data-stu-id="7e2e9-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="7e2e9-111">Подключиться к Google Рекламе</span><span class="sxs-lookup"><span data-stu-id="7e2e9-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="7e2e9-112">Откройте **Администратор** > **Пункты назначения экспорта**.</span><span class="sxs-lookup"><span data-stu-id="7e2e9-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="7e2e9-113">Под **Google Ads** выберите **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="7e2e9-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="7e2e9-114">Дайте вашему пункту назначения экспорта узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="7e2e9-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="7e2e9-115">Введите ваш **[Идентификатор клиента Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="7e2e9-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="7e2e9-116">Введите ваш **[одобренный токен разработчика Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="7e2e9-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="7e2e9-117">Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.</span><span class="sxs-lookup"><span data-stu-id="7e2e9-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="7e2e9-118">Введите ваш **[Идентификатор аудитории Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** и выберите **Подключиться** для инициализации подключения к Google Ads.</span><span class="sxs-lookup"><span data-stu-id="7e2e9-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="7e2e9-119">Выберите **Авторизоваться в Google Ads** и укажите свои учетные данные Google Ads.</span><span class="sxs-lookup"><span data-stu-id="7e2e9-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="7e2e9-120">Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7e2e9-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Снимок экрана экспорта подключения Google Ads":::

1. <span data-ttu-id="7e2e9-122">Выберите **Далее**, чтобы настроить экспорт.</span><span class="sxs-lookup"><span data-stu-id="7e2e9-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="7e2e9-123">Настройка соединителя</span><span class="sxs-lookup"><span data-stu-id="7e2e9-123">Configure the connector</span></span>

1. <span data-ttu-id="7e2e9-124">В разделе **Сопоставление данных** в поле **Электронная почта** выберите унифицированный профиль клиента, который представляет адрес электронной почты клиента.</span><span class="sxs-lookup"><span data-stu-id="7e2e9-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="7e2e9-125">Повторите те же шаги для полей **Имя** и **Фамилия**.</span><span class="sxs-lookup"><span data-stu-id="7e2e9-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="7e2e9-126">Выберите сегменты, которые нужно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="7e2e9-126">Select the segments you want to export.</span></span> <span data-ttu-id="7e2e9-127">Всего в Google Ads можно экспортировать до 1 миллиона профилей клиентов.</span><span class="sxs-lookup"><span data-stu-id="7e2e9-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="7e2e9-128">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7e2e9-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="7e2e9-129">Экспорт данных</span><span class="sxs-lookup"><span data-stu-id="7e2e9-129">Export the data</span></span>

<span data-ttu-id="7e2e9-130">Вы можете [экспортировать данных по требованию](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="7e2e9-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="7e2e9-131">Экспорт также будет выполняться с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7e2e9-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7e2e9-132">Теперь в Google Ads вы можете найти свои сегменты в [Аудитории Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="7e2e9-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="7e2e9-133">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="7e2e9-133">Known limitations</span></span>

- <span data-ttu-id="7e2e9-134">До 1 миллиона профилей на экспорт в Google Ads.</span><span class="sxs-lookup"><span data-stu-id="7e2e9-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="7e2e9-135">Экспорт в Google Ads ограничен сегментами.</span><span class="sxs-lookup"><span data-stu-id="7e2e9-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="7e2e9-136">Экспорт сегментов с общим количеством профилей 1 миллион может занять до 5 минут из-за ограничений со стороны провайдера.</span><span class="sxs-lookup"><span data-stu-id="7e2e9-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="7e2e9-137">Сопоставление в Google Ads может занять до 48 часов.</span><span class="sxs-lookup"><span data-stu-id="7e2e9-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7e2e9-138">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="7e2e9-138">Data privacy and compliance</span></span>

<span data-ttu-id="7e2e9-139">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в Google Ads, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="7e2e9-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7e2e9-140">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией Google Ads любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть.</span><span class="sxs-lookup"><span data-stu-id="7e2e9-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="7e2e9-141">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="7e2e9-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="7e2e9-142">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="7e2e9-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
