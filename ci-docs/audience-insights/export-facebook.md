---
title: Экспорт данных Customer Insights в Facebook Ads Manager
description: Узнайте, как настроить соединение с Facebook Ads Manager.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269990"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="9c6fa-103">Соединитель для Facebook Ads Manager (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="9c6fa-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="9c6fa-104">Экспортируйте сегменты унифицированных профилей клиентов в Facebook Ads Manager для создания кампаний в Facebook и Instagram.</span><span class="sxs-lookup"><span data-stu-id="9c6fa-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9c6fa-105">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="9c6fa-105">Prerequisites</span></span>

- <span data-ttu-id="9c6fa-106">У вас должен быть [**рекламный аккаунт Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), который включает в себя [**бизнес-аккаунт Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="9c6fa-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="9c6fa-107">Вы должны быть администратором на [**рекламном аккаунте Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="9c6fa-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="9c6fa-108">Присоединение к Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="9c6fa-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="9c6fa-109">Откройте **Администратор** > **Пункты назначения экспорта**.</span><span class="sxs-lookup"><span data-stu-id="9c6fa-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="9c6fa-110">В пункте **Facebook Ads Manager** выберите **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="9c6fa-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="9c6fa-111">Дайте вашему пункту назначения экспорта узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="9c6fa-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="9c6fa-112">Выберите **Продолжить с Facebook**, чтобы войти в свой рекламный аккаунт Facebook.</span><span class="sxs-lookup"><span data-stu-id="9c6fa-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="9c6fa-113">Дайте разрешение **ads_management** после аутентификации с Facebook.</span><span class="sxs-lookup"><span data-stu-id="9c6fa-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="9c6fa-114">Выберите **рекламный аккаунт Facebook**, с которым хотите работать.</span><span class="sxs-lookup"><span data-stu-id="9c6fa-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="9c6fa-115">Выберите **Существующая пользовательская аудитория** из раскрывающегося списка или создайте **Новую пользовательскую аудиторию**.</span><span class="sxs-lookup"><span data-stu-id="9c6fa-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="9c6fa-116">Для получения дополнительной информации см. раздел [**Аудитории в Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="9c6fa-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="9c6fa-117">Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.</span><span class="sxs-lookup"><span data-stu-id="9c6fa-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="9c6fa-118">Выберите **Далее**, чтобы настроить экспорт.</span><span class="sxs-lookup"><span data-stu-id="9c6fa-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="9c6fa-119">Настройка соединителя</span><span class="sxs-lookup"><span data-stu-id="9c6fa-119">Configure the connector</span></span>

1. <span data-ttu-id="9c6fa-120">В поле **Выберите поле ключевого идентификатора** выберите **Адрес электронной почты**, **Имя и адрес** или **Телефон**, чтобы отправить в Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="9c6fa-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="9c6fa-121">Сопоставьте соответствующие атрибуты из вашей унифицированной сущности клиента с выбранным ключевым идентификатором.</span><span class="sxs-lookup"><span data-stu-id="9c6fa-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="9c6fa-122">[СОВЕТ] Наилучшие шансы на соответствие возникают, если вы выбираете **Адрес электронной почты** в качестве ключевого идентификатора.</span><span class="sxs-lookup"><span data-stu-id="9c6fa-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="9c6fa-123">Добавление дополнительных идентификаторов может улучшить сопоставление.</span><span class="sxs-lookup"><span data-stu-id="9c6fa-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="9c6fa-124">Выберите **Добавить атрибут**, чтобы сопоставить дополнительные атрибуты для отправки в Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="9c6fa-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="9c6fa-125">Атрибуты из Facebook Ads Manager сопоставляются следующим понятным именам: **FN** = **Имя**, **LN** = **Фамилия**, **FI** = **Буква имени**, **PHONE** = **Телефон**, **GEN** = **Пол**, **DOB** = **Дата рождения**, **ST** = **Штат**, **CT** = **Город**, **ZIP** = **Почтовый индекс**, **COUNTRY** = **Страна/регион**</span><span class="sxs-lookup"><span data-stu-id="9c6fa-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="9c6fa-126">Выберите сегменты, которые нужно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="9c6fa-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="9c6fa-127">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9c6fa-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="9c6fa-128">Экспорт данных</span><span class="sxs-lookup"><span data-stu-id="9c6fa-128">Export the data</span></span>

<span data-ttu-id="9c6fa-129">Вы можете [экспортировать данных по требованию](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="9c6fa-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="9c6fa-130">Экспорт также будет выполняться с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9c6fa-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="9c6fa-131">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="9c6fa-131">Known limitations</span></span>

- <span data-ttu-id="9c6fa-132">До 10 млн профилей клиентов на экспорт в Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="9c6fa-132">Up to 10 million customer profile per export to Facebook Ads Manager</span></span> 
- <span data-ttu-id="9c6fa-133">Экспорт в Facebook Ads Manager ограничен сегментами</span><span class="sxs-lookup"><span data-stu-id="9c6fa-133">Export to Facebook Ads Manager is limited to segments</span></span>
- <span data-ttu-id="9c6fa-134">Экспорт сегментов с общим количеством профилей 10 миллион может занять до 90 минут.</span><span class="sxs-lookup"><span data-stu-id="9c6fa-134">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9c6fa-135">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="9c6fa-135">Data privacy and compliance</span></span>

<span data-ttu-id="9c6fa-136">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в Facebook Ads Manager, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="9c6fa-136">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9c6fa-137">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией Facebook Ads любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть.</span><span class="sxs-lookup"><span data-stu-id="9c6fa-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="9c6fa-138">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9c6fa-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9c6fa-139">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="9c6fa-139">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]