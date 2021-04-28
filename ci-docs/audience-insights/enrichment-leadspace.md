---
title: Обогащение профилей компаний сторонним обогащением Leadspace
description: Общие сведения о стороннем обогащении Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ccf4f661ecffb281556a4545b1f26ee809c697cd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895929"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="08825-103">Обогащение профилей компаний с помощью Leadspace (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="08825-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="08825-104">Leadspace — это компания, занимающаяся обработка и анализ данных, которая предоставляет платформу B2B Customer Data Platform.</span><span class="sxs-lookup"><span data-stu-id="08825-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="08825-105">Это позволяет клиентам с унифицированными профилями клиентов для компаний обогащать свои данные.</span><span class="sxs-lookup"><span data-stu-id="08825-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="08825-106">Обогащения включают дополнительные атрибуты, такие как размер компании, местоположение, отрасль и т. д.</span><span class="sxs-lookup"><span data-stu-id="08825-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="08825-107">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="08825-107">Prerequisites</span></span>

<span data-ttu-id="08825-108">Чтобы настроить Leadspace должны выполняться следующие требования:</span><span class="sxs-lookup"><span data-stu-id="08825-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="08825-109">У вас есть активная лицензия Leadspace.</span><span class="sxs-lookup"><span data-stu-id="08825-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="08825-110">У вас есть [унифицированные профили клиентов](customer-profiles.md) для компаний.</span><span class="sxs-lookup"><span data-stu-id="08825-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="08825-111">Подключение Leadspace уже настроено администратором или у вас есть разрешения [администратора](permissions.md#administrator) и "бессрочный ключ" (именуемый **Токен Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="08825-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="08825-112">Обращайтесь напрямую в [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) для получения подробной информации об их продукте.</span><span class="sxs-lookup"><span data-stu-id="08825-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="08825-113">Настройка обогащения</span><span class="sxs-lookup"><span data-stu-id="08825-113">Configure the enrichment</span></span>

1. <span data-ttu-id="08825-114">В аналитике аудитории перейдите **Данные** > **Обогащение**.</span><span class="sxs-lookup"><span data-stu-id="08825-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="08825-115">Выберите **Обогатить данные** на плитке Leadspace, затем выберите **Начать**.</span><span class="sxs-lookup"><span data-stu-id="08825-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Симок экрана плитки Leadspace.":::

1. <span data-ttu-id="08825-117">Выберите [подключение](connections.md) из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="08825-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="08825-118">Свяжитесь с администратором, если подключение недоступно.</span><span class="sxs-lookup"><span data-stu-id="08825-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="08825-119">Если вы администратор, вы можете создать подключение, выбрав **Добавить подключение** и выбрав **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="08825-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="08825-120">Выберите **Подключиться к Leadspace** для подтверждения подключения.</span><span class="sxs-lookup"><span data-stu-id="08825-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="08825-121">Выберите **Далее** и выберите **Набор данных клиента**, который вы хотите обогатить данными о компаниях от Leadspace.</span><span class="sxs-lookup"><span data-stu-id="08825-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="08825-122">Вы можете выбрать сущность **Клиент**, чтобы обогатить все ваши профили клиентов, или выбрать сущность сегмента, чтобы обогатить только профили клиентов, содержащиеся в этом сегменте.</span><span class="sxs-lookup"><span data-stu-id="08825-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Снимок экрана при выборе набора данных клиента.":::

1. <span data-ttu-id="08825-124">Выберите **Далее** и определите, какие поля из ваших унифицированных профилей следует использовать для поиска совпадающих данных о компаниях из Leadspace.</span><span class="sxs-lookup"><span data-stu-id="08825-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="08825-125">Поле **Название компании** обязательно для заполнения.</span><span class="sxs-lookup"><span data-stu-id="08825-125">The **Name of company** field is required.</span></span> <span data-ttu-id="08825-126">Для большей точности совпадения можно добавить до двух других полей, **Веб-сайт компании** и **Расположение компании**.</span><span class="sxs-lookup"><span data-stu-id="08825-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Панель сопоставления полей Leadspace.":::

1. <span data-ttu-id="08825-128">Выберите **Далее**, чтобы завершить сопоставление полей.</span><span class="sxs-lookup"><span data-stu-id="08825-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="08825-129">Введите имя обогащения и выберите **Сохранить обогащение** после просмотра вашего выбора.</span><span class="sxs-lookup"><span data-stu-id="08825-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="08825-130">Настройка подключения для Leadspace</span><span class="sxs-lookup"><span data-stu-id="08825-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="08825-131">Чтобы настраивать подключения, вы должны быть администратором.</span><span class="sxs-lookup"><span data-stu-id="08825-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="08825-132">Выберите **Добавить подключение** при настройке обогащения *или* перейдите в раздел **Администрирование** > **Подключения** и выберите **Настроить** на плитке Leadspace.</span><span class="sxs-lookup"><span data-stu-id="08825-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="08825-133">Выберите **Начать**</span><span class="sxs-lookup"><span data-stu-id="08825-133">Select **Get Started**</span></span> 

1. <span data-ttu-id="08825-134">Введите имя для подключения в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="08825-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="08825-135">Введите действительный токен Leadspace.</span><span class="sxs-lookup"><span data-stu-id="08825-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="08825-136">Изучите текст **Соответствие и конфиденциальность данных** и предоставьте свое согласие, установив флажок **Принимаю**</span><span class="sxs-lookup"><span data-stu-id="08825-136">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="08825-137">Выберите **Проверить** для проверки конфигурации.</span><span class="sxs-lookup"><span data-stu-id="08825-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="08825-138">После завершения проверки выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="08825-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Страница настройки подключения Leadspace.":::

## <a name="enrichment-results"></a><span data-ttu-id="08825-140">Результаты обогащения</span><span class="sxs-lookup"><span data-stu-id="08825-140">Enrichment results</span></span>

<span data-ttu-id="08825-141">После обновления обогащения вы можете просмотреть новые обновленные данные компании в разделе [Мои обогащения](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="08825-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="08825-142">Вы можете найти время последнего обновления и количество обогащенных профилей.</span><span class="sxs-lookup"><span data-stu-id="08825-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="08825-143">Вы можете получить доступ к детализированному представлению каждого обогащенного профиля, выбрав **Просмотр обогащенных данных**.</span><span class="sxs-lookup"><span data-stu-id="08825-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="08825-144">Дополнительные сведения см. в [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="08825-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="08825-145">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="08825-145">Next steps</span></span>

<span data-ttu-id="08825-146">Основывайтесь на ваших обогащенных данных клиентов.</span><span class="sxs-lookup"><span data-stu-id="08825-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="08825-147">Создайте [сегменты](segments.md), [меры](measures.md) и даже [экспортируйте данные](export-destinations.md), чтобы предоставлять персонализированное взаимодействие вашим клиентам.</span><span class="sxs-lookup"><span data-stu-id="08825-147">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="08825-148">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="08825-148">Data privacy and compliance</span></span>

<span data-ttu-id="08825-149">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в Leadspace, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="08825-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="08825-150">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией Leadspace любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть.</span><span class="sxs-lookup"><span data-stu-id="08825-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="08825-151">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="08825-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="08825-152">Ваш администратор Dynamics 365 Customer Insights может удалить это обогащение в любое время, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="08825-152">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
