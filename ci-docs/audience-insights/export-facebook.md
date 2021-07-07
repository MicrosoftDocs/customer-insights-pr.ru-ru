---
title: Экспорт данных Customer Insights в Facebook Ads Manager
description: Узнайте, как настроить подключение и экспорт в Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e20c7b7fd3989d7621cb7765f38b85c8ab4adfcb
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305126"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="a0cc3-103">Экспорт списка сегментов в Facebook Ads Manager (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="a0cc3-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="a0cc3-104">Экспортируйте сегменты унифицированных профилей клиентов в Facebook Ads Manager для создания кампаний в Facebook и Instagram.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="a0cc3-105">Предварительные требования для подключения</span><span class="sxs-lookup"><span data-stu-id="a0cc3-105">Prerequisites for connection</span></span>

- <span data-ttu-id="a0cc3-106">У вас должен быть [**рекламный аккаунт Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), включающий в себя [**аккаунт Facebook Business**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="a0cc3-106">You need to have a [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="a0cc3-107">Вы должны быть администратором [**рекламного аккаунта Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="a0cc3-107">You need to be an administrator on the [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a0cc3-108">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="a0cc3-108">Known limitations</span></span>

- <span data-ttu-id="a0cc3-109">До 10 миллионов профилей клиентов на экспорт в Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-109">Up to 10 million customer profiles per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="a0cc3-110">Экспорт в Facebook Ads Manager ограничен сегментами.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="a0cc3-111">Создайте или обновите индивидуализированные аудитории в Facebook типа только *список клиентов*.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="a0cc3-112">Экспорт сегментов с общим количеством профилей 10 миллион может занять до 90 минут.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="a0cc3-113">Настройка подключения к Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="a0cc3-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="a0cc3-114">Прежде чем пользователи смогут создать экспорт, администратор должен настроить подключение к службе и разрешить участникам использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="a0cc3-115">Перейти в раздел **Администрирование** > **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a0cc3-116">Выберите **Добавить подключение** и выберите **Facebook Ads Manager** для настройки подключения.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="a0cc3-117">Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a0cc3-118">Имя и тип подключения описывают это подключение.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a0cc3-119">Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a0cc3-120">Укажите, кто может использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-120">Choose who can use this connection.</span></span> <span data-ttu-id="a0cc3-121">Если вы не предпримете никаких действий, по умолчанию это будут администраторы.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a0cc3-122">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a0cc3-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a0cc3-123">Проверка подлинности с помощью Facebook Ads:</span><span class="sxs-lookup"><span data-stu-id="a0cc3-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="a0cc3-124">Выберите **Продолжить с Facebook**, чтобы войти в свой рекламный аккаунт Facebook.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-124">Select **Continue with Facebook** to sign in to your Facebook Ads account.</span></span>

   1. <span data-ttu-id="a0cc3-125">Дайте разрешение **ads_management** после аутентификации с Facebook.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="a0cc3-126">Выберите **рекламный аккаунт Facebook**, с которым хотите работать.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="a0cc3-127">Выберите **Существующая пользовательская аудитория** из раскрывающегося списка или создайте **Новая пользовательская аудитория**.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-127">Select an **Existing custom audience** from the dropdown list or create a **New custom audience**.</span></span> <span data-ttu-id="a0cc3-128">Для получения дополнительной информации см. раздел [**Аудитории в Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="a0cc3-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="a0cc3-129">Вы можете создавать или обновлять индивидуализированные аудитории на Facebook только типа *список клиентов* с этим экспортом.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="a0cc3-130">В некоторых случаях в раскрывающемся списке отображаются пользовательские аудитории разных типов.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-130">In some cases, you see custom audiences of different types in the dropdown list.</span></span> <span data-ttu-id="a0cc3-131">Выбор типа, отличного от *список клиентов*, приведет к сбою экспорта.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="a0cc3-132">Ознакомьтесь с положениями **Соответствие и конфиденциальность данных** и выберите **Принимаю**.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="a0cc3-133">Выберите **Сохранить**, чтобы завершить подключение.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a0cc3-134">Настройка экспорта</span><span class="sxs-lookup"><span data-stu-id="a0cc3-134">Configure an export</span></span>

<span data-ttu-id="a0cc3-135">Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a0cc3-136">Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a0cc3-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a0cc3-137">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a0cc3-138">Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="a0cc3-139">В разделе **Подключение для экспорта** выберите подключение из раздела **Facebook Ads Manager**.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="a0cc3-140">Если вы не видите название этого раздела, значит, вам недоступны соединения этого типа.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-140">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="a0cc3-141">В поле **Выберите поле ключевого идентификатора** выберите **Адрес электронной почты**, **Имя и адрес** или **Телефон**, чтобы отправить в Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="a0cc3-142">Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="a0cc3-143">Сопоставьте соответствующие атрибуты из вашей унифицированной сущности клиента с выбранным ключевым идентификатором.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > [!TIP]
   > <span data-ttu-id="a0cc3-144">Наилучшие шансы на соответствие возникают, если вы выбираете **Адрес электронной почты** в качестве ключевого идентификатора.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-144">The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="a0cc3-145">Добавление дополнительных идентификаторов может улучшить сопоставление.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="a0cc3-146">Выберите **Добавить атрибут** для отображения дополнительных атрибутов для отправки в Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="a0cc3-147">Атрибуты из Facebook Ads Manager сопоставляются следующим понятным именам: **FN** = **Имя**, **LN** = **Фамилия**, **FI** = **Буква имени**, **PHONE** = **Телефон**, **GEN** = **Пол**, **DOB** = **Дата рождения**, **ST** = **Штат**, **CT** = **Город**, **ZIP** = **Почтовый индекс**, **COUNTRY** = **Страна/регион**</span><span class="sxs-lookup"><span data-stu-id="a0cc3-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / ZIP Code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="a0cc3-148">Выберите сегменты, которые нужно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="a0cc3-149">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-149">Select **Save**.</span></span>

<span data-ttu-id="a0cc3-150">Сохранение экспорта не запускает экспорт сразу.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a0cc3-151">Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a0cc3-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="a0cc3-152">Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a0cc3-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a0cc3-153">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="a0cc3-153">Data privacy and compliance</span></span>

<span data-ttu-id="a0cc3-154">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в Facebook Ads Manager, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a0cc3-155">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией Facebook Ads любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="a0cc3-156">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a0cc3-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a0cc3-157">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-157">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
