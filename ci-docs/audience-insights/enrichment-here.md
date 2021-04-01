---
title: Обогащение за счет стороннего обогащения HERE Technologies
description: Общие сведения о стороннем обогащении HERE Technologies.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 8e8d6bfea4e0df54682501f60759c24c893444af
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597757"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="6d229-103">Обогащение профилей клиентов с помощью HERE Technologies (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="6d229-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="6d229-104">HERE Technologies — компания, занимающаяся платформой определения местоположения, которая предоставляет данные и услуги, ориентированные на местоположение.</span><span class="sxs-lookup"><span data-stu-id="6d229-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="6d229-105">С помощью услуг по обогащению данных HERE Technologies вы можете получить более точное представление о местоположении ваших клиентов с помощью нормализации адресов, извлечения широты и долготы и т. д.</span><span class="sxs-lookup"><span data-stu-id="6d229-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6d229-106">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="6d229-106">Prerequisites</span></span>

<span data-ttu-id="6d229-107">Для настройки обогащения HERE Technologies должны быть соблюдены следующие предварительные условия:</span><span class="sxs-lookup"><span data-stu-id="6d229-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="6d229-108">Требуется активная подписка HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="6d229-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="6d229-109">Чтобы получить подписку, вы можете [зарегистрироваться здесь](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) или [связаться с HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) напрямую.</span><span class="sxs-lookup"><span data-stu-id="6d229-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="6d229-110">Узнайте больше об обогащении на основе местоположения от HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="6d229-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="6d229-111">У вас есть ключ API HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="6d229-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="6d229-112">У вас есть разрешения [Администратор](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="6d229-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="6d229-113">Настройка</span><span class="sxs-lookup"><span data-stu-id="6d229-113">Configuration</span></span>

1. <span data-ttu-id="6d229-114">Перейти к **Данные** > **Обогащение**.</span><span class="sxs-lookup"><span data-stu-id="6d229-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="6d229-115">Выберите **Обогатить мои данные** на плитке HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="6d229-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6d229-116">![Плитка HERE Technologies](media/HERE-tile.png "Плитка HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="6d229-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="6d229-117">Введите активный **ключ API HERE Technologies**.</span><span class="sxs-lookup"><span data-stu-id="6d229-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="6d229-118">Изучите и предоставьте свое согласие на **Конфиденциальность данных и соответствие**, установив флажок **Принимаю**.</span><span class="sxs-lookup"><span data-stu-id="6d229-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="6d229-119">Подтвердите оба ввода, выбрав **Подключиться к HERE**.</span><span class="sxs-lookup"><span data-stu-id="6d229-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1.  <span data-ttu-id="6d229-120">Выберите **Добавить данные** и выберите **Набор данных клиента**, который вы хотите обогатить с помощью данных о местоположении из HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="6d229-120">Select **Add data** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="6d229-121">Вы можете выбрать сущность **Клиент**, чтобы обогатить все ваши профили клиентов, или выбрать сущность сегмента, чтобы обогатить только профили клиентов, содержащиеся в этом сегменте.</span><span class="sxs-lookup"><span data-stu-id="6d229-121">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Снимок экрана при выборе набора данных клиента.":::

1. <span data-ttu-id="6d229-123">Выберите, хотите ли вы сопоставить поля с основным и/или дополнительным адресом.</span><span class="sxs-lookup"><span data-stu-id="6d229-123">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="6d229-124">Вы можете указать сопоставление полей для обоих адресов (например, домашнего и рабочего адресов) и дополнить профили для обоих адресов по отдельности.</span><span class="sxs-lookup"><span data-stu-id="6d229-124">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="6d229-125">Выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6d229-125">Select **Next**.</span></span>

1. <span data-ttu-id="6d229-126">Определите, какие поля из ваших унифицированных профилей следует использовать для поиска соответствия данные расположения от HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="6d229-126">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="6d229-127">Поля **Улица 1** и **Почтовый индекс** обязательны для выбранного основного и/или дополнительного адреса.</span><span class="sxs-lookup"><span data-stu-id="6d229-127">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="6d229-128">Для большей точности соответствия можно добавить больше полей.</span><span class="sxs-lookup"><span data-stu-id="6d229-128">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6d229-129">![Страница конфигурации обогащения HERE Technologies](media/enrichment-HERE-configuration.png "Страница конфигурации обогащения HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="6d229-129">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="6d229-130">Выберите **Применить** для завершения сопоставления полей.</span><span class="sxs-lookup"><span data-stu-id="6d229-130">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="6d229-131">Результаты обогащения</span><span class="sxs-lookup"><span data-stu-id="6d229-131">Enrichment results</span></span>

<span data-ttu-id="6d229-132">Чтобы начать процесс обогащения, выберите **Выполнить** на панели команд.</span><span class="sxs-lookup"><span data-stu-id="6d229-132">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="6d229-133">Вы также можете позволить системе запускать обогащение автоматически как часть [запланированного обновления](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6d229-133">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6d229-134">Время обработки будет зависеть от объема данных вашего клиента и времени ответа API от HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="6d229-134">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="6d229-135">После завершения процесса обогащения вы можете просмотреть недавно обогащенные данные профилей клиентов в разделе **Мои обогащения**.</span><span class="sxs-lookup"><span data-stu-id="6d229-135">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="6d229-136">Кроме того, вы найдете время последнего обновления и количество обогащенных профилей.</span><span class="sxs-lookup"><span data-stu-id="6d229-136">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="6d229-137">Вы можете получить доступ к детализированному представлению каждого обогащенного профиля, выбрав **Просмотр обогащенных данных**.</span><span class="sxs-lookup"><span data-stu-id="6d229-137">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6d229-138">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="6d229-138">Next steps</span></span>

<span data-ttu-id="6d229-139">Основывайтесь на ваших обогащенных данных клиентов.</span><span class="sxs-lookup"><span data-stu-id="6d229-139">Build on top of your enriched customer data.</span></span> <span data-ttu-id="6d229-140">Создайте [сегменты](segments.md), [меры](measures.md) и даже [экспортируйте данные](export-destinations.md), чтобы предоставлять персонализированное взаимодействие вашим клиентам.</span><span class="sxs-lookup"><span data-stu-id="6d229-140">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6d229-141">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="6d229-141">Data privacy and compliance</span></span>

<span data-ttu-id="6d229-142">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в HERE Technologies, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="6d229-142">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6d229-143">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией HERE Technologies любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть.</span><span class="sxs-lookup"><span data-stu-id="6d229-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="6d229-144">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6d229-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="6d229-145">Ваш администратор Dynamics 365 Customer Insights может удалить это обогащение в любое время, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="6d229-145">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]