---
title: Обогащение унифицированных профилей клиентов
description: Используйте возможности для обогащения данных о ваших клиентах.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c8e4a7247ccf575a62440038180010916b09d51b
ms.sourcegitcommit: f9e2fa3f11ecf11a5d9cccc376fdeb1ecea54880
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2021
ms.locfileid: "5954503"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="f77ce-103">Обогащение профилей клиентов (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="f77ce-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="f77ce-104">Используйте данные из таких источников, как Microsoft и другие партнеры, чтобы обогатить данные ваших клиентов.</span><span class="sxs-lookup"><span data-stu-id="f77ce-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Страница центра обогащения":::

<span data-ttu-id="f77ce-106">В аналитике аудитории перейдите **Данные** > **Обогащение**, чтобы открыть параметры обогащения.</span><span class="sxs-lookup"><span data-stu-id="f77ce-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="f77ce-107">У вас должны быть разрешения участника или администратора для создания или редактирования обогащений.</span><span class="sxs-lookup"><span data-stu-id="f77ce-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="f77ce-108">Дополнительные сведения см. [Разрешения](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f77ce-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="f77ce-109">На вкладке **Обнаружить** вы найдете следующие обогащения:</span><span class="sxs-lookup"><span data-stu-id="f77ce-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="f77ce-110">[Бренды](enrichment-microsoft.md), предоставленные Microsoft</span><span class="sxs-lookup"><span data-stu-id="f77ce-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="f77ce-111">[Интересы](enrichment-microsoft.md), предоставленные Microsoft</span><span class="sxs-lookup"><span data-stu-id="f77ce-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="f77ce-112">[Расширенные адреса](enrichment-enhanced-addresses.md), предоставленные Microsoft</span><span class="sxs-lookup"><span data-stu-id="f77ce-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="f77ce-113">[Данные компании](enrichment-leadspace.md) предоставлены Leadspace</span><span class="sxs-lookup"><span data-stu-id="f77ce-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="f77ce-114">[Демографические данные](enrichment-experian.md) предоставлены Experian</span><span class="sxs-lookup"><span data-stu-id="f77ce-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="f77ce-115">[Данные расположения](enrichment-here.md) предоставлены HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="f77ce-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="f77ce-116">[Пользовательские данные](enrichment-SFTP-custom-import.md) через протокол SFTP</span><span class="sxs-lookup"><span data-stu-id="f77ce-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="f77ce-117">На вкладке **Мои обогащения** можно увидеть обогащения, которые вы настроили, и отредактировать их свойства.</span><span class="sxs-lookup"><span data-stu-id="f77ce-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="f77ce-118">Управление существующими обогащениями</span><span class="sxs-lookup"><span data-stu-id="f77ce-118">Manage existing enrichments</span></span>

<span data-ttu-id="f77ce-119">Перейдите в раздел **Мои обогащения**, чтобы увидеть все настроенные обогащения.</span><span class="sxs-lookup"><span data-stu-id="f77ce-119">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="f77ce-120">Каждое обогащение представлено в виде строки, которая включает дополнительную информацию об обогащении.</span><span class="sxs-lookup"><span data-stu-id="f77ce-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="f77ce-121">Выберите обогащение, чтобы увидеть доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="f77ce-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="f77ce-122">Вы также можете выбрать многоточие (...) в элементе списка, чтобы просмотреть параметры.</span><span class="sxs-lookup"><span data-stu-id="f77ce-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Параметры для управления обогащениями в списке обогащений":::

- <span data-ttu-id="f77ce-124">**Просмотр** сведений об обогащении с рядом обогащенных профилей клиентов.</span><span class="sxs-lookup"><span data-stu-id="f77ce-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="f77ce-125">**Изменение** конфигурации обогащения.</span><span class="sxs-lookup"><span data-stu-id="f77ce-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="f77ce-126">**Выполните** обогащение для обновления профилей клиентов последними данными.</span><span class="sxs-lookup"><span data-stu-id="f77ce-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="f77ce-127">**Деактивирование** существующего обогащения, чтобы оно не обновлялось автоматически при каждом запланированном обновлении.</span><span class="sxs-lookup"><span data-stu-id="f77ce-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="f77ce-128">Данные последнего успешного обновления будут по-прежнему доступны.</span><span class="sxs-lookup"><span data-stu-id="f77ce-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="f77ce-129">**Активирование** неактивного обогащения для перезапуска автоматического обновления при каждом запланированном обновлении.</span><span class="sxs-lookup"><span data-stu-id="f77ce-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="f77ce-130">**Удалите** обогащение.</span><span class="sxs-lookup"><span data-stu-id="f77ce-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="f77ce-131">Вы можете запустить или деактивировать несколько обогащений одновременно, выбрав их в списке.</span><span class="sxs-lookup"><span data-stu-id="f77ce-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="f77ce-132">Параметры просмотра и редактирования недоступны как массовые действия и работают только для одного обогащения за раз.</span><span class="sxs-lookup"><span data-stu-id="f77ce-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="f77ce-133">Обогащения и подключения</span><span class="sxs-lookup"><span data-stu-id="f77ce-133">Enrichments and connections</span></span>

<span data-ttu-id="f77ce-134">Сторонние обогащения настраиваются с помощью [подключений](connections.md), которые администратор настраивает с учетными данными и для которых дает согласие на передачу данных.</span><span class="sxs-lookup"><span data-stu-id="f77ce-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="f77ce-135">Это подключение может быть использовано как администраторами, так и участниками для настройки обогащений.</span><span class="sxs-lookup"><span data-stu-id="f77ce-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="f77ce-136">Несколько обогащений одного типа</span><span class="sxs-lookup"><span data-stu-id="f77ce-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="f77ce-137">Сущность, которую нужно обогатить, указывается во время настройки обогащения, что позволяет вам обогатить только подмножество ваших профилей.</span><span class="sxs-lookup"><span data-stu-id="f77ce-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="f77ce-138">Например, обогащайте данные только для определенного сегмента.</span><span class="sxs-lookup"><span data-stu-id="f77ce-138">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="f77ce-139">Вы можете настроить несколько обогащений одного типа и повторно использовать одно и то же подключение.</span><span class="sxs-lookup"><span data-stu-id="f77ce-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="f77ce-140">Некоторые обогащения будут иметь ограничения на количество обогащений одного и того же типа, которые могут быть созданы.</span><span class="sxs-lookup"><span data-stu-id="f77ce-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="f77ce-141">Пределы и текущее использование можно увидеть на странице **Обогащение**.</span><span class="sxs-lookup"><span data-stu-id="f77ce-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
