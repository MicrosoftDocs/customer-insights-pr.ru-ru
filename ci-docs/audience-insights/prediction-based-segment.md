---
title: Сегменты на основе выходных данных прогноза
description: Создайте сегменты на основе выходной сущности модели прогноза.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741445"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="675d1-103">Создание сегмента на основе модели прогноза (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="675d1-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="675d1-104">Результаты прогнозов иногда применимы только к подмножеству ваших клиентов.</span><span class="sxs-lookup"><span data-stu-id="675d1-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="675d1-105">Повысьте персонализацию рекомендаций, создав сегменты на основе результатов моделей прогноза.</span><span class="sxs-lookup"><span data-stu-id="675d1-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="675d1-106">Например, вы можете дать конкретные рекомендации клиентам, которые предпочитают определенный тип услуг.</span><span class="sxs-lookup"><span data-stu-id="675d1-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="675d1-107">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="675d1-107">Prerequisites</span></span>

- <span data-ttu-id="675d1-108">По крайней мере [разрешения участника](permissions.md) в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="675d1-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="675d1-109">Рекомендация продукта, транзакционный отток, отток подписок или модель ценности клиента на протяжении жизненного цикла, настроенная в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="675d1-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="675d1-110">Ознакомьтесь с требованиями для настройки различных моделей:</span><span class="sxs-lookup"><span data-stu-id="675d1-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="675d1-111">Модель рекомендаций по продукту</span><span class="sxs-lookup"><span data-stu-id="675d1-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="675d1-112">Модель оттока подписок</span><span class="sxs-lookup"><span data-stu-id="675d1-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="675d1-113">Модель транзакционного оттока</span><span class="sxs-lookup"><span data-stu-id="675d1-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="675d1-114">Модель ценности клиента на протяжении жизненного цикла</span><span class="sxs-lookup"><span data-stu-id="675d1-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="675d1-115">Создание сегмента клиентов на основе прогнозов</span><span class="sxs-lookup"><span data-stu-id="675d1-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="675d1-116">Перейдите **Аналитика** > **Прогнозы** и выберите вкладку **Мои прогнозы**.</span><span class="sxs-lookup"><span data-stu-id="675d1-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="675d1-117">Выделите вертикальное многоточие рядом с моделью, которую хотите просмотреть, и выберите **Посмотреть**.</span><span class="sxs-lookup"><span data-stu-id="675d1-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="675d1-118">На странице результатов выберите **Создать сегмент**.</span><span class="sxs-lookup"><span data-stu-id="675d1-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="675d1-119">Дополнительные сведения о странице результатов см. в статье о модели.</span><span class="sxs-lookup"><span data-stu-id="675d1-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Снимок экрана страницы результатов прогноза с выделенным действием создания сегмента.":::

1. <span data-ttu-id="675d1-121">Создайте новый сегмент на основе выходной сущности выбранной модели.</span><span class="sxs-lookup"><span data-stu-id="675d1-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="675d1-122">Дополнительные сведения см. в разделе [Создание сегментов и управление ими](segments.md).</span><span class="sxs-lookup"><span data-stu-id="675d1-122">For more information, see [Create and manage segments](segments.md).</span></span>