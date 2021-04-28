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
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896021"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="575a5-103">Обогащение профилей клиентов (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="575a5-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="575a5-104">Используйте данные из таких источников, как Microsoft и другие партнеры, чтобы обогатить данные ваших клиентов.</span><span class="sxs-lookup"><span data-stu-id="575a5-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Страница центра обогащения":::

<span data-ttu-id="575a5-106">В аналитике аудитории перейдите **Данные** > **Обогащение**, чтобы открыть параметры обогащения.</span><span class="sxs-lookup"><span data-stu-id="575a5-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="575a5-107">У вас должны быть разрешения участника или администратора для создания или редактирования обогащений.</span><span class="sxs-lookup"><span data-stu-id="575a5-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="575a5-108">Дополнительные сведения см. [Разрешения](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="575a5-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="575a5-109">На вкладке **Обнаружить** вы найдете следующие обогащения:</span><span class="sxs-lookup"><span data-stu-id="575a5-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="575a5-110">[Бренды](enrichment-microsoft.md), предоставленные Microsoft</span><span class="sxs-lookup"><span data-stu-id="575a5-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="575a5-111">[Интересы](enrichment-microsoft.md), предоставленные Microsoft</span><span class="sxs-lookup"><span data-stu-id="575a5-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="575a5-112">[Данные компании](enrichment-leadspace.md) предоставлены Leadspace</span><span class="sxs-lookup"><span data-stu-id="575a5-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="575a5-113">[Демографические данные](enrichment-experian.md) предоставлены Experian</span><span class="sxs-lookup"><span data-stu-id="575a5-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="575a5-114">[Данные расположения](enrichment-here.md) предоставлены HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="575a5-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="575a5-115">[Пользовательские данные](enrichment-SFTP-custom-import.md) через протокол SFTP</span><span class="sxs-lookup"><span data-stu-id="575a5-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="575a5-116">На вкладке **Мои обогащения** можно увидеть обогащения, которые вы настроили, и отредактировать их свойства.</span><span class="sxs-lookup"><span data-stu-id="575a5-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="575a5-117">Управление существующими обогащениями</span><span class="sxs-lookup"><span data-stu-id="575a5-117">Manage existing enrichments</span></span>

<span data-ttu-id="575a5-118">Перейдите в раздел **Мои обогащения**, чтобы увидеть все настроенные обогащения.</span><span class="sxs-lookup"><span data-stu-id="575a5-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="575a5-119">Каждое обогащение представлено в виде строки, которая включает дополнительную информацию об обогащении.</span><span class="sxs-lookup"><span data-stu-id="575a5-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="575a5-120">Выберите обогащение, чтобы увидеть доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="575a5-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="575a5-121">Вы также можете выбрать многоточие (...) в элементе списка, чтобы просмотреть параметры.</span><span class="sxs-lookup"><span data-stu-id="575a5-121">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Параметры для управления обогащениями в списке обогащений":::

- <span data-ttu-id="575a5-123">**Просмотр** сведений об обогащении с рядом обогащенных профилей клиентов.</span><span class="sxs-lookup"><span data-stu-id="575a5-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="575a5-124">**Изменение** конфигурации обогащения.</span><span class="sxs-lookup"><span data-stu-id="575a5-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="575a5-125">**Выполните** обогащение для обновления профилей клиентов последними данными.</span><span class="sxs-lookup"><span data-stu-id="575a5-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="575a5-126">**Деактивирование** существующего обогащения, чтобы оно не обновлялось автоматически при каждом запланированном обновлении.</span><span class="sxs-lookup"><span data-stu-id="575a5-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="575a5-127">Данные последнего успешного обновления будут по-прежнему доступны.</span><span class="sxs-lookup"><span data-stu-id="575a5-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="575a5-128">**Активирование** неактивного обогащения для перезапуска автоматического обновления при каждом запланированном обновлении.</span><span class="sxs-lookup"><span data-stu-id="575a5-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="575a5-129">**Удалите** обогащение.</span><span class="sxs-lookup"><span data-stu-id="575a5-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="575a5-130">Вы можете запустить или деактивировать несколько обогащений одновременно, выбрав их в списке.</span><span class="sxs-lookup"><span data-stu-id="575a5-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="575a5-131">Параметры просмотра и редактирования недоступны как массовые действия и работают только для одного обогащения за раз.</span><span class="sxs-lookup"><span data-stu-id="575a5-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="575a5-132">Обогащения и подключения</span><span class="sxs-lookup"><span data-stu-id="575a5-132">Enrichments and connections</span></span>

<span data-ttu-id="575a5-133">Сторонние обогащения настраиваются с помощью [подключений](connections.md), которые администратор настраивает с учетными данными и для которых дает согласие на передачу данных.</span><span class="sxs-lookup"><span data-stu-id="575a5-133">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="575a5-134">Это подключение может быть использовано как администраторами, так и участниками для настройки обогащений.</span><span class="sxs-lookup"><span data-stu-id="575a5-134">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="575a5-135">Несколько обогащений одного типа</span><span class="sxs-lookup"><span data-stu-id="575a5-135">Multiple enrichments of the same type</span></span>

<span data-ttu-id="575a5-136">Сущность, которую нужно обогатить, указывается во время настройки обогащения, что позволяет вам обогатить только подмножество ваших профилей.</span><span class="sxs-lookup"><span data-stu-id="575a5-136">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="575a5-137">Например, обогащайте данные только для определенного сегмента.</span><span class="sxs-lookup"><span data-stu-id="575a5-137">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="575a5-138">Вы можете настроить несколько обогащений одного типа и повторно использовать одно и то же подключение.</span><span class="sxs-lookup"><span data-stu-id="575a5-138">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="575a5-139">Некоторые обогащения будут иметь ограничения на количество обогащений одного и того же типа, которые могут быть созданы.</span><span class="sxs-lookup"><span data-stu-id="575a5-139">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="575a5-140">Пределы и текущее использование можно увидеть на странице **Обогащение**.</span><span class="sxs-lookup"><span data-stu-id="575a5-140">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
