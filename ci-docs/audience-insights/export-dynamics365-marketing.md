---
title: Экспорт данных Customer Insights в Dynamics 365 Marketing
description: Узнайте, как настроить подключение и экспорт в Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 195bee789dc043057b47c12c8d93e6d53edb59cd
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976816"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="e21d8-103">Использование сегментов в Dynamics 365 Marketing (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="e21d8-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="e21d8-104">Используйте [сегменты](segments.md) для создания кампаний и связи с определенными группами клиентов с помощью Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="e21d8-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="e21d8-105">Дополнительные сведения см. в [Используйте сегменты из Dynamics 365 Customer Insights с Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="e21d8-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="e21d8-106">Предварительное требование для подключения</span><span class="sxs-lookup"><span data-stu-id="e21d8-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="e21d8-107">Записи контактов должны присутствовать в Dynamics 365 Marketing, прежде чем вы сможете экспортировать сегмент из Customer Insights в Marketing.</span><span class="sxs-lookup"><span data-stu-id="e21d8-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="e21d8-108">См. дополнительные сведения о загрузке контактов в [Dynamics 365 Marketing с помощью Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="e21d8-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="e21d8-109">Экспорт сегментов из аналитики аудитории в Marketing не приведет к созданию новых записей контактов в экземплярах Marketing.</span><span class="sxs-lookup"><span data-stu-id="e21d8-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="e21d8-110">Записи контактов из Marketing должны быть загружены в аналитику аудитории и использованы как источник данных.</span><span class="sxs-lookup"><span data-stu-id="e21d8-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="e21d8-111">Их также необходимо включить в объединенную сущность «Клиент», чтобы сопоставить идентификаторы клиентов с идентификаторами контактов, прежде чем сегменты можно будет экспортировать.</span><span class="sxs-lookup"><span data-stu-id="e21d8-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="e21d8-112">Настройка подключения к Marketing</span><span class="sxs-lookup"><span data-stu-id="e21d8-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="e21d8-113">Перейти в раздел **Администрирование** > **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="e21d8-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e21d8-114">Выберите **Добавить подключение** и выберите **Dynamics 365 Marketing** для настройки подключения.</span><span class="sxs-lookup"><span data-stu-id="e21d8-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="e21d8-115">Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="e21d8-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e21d8-116">Имя и тип подключения описывают это подключение.</span><span class="sxs-lookup"><span data-stu-id="e21d8-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e21d8-117">Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.</span><span class="sxs-lookup"><span data-stu-id="e21d8-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e21d8-118">Укажите, кто может использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="e21d8-118">Choose who can use this connection.</span></span> <span data-ttu-id="e21d8-119">Если вы не предпримете никаких действий, по умолчанию это будут администраторы.</span><span class="sxs-lookup"><span data-stu-id="e21d8-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e21d8-120">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e21d8-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e21d8-121">Введите URL-адрес Marketing вашей организации в поле **Адрес сервера**.</span><span class="sxs-lookup"><span data-stu-id="e21d8-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="e21d8-122">В разделе **Учетная запись администратора сервера** выберите **Войти** и выберите учетную запись Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="e21d8-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="e21d8-123">Сопоставьте поле идентификатора клиента с идентификатором контакта Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e21d8-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="e21d8-124">Выберите **Сохранить**, чтобы завершить подключение.</span><span class="sxs-lookup"><span data-stu-id="e21d8-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="e21d8-125">Настройка экспорта</span><span class="sxs-lookup"><span data-stu-id="e21d8-125">Configure an export</span></span>

<span data-ttu-id="e21d8-126">Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа.</span><span class="sxs-lookup"><span data-stu-id="e21d8-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e21d8-127">Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e21d8-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e21d8-128">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="e21d8-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e21d8-129">Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.</span><span class="sxs-lookup"><span data-stu-id="e21d8-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e21d8-130">В поле **Подключение для экспорта** выберите подключение из раздела Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="e21d8-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="e21d8-131">Если вы не видите название этого раздела, вам не доступны подключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="e21d8-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e21d8-132">Выберите один или несколько сегментов.</span><span class="sxs-lookup"><span data-stu-id="e21d8-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="e21d8-133">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e21d8-133">Select **Save**.</span></span>

<span data-ttu-id="e21d8-134">Сохранение экспорта не запускает экспорт сразу.</span><span class="sxs-lookup"><span data-stu-id="e21d8-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e21d8-135">Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e21d8-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e21d8-136">Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e21d8-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
