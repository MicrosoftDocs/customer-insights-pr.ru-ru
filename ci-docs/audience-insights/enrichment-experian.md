---
title: Обогащение за счет стороннего обогащения Experian
description: Общие сведения о стороннем обогащении Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896389"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="6e813-103">Обогащение профилей клиентов демографическими данными из Experian (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="6e813-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="6e813-104">Experian является мировым лидером в области потребительской и деловой кредитной отчетности и маркетинговых услуг.</span><span class="sxs-lookup"><span data-stu-id="6e813-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="6e813-105">Со службами Experian по обогащению данных вы можете глубже понять своих клиентов, обогатив профили клиентов демографическими данными, такими как размер семьи, доход и т. д.</span><span class="sxs-lookup"><span data-stu-id="6e813-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6e813-106">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="6e813-106">Prerequisites</span></span>

<span data-ttu-id="6e813-107">Для настройки Experian должны выполняться следующие предварительные требования:</span><span class="sxs-lookup"><span data-stu-id="6e813-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="6e813-108">У вас есть активная подписка Experian.</span><span class="sxs-lookup"><span data-stu-id="6e813-108">You have an active Experian subscription.</span></span> <span data-ttu-id="6e813-109">Чтобы получить подписку, [обращайтесь в Experian](https://www.experian.com/marketing-services/contact) напрямую.</span><span class="sxs-lookup"><span data-stu-id="6e813-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="6e813-110">[Дополнительные сведения об обогащении данных Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="6e813-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="6e813-111">Подключение Experian уже настроено администратором *или* у вас есть разрешения [администратора](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="6e813-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="6e813-112">Вам также понадобятся идентификатор пользователя, идентификатор субъекта и номер модели для вашей учетной записи Secure Transport (ST) с поддержкой SSH, которую Experian создала для вас.</span><span class="sxs-lookup"><span data-stu-id="6e813-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="6e813-113">Настройка обогащения</span><span class="sxs-lookup"><span data-stu-id="6e813-113">Configure the enrichment</span></span>

1. <span data-ttu-id="6e813-114">Перейдите в раздел **Данные** > **Обогащение** и выберите вкладку **Обнаружить**.</span><span class="sxs-lookup"><span data-stu-id="6e813-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="6e813-115">Выберите **Обогатить мои данные** на плитке Experian.</span><span class="sxs-lookup"><span data-stu-id="6e813-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6e813-116">![Плитка Experian](media/experian-tile.png "Плитка Experian")</span><span class="sxs-lookup"><span data-stu-id="6e813-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="6e813-117">Выберите [подключение](connections.md) из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="6e813-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="6e813-118">Свяжитесь с администратором, если подключение недоступно.</span><span class="sxs-lookup"><span data-stu-id="6e813-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="6e813-119">Если вы администратор, вы можете создать подключение, выбрав **Добавить подключение** и выбрав Experian из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="6e813-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="6e813-120">Выберите **Подключиться к Experian** для подтверждения выбора подключения.</span><span class="sxs-lookup"><span data-stu-id="6e813-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="6e813-121">Выберите **Далее** и выберите **Набор данных клиента**, который вы хотите обогатить демографическими данными от Experian.</span><span class="sxs-lookup"><span data-stu-id="6e813-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="6e813-122">Вы можете выбрать сущность **Клиент**, чтобы обогатить все ваши профили клиентов, или выбрать сущность сегмента, чтобы обогатить только профили клиентов, содержащиеся в этом сегменте.</span><span class="sxs-lookup"><span data-stu-id="6e813-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Снимок экрана при выборе набора данных клиента.":::

1. <span data-ttu-id="6e813-124">Выберите **Далее** и определите, какой тип полей из ваших унифицированных профилей следует использовать для поиска совпадающих демографических данных из Experian.</span><span class="sxs-lookup"><span data-stu-id="6e813-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="6e813-125">Хотя бы одно из полей **Имя и адрес**, **Телефон** или **Электронная почта** является обязательным.</span><span class="sxs-lookup"><span data-stu-id="6e813-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="6e813-126">Для более высокой точности совпадения можно добавить до двух других полей.</span><span class="sxs-lookup"><span data-stu-id="6e813-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="6e813-127">Этот выбор повлияет на поля сопоставления, к которым у вас будет доступ на следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="6e813-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="6e813-128">Чем больше атрибутов ключевого идентификатора, отправляемого в Experian, тем выше вероятность совпадения.</span><span class="sxs-lookup"><span data-stu-id="6e813-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="6e813-129">Выберите **Далее**, чтобы запустить сопоставление полей.</span><span class="sxs-lookup"><span data-stu-id="6e813-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="6e813-130">Определите, какие поля из ваших унифицированных профилей следует использовать для поиска совпадающих демографических данных из Experian.</span><span class="sxs-lookup"><span data-stu-id="6e813-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="6e813-131">Обязательные поля отмечены.</span><span class="sxs-lookup"><span data-stu-id="6e813-131">Required fields are marked.</span></span>

1. <span data-ttu-id="6e813-132">Укажите имя для обогащения и имя для выходной сущности.</span><span class="sxs-lookup"><span data-stu-id="6e813-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="6e813-133">Выберите **Сохранить обогащение** после просмотра вашего выбора.</span><span class="sxs-lookup"><span data-stu-id="6e813-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="6e813-134">Настройка подключения для Experian</span><span class="sxs-lookup"><span data-stu-id="6e813-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="6e813-135">Чтобы настраивать подключения, вы должны быть администратором.</span><span class="sxs-lookup"><span data-stu-id="6e813-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="6e813-136">Выберите **Добавить подключение** при настройке обогащения *или* перейдите в раздел **Администрирование** > **Подключения** и выберите **Настроить** на плитке Experian.</span><span class="sxs-lookup"><span data-stu-id="6e813-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="6e813-137">Выберите **Приступая к работе**.</span><span class="sxs-lookup"><span data-stu-id="6e813-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="6e813-138">Введите имя для подключения в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="6e813-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="6e813-139">Введите действительный идентификатор пользователя, идентификатор субъекта и номер модели для своей учетной записи Experian Secure Transport.</span><span class="sxs-lookup"><span data-stu-id="6e813-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="6e813-140">Изучите текст **Соответствие и конфиденциальность данных** и предоставьте свое согласие, установив флажок **Принимаю**</span><span class="sxs-lookup"><span data-stu-id="6e813-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="6e813-141">Выберите **Проверить** для проверки конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6e813-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="6e813-142">После завершения проверки выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="6e813-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Панель настройки подключения Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="6e813-144">Результаты обогащения</span><span class="sxs-lookup"><span data-stu-id="6e813-144">Enrichment results</span></span>

<span data-ttu-id="6e813-145">Чтобы начать процесс обогащения, выберите **Выполнить** на панели команд.</span><span class="sxs-lookup"><span data-stu-id="6e813-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="6e813-146">Вы также можете позволить системе запускать обогащение автоматически как часть [запланированного обновления](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6e813-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6e813-147">Время обработки будет зависеть от размера ваших данных о клиентах и процессов обогащения, настроенных для вашей учетной записи Experian.</span><span class="sxs-lookup"><span data-stu-id="6e813-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="6e813-148">После завершения процесса обогащения вы можете просмотреть недавно обогащенные данные профилей клиентов в разделе **Мои обогащения**.</span><span class="sxs-lookup"><span data-stu-id="6e813-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="6e813-149">Кроме того, вы найдете время последнего обновления и количество обогащенных профилей.</span><span class="sxs-lookup"><span data-stu-id="6e813-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="6e813-150">Вы можете получить доступ к детализированному представлению каждого обогащенного профиля, выбрав **Просмотр обогащенных данных**.</span><span class="sxs-lookup"><span data-stu-id="6e813-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6e813-151">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="6e813-151">Next steps</span></span>

<span data-ttu-id="6e813-152">Основывайтесь на ваших обогащенных данных клиентов.</span><span class="sxs-lookup"><span data-stu-id="6e813-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="6e813-153">Создайте [сегменты](segments.md), [меры](measures.md) и даже [экспортируйте данные](export-destinations.md), чтобы предоставлять персонализированное взаимодействие вашим клиентам.</span><span class="sxs-lookup"><span data-stu-id="6e813-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6e813-154">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="6e813-154">Data privacy and compliance</span></span>

<span data-ttu-id="6e813-155">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в Experian, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="6e813-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6e813-156">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией Experian любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть.</span><span class="sxs-lookup"><span data-stu-id="6e813-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="6e813-157">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6e813-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="6e813-158">Ваш администратор Dynamics 365 Customer Insights может удалить это обогащение в любое время, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="6e813-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
