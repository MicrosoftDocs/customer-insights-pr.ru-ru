---
title: Соединитель Power Automate | Документация Майкрософт
description: Создание потоков в Microsoft Power Automate из Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 57be0a204ef920b7a4bb31cf9a5b3a77f96eca0d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305080"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="73b8c-103">Соединитель Power Automate (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="73b8c-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="73b8c-104">Автоматически запускайте определенные события при изменении данных и управляйте более сложными потоками непосредственно в [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="73b8c-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="73b8c-105">Триггеры Power Automate</span><span class="sxs-lookup"><span data-stu-id="73b8c-105">Power Automate triggers</span></span>

<span data-ttu-id="73b8c-106">Используйте триггеры для создания облачных потоков и автоматизации повторяющихся задач, таких как уведомления или более сложные действия.</span><span class="sxs-lookup"><span data-stu-id="73b8c-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="73b8c-107">Триггер при сбое обновления источника данных.</span><span class="sxs-lookup"><span data-stu-id="73b8c-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="73b8c-108">Триггер при успешном обновлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="73b8c-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="73b8c-109">Триггер, когда порог пересекается на сегменте.</span><span class="sxs-lookup"><span data-stu-id="73b8c-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="73b8c-110">Триггер ограничен пересечением выше порога.</span><span class="sxs-lookup"><span data-stu-id="73b8c-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="73b8c-111">Триггер, когда порог пересекается на бизнес-мере.</span><span class="sxs-lookup"><span data-stu-id="73b8c-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="73b8c-112">Поддерживаются только бизнес-меры без измерения.</span><span class="sxs-lookup"><span data-stu-id="73b8c-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="73b8c-113">Триггер ограничен пересечением выше порога.</span><span class="sxs-lookup"><span data-stu-id="73b8c-113">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="73b8c-114">Запускается по завершении полного обновления (источников данных, сегментов, мер...).</span><span class="sxs-lookup"><span data-stu-id="73b8c-114">Trigger when a full refresh of (data sources, segments, measures, ...) is completed.</span></span>
- <span data-ttu-id="73b8c-115">Запускается, когда обновление процесса объединения (сопоставление, поиск соответствия, объединение) завершено.</span><span class="sxs-lookup"><span data-stu-id="73b8c-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

[<span data-ttu-id="73b8c-116">Настройте свои триггеры в Power Automate.</span><span class="sxs-lookup"><span data-stu-id="73b8c-116">Configure your triggers in Power Automate.</span></span>](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a><span data-ttu-id="73b8c-117">Действия Power Automate</span><span class="sxs-lookup"><span data-stu-id="73b8c-117">Power Automate actions</span></span>

<span data-ttu-id="73b8c-118">Соединитель Power Automate обеспечивает другие действия, кроме доступных триггеров.</span><span class="sxs-lookup"><span data-stu-id="73b8c-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="73b8c-119">Для получения дополнительных сведений см. [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="73b8c-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="73b8c-120">Создание потока Power Automate</span><span class="sxs-lookup"><span data-stu-id="73b8c-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="73b8c-121">В аналитике аудитории перейдите **Администрирование** > **Экспорт пунктов назначения**.</span><span class="sxs-lookup"><span data-stu-id="73b8c-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="73b8c-122">На плитке **Power Automate** выберите **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="73b8c-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="73b8c-123">Откроется соединитель Customer Insights (предварительная версия) в Power Automate.</span><span class="sxs-lookup"><span data-stu-id="73b8c-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="73b8c-124">**Войдите** в Power Automate.</span><span class="sxs-lookup"><span data-stu-id="73b8c-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="73b8c-125">Выберите один из доступных триггеров и добавьте дополнительные шаги в новый поток.</span><span class="sxs-lookup"><span data-stu-id="73b8c-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="73b8c-126">Для получения дополнительной информации см. [Создание облачного потока в Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="73b8c-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="73b8c-127">Примеры использования потоков:</span><span class="sxs-lookup"><span data-stu-id="73b8c-127">Examples of how to use flows:</span></span> 
- <span data-ttu-id="73b8c-128">Отправьте сообщение в канал Microsoft Teams в случае сбоя обновления источника данных.</span><span class="sxs-lookup"><span data-stu-id="73b8c-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="73b8c-129">Отправьте электронное письмо владельцам данных, когда будет превышен порог сегмента.</span><span class="sxs-lookup"><span data-stu-id="73b8c-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
