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
ms.openlocfilehash: 37d25aa038ea32b98f2d1850d7b42b701292438d
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976058"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="49937-103">Экспорт списка сегментов в Facebook Ads Manager (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="49937-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="49937-104">Экспортируйте сегменты унифицированных профилей клиентов в Facebook Ads Manager для создания кампаний в Facebook и Instagram.</span><span class="sxs-lookup"><span data-stu-id="49937-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="49937-105">Предварительные требования для подключения</span><span class="sxs-lookup"><span data-stu-id="49937-105">Prerequisites for connection</span></span>

- <span data-ttu-id="49937-106">У вас должен быть [**Рекламный аккаунт Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), включающий в себя [**аккаунт Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="49937-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="49937-107">Вы должны быть администратором на [**рекламном аккаунте Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="49937-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="49937-108">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="49937-108">Known limitations</span></span>

- <span data-ttu-id="49937-109">До 10 млн профилей клиентов на экспорт в Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="49937-109">Up to 10 million customer profile per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="49937-110">Экспорт в Facebook Ads Manager ограничен сегментами.</span><span class="sxs-lookup"><span data-stu-id="49937-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="49937-111">Создайте или обновите индивидуализированные аудитории в Facebook типа только *список клиентов*.</span><span class="sxs-lookup"><span data-stu-id="49937-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="49937-112">Экспорт сегментов с общим количеством профилей 10 миллион может занять до 90 минут.</span><span class="sxs-lookup"><span data-stu-id="49937-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="49937-113">Настройка подключения к Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="49937-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="49937-114">Прежде чем пользователи смогут создать экспорт, администратор должен настроить подключение к службе и разрешить участникам использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="49937-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="49937-115">Перейти в раздел **Администрирование** > **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="49937-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="49937-116">Выберите **Добавить подключение** и выберите **Facebook Ads Manager** для настройки подключения.</span><span class="sxs-lookup"><span data-stu-id="49937-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="49937-117">Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="49937-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="49937-118">Имя и тип подключения описывают это подключение.</span><span class="sxs-lookup"><span data-stu-id="49937-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="49937-119">Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.</span><span class="sxs-lookup"><span data-stu-id="49937-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="49937-120">Укажите, кто может использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="49937-120">Choose who can use this connection.</span></span> <span data-ttu-id="49937-121">Если вы не предпримете никаких действий, по умолчанию это будут **Администраторы**.</span><span class="sxs-lookup"><span data-stu-id="49937-121">If you take no action, the default will be **Administrators**.</span></span> <span data-ttu-id="49937-122">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="49937-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="49937-123">Проверка подлинности с помощью Facebook Ads:</span><span class="sxs-lookup"><span data-stu-id="49937-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="49937-124">Выберите **Продолжить с Facebook**, чтобы войти в свой рекламный аккаунт Facebook.</span><span class="sxs-lookup"><span data-stu-id="49937-124">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

   1. <span data-ttu-id="49937-125">Дайте разрешение **ads_management** после аутентификации с Facebook.</span><span class="sxs-lookup"><span data-stu-id="49937-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="49937-126">Выберите **рекламный аккаунт Facebook**, с которым хотите работать.</span><span class="sxs-lookup"><span data-stu-id="49937-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="49937-127">Выберите **Существующая пользовательская аудитория** из раскрывающегося списка или создайте **Новую пользовательскую аудиторию**.</span><span class="sxs-lookup"><span data-stu-id="49937-127">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="49937-128">Для получения дополнительной информации см. раздел [**Аудитории в Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="49937-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="49937-129">Вы можете создавать или обновлять индивидуализированные аудитории на Facebook только типа *список клиентов* с этим экспортом.</span><span class="sxs-lookup"><span data-stu-id="49937-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="49937-130">В некоторых случаях в раскрывающемся списке отображаются пользовательские аудитории других типов.</span><span class="sxs-lookup"><span data-stu-id="49937-130">In some cases, you see custom audiences of different types in the drop-down list.</span></span> <span data-ttu-id="49937-131">Выбор типа, отличного от *список клиентов*, приведет к сбою экспорта.</span><span class="sxs-lookup"><span data-stu-id="49937-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="49937-132">Ознакомьтесь с положениями **Соответствие и конфиденциальность данных** и выберите **Принимаю**.</span><span class="sxs-lookup"><span data-stu-id="49937-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="49937-133">Выберите **Сохранить**, чтобы завершить подключение.</span><span class="sxs-lookup"><span data-stu-id="49937-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="49937-134">Настройка экспорта</span><span class="sxs-lookup"><span data-stu-id="49937-134">Configure an export</span></span>

<span data-ttu-id="49937-135">Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа.</span><span class="sxs-lookup"><span data-stu-id="49937-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="49937-136">Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="49937-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="49937-137">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="49937-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="49937-138">Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.</span><span class="sxs-lookup"><span data-stu-id="49937-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="49937-139">В разделе **Подключение для экспорта** выберите подключение из раздела **Facebook Ads Manager**.</span><span class="sxs-lookup"><span data-stu-id="49937-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="49937-140">Если вы не видите название этого раздела, вам не доступны подключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="49937-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="49937-141">В поле **Выберите поле ключевого идентификатора** выберите **Адрес электронной почты**, **Имя и адрес** или **Телефон**, чтобы отправить в Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="49937-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="49937-142">Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="49937-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="49937-143">Сопоставьте соответствующие атрибуты из вашей унифицированной сущности клиента с выбранным ключевым идентификатором.</span><span class="sxs-lookup"><span data-stu-id="49937-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="49937-144">[СОВЕТ] Наилучшие шансы на соответствие возникают, если вы выбираете **Адрес электронной почты** в качестве ключевого идентификатора.</span><span class="sxs-lookup"><span data-stu-id="49937-144">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="49937-145">Добавление дополнительных идентификаторов может улучшить сопоставление.</span><span class="sxs-lookup"><span data-stu-id="49937-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="49937-146">Выберите **Добавить атрибут** для отображения дополнительных атрибутов для отправки в Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="49937-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="49937-147">Атрибуты из Facebook Ads Manager сопоставляются следующим понятным именам: **FN** = **Имя**, **LN** = **Фамилия**, **FI** = **Буква имени**, **PHONE** = **Телефон**, **GEN** = **Пол**, **DOB** = **Дата рождения**, **ST** = **Штат**, **CT** = **Город**, **ZIP** = **Почтовый индекс**, **COUNTRY** = **Страна/регион**</span><span class="sxs-lookup"><span data-stu-id="49937-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="49937-148">Выберите сегменты, которые нужно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="49937-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="49937-149">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="49937-149">Select **Save**.</span></span>

<span data-ttu-id="49937-150">Сохранение экспорта не запускает экспорт сразу.</span><span class="sxs-lookup"><span data-stu-id="49937-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="49937-151">Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="49937-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="49937-152">Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="49937-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="49937-153">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="49937-153">Data privacy and compliance</span></span>

<span data-ttu-id="49937-154">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в Facebook Ads Manager, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="49937-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="49937-155">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией Facebook Ads любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть.</span><span class="sxs-lookup"><span data-stu-id="49937-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="49937-156">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="49937-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="49937-157">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="49937-157">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
