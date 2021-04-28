---
title: Экспорт данных Customer Insights в Dynamics 365 Sales
description: Узнайте, как настроить подключение и экспорт в Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc1a05ba4d21d96aa1a9724d158687bbb86949b6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759620"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="76c6c-103">Использование сегментов в Dynamics 365 Sales (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="76c6c-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="76c6c-104">Используйте свои данные о клиентах для создания маркетинговых списков, бизнес-процессов для дальнейших действий, а также рассылки предложений с помощью Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="76c6c-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="76c6c-105">Предварительные требования для подключения</span><span class="sxs-lookup"><span data-stu-id="76c6c-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="76c6c-106">Записи контактов должны присутствовать в Dynamics 365 Sales, прежде чем вы сможете экспортировать сегмент из Customer Insights в Sales.</span><span class="sxs-lookup"><span data-stu-id="76c6c-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="76c6c-107">См. дополнительные сведения о загрузке контактов в [Dynamics 365 Sales с помощью Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="76c6c-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="76c6c-108">Экспорт сегментов из аналитики аудитории в Sales не приведет к созданию новых записей контактов в экземплярах Sales.</span><span class="sxs-lookup"><span data-stu-id="76c6c-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="76c6c-109">Записи контактов из Sales должны быть загружены в аналитику аудитории и использованы как источник данных.</span><span class="sxs-lookup"><span data-stu-id="76c6c-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="76c6c-110">Их также необходимо включить в объединенную сущность «Клиент», чтобы сопоставить идентификаторы клиентов с идентификаторами контактов, прежде чем сегменты можно будет экспортировать.</span><span class="sxs-lookup"><span data-stu-id="76c6c-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="76c6c-111">Настройка подключения к Sales</span><span class="sxs-lookup"><span data-stu-id="76c6c-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="76c6c-112">Перейти в раздел **Администрирование** > **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="76c6c-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="76c6c-113">Выберите **Добавить подключение** и выберите **Dynamics 365 Sales** для настройки подключения.</span><span class="sxs-lookup"><span data-stu-id="76c6c-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="76c6c-114">Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="76c6c-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="76c6c-115">Имя и тип подключения описывают это подключение.</span><span class="sxs-lookup"><span data-stu-id="76c6c-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="76c6c-116">Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.</span><span class="sxs-lookup"><span data-stu-id="76c6c-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="76c6c-117">Укажите, кто может использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="76c6c-117">Choose who can use this connection.</span></span> <span data-ttu-id="76c6c-118">Если вы не предпримете никаких действий, по умолчанию это будут администраторы.</span><span class="sxs-lookup"><span data-stu-id="76c6c-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="76c6c-119">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="76c6c-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="76c6c-120">Введите URL-адрес Sales вашей организации в поле **Адрес сервера**.</span><span class="sxs-lookup"><span data-stu-id="76c6c-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="76c6c-121">В разделе **Учетная запись администратора сервера** выберите **Войти** и выберите учетную запись Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="76c6c-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="76c6c-122">Сопоставьте поле идентификатора клиента с идентификатором контакта Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="76c6c-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="76c6c-123">Выберите **Сохранить**, чтобы завершить подключение.</span><span class="sxs-lookup"><span data-stu-id="76c6c-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="76c6c-124">Настройка экспорта</span><span class="sxs-lookup"><span data-stu-id="76c6c-124">Configure an export</span></span>

<span data-ttu-id="76c6c-125">Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа.</span><span class="sxs-lookup"><span data-stu-id="76c6c-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="76c6c-126">Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="76c6c-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="76c6c-127">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="76c6c-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="76c6c-128">Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.</span><span class="sxs-lookup"><span data-stu-id="76c6c-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="76c6c-129">В поле **Подключение для экспорта** выберите подключение из раздела Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="76c6c-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="76c6c-130">Если вы не видите название этого раздела, вам не доступны подключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="76c6c-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="76c6c-131">Выберите один или несколько сегментов.</span><span class="sxs-lookup"><span data-stu-id="76c6c-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="76c6c-132">Выберите **Сохранить**</span><span class="sxs-lookup"><span data-stu-id="76c6c-132">Select **Save**</span></span>

<span data-ttu-id="76c6c-133">Сохранение экспорта не запускает экспорт сразу.</span><span class="sxs-lookup"><span data-stu-id="76c6c-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="76c6c-134">Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="76c6c-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="76c6c-135">Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="76c6c-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
