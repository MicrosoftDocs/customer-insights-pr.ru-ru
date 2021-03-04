---
title: Экспорт данных Customer Insights в Mailchimp
description: Узнайте, как настроить подключение к Mailchimp.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2b465b32fa956e3f45a23f471dc3a3183def16ef
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267189"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="c2300-103">Соединитель для Mailchimp (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="c2300-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="c2300-104">Экспортируйте сегменты унифицированных профилей клиентов в Mailchimp для создания информационных бюллетеней и кампаний по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="c2300-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c2300-105">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="c2300-105">Prerequisites</span></span>

-   <span data-ttu-id="c2300-106">У вас есть [учетная запись Mailchimp](https://mailchimp.com/) и соответствующие учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="c2300-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c2300-107">В Mailchimp уже есть аудитории и соответствующие идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="c2300-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="c2300-108">Для получения дополнительной информации см. [Аудитории Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="c2300-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="c2300-109">У вас есть [настроенные сегменты](segments.md)</span><span class="sxs-lookup"><span data-stu-id="c2300-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="c2300-110">Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c2300-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="c2300-111">Подключиться к Mailchimp</span><span class="sxs-lookup"><span data-stu-id="c2300-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="c2300-112">Откройте **Администратор** > **Пункты назначения экспорта**.</span><span class="sxs-lookup"><span data-stu-id="c2300-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c2300-113">Под **Mailchimp** выберите **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="c2300-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="c2300-114">Дайте вашему пункту назначения экспорта узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="c2300-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="c2300-115">Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.</span><span class="sxs-lookup"><span data-stu-id="c2300-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c2300-116">Введите ваш **[Идентификатор аудитории Mailchimp](https://mailchimp.com/help/find-audience-id/)** и выберите **Подключиться** для инициализации подключения к Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="c2300-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="c2300-117">Выберите **Авторизоваться в Mailchimp** и укажите свои учетные данные Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="c2300-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="c2300-118">Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c2300-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Снимок экрана экспорта подключения Mailchimp":::

1. <span data-ttu-id="c2300-120">Выберите **Далее**, чтобы настроить экспорт.</span><span class="sxs-lookup"><span data-stu-id="c2300-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="c2300-121">Настройка соединителя</span><span class="sxs-lookup"><span data-stu-id="c2300-121">Configure the connector</span></span>

1. <span data-ttu-id="c2300-122">В разделе **Сопоставление данных** в поле **Электронная почта** выберите унифицированный профиль клиента, который представляет адрес электронной почты клиента.</span><span class="sxs-lookup"><span data-stu-id="c2300-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="c2300-123">По желанию вы можете экспортировать **Имя** и **Фамилия** в качестве дополнительных полей для создания более персонализированных писем.</span><span class="sxs-lookup"><span data-stu-id="c2300-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="c2300-124">Выберите **Добавить атрибут**, чтобы сопоставить эти поля.</span><span class="sxs-lookup"><span data-stu-id="c2300-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="c2300-125">Выберите сегменты, которые нужно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="c2300-125">Select the segments you want to export.</span></span> <span data-ttu-id="c2300-126">Всего в Mailchimp можно экспортировать до 1 миллиона профилей клиентов.</span><span class="sxs-lookup"><span data-stu-id="c2300-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Выберите поля и сегменты для экспорта в Mailchimp":::

1. <span data-ttu-id="c2300-128">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c2300-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c2300-129">Экспорт данных</span><span class="sxs-lookup"><span data-stu-id="c2300-129">Export the data</span></span>

<span data-ttu-id="c2300-130">Вы можете [экспортировать данных по требованию](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c2300-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="c2300-131">Экспорт также будет выполняться с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c2300-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c2300-132">Теперь в Mailchimp вы можете найти свои сегменты в [Аудитории Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="c2300-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c2300-133">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="c2300-133">Known limitations</span></span>

- <span data-ttu-id="c2300-134">До 1 миллиона профилей на экспорт в Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="c2300-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="c2300-135">Экспорт в Mailchimp ограничен сегментами.</span><span class="sxs-lookup"><span data-stu-id="c2300-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="c2300-136">Экспорт сегментов с общим количеством профилей 1 миллион может занять до трех часов из-за ограничений со стороны провайдера.</span><span class="sxs-lookup"><span data-stu-id="c2300-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="c2300-137">Количество профилей, которые вы можете экспортировать в Mailchimp, зависит и ограничивается вашим контрактом с Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="c2300-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c2300-138">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="c2300-138">Data privacy and compliance</span></span>

<span data-ttu-id="c2300-139">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в Mailchimp, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="c2300-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c2300-140">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией Mailchimp любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть.</span><span class="sxs-lookup"><span data-stu-id="c2300-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c2300-141">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c2300-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c2300-142">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="c2300-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]