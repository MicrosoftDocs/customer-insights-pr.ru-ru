---
title: Обогащение унифицированных профилей клиентов
description: Используйте возможности для обогащения данных о ваших клиентах.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667110"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="950b3-103">Обогащение профилей клиентов (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="950b3-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="950b3-104">Используйте данные из таких источников, как Microsoft и другие партнеры, чтобы обогатить данные ваших клиентов.</span><span class="sxs-lookup"><span data-stu-id="950b3-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Страница центра обогащения":::

<span data-ttu-id="950b3-106">В аналитике аудитории перейдите **Данные** > **Обогащение**, чтобы открыть параметры обогащения.</span><span class="sxs-lookup"><span data-stu-id="950b3-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="950b3-107">У вас должны быть разрешения участника или администратора для создания или редактирования обогащений.</span><span class="sxs-lookup"><span data-stu-id="950b3-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="950b3-108">Дополнительные сведения см. [Разрешения](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="950b3-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="950b3-109">На вкладке **Обнаружить** вы найдете следующие обогащения:</span><span class="sxs-lookup"><span data-stu-id="950b3-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="950b3-110">[Торговые марки](enrichment-microsoft-graph.md) предоставлены Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="950b3-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="950b3-111">[Интересы](enrichment-microsoft-graph.md) предоставлены Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="950b3-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="950b3-112">[Данные компании](enrichment-leadspace.md) предоставлены Leadspace</span><span class="sxs-lookup"><span data-stu-id="950b3-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="950b3-113">[Демографические данные](enrichment-experian.md) предоставлены Experian</span><span class="sxs-lookup"><span data-stu-id="950b3-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="950b3-114">[Данные расположения](enrichment-here.md) предоставлены HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="950b3-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="950b3-115">[Пользовательские данные](enrichment-SFTP-custom-import.md) через протокол SFTP</span><span class="sxs-lookup"><span data-stu-id="950b3-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="950b3-116">На вкладке **Мои обогащения** можно увидеть обогащения, которые вы настроили, и отредактировать их свойства.</span><span class="sxs-lookup"><span data-stu-id="950b3-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="950b3-117">Управление существующими обогащениями</span><span class="sxs-lookup"><span data-stu-id="950b3-117">Manage existing enrichments</span></span>

<span data-ttu-id="950b3-118">Перейдите в раздел **Мои обогащения**, чтобы увидеть все настроенные обогащения.</span><span class="sxs-lookup"><span data-stu-id="950b3-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="950b3-119">Каждое обогащение представлено в виде строки, которая включает дополнительную информацию об обогащении.</span><span class="sxs-lookup"><span data-stu-id="950b3-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="950b3-120">Выберите обогащение, чтобы увидеть доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="950b3-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="950b3-121">Кроме того, вы можете выбрать многоточие (...) в элементе списка, чтобы просмотреть параметры.</span><span class="sxs-lookup"><span data-stu-id="950b3-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Параметры для управления обогащениями в списке обогащений":::

- <span data-ttu-id="950b3-123">**Просмотр** сведений об обогащении с рядом обогащенных профилей клиентов.</span><span class="sxs-lookup"><span data-stu-id="950b3-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="950b3-124">**Изменение** конфигурации обогащения.</span><span class="sxs-lookup"><span data-stu-id="950b3-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="950b3-125">**Выполните** обогащение для обновления профилей клиентов последними данными.</span><span class="sxs-lookup"><span data-stu-id="950b3-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="950b3-126">**Деактивирование** существующего обогащения, чтобы оно не обновлялось автоматически при каждом запланированном обновлении.</span><span class="sxs-lookup"><span data-stu-id="950b3-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="950b3-127">Данные последнего успешного обновления будут по-прежнему доступны.</span><span class="sxs-lookup"><span data-stu-id="950b3-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="950b3-128">**Активирование** неактивного обогащения для перезапуска автоматического обновления при каждом запланированном обновлении.</span><span class="sxs-lookup"><span data-stu-id="950b3-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="950b3-129">**Удалите** обогащение.</span><span class="sxs-lookup"><span data-stu-id="950b3-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="950b3-130">Вы можете запустить или деактивировать несколько обогащений одновременно, выбрав их в списке.</span><span class="sxs-lookup"><span data-stu-id="950b3-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="950b3-131">Параметры просмотра и редактирования недоступны как массовые действия и работают только для одного обогащения за раз.</span><span class="sxs-lookup"><span data-stu-id="950b3-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>
