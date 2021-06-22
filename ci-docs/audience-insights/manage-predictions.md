---
title: Общие задачи для сценариев прогноза
description: Узнайте, как управлять прогнозами, устранять неполадки и уточнять их.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095744"
---
# <a name="manage-predictions"></a><span data-ttu-id="13b80-103">Управляйте прогнозами</span><span class="sxs-lookup"><span data-stu-id="13b80-103">Manage predictions</span></span>

<span data-ttu-id="13b80-104">В этой статье обсуждаются некоторые задачи, которые используются в большинстве сценариев прогноза.</span><span class="sxs-lookup"><span data-stu-id="13b80-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="13b80-105">Устранение неполадок со сбоем прогноза</span><span class="sxs-lookup"><span data-stu-id="13b80-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="13b80-106">Перейдите **Аналитика** > **Прогнозы** и выберите вкладку **Мои прогнозы**.</span><span class="sxs-lookup"><span data-stu-id="13b80-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="13b80-107">Выберите вертикальные многоточия рядом с прогнозом, для которого вы хотите просмотреть журналы ошибок.</span><span class="sxs-lookup"><span data-stu-id="13b80-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="13b80-108">Выберите **Журналы**.</span><span class="sxs-lookup"><span data-stu-id="13b80-108">Select **Logs**.</span></span>

1. <span data-ttu-id="13b80-109">Просмотр всех ошибок.</span><span class="sxs-lookup"><span data-stu-id="13b80-109">Review all the errors.</span></span> <span data-ttu-id="13b80-110">Существует несколько типов ошибок, которые описывают, в каком состоянии возникла ошибка.</span><span class="sxs-lookup"><span data-stu-id="13b80-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="13b80-111">Например, ошибка, связанная с недостаточным количеством данных для точного прогнозирования, обычно устраняется путем загрузки дополнительных данных в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="13b80-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="13b80-112">Отчет об используемости входных данных</span><span class="sxs-lookup"><span data-stu-id="13b80-112">Input data usability report</span></span>

<span data-ttu-id="13b80-113">Отчет об удобстве использования входных данных предоставляет консолидированное представление об ошибках и предупреждениях, которые могут генерироваться вашими готовыми прогнозами.</span><span class="sxs-lookup"><span data-stu-id="13b80-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="13b80-114">Также даются рекомендации по повышению производительности модели.</span><span class="sxs-lookup"><span data-stu-id="13b80-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="13b80-115">Отчет доступен после завершения процесса обучения модели.</span><span class="sxs-lookup"><span data-stu-id="13b80-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="13b80-116">Он создается для каждой модели отдельно, независимо от того, успешно она завершилась или нет.</span><span class="sxs-lookup"><span data-stu-id="13b80-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

> [!NOTE]
> <span data-ttu-id="13b80-117">В настоящее время эта функция работает только для модели оттока транзакций.</span><span class="sxs-lookup"><span data-stu-id="13b80-117">Currently, this feature only works for the Transaction Churn model.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="13b80-118">Просмотр отчета о полезности входных данных</span><span class="sxs-lookup"><span data-stu-id="13b80-118">View the input data usability report</span></span>

<span data-ttu-id="13b80-119">После того, как готовая модель завершит этап обучения, просмотрите отчет:</span><span class="sxs-lookup"><span data-stu-id="13b80-119">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="13b80-120">Выделите многоточия рядом с названием модели и выберите **Отчет об используемости входных данных**.</span><span class="sxs-lookup"><span data-stu-id="13b80-120">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="13b80-121">Выберите статус модели выберите **Отчет об используемости входных данных** на боковой панели.</span><span class="sxs-lookup"><span data-stu-id="13b80-121">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="13b80-122">Выбрав одну из моделей в списке и выберите **Отчет об используемости входных данных** на панели команд.</span><span class="sxs-lookup"><span data-stu-id="13b80-122">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="13b80-123">Откройте страницу результатов модели и выберите **Отчет об используемости входных данных** на панели команд.</span><span class="sxs-lookup"><span data-stu-id="13b80-123">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="13b80-124">Информация в отчете о полезности входных данных</span><span class="sxs-lookup"><span data-stu-id="13b80-124">Information in the input data usability report</span></span>

<span data-ttu-id="13b80-125">Следующие столбцы в отчете содержат полезную информацию для улучшения данных для модели.</span><span class="sxs-lookup"><span data-stu-id="13b80-125">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Пример отчета об удобстве использования входных данных с таблицей с ошибками, предупреждениями и рекомендациями.":::

- <span data-ttu-id="13b80-127">Имя: описательное имя ошибки, предупреждения или рекомендации.</span><span class="sxs-lookup"><span data-stu-id="13b80-127">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="13b80-128">Шаг: этап моделирования, тренировка или оценка, к которой относится информация.</span><span class="sxs-lookup"><span data-stu-id="13b80-128">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="13b80-129">Состояние: серьезность информации (ошибка, предупреждение, рекомендация).</span><span class="sxs-lookup"><span data-stu-id="13b80-129">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="13b80-130">Имя столбца: столбец в сущности, который необходимо изменить для повышения производительности модели.</span><span class="sxs-lookup"><span data-stu-id="13b80-130">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="13b80-131">Имя сущности:: имя сущности, которую необходимо изменить для повышения производительности модели.</span><span class="sxs-lookup"><span data-stu-id="13b80-131">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="13b80-132">Сведения: подробные сведения об ошибке, предупреждении или рекомендации.</span><span class="sxs-lookup"><span data-stu-id="13b80-132">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="13b80-133">Обновить прогноз</span><span class="sxs-lookup"><span data-stu-id="13b80-133">Refresh a prediction</span></span>

<span data-ttu-id="13b80-134">Прогнозы будут автоматически обновляться по тому же [графику обновления данных](system.md#schedule-tab), как настроено в параметрах.</span><span class="sxs-lookup"><span data-stu-id="13b80-134">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="13b80-135">Вы также можете обновить их вручную.</span><span class="sxs-lookup"><span data-stu-id="13b80-135">You can refresh them manually too.</span></span>

1. <span data-ttu-id="13b80-136">Перейдите **Аналитика** > **Прогнозы** и выберите вкладку **Мои прогнозы**.</span><span class="sxs-lookup"><span data-stu-id="13b80-136">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="13b80-137">Выберите вертикальное многоточие рядом с прогнозом, который вы хотите обновить.</span><span class="sxs-lookup"><span data-stu-id="13b80-137">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="13b80-138">Выбрать **обновить**.</span><span class="sxs-lookup"><span data-stu-id="13b80-138">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="13b80-139">Удаление прогноз</span><span class="sxs-lookup"><span data-stu-id="13b80-139">Delete a prediction</span></span>

<span data-ttu-id="13b80-140">Удаление прогноза также удаляет его выходную сущность.</span><span class="sxs-lookup"><span data-stu-id="13b80-140">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="13b80-141">Перейдите **Аналитика** > **Прогнозы** и выберите вкладку **Мои прогнозы**.</span><span class="sxs-lookup"><span data-stu-id="13b80-141">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="13b80-142">Выберите вертикальное многоточие рядом с прогнозом, который вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="13b80-142">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="13b80-143">Выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="13b80-143">Select **Delete**.</span></span>
