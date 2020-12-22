---
title: Обогащение профилей компаний сторонним обогащением Leadspace
description: Общие сведения о стороннем обогащении Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668739"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="d654e-103">Обогащение профилей компаний с помощью Leadspace (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="d654e-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="d654e-104">Leadspace — это компания, занимающаяся обработка и анализ данных, которая предоставляет платформу B2B Customer Data Platform.</span><span class="sxs-lookup"><span data-stu-id="d654e-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="d654e-105">Это позволяет клиентам с унифицированными профилями клиентов для компаний обогащать свои данные.</span><span class="sxs-lookup"><span data-stu-id="d654e-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="d654e-106">Обогащения включают дополнительные атрибуты, такие как размер компании, местоположение, отрасль и т. д.</span><span class="sxs-lookup"><span data-stu-id="d654e-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d654e-107">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="d654e-107">Prerequisites</span></span>

<span data-ttu-id="d654e-108">Чтобы настроить Leadspace должны выполняться следующие требования:</span><span class="sxs-lookup"><span data-stu-id="d654e-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="d654e-109">У вас есть активная лицензия Leadspace и "бессрочный ключ" (называемый **токеном Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="d654e-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="d654e-110">Свяжитесь напрямую с [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) для получения сведений об их продукте.</span><span class="sxs-lookup"><span data-stu-id="d654e-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="d654e-111">У вас есть разрешения [Администратор](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="d654e-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="d654e-112">У вас есть [унифицированные профили клиентов](customer-profiles.md) для компаний.</span><span class="sxs-lookup"><span data-stu-id="d654e-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="d654e-113">Настройка</span><span class="sxs-lookup"><span data-stu-id="d654e-113">Configuration</span></span>

1. <span data-ttu-id="d654e-114">В аналитике аудитории перейдите **Данные** > **Обогащение**.</span><span class="sxs-lookup"><span data-stu-id="d654e-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="d654e-115">Выберите **Обогатить мои данные** на плитке Leadspace.</span><span class="sxs-lookup"><span data-stu-id="d654e-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Симок экрана плитки Leadspace.":::

1. <span data-ttu-id="d654e-117">Выберите **Начать**, а затем введите активный **токен Leadspace** (бессрочный ключ).</span><span class="sxs-lookup"><span data-stu-id="d654e-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="d654e-118">Изучите и предоставьте свое согласие на **Конфиденциальность данных и соответствие**, установив флажок **Принимаю**.</span><span class="sxs-lookup"><span data-stu-id="d654e-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="d654e-119">Подтвердите оба ввода, выбрав **Подключиться к Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="d654e-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="d654e-120">Выберите **Сопоставить данные** и определите, какие поля из ваших унифицированных профилей следует использовать для поиска соответствующих данных компании из Leadspace.</span><span class="sxs-lookup"><span data-stu-id="d654e-120">Select **Map data** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="d654e-121">Поле **Название компании** обязательно для заполнения.</span><span class="sxs-lookup"><span data-stu-id="d654e-121">The **Name of company** field is required.</span></span> <span data-ttu-id="d654e-122">Для большей точности совпадения можно добавить до двух других полей, **Веб-сайт компании** и **Расположение компании**.</span><span class="sxs-lookup"><span data-stu-id="d654e-122">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Панель сопоставления полей Leadspace.":::
   
1. <span data-ttu-id="d654e-124">Выберите **Применить** для завершения сопоставления полей.</span><span class="sxs-lookup"><span data-stu-id="d654e-124">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="d654e-125">Выбрать **Выполнить**, чтобы обогатить профили компании.</span><span class="sxs-lookup"><span data-stu-id="d654e-125">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="d654e-126">Сколько времени займет обогащение, зависит от количества унифицированных профилей клиентов.</span><span class="sxs-lookup"><span data-stu-id="d654e-126">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="d654e-127">Результаты обогащения</span><span class="sxs-lookup"><span data-stu-id="d654e-127">Enrichment results</span></span>

<span data-ttu-id="d654e-128">После обновления обогащения вы можете просмотреть новые обновленные данные компании в разделе [Мои обогащения](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="d654e-128">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="d654e-129">Вы можете найти время последнего обновления и количество обогащенных профилей.</span><span class="sxs-lookup"><span data-stu-id="d654e-129">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="d654e-130">Вы можете получить доступ к детализированному представлению каждого обогащенного профиля, выбрав **Просмотр обогащенных данных**.</span><span class="sxs-lookup"><span data-stu-id="d654e-130">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="d654e-131">Дополнительные сведения см. в [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="d654e-131">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d654e-132">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="d654e-132">Next steps</span></span>

<span data-ttu-id="d654e-133">Основывайтесь на ваших обогащенных данных клиентов.</span><span class="sxs-lookup"><span data-stu-id="d654e-133">Build on top of your enriched customer data.</span></span> <span data-ttu-id="d654e-134">Создайте [сегменты](segments.md), [меры](measures.md) и даже [экспортируйте данные](export-destinations.md), чтобы предоставлять персонализированное взаимодействие вашим клиентам.</span><span class="sxs-lookup"><span data-stu-id="d654e-134">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d654e-135">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="d654e-135">Data privacy and compliance</span></span>

<span data-ttu-id="d654e-136">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в Leadspace, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="d654e-136">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d654e-137">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией Leadspace любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть.</span><span class="sxs-lookup"><span data-stu-id="d654e-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d654e-138">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d654e-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d654e-139">Ваш администратор Dynamics 365 Customer Insights может удалить это обогащение в любое время, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="d654e-139">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>