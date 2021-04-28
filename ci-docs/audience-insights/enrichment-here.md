---
title: Обогащение за счет стороннего обогащения HERE Technologies
description: Общие сведения о стороннем обогащении HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896067"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="12a2c-103">Обогащение профилей клиентов с помощью HERE Technologies (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="12a2c-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="12a2c-104">HERE Technologies — компания, занимающаяся платформой определения местоположения, которая предоставляет данные и услуги, ориентированные на местоположение.</span><span class="sxs-lookup"><span data-stu-id="12a2c-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="12a2c-105">С помощью услуг по обогащению данных HERE Technologies вы можете получить более точное представление о местоположении ваших клиентов с помощью нормализации адресов, извлечения широты и долготы и т. д.</span><span class="sxs-lookup"><span data-stu-id="12a2c-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="12a2c-106">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="12a2c-106">Prerequisites</span></span>

<span data-ttu-id="12a2c-107">Для настройки обогащения HERE Technologies должны быть соблюдены следующие предварительные условия:</span><span class="sxs-lookup"><span data-stu-id="12a2c-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="12a2c-108">Требуется активная подписка HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="12a2c-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="12a2c-109">Чтобы получить подписку, вы можете [зарегистрироваться здесь](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) или [связаться с HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) напрямую.</span><span class="sxs-lookup"><span data-stu-id="12a2c-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="12a2c-110">Узнайте больше об обогащении на основе местоположения от HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="12a2c-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="12a2c-111">Есть [подключение](connections.md) HERE доступно *или* у вас есть разрешения [администратора](permissions.md#administrator) и ключ API-интерфейса HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="12a2c-111">There is a HERE [connection](connections.md) available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="12a2c-112">Настройка обогащения</span><span class="sxs-lookup"><span data-stu-id="12a2c-112">Configure the enrichment</span></span>

1. <span data-ttu-id="12a2c-113">Перейти к **Данные** > **Обогащение**.</span><span class="sxs-lookup"><span data-stu-id="12a2c-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="12a2c-114">Выберите **Обогатить данные** на плитке HERE Technologies, затем выберите **Начать**.</span><span class="sxs-lookup"><span data-stu-id="12a2c-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="12a2c-115">![Плитка HERE Technologies](media/HERE-tile.png "Плитка HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="12a2c-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="12a2c-116">Выберите [подключение](connections.md) из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="12a2c-116">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="12a2c-117">Свяжитесь с администратором, если подключение недоступно.</span><span class="sxs-lookup"><span data-stu-id="12a2c-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="12a2c-118">Если вы администратор, вы можете создать подключение, выбрав **Добавить подключение**.</span><span class="sxs-lookup"><span data-stu-id="12a2c-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="12a2c-119">Выберите **HERE Technologies** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="12a2c-119">Choose **HERE Technologies** from the drop-down.</span></span> 

1. <span data-ttu-id="12a2c-120">Выберите **Подключиться к HERE Technologies** для подтверждения выбора.</span><span class="sxs-lookup"><span data-stu-id="12a2c-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="12a2c-121">Выберите **Далее** и выберите **Набор данных клиента**, который вы хотите обогатить данными о местоположении от HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="12a2c-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="12a2c-122">Вы можете выбрать сущность **Клиент**, чтобы обогатить все ваши профили клиентов, или выбрать сущность сегмента, чтобы обогатить только профили клиентов, содержащиеся в этом сегменте.</span><span class="sxs-lookup"><span data-stu-id="12a2c-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Снимок экрана при выборе набора данных клиента.":::

1. <span data-ttu-id="12a2c-124">Выберите, хотите ли вы сопоставить поля с основным и/или дополнительным адресом.</span><span class="sxs-lookup"><span data-stu-id="12a2c-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="12a2c-125">Вы можете указать сопоставление полей для обоих адресов и обогатить профили для обоих адресов по отдельности.</span><span class="sxs-lookup"><span data-stu-id="12a2c-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="12a2c-126">Например, если есть домашний и рабочий адреса.</span><span class="sxs-lookup"><span data-stu-id="12a2c-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="12a2c-127">Выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="12a2c-127">Select **Next**.</span></span>

1. <span data-ttu-id="12a2c-128">Определите, какие поля из ваших унифицированных профилей следует использовать для поиска соответствия данные расположения от HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="12a2c-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="12a2c-129">Поля **Улица 1** и **Почтовый индекс** обязательны для выбранного основного и/или дополнительного адреса.</span><span class="sxs-lookup"><span data-stu-id="12a2c-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="12a2c-130">Для большей точности соответствия можно добавить больше полей.</span><span class="sxs-lookup"><span data-stu-id="12a2c-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="12a2c-131">![Страница конфигурации обогащения HERE Technologies](media/enrichment-HERE-configuration.png "Страница конфигурации обогащения HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="12a2c-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="12a2c-132">Выберите **Далее**, чтобы завершить сопоставление полей.</span><span class="sxs-lookup"><span data-stu-id="12a2c-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="12a2c-133">Задайте имя для обогащения.</span><span class="sxs-lookup"><span data-stu-id="12a2c-133">Provide a name for the enrichment.</span></span> 

<span data-ttu-id="12a2c-134">1. Выберите **Сохранить обогащение** после просмотра вашего выбора.</span><span class="sxs-lookup"><span data-stu-id="12a2c-134">1.Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="12a2c-135">Настройка подключения для HERE technologies</span><span class="sxs-lookup"><span data-stu-id="12a2c-135">Configure the connection for HERE technologies</span></span> 

<span data-ttu-id="12a2c-136">Чтобы настраивать подключения, вы должны быть администратором.</span><span class="sxs-lookup"><span data-stu-id="12a2c-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="12a2c-137">Выберите **Добавить подключение** при настройке обогащения *или* перейдите в раздел **Администрирование** > **Подключения** и выберите **Настроить** на плитке HERE technologies.</span><span class="sxs-lookup"><span data-stu-id="12a2c-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="12a2c-138">Введите имя для подключения в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="12a2c-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="12a2c-139">Предоставьте действующий ключ API-интерфейса HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="12a2c-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="12a2c-140">Изучите текст **Соответствие и конфиденциальность данных** и предоставьте свое согласие, установив флажок **Принимаю**</span><span class="sxs-lookup"><span data-stu-id="12a2c-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="12a2c-141">Выберите **Проверить** для проверки конфигурации.</span><span class="sxs-lookup"><span data-stu-id="12a2c-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="12a2c-142">После завершения проверки выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="12a2c-142">After completing the verification, select **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="12a2c-143">![Страница настройки подключения HERE technologies](media/enrichment-HERE-connection.png "Страница настройки подключения HERE technologies")</span><span class="sxs-lookup"><span data-stu-id="12a2c-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="12a2c-144">Результаты обогащения</span><span class="sxs-lookup"><span data-stu-id="12a2c-144">Enrichment results</span></span>

<span data-ttu-id="12a2c-145">Чтобы начать процесс обогащения, выберите **Выполнить** на панели команд.</span><span class="sxs-lookup"><span data-stu-id="12a2c-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="12a2c-146">Вы также можете позволить системе запускать обогащение автоматически как часть [запланированного обновления](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="12a2c-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="12a2c-147">Время обработки будет зависеть от объема данных вашего клиента и времени ответа API от HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="12a2c-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="12a2c-148">После завершения процесса обогащения вы можете просмотреть недавно обогащенные данные профилей клиентов в разделе **Мои обогащения**.</span><span class="sxs-lookup"><span data-stu-id="12a2c-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="12a2c-149">Кроме того, вы найдете время последнего обновления и количество обогащенных профилей.</span><span class="sxs-lookup"><span data-stu-id="12a2c-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="12a2c-150">Вы можете получить доступ к детализированному представлению каждого обогащенного профиля, выбрав **Просмотр обогащенных данных**.</span><span class="sxs-lookup"><span data-stu-id="12a2c-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="12a2c-151">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="12a2c-151">Next steps</span></span>

<span data-ttu-id="12a2c-152">Основывайтесь на ваших обогащенных данных клиентов.</span><span class="sxs-lookup"><span data-stu-id="12a2c-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="12a2c-153">Создайте [сегменты](segments.md), [меры](measures.md) и даже [экспортируйте данные](export-destinations.md), чтобы предоставлять персонализированное взаимодействие вашим клиентам.</span><span class="sxs-lookup"><span data-stu-id="12a2c-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="12a2c-154">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="12a2c-154">Data privacy and compliance</span></span>

<span data-ttu-id="12a2c-155">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в HERE Technologies, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="12a2c-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="12a2c-156">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией HERE Technologies любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть.</span><span class="sxs-lookup"><span data-stu-id="12a2c-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="12a2c-157">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="12a2c-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="12a2c-158">Ваш администратор Dynamics 365 Customer Insights может удалить это обогащение в любое время, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="12a2c-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
