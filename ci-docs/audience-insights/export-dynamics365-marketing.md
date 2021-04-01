---
title: Экспорт данных Customer Insights в Dynamics 365 Marketing
description: Узнайте, как настроить подключение к Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597619"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="c80a6-103">Соединитель для Dynamics 365 Marketing (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="c80a6-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="c80a6-104">Используйте [сегменты](segments.md) для создания кампаний и связи с определенными группами клиентов с помощью Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="c80a6-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="c80a6-105">Дополнительные сведения см. в [Используйте сегменты из Dynamics 365 Customer Insights с Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="c80a6-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="c80a6-106">Необходимые условия</span><span class="sxs-lookup"><span data-stu-id="c80a6-106">Prerequisite</span></span>

- <span data-ttu-id="c80a6-107">Записи контактов должны присутствовать в Dynamics 365 Marketing, прежде чем вы сможете экспортировать сегмент из Customer Insights в Marketing.</span><span class="sxs-lookup"><span data-stu-id="c80a6-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="c80a6-108">См. дополнительные сведения о загрузке контактов в [Dynamics 365 Marketing с помощью Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="c80a6-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="c80a6-109">Экспорт сегментов из аналитики аудитории в Marketing не приведет к созданию новых записей контактов в экземплярах Marketing.</span><span class="sxs-lookup"><span data-stu-id="c80a6-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="c80a6-110">Записи контактов из Marketing должны быть загружены в аналитику аудитории и использованы как источник данных.</span><span class="sxs-lookup"><span data-stu-id="c80a6-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="c80a6-111">Их также необходимо включить в объединенную сущность «Клиент», чтобы сопоставить идентификаторы клиентов с идентификаторами контактов, прежде чем сегменты можно будет экспортировать.</span><span class="sxs-lookup"><span data-stu-id="c80a6-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="c80a6-112">Настройка соединителя для Marketing</span><span class="sxs-lookup"><span data-stu-id="c80a6-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="c80a6-113">В аналитике аудитории перейдите **Администрирование** > **Экспорт пунктов назначения**.</span><span class="sxs-lookup"><span data-stu-id="c80a6-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c80a6-114">В пункте **Dynamics 365 Marketing** выберите **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="c80a6-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="c80a6-115">Дайте вашему пункту назначения экспорта узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="c80a6-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="c80a6-116">Введите URL-адрес Marketing вашей организации в поле **Адрес сервера**.</span><span class="sxs-lookup"><span data-stu-id="c80a6-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="c80a6-117">В разделе **Учетная запись администратора сервера** выберите **Войти** и выберите учетную запись Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="c80a6-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="c80a6-118">Сопоставьте поле идентификатора клиента с идентификатором контакта Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="c80a6-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="c80a6-119">Выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c80a6-119">Select **Next**.</span></span>

1. <span data-ttu-id="c80a6-120">Выберите один или несколько сегментов.</span><span class="sxs-lookup"><span data-stu-id="c80a6-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="c80a6-121">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c80a6-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c80a6-122">Экспорт данных</span><span class="sxs-lookup"><span data-stu-id="c80a6-122">Export the data</span></span>

<span data-ttu-id="c80a6-123">Вы можете [экспортировать данных по требованию](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c80a6-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="c80a6-124">Экспорт также будет выполняться с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c80a6-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]