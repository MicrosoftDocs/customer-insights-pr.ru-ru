---
title: Предложенные сегменты на основе действий.
description: Позвольте машинному обучению помочь вам найти новые и интересные сегменты на основе действий клиентов.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034107"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="5eb5e-103">Предложенные сегменты на основе данных о действиях (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="5eb5e-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="5eb5e-104">Откройте для себя интересные сегменты своих клиентов на основе данных о действиях клиентов, которые поступают в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="5eb5e-105">Примерами данных о действиях являются транзакции, продолжительность обращения в службу поддержки, покупки или возврат.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="5eb5e-106">Чтобы предложить сегменты, данные о действиях анализируются на предмет новизны, частоты и денежной ценности (или продолжительности).</span><span class="sxs-lookup"><span data-stu-id="5eb5e-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="5eb5e-107">В качестве альтернативы вы можете сгенерировать [предлагаемые сегменты, чтобы улучшить показатель или лучше понять, что влияет на атрибут](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="5eb5e-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Вкладка «Предлагаемые сегменты», на которой показаны предложения для сегментов на основе действий и атрибутов.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="5eb5e-109">Классификация клиентов по действиям</span><span class="sxs-lookup"><span data-stu-id="5eb5e-109">Categorize customers by activity</span></span>

<span data-ttu-id="5eb5e-110">С помощью [данных о действиях](activities.md), доступных в Customer Insights, мы можем генерировать предложения, которые представляют группы клиентов:</span><span class="sxs-lookup"><span data-stu-id="5eb5e-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="5eb5e-111">наиболее активные клиенты</span><span class="sxs-lookup"><span data-stu-id="5eb5e-111">most active customers</span></span> 
- <span data-ttu-id="5eb5e-112">клиенты, совершившие наибольшее количество покупок</span><span class="sxs-lookup"><span data-stu-id="5eb5e-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="5eb5e-113">клиенты, которые принесли наибольший доход</span><span class="sxs-lookup"><span data-stu-id="5eb5e-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="5eb5e-114">клиенты, которые не были активны в последнее время</span><span class="sxs-lookup"><span data-stu-id="5eb5e-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="5eb5e-115">клиенты, которые часто взаимодействуют с вашим бизнесом</span><span class="sxs-lookup"><span data-stu-id="5eb5e-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="5eb5e-116">Если у вас есть розничный бизнес, вы можете выяснить, какие клиенты приносят наибольший доход, и вознаградить их купоном.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="5eb5e-117">Или вы можете найти случайных клиентов и предложить им присоединиться к программе вознаграждений, чтобы они чаще посещали ваш бизнес.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="5eb5e-118">Если вы работаете в сфере здравоохранения, предоставляя услуги здравоохранения, и ваша цель — минимизировать расходы для отдельных пациентов.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="5eb5e-119">Одним из способов сделать это может быть сокращение повторяющихся посещений за счет предоставления наилучшего ухода за минимально возможное количество посещений.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="5eb5e-120">В этом случае ваша цель — снизить частоту посещений и свести к минимуму повторяющиеся расходы для пациентов.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="5eb5e-121">Или вы можете определить сегменты пациентов, которые часто обращаются к врачу и имеют высокие текущие расходы, и анализировать эти случаи, чтобы улучшить лечение отдельного человека.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="5eb5e-122">Необходимые данные</span><span class="sxs-lookup"><span data-stu-id="5eb5e-122">Required data</span></span>

<span data-ttu-id="5eb5e-123">Предложения генерируются на основе выбранных входных данных.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="5eb5e-124">Профили клиентов: все клиенты или участники определенного сегмента.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="5eb5e-125">Период времени: прошлый месяц, прошлый год или любой настраиваемый интервал времени.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="5eb5e-126">Тип действий: покупки, розничные транзакции, онлайн-транзакции, обращения в службу поддержки, подписки и т. д.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="5eb5e-127">Сущность в Customer Insights, содержащая данные о действиях: сущность UnifiedActivity или сущность для определенного действия.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="5eb5e-128">Включаемые измерения: недавность, периодичность или денежное выражение, в зависимости от требований вашего бизнеса.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="5eb5e-129">Создание предлагаемых сегментов</span><span class="sxs-lookup"><span data-stu-id="5eb5e-129">Generate suggested segments</span></span>

1. <span data-ttu-id="5eb5e-130">Перейдите **Сегменты**.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="5eb5e-131">Выберите вкладку **Предложения (предварительная версия)**.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="5eb5e-132">Выберите **Найти новые предложения** и выберите **Просмотр или прогнозирование поведения клиента**.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="5eb5e-133">Выберите **Запустить** для запуска управляемого опыта.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Первый шаг мастера настройки для предлагаемого сегмента на основе действий.":::

1. <span data-ttu-id="5eb5e-135">Введите необходимые входные данные и выберите **Далее** для продолжения.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="5eb5e-136">Выберите клиентов: включите всех клиентов или определенный сегмент.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="5eb5e-137">Выберите действие: выберите тип действия и сущности, которые описывают действие.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="5eb5e-138">Предпочтения: установите период времени для рассмотрения, факторы для предложений и сопоставьте атрибуты.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="5eb5e-139">Просмотрите свои входные данные и выберите **Запустить** для запуска модели и создания предложений.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="5eb5e-140">В зависимости от количества профилей клиентов и выбранных действий это может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="5eb5e-141">После создания предложений вы можете отфильтровать их по аналитике или значению, которые вас больше всего интересуют.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="5eb5e-142">Просмотр сведений о предлагаемом сегменте</span><span class="sxs-lookup"><span data-stu-id="5eb5e-142">View details of a suggested segment</span></span>

<span data-ttu-id="5eb5e-143">После того, как предложения будут сгенерированы, вы найдете их в списке в пункте **Сегменты** > **Предложения (предварительная версия)** в разделе **Предложения на основе действий**.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Развернутая боковая панель с подробными данными предлагаемого сегмента.":::

<span data-ttu-id="5eb5e-145">Выберите **Показать предложение** на предложенном сегменте, чтобы просмотреть подробные сведения об этом сегменте.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="5eb5e-146">На боковой панели представлены такие подробности, как размер каждого измерения по сравнению с целевой группой.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="5eb5e-147">Он также указывает на количество потенциальных участников в сегменте и соответствующий процент от общего числа клиентов.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="5eb5e-148">Если вы хотите сохранить предложение как сегмент, выберите **Создать сегмент**.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="5eb5e-149">Сохранение предложения в качестве сегмента</span><span class="sxs-lookup"><span data-stu-id="5eb5e-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="5eb5e-150">Перейдите **Сегменты** > **Предложения (предварительная версия)**.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="5eb5e-151">Выберите сегмент для сохранения.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="5eb5e-152">На боковой панели выберите **Создать сегмент**.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="5eb5e-153">После сохранения сегмента он отобразится в списке сегментов на вкладке **Все сегменты**. Теперь он может быть [обновлен или удален, как и любой другой сегмент](segments.md).</span><span class="sxs-lookup"><span data-stu-id="5eb5e-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="5eb5e-154">Вы не можете редактировать детали сегмента.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-154">You can't edit the segment details.</span></span> <span data-ttu-id="5eb5e-155">Однако вы можете изменить критерии входных данных для предложений и создать различные предложения.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="5eb5e-156">Обновите или отредактируйте набор предложений</span><span class="sxs-lookup"><span data-stu-id="5eb5e-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="5eb5e-157">Перейдите к пункту **Сегменты** > **Предложения (предварительная версия)** и ищите сегмент в разделе **Предложения на основе действий**.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="5eb5e-158">Выберите **Обновить предложения** для обновления предложений, сохранив настроенные атрибуты.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="5eb5e-159">Или выберите **Изменить предложения** для изменения настроенных атрибутов.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="5eb5e-160">Система повторно запустит процесс, сгенерирует предложения по сегментам на основе последних данных и заменит текущие предложения.</span><span class="sxs-lookup"><span data-stu-id="5eb5e-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
