---
title: Найти похожих клиентов с помощью ИИ
description: Ищите похожие сегменты клиентов с помощью искусственного интеллекта.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: b9b2e7fa862b595c6a364a7208e42295b4f9df83
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268886"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="7a245-103">Похожие клиенты (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="7a245-103">Similar Customers (preview)</span></span>

<span data-ttu-id="7a245-104">Эта функция позволяет вам найти похожих клиентов в вашей клиентской базе, используя искусственный интеллект.</span><span class="sxs-lookup"><span data-stu-id="7a245-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="7a245-105">Для использования этой функции необходимо создать хотя бы один сегмент.</span><span class="sxs-lookup"><span data-stu-id="7a245-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="7a245-106">Расширение критериев существующего сегмента поможет найти клиентов, похожих на этот сегмент.</span><span class="sxs-lookup"><span data-stu-id="7a245-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="7a245-107">*Поиск похожих клиентов* использует автоматизированные средства для оценки данных и прогнозирования на основе этих данных и, следовательно, может использоваться в качестве метода профилирования, как этот термин определяется в Общем регламенте по защите данных (GDPR).</span><span class="sxs-lookup"><span data-stu-id="7a245-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="7a245-108">Использование клиентом этой функции для обработки данных может регулироваться GDPR или другими законами или правилами.</span><span class="sxs-lookup"><span data-stu-id="7a245-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="7a245-109">Вы несете ответственность за то, что использование Dynamics 365 Customer Insights, включая прогнозы, соответствует всем применимым законам и требованиям, включая законы, касающиеся конфиденциальности, личных данных, биометрических данных, защиты данных и конфиденциальности сообщений.</span><span class="sxs-lookup"><span data-stu-id="7a245-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="7a245-110">Поиск похожих клиентов</span><span class="sxs-lookup"><span data-stu-id="7a245-110">Finding similar customers</span></span>

1. <span data-ttu-id="7a245-111">В аналитике аудитории перейдите **Сегменты** и выберите сегмент, на основе которого вы хотите создать новый сегмент.</span><span class="sxs-lookup"><span data-stu-id="7a245-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="7a245-112">Это ваш *исходный сегмент*.</span><span class="sxs-lookup"><span data-stu-id="7a245-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="7a245-113">На панели действий выберите **Найти похожих клиентов**.</span><span class="sxs-lookup"><span data-stu-id="7a245-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="7a245-114">Просмотрите предлагаемое имя для нового сегмента и, при необходимости, измените его.</span><span class="sxs-lookup"><span data-stu-id="7a245-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="7a245-115">Просмотрите поля, которые определяют ваш новый сегмент.</span><span class="sxs-lookup"><span data-stu-id="7a245-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="7a245-116">Эти поля определяют основу, на которой система будет пытаться найти клиентов, похожих на ваш исходный сегмент.</span><span class="sxs-lookup"><span data-stu-id="7a245-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="7a245-117">Система выберет рекомендуемые поля по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7a245-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="7a245-118">Поля, которые могут значительно снизить производительность модели, автоматически исключаются:</span><span class="sxs-lookup"><span data-stu-id="7a245-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="7a245-119">Поля со следующими типами данных: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="7a245-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="7a245-120">Поля с кратностью (количеством элементов в поле) менее 2 или более 30</span><span class="sxs-lookup"><span data-stu-id="7a245-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="7a245-121">Выберите, если вы хотите включить **Всех клиентов** или только клиентов в **Конкретном существующем сегменте** в вашем новом сегменте.</span><span class="sxs-lookup"><span data-stu-id="7a245-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="7a245-122">Исключите клиентов из исходного сегмента, выбрав флажок **Исключить всех в исходном сегменте**.</span><span class="sxs-lookup"><span data-stu-id="7a245-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="7a245-123">По умолчанию система предлагает включать в вывод только 20% целевого размера аудитории.</span><span class="sxs-lookup"><span data-stu-id="7a245-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="7a245-124">Отредактируйте этот порог по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="7a245-124">Edit this threshold as needed.</span></span> <span data-ttu-id="7a245-125">Увеличение порога снизит точность.</span><span class="sxs-lookup"><span data-stu-id="7a245-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="7a245-126">Выберите **Выполнить** внизу страницы, чтобы запустить задачу двоичной классификации (метод машинного обучения), которая анализирует набор данных.</span><span class="sxs-lookup"><span data-stu-id="7a245-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="7a245-127">Просмотр похожих сегментов</span><span class="sxs-lookup"><span data-stu-id="7a245-127">View the similar segment</span></span>

<span data-ttu-id="7a245-128">После обработки аналогичного сегмента вы найдете новый сегмент, указанный на странице **Сегменты**.</span><span class="sxs-lookup"><span data-stu-id="7a245-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7a245-129">![Похожий сегмент клиентов](media/expanded-segment.png "Сегмент похожих клиентов")</span><span class="sxs-lookup"><span data-stu-id="7a245-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="7a245-130">Выберите **Просмотреть** на панели действий, чтобы открыть сведения сегмента.</span><span class="sxs-lookup"><span data-stu-id="7a245-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="7a245-131">Это представление содержит информацию о распределении результатов по [баллам сходства](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="7a245-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="7a245-132">Вы также найдете значения показателя сходства в разделе **Предварительный просмотр участников сегмента**.</span><span class="sxs-lookup"><span data-stu-id="7a245-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="7a245-133">Использование выходных данных аналогичного сегмента</span><span class="sxs-lookup"><span data-stu-id="7a245-133">Use the output of a similar segment</span></span>

<span data-ttu-id="7a245-134">Вы можете [работать с выходными данными аналогичного сегмента](segments.md), как вы это делаете с другими сегментами.</span><span class="sxs-lookup"><span data-stu-id="7a245-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="7a245-135">Например, экспортируйте сегмент или постройте меру.</span><span class="sxs-lookup"><span data-stu-id="7a245-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="7a245-136">Обновление и редактирование похожего сегмента</span><span class="sxs-lookup"><span data-stu-id="7a245-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="7a245-137">Чтобы обновить аналогичный сегмент, выберите его на странице **Сегменты** и выберите **Обновить** на панели действий.</span><span class="sxs-lookup"><span data-stu-id="7a245-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="7a245-138">Редактирование аналогичного сегмента приведет к повторной обработке ваших данных.</span><span class="sxs-lookup"><span data-stu-id="7a245-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="7a245-139">Ранее созданный сегмент обновляется обновленными данными.</span><span class="sxs-lookup"><span data-stu-id="7a245-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="7a245-140">Чтобы изменить аналогичный сегмент, выберите его на странице **Сегменты** и выберите **Изменить** на панели действий.</span><span class="sxs-lookup"><span data-stu-id="7a245-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="7a245-141">Примените свои изменения и выберите **Выполнить**, чтобы начать обработку.</span><span class="sxs-lookup"><span data-stu-id="7a245-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="7a245-142">Удаление похожего сегмента</span><span class="sxs-lookup"><span data-stu-id="7a245-142">Delete a similar segment</span></span>

<span data-ttu-id="7a245-143">Выберите сегмент на странице **Сегменты** и выберите **Удалить** на панели действий.</span><span class="sxs-lookup"><span data-stu-id="7a245-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="7a245-144">Затем подтвердите удаление.</span><span class="sxs-lookup"><span data-stu-id="7a245-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="7a245-145">Об оценках подобия</span><span class="sxs-lookup"><span data-stu-id="7a245-145">About similarity scores</span></span>

<span data-ttu-id="7a245-146">Бинарная классификационная модель машинного обучения присваивает оценку клиентам в аналогичном сегменте.</span><span class="sxs-lookup"><span data-stu-id="7a245-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="7a245-147">Оценка основана на сходстве с клиентами в исходном сегменте.</span><span class="sxs-lookup"><span data-stu-id="7a245-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="7a245-148">Оценки сходства ниже 0,55 соответствует клиентам, которых система классифицирует как *не похожие* на клиентов в исходном сегменте</span><span class="sxs-lookup"><span data-stu-id="7a245-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="7a245-149">Баллы сходства от 0,55 до 0,7 классифицируются как *несколько похожи*</span><span class="sxs-lookup"><span data-stu-id="7a245-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="7a245-150">Баллы сходства от 0,7 до 0,85 классифицируются как *похожие*</span><span class="sxs-lookup"><span data-stu-id="7a245-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="7a245-151">Оценки сходства от 0,85 до 1 соответствуют клиентам, которых система классифицирует как *очень похожие*</span><span class="sxs-lookup"><span data-stu-id="7a245-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="7a245-152">Клиенты с показателями сходства ниже 0,4 не включаются в результаты модели.</span><span class="sxs-lookup"><span data-stu-id="7a245-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="7a245-153">Система не считает их достаточно похожими на исходный сегмент.</span><span class="sxs-lookup"><span data-stu-id="7a245-153">The system doesn't consider them similar enough to the source segment.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]