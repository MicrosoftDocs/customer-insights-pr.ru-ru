---
title: Соединитель Power Automate | Документация Майкрософт
description: Создавайте потоки в Microsoft Power Automate из Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406719"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="889ee-103">Соединитель Power Automate (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="889ee-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="889ee-104">Автоматически запускайте определенные события при изменении данных и управляйте более сложными потоками непосредственно в [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="889ee-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="889ee-105">Триггеры Power Automate</span><span class="sxs-lookup"><span data-stu-id="889ee-105">Power Automate triggers</span></span>

<span data-ttu-id="889ee-106">Вы можете использовать различные триггеры, которые позволяют создавать потоки для автоматизации повторяющихся задач, таких как уведомления или более сложные действия.</span><span class="sxs-lookup"><span data-stu-id="889ee-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="889ee-107">Триггер при сбое обновления источника данных.</span><span class="sxs-lookup"><span data-stu-id="889ee-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="889ee-108">Триггер при успешном обновлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="889ee-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="889ee-109">Триггер, когда порог пересекается на сегменте.</span><span class="sxs-lookup"><span data-stu-id="889ee-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="889ee-110">Триггер ограничен пересечением выше порога.</span><span class="sxs-lookup"><span data-stu-id="889ee-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="889ee-111">Триггер, когда порог пересекается на бизнес-мере.</span><span class="sxs-lookup"><span data-stu-id="889ee-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="889ee-112">Триггер ограничен пересечением выше порога.</span><span class="sxs-lookup"><span data-stu-id="889ee-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="889ee-113">Запускается по завершении полного обновления (источников данных, сегментов, мер...).</span><span class="sxs-lookup"><span data-stu-id="889ee-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="889ee-114">Запускается, когда обновление процесса объединения (сопоставление, поиск соответствия, объединение) завершено.</span><span class="sxs-lookup"><span data-stu-id="889ee-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="889ee-115">[Настройте свои триггеры в Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="889ee-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="889ee-116">Действия Power Automate</span><span class="sxs-lookup"><span data-stu-id="889ee-116">Power Automate actions</span></span>
<span data-ttu-id="889ee-117">Соединитель Power Automate обеспечивает другие действия, кроме доступных триггеров.</span><span class="sxs-lookup"><span data-stu-id="889ee-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="889ee-118">Для получения дополнительных сведений см. [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="889ee-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="889ee-119">Создание потока Power Automate в аналитике аудитории</span><span class="sxs-lookup"><span data-stu-id="889ee-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="889ee-120">В аналитике аудитории перейдите **Администрирование** > **Система**.</span><span class="sxs-lookup"><span data-stu-id="889ee-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="889ee-121">На странице **Система** выберите вкладку **Состояние**.</span><span class="sxs-lookup"><span data-stu-id="889ee-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="889ee-122">В разделе **Источники данных** выберите **Потоки** и выберите **Создать поток** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="889ee-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="889ee-123">![Соединитель Power Automate, показывающий действие "Создать поток"](media/power-automate-connector-create-flow.png "Соединитель Power Automate, показывающий действие "Создать поток"")</span><span class="sxs-lookup"><span data-stu-id="889ee-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="889ee-124">В Power Automate выберите один из доступных триггеров, чтобы создать предпочтительный поток.</span><span class="sxs-lookup"><span data-stu-id="889ee-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="889ee-125">Если вы создаете свой первый поток, вам сначала нужно пройти аутентификацию с соединителем Power Automate.</span><span class="sxs-lookup"><span data-stu-id="889ee-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
