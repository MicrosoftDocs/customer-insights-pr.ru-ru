---
title: Обогащение сторонним обогащением Experian
description: Общие сведения о стороннем обогащении Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309836"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="75970-103">Обогатите профили клиентов демографическими данными из Experian (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="75970-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="75970-104">Experian является мировым лидером в области потребительской и коммерческой кредитной отчетности и маркетинговых услуг.</span><span class="sxs-lookup"><span data-stu-id="75970-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="75970-105">С помощью услуг по обогащению данных Experian вы можете глубже понять своих клиентов, обогатив свои профили клиентов демографическими данными, такими как размер домохозяйства, доход и т. д.</span><span class="sxs-lookup"><span data-stu-id="75970-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="75970-106">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="75970-106">Prerequisites</span></span>

<span data-ttu-id="75970-107">Для настройки Experian должны выполняться следующие требования:</span><span class="sxs-lookup"><span data-stu-id="75970-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="75970-108">У вас есть активная подписка Experian.</span><span class="sxs-lookup"><span data-stu-id="75970-108">You have an active Experian subscription.</span></span> <span data-ttu-id="75970-109">Чтобы получить подписку, [свяжитесь с Experian](https://www.experian.com/marketing-services/contact) напрямую.</span><span class="sxs-lookup"><span data-stu-id="75970-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="75970-110">[Подробнее об обогащении данных Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="75970-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="75970-111">Подключение Experian уже настроено администратором *или* у вас есть разрешения [администратора](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="75970-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="75970-112">Вам также понадобятся идентификатор пользователя, идентификатор стороны и номер модели для вашей учетной записи Secure Transport (ST) с поддержкой SSH, которую Experian создал для вас.</span><span class="sxs-lookup"><span data-stu-id="75970-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="75970-113">Поддерживаемые страны/регионы</span><span class="sxs-lookup"><span data-stu-id="75970-113">Supported countries/regions</span></span>

<span data-ttu-id="75970-114">В настоящее время мы поддерживаем обогащение профилей клиентов только в США.</span><span class="sxs-lookup"><span data-stu-id="75970-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="75970-115">Настройка обогащения</span><span class="sxs-lookup"><span data-stu-id="75970-115">Configure the enrichment</span></span>

1. <span data-ttu-id="75970-116">Перейдите в раздел **Данные** > **Обогащение** и выберите вкладку **Обнаружить**.</span><span class="sxs-lookup"><span data-stu-id="75970-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="75970-117">Выберите **Обогатить данные** на плитке Experian.</span><span class="sxs-lookup"><span data-stu-id="75970-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="75970-118">![Experian плит](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="75970-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="75970-119">Выберите [подключение](connections.md) из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="75970-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="75970-120">Свяжитесь с администратором, если подключение недоступно.</span><span class="sxs-lookup"><span data-stu-id="75970-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="75970-121">Если вы администратор, вы можете создать соединение, выбрав **Добавить подключение** и выбрав Experian из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="75970-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="75970-122">Выберите **Подключиться к Experian** для подтверждения выбора подключения.</span><span class="sxs-lookup"><span data-stu-id="75970-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="75970-123">Выберите **Далее** и выберите **Набор данных клиента**, который вы хотите обогатить демографическими данными из Experian.</span><span class="sxs-lookup"><span data-stu-id="75970-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="75970-124">Вы можете выбрать сущность **Клиент**, чтобы обогатить все ваши профили клиентов, или выбрать сущность сегмента, чтобы обогатить только профили клиентов, содержащиеся в этом сегменте.</span><span class="sxs-lookup"><span data-stu-id="75970-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Снимок экрана при выборе набора данных клиента.":::

1. <span data-ttu-id="75970-126">Выберите **Далее** и определите, какой тип полей из ваших единых профилей следует использовать для поиска совпадающих демографических данных из Experian.</span><span class="sxs-lookup"><span data-stu-id="75970-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="75970-127">Хотя бы одно из полей **Имя и адрес**, **Телефон** или **Электронная почта** является обязательным.</span><span class="sxs-lookup"><span data-stu-id="75970-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="75970-128">Для более высокой точности совпадения можно добавить до двух других полей.</span><span class="sxs-lookup"><span data-stu-id="75970-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="75970-129">Этот выбор повлияет на поля сопоставления, к которым у вас будет доступ на следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="75970-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="75970-130">Дополнительные ключевые атрибуты идентификатора, отправленные в Experian, вероятно, дадут более высокий коэффициент соответствия.</span><span class="sxs-lookup"><span data-stu-id="75970-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="75970-131">Выберите **Далее**, чтобы запустить сопоставление полей.</span><span class="sxs-lookup"><span data-stu-id="75970-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="75970-132">Определите, какой тип полей из ваших единых профилей следует использовать для поиска совпадающих демографических данных из Experian.</span><span class="sxs-lookup"><span data-stu-id="75970-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="75970-133">Обязательные поля отмечены.</span><span class="sxs-lookup"><span data-stu-id="75970-133">Required fields are marked.</span></span>

1. <span data-ttu-id="75970-134">Укажите имя для обогащения и имя для выходной сущности.</span><span class="sxs-lookup"><span data-stu-id="75970-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="75970-135">Выберите **Сохранить обогащение** после просмотра вашего выбора.</span><span class="sxs-lookup"><span data-stu-id="75970-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="75970-136">Настройка подключения для Experian</span><span class="sxs-lookup"><span data-stu-id="75970-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="75970-137">Чтобы настраивать подключения, вы должны быть администратором.</span><span class="sxs-lookup"><span data-stu-id="75970-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="75970-138">Выберите **Добавить подключение** при настройке обогащения *или* перейдите **Администратор** > **Подключения** и выберите **Настройка** на плитке Experian.</span><span class="sxs-lookup"><span data-stu-id="75970-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="75970-139">Выберите **Приступая к работе**.</span><span class="sxs-lookup"><span data-stu-id="75970-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="75970-140">Введите имя для подключения в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="75970-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="75970-141">Введите действительный идентификатор пользователя, идентификатор стороны и номер модели для вашей учетной записи Experian Secure Transport.</span><span class="sxs-lookup"><span data-stu-id="75970-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="75970-142">Проверьте и дайте свое согласие для **Конфиденциальность и соответствие данных**, выбрав **Принимаю**.</span><span class="sxs-lookup"><span data-stu-id="75970-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="75970-143">Выберите **Проверить** для проверки конфигурации.</span><span class="sxs-lookup"><span data-stu-id="75970-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="75970-144">После завершения проверки выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="75970-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Область настройки подключения Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="75970-146">Результаты обогащения</span><span class="sxs-lookup"><span data-stu-id="75970-146">Enrichment results</span></span>

<span data-ttu-id="75970-147">Чтобы начать процесс обогащения, выберите **Выполнить** на панели команд.</span><span class="sxs-lookup"><span data-stu-id="75970-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="75970-148">Вы также можете позволить системе запускать обогащение автоматически как часть [запланированного обновления](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="75970-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="75970-149">Время обработки будет зависеть от размера ваших данных о клиентах и процессов обогащения, настроенных для вашей учетной записи со стороны Experian.</span><span class="sxs-lookup"><span data-stu-id="75970-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="75970-150">После завершения процесса обогащения вы можете просмотреть недавно обогащенные данные профилей клиентов в разделе **Мои обогащения**.</span><span class="sxs-lookup"><span data-stu-id="75970-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="75970-151">Кроме того, вы найдете время последнего обновления и количество обогащенных профилей.</span><span class="sxs-lookup"><span data-stu-id="75970-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="75970-152">Вы можете получить доступ к детализированному представлению каждого обогащенного профиля, выбрав **Просмотр обогащенных данных**.</span><span class="sxs-lookup"><span data-stu-id="75970-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="75970-153">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="75970-153">Next steps</span></span>

<span data-ttu-id="75970-154">Основывайтесь на ваших обогащенных данных клиентов.</span><span class="sxs-lookup"><span data-stu-id="75970-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="75970-155">Создайте [сегменты](segments.md) и [меры](measures.md), и даже [экспортируйте данные](export-destinations.md), чтобы предоставить вашим клиентам индивидуальный подход.</span><span class="sxs-lookup"><span data-stu-id="75970-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="75970-156">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="75970-156">Data privacy and compliance</span></span>

<span data-ttu-id="75970-157">Когда вы разрешаете для Dynamics 365 Customer Insights передавать данные в Experian, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="75970-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="75970-158">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за обеспечение того, чтобы Experian отвечает всем вашим обязательствам по обеспечению конфиденциальности и безопасности.</span><span class="sxs-lookup"><span data-stu-id="75970-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="75970-159">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="75970-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="75970-160">Ваш администратор Dynamics 365 Customer Insights может удалить это обогащение в любое время, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="75970-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
