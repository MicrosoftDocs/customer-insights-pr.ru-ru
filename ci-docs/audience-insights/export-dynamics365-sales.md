---
title: Экспорт данных Customer Insights в Dynamics 365 Sales
description: Узнайте, как настроить подключение к Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598125"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="ed212-103">Соединитель для Dynamics 365 Sales (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="ed212-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ed212-104">Используйте свои данные о клиентах для создания маркетинговых списков, бизнес-процессов для дальнейших действий, а также рассылки предложений с помощью Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="ed212-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="ed212-105">Необходимые условия</span><span class="sxs-lookup"><span data-stu-id="ed212-105">Prerequisite</span></span>

1. <span data-ttu-id="ed212-106">Записи контактов должны присутствовать в Dynamics 365 Sales, прежде чем вы сможете экспортировать сегмент из Customer Insights в Sales.</span><span class="sxs-lookup"><span data-stu-id="ed212-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="ed212-107">См. дополнительные сведения о загрузке контактов в [Dynamics 365 Sales с помощью Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="ed212-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="ed212-108">Экспорт сегментов из аналитики аудитории в Sales не приведет к созданию новых записей контактов в экземплярах Sales.</span><span class="sxs-lookup"><span data-stu-id="ed212-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="ed212-109">Записи контактов из Sales должны быть загружены в аналитику аудитории и использованы как источник данных.</span><span class="sxs-lookup"><span data-stu-id="ed212-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="ed212-110">Их также необходимо включить в объединенную сущность «Клиент», чтобы сопоставить идентификаторы клиентов с идентификаторами контактов, прежде чем сегменты можно будет экспортировать.</span><span class="sxs-lookup"><span data-stu-id="ed212-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="ed212-111">Настройка соединителя для Sales</span><span class="sxs-lookup"><span data-stu-id="ed212-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="ed212-112">В аналитике аудитории перейдите **Администрирование** > **Экспорт пунктов назначения**.</span><span class="sxs-lookup"><span data-stu-id="ed212-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ed212-113">В пункте **Dynamics 365 Sales** выберите **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="ed212-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="ed212-114">Дайте вашему пункту назначения экспорта узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="ed212-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="ed212-115">Введите URL-адрес Sales вашей организации в поле **Адрес сервера**.</span><span class="sxs-lookup"><span data-stu-id="ed212-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="ed212-116">В разделе **Учетная запись администратора сервера** выберите **Войти** и выберите учетную запись Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="ed212-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="ed212-117">Сопоставьте поле идентификатора клиента с идентификатором контакта Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="ed212-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="ed212-118">Выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ed212-118">Select **Next**.</span></span>

1. <span data-ttu-id="ed212-119">Выберите один или несколько сегментов.</span><span class="sxs-lookup"><span data-stu-id="ed212-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="ed212-120">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ed212-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ed212-121">Экспорт данных</span><span class="sxs-lookup"><span data-stu-id="ed212-121">Export the data</span></span>

<span data-ttu-id="ed212-122">Вы можете [экспортировать данных по требованию](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="ed212-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="ed212-123">Экспорт также будет выполняться с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ed212-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]