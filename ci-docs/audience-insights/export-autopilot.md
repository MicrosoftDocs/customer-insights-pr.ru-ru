---
title: Экспорт данных Customer Insights в Autopilot
description: Узнайте, как настроить подключение к Autopilot.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596147"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="0c2b8-103">Соединитель для Autopilot (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="0c2b8-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="0c2b8-104">Экспортируйте сегменты единых профилей клиентов в Autopilot и используйте их для маркетинга по электронной почте в Autopilot.</span><span class="sxs-lookup"><span data-stu-id="0c2b8-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="0c2b8-105">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="0c2b8-105">Prerequisites</span></span>

-   <span data-ttu-id="0c2b8-106">У вас есть [учетная запись Autopilot](https://www.autopilothq.com/) и соответствующие учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="0c2b8-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0c2b8-107">У вас есть [настроенные сегменты](segments.md) в аналитике аудитории.</span><span class="sxs-lookup"><span data-stu-id="0c2b8-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="0c2b8-108">Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="0c2b8-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="0c2b8-109">Подключиться к Autopilot</span><span class="sxs-lookup"><span data-stu-id="0c2b8-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="0c2b8-110">Откройте **Администратор** > **Пункты назначения экспорта**.</span><span class="sxs-lookup"><span data-stu-id="0c2b8-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="0c2b8-111">В **Autopilot** выберите **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="0c2b8-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="0c2b8-112">Дайте вашему пункту назначения экспорта узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="0c2b8-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Панель конфигурации для подключения Autopilot.":::

1. <span data-ttu-id="0c2b8-114">Введите ваш **Ключ API Autopilot** [Ключ API Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="0c2b8-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="0c2b8-115">Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.</span><span class="sxs-lookup"><span data-stu-id="0c2b8-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0c2b8-116">Выберите **Подключиться** для инициализации подключения к Autopilot.</span><span class="sxs-lookup"><span data-stu-id="0c2b8-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="0c2b8-117">Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0c2b8-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="0c2b8-118">Выберите **Далее**, чтобы настроить экспорт.</span><span class="sxs-lookup"><span data-stu-id="0c2b8-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="0c2b8-119">Настройка соединителя</span><span class="sxs-lookup"><span data-stu-id="0c2b8-119">Configure the connector</span></span>

1. <span data-ttu-id="0c2b8-120">В разделе **Сопоставление данных** в поле **Электронная почта** выберите унифицированный профиль клиента, который представляет адрес электронной почты клиента.</span><span class="sxs-lookup"><span data-stu-id="0c2b8-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="0c2b8-121">Повторите те же шаги для других необязательных полей, таких как **Имя**, **Фамилия**.</span><span class="sxs-lookup"><span data-stu-id="0c2b8-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="0c2b8-122">Выберите сегменты, которые нужно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="0c2b8-122">Select the segments you want to export.</span></span> <span data-ttu-id="0c2b8-123">Мы настоятельно **рекомендуем не экспортировать в общей сложности более 100 000 профилей клиентов** в Autopilot.</span><span class="sxs-lookup"><span data-stu-id="0c2b8-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="0c2b8-124">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0c2b8-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="0c2b8-125">Экспорт данных</span><span class="sxs-lookup"><span data-stu-id="0c2b8-125">Export the data</span></span>

<span data-ttu-id="0c2b8-126">Вы можете [экспортировать данных по требованию](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="0c2b8-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="0c2b8-127">Экспорт также будет выполняться с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0c2b8-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0c2b8-128">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="0c2b8-128">Known limitations</span></span>

- <span data-ttu-id="0c2b8-129">Всего в Autopilot можно экспортировать до 100 000 профилей.</span><span class="sxs-lookup"><span data-stu-id="0c2b8-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="0c2b8-130">Экспорт в Autopilot ограничен сегментами.</span><span class="sxs-lookup"><span data-stu-id="0c2b8-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="0c2b8-131">Экспорт до 100 000 профилей в Autopilot может занять до нескольких часов.</span><span class="sxs-lookup"><span data-stu-id="0c2b8-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="0c2b8-132">Количество профилей, которые вы можете экспортировать в Autopilot, зависит и ограничивается вашим контрактом с Autopilot.</span><span class="sxs-lookup"><span data-stu-id="0c2b8-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0c2b8-133">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="0c2b8-133">Data privacy and compliance</span></span>

<span data-ttu-id="0c2b8-134">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в Autopilot, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="0c2b8-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0c2b8-135">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией Autopilot любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть.</span><span class="sxs-lookup"><span data-stu-id="0c2b8-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="0c2b8-136">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0c2b8-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0c2b8-137">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="0c2b8-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]