---
title: Обогащение за счет стороннего обогащения Experian
description: Общие сведения о стороннем обогащении Experian.
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: baf3cc58a233b70c48fb94ac4a543d162f91bdd1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269576"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="20302-103">Обогащение профилей клиентов демографическими данными из Experian (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="20302-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="20302-104">Experian является мировым лидером в области потребительской и деловой кредитной отчетности и маркетинговых услуг.</span><span class="sxs-lookup"><span data-stu-id="20302-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="20302-105">Со службами Experian по обогащению данных вы можете глубже понять своих клиентов, обогатив профили клиентов демографическими данными, такими как размер семьи, доход и т. д.</span><span class="sxs-lookup"><span data-stu-id="20302-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="20302-106">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="20302-106">Prerequisites</span></span>

<span data-ttu-id="20302-107">Для настройки Experian должны выполняться следующие предварительные требования:</span><span class="sxs-lookup"><span data-stu-id="20302-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="20302-108">У вас есть активная подписка Experian.</span><span class="sxs-lookup"><span data-stu-id="20302-108">You have an active Experian subscription.</span></span> <span data-ttu-id="20302-109">Чтобы получить подписку, [обращайтесь в Experian](https://www.experian.com/marketing-services/contact) напрямую.</span><span class="sxs-lookup"><span data-stu-id="20302-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="20302-110">[Дополнительные сведения об обогащении данных Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="20302-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="20302-111">У вас есть идентификатор пользователя, идентификатор стороны и номер модели для вашей учетной записи Secure Transport (ST) с поддержкой SSH, которую компания Experian создала для вас.</span><span class="sxs-lookup"><span data-stu-id="20302-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="20302-112">У вас есть разрешения [Администратор](permissions.md#administrator) в аналитике аудитории.</span><span class="sxs-lookup"><span data-stu-id="20302-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="20302-113">Настройка</span><span class="sxs-lookup"><span data-stu-id="20302-113">Configuration</span></span>

1. <span data-ttu-id="20302-114">Перейдите в раздел **Данные** > **Обогащение** и выберите вкладку **Обнаружить**.</span><span class="sxs-lookup"><span data-stu-id="20302-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="20302-115">Выберите **Обогатить мои данные** на плитке Experian.</span><span class="sxs-lookup"><span data-stu-id="20302-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="20302-116">![Плитка Experian](media/experian-tile.png "Плитка Experian")</span><span class="sxs-lookup"><span data-stu-id="20302-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="20302-117">Выберите **Начать** и введите идентификатор пользователя, идентификатор стороны и номер модели для своей учетной записи Experian Secure Transport.</span><span class="sxs-lookup"><span data-stu-id="20302-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="20302-118">Изучите и предоставьте свое согласие на **Конфиденциальность данных и соответствие**, установив флажок **Принимаю**.</span><span class="sxs-lookup"><span data-stu-id="20302-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="20302-119">Подтвердите все введенные данные, выбрав **Применить**.</span><span class="sxs-lookup"><span data-stu-id="20302-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="20302-120">Сопоставление полей</span><span class="sxs-lookup"><span data-stu-id="20302-120">Map your fields</span></span>

1.  <span data-ttu-id="20302-121">Выберите **Добавить данные** и выберите **Набор данных клиента**, который вы хотите обогатить с помощью демографических данных из Experian.</span><span class="sxs-lookup"><span data-stu-id="20302-121">Select **Add data** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="20302-122">Вы можете выбрать сущность **Клиент**, чтобы обогатить все ваши профили клиентов, или выбрать сущность сегмента, чтобы обогатить только профили клиентов, содержащиеся в этом сегменте.</span><span class="sxs-lookup"><span data-stu-id="20302-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="20302-123">Выберите ключевые идентификаторы из **Имя и адрес**, **Электронная почта** или **Телефон**, чтобы отправить в Experian для разрешения удостоверения.</span><span class="sxs-lookup"><span data-stu-id="20302-123">Select your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="20302-124">Чем больше атрибутов ключевого идентификатора, отправляемого в Experian, тем выше вероятность совпадения.</span><span class="sxs-lookup"><span data-stu-id="20302-124">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="20302-125">Выберите **Далее** и сопоставьте соответствующие атрибуты из вашей объединенной сущности клиента для выбранных полей ключевого идентификатора.</span><span class="sxs-lookup"><span data-stu-id="20302-125">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="20302-126">Выберите **Добавить атрибут** для сопоставления любых дополнительных атрибутов, которые вы хотите отправить в Experian.</span><span class="sxs-lookup"><span data-stu-id="20302-126">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="20302-127">Выберите **Сохранить**, чтобы завершить отображение полей.</span><span class="sxs-lookup"><span data-stu-id="20302-127">Select **Save** to complete the field mapping.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="20302-128">![Сопоставление полей Experian](media/experian-field-mapping.png "Сопоставление полей Experian")</span><span class="sxs-lookup"><span data-stu-id="20302-128">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="20302-129">Результаты обогащения</span><span class="sxs-lookup"><span data-stu-id="20302-129">Enrichment results</span></span>

<span data-ttu-id="20302-130">Чтобы начать процесс обогащения, выберите **Выполнить** на панели команд.</span><span class="sxs-lookup"><span data-stu-id="20302-130">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="20302-131">Вы также можете позволить системе запускать обогащение автоматически как часть [запланированного обновления](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="20302-131">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="20302-132">Время обработки будет зависеть от размера ваших данных о клиентах и процессов обогащения, настроенных для вашей учетной записи Experian.</span><span class="sxs-lookup"><span data-stu-id="20302-132">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="20302-133">После завершения процесса обогащения вы можете просмотреть недавно обогащенные данные профилей клиентов в разделе **Мои обогащения**.</span><span class="sxs-lookup"><span data-stu-id="20302-133">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="20302-134">Кроме того, вы найдете время последнего обновления и количество обогащенных профилей.</span><span class="sxs-lookup"><span data-stu-id="20302-134">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="20302-135">Вы можете получить доступ к детализированному представлению каждого обогащенного профиля, выбрав **Просмотр обогащенных данных**.</span><span class="sxs-lookup"><span data-stu-id="20302-135">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="20302-136">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="20302-136">Next steps</span></span>

<span data-ttu-id="20302-137">Основывайтесь на ваших обогащенных данных клиентов.</span><span class="sxs-lookup"><span data-stu-id="20302-137">Build on top of your enriched customer data.</span></span> <span data-ttu-id="20302-138">Создайте [сегменты](segments.md), [меры](measures.md) и даже [экспортируйте данные](export-destinations.md), чтобы предоставлять персонализированное взаимодействие вашим клиентам.</span><span class="sxs-lookup"><span data-stu-id="20302-138">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="20302-139">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="20302-139">Data privacy and compliance</span></span>

<span data-ttu-id="20302-140">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в Experian, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="20302-140">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="20302-141">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией Experian любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть.</span><span class="sxs-lookup"><span data-stu-id="20302-141">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="20302-142">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="20302-142">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="20302-143">Ваш администратор Dynamics 365 Customer Insights может удалить это обогащение в любое время, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="20302-143">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]