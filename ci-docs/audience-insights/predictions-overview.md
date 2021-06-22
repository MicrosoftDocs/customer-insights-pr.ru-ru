---
title: Обзор поддерживаемых сценариев прогноза
description: Сценарии прогноза и варианты, охватываемые приложением Dynamics 365 Customer Insights.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095743"
---
# <a name="predictions-overview"></a><span data-ttu-id="0a252-103">Обзор прогнозов</span><span class="sxs-lookup"><span data-stu-id="0a252-103">Predictions overview</span></span>

<span data-ttu-id="0a252-104">Dynamics 365 Customer Insights поставляется с множеством вариантов, которые используют ИИ и машинное обучение для прогнозирования данных.</span><span class="sxs-lookup"><span data-stu-id="0a252-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="0a252-105">Готовые модели</span><span class="sxs-lookup"><span data-stu-id="0a252-105">Out-of-box models</span></span>

<span data-ttu-id="0a252-106">Самый простой способ начать с прогнозирования данных — это предварительно определенные модели, часто называемые готовыми моделями.</span><span class="sxs-lookup"><span data-stu-id="0a252-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="0a252-107">Им требуются только определенные данные и структура, чтобы быстро генерировать аналитику.</span><span class="sxs-lookup"><span data-stu-id="0a252-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="0a252-108">В настоящее время доступны следующие модели:</span><span class="sxs-lookup"><span data-stu-id="0a252-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="0a252-109">[Значение клиента на протяжении жизненного цикла](predict-customer-lifetime-value.md): прогнозирует потенциальный доход клиента на протяжении всего взаимодействия с бизнесом.</span><span class="sxs-lookup"><span data-stu-id="0a252-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="0a252-110">[Рекомендация продукта](predict-product-recommendation.md): наборы прогностических рекомендаций по продуктам, основанные на покупательском поведении и покупателях с похожими моделями покупок.</span><span class="sxs-lookup"><span data-stu-id="0a252-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="0a252-111">[Отток подписок](predict-subscription-churn.md): прогнозирование риска того, что клиент перестанет пользоваться предоставляемыми по подписке продуктами или услугами вашей компании.</span><span class="sxs-lookup"><span data-stu-id="0a252-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="0a252-112">[Транзакционный отток](predict-transactional-churn.md): спрогнозируйте, не будет ли клиент больше покупать ваши продукты или услуги в определенном интервале времени.</span><span class="sxs-lookup"><span data-stu-id="0a252-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="0a252-113">Интеграция машинного обучения Azure</span><span class="sxs-lookup"><span data-stu-id="0a252-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="0a252-114">Если организация уже использует сценарии машинного обучения, основанные на экспериментах машинного обучения Azure, функция настраиваемых моделей в Customer Insights помогает соединить точки.</span><span class="sxs-lookup"><span data-stu-id="0a252-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="0a252-115">Создавайте рабочие процессы, которые помогут вам выбрать данные, на основе которых вы хотите получать информацию, и сопоставить результаты с вашими едиными профилями клиентов.</span><span class="sxs-lookup"><span data-stu-id="0a252-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="0a252-116">Дополнительные сведения см. в разделе [Пользовательские модели машинного обучения](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="0a252-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="0a252-117">Прогноз AI Builder</span><span class="sxs-lookup"><span data-stu-id="0a252-117">AI Builder prediction</span></span>

<span data-ttu-id="0a252-118">Иногда наборы данных неполные, а некоторые значения отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="0a252-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="0a252-119">Customer Insights может помочь предсказать недостающие значения для сущности и сегментов "Клиент".</span><span class="sxs-lookup"><span data-stu-id="0a252-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="0a252-120">Для получения дополнительной информации см. [Дополните свои частичные данные прогнозами](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="0a252-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
