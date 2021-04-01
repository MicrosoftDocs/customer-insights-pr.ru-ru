---
title: Соединитель Power Automate | Документация Майкрософт
description: Создание потоков в Microsoft Power Automate из Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e973bb11b31c9e70b695ebec8aa2700fdaa5e44f
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597941"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="f4819-103">Соединитель Power Automate (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="f4819-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="f4819-104">Автоматически запускайте определенные события при изменении данных и управляйте более сложными потоками непосредственно в [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="f4819-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="f4819-105">Триггеры Power Automate</span><span class="sxs-lookup"><span data-stu-id="f4819-105">Power Automate triggers</span></span>

<span data-ttu-id="f4819-106">Используйте триггеры для создания облачных потоков и автоматизации повторяющихся задач, таких как уведомления или более сложные действия.</span><span class="sxs-lookup"><span data-stu-id="f4819-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="f4819-107">Триггер при сбое обновления источника данных.</span><span class="sxs-lookup"><span data-stu-id="f4819-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="f4819-108">Триггер при успешном обновлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="f4819-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="f4819-109">Триггер, когда порог пересекается на сегменте.</span><span class="sxs-lookup"><span data-stu-id="f4819-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="f4819-110">Триггер ограничен пересечением выше порога.</span><span class="sxs-lookup"><span data-stu-id="f4819-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="f4819-111">Триггер, когда порог пересекается на бизнес-мере.</span><span class="sxs-lookup"><span data-stu-id="f4819-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="f4819-112">Триггер ограничен пересечением выше порога.</span><span class="sxs-lookup"><span data-stu-id="f4819-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="f4819-113">Запускается по завершении полного обновления (источников данных, сегментов, мер...).</span><span class="sxs-lookup"><span data-stu-id="f4819-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="f4819-114">Запускается, когда обновление процесса объединения (сопоставление, поиск соответствия, объединение) завершено.</span><span class="sxs-lookup"><span data-stu-id="f4819-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="f4819-115">[Настройте свои триггеры в Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="f4819-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="f4819-116">Действия Power Automate</span><span class="sxs-lookup"><span data-stu-id="f4819-116">Power Automate actions</span></span>
<span data-ttu-id="f4819-117">Соединитель Power Automate обеспечивает другие действия, кроме доступных триггеров.</span><span class="sxs-lookup"><span data-stu-id="f4819-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="f4819-118">Для получения дополнительных сведений см. [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="f4819-118">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="f4819-119">Создание потока Power Automate</span><span class="sxs-lookup"><span data-stu-id="f4819-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="f4819-120">В аналитике аудитории перейдите **Администрирование** > **Экспорт пунктов назначения**.</span><span class="sxs-lookup"><span data-stu-id="f4819-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f4819-121">На плитке **Power Automate** выберите **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="f4819-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="f4819-122">Откроется соединитель Customer Insights (предварительная версия) в Power Automate.</span><span class="sxs-lookup"><span data-stu-id="f4819-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="f4819-123">**Войдите** в Power Automate.</span><span class="sxs-lookup"><span data-stu-id="f4819-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="f4819-124">Выберите один из доступных триггеров и добавьте дополнительные шаги в новый поток.</span><span class="sxs-lookup"><span data-stu-id="f4819-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="f4819-125">Для получения дополнительной информации см. [Создание облачного потока в Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="f4819-125">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="f4819-126">Примеры использования потоков:</span><span class="sxs-lookup"><span data-stu-id="f4819-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="f4819-127">Отправьте сообщение в канал Microsoft Teams в случае сбоя обновления источника данных.</span><span class="sxs-lookup"><span data-stu-id="f4819-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="f4819-128">Отправьте электронное письмо владельцам данных, когда будет превышен порог сегмента.</span><span class="sxs-lookup"><span data-stu-id="f4819-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]