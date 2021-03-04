---
title: Соединитель LiveRamp
description: Узнайте, как экспортировать данные в LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 64d781f52e8124fc3e83a7b84f468830c5249cfd
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270174"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="22349-103">Соединитель LiveRamp&reg; (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="22349-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="22349-104">Активируйте свои данные в LiveRamp, чтобы соединиться с более чем 500 платформами в цифровых, социальных и телевизионных экосистемах.</span><span class="sxs-lookup"><span data-stu-id="22349-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="22349-105">Работайте со своими данными в LiveRamp для нацеливания, подавления и персонализации рекламных кампаний.</span><span class="sxs-lookup"><span data-stu-id="22349-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="22349-106">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="22349-106">Prerequisites</span></span>

- <span data-ttu-id="22349-107">Вам нужна подписка LiveRamp, чтобы использовать этот соединитель.</span><span class="sxs-lookup"><span data-stu-id="22349-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="22349-108">Чтобы получить подписку, [обратитесь в LiveRamp](https://liveramp.com/contact/) непосредственно.</span><span class="sxs-lookup"><span data-stu-id="22349-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="22349-109">[Дополнительные сведения о LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="22349-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="22349-110">Подключение к LiveRamp</span><span class="sxs-lookup"><span data-stu-id="22349-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="22349-111">В аналитике аудитории перейдите **Администрирование** > **Экспорт пунктов назначения**.</span><span class="sxs-lookup"><span data-stu-id="22349-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="22349-112">На плитке **LiveRamp** выберите **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="22349-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="22349-113">Дайте вашему месту назначения узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="22349-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="22349-114">Укажите **Имя пользователя** и **Пароль** для вашей учетной записи LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="22349-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="22349-115">Эти учетные данные могут отличаться от ваших учетных данных LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="22349-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="22349-116">Выберите **Проверить** ,чтобы проверить подключение к LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="22349-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="22349-117">После успешной проверки предоставьте свое согласие на **Конфиденциальность данных и соответствие**, установив флажок **Принимаю**.</span><span class="sxs-lookup"><span data-stu-id="22349-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="22349-118">Выберите **Далее**, чтобы настроить соединитель LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="22349-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="22349-119">Настройка соединителя</span><span class="sxs-lookup"><span data-stu-id="22349-119">Configure the connector</span></span>

1. <span data-ttu-id="22349-120">В поле **Выберите ваш ключевой идентификатор** выберите **Электронная почта**, **Имя и адрес** или **Телефон**, чтобы отправить в LiveRamp для разрешения личности.</span><span class="sxs-lookup"><span data-stu-id="22349-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="22349-121">Сопоставьте соответствующие атрибуты из вашей унифицированной сущности клиента с выбранным ключевым идентификатором.</span><span class="sxs-lookup"><span data-stu-id="22349-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="22349-122">Выберите **Добавить атрибут**, чтобы сопоставить дополнительные атрибуты для отправки в LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="22349-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="22349-123">Отправка большего количества атрибутов ключевых идентификаторов в LiveRamp, вероятно, даст вам более высокий уровень соответствия.</span><span class="sxs-lookup"><span data-stu-id="22349-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="22349-124">Выберите сегменты, которые вы хотите экспортировать в LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="22349-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="22349-125">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="22349-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="22349-126">![Соединитель LiveRamp с сопоставлением атрибутов](media/export-liveramp-segments.png "Соединитель LiveRamp с сопоставлением атрибутов")</span><span class="sxs-lookup"><span data-stu-id="22349-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="22349-127">Экспорт данных</span><span class="sxs-lookup"><span data-stu-id="22349-127">Export the data</span></span>

<span data-ttu-id="22349-128">Экспорт начнется в ближайшее время, если все предварительные условия для экспорта были выполнены.</span><span class="sxs-lookup"><span data-stu-id="22349-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="22349-129">Экспорт также будет выполняться с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="22349-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="22349-130">После успешного завершения экспорта вы можете войти в LiveRamp Onboarding, чтобы активировать и распространять свои данные.</span><span class="sxs-lookup"><span data-stu-id="22349-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="22349-131">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="22349-131">Data privacy and compliance</span></span>

<span data-ttu-id="22349-132">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в Liveramp, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="22349-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="22349-133">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией Liveramp любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть.</span><span class="sxs-lookup"><span data-stu-id="22349-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="22349-134">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="22349-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="22349-135">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="22349-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]