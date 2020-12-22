---
title: Экспорт данных Customer Insights в Dynamics 365 Marketing
description: Узнайте, как настроить подключение к Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643789"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="a78a4-103">Соединитель для Dynamics 365 Marketing (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="a78a4-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a78a4-104">Используйте [сегменты](segments.md) для создания кампаний и связи с определенными группами клиентов с помощью Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="a78a4-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="a78a4-105">Дополнительные сведения см. в [Используйте сегменты из Dynamics 365 Customer Insights с Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="a78a4-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="a78a4-106">Необходимые условия</span><span class="sxs-lookup"><span data-stu-id="a78a4-106">Prerequisite</span></span>

<span data-ttu-id="a78a4-107">Записи контактов, [полученные из Dynamics 365 Marketing Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="a78a4-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="a78a4-108">Настройка соединителя для Marketing</span><span class="sxs-lookup"><span data-stu-id="a78a4-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="a78a4-109">В аналитике аудитории перейдите **Администрирование** > **Экспорт пунктов назначения**.</span><span class="sxs-lookup"><span data-stu-id="a78a4-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a78a4-110">В пункте **Dynamics 365 Marketing** выберите **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="a78a4-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="a78a4-111">Дайте вашему пункту назначения экспорта узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="a78a4-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="a78a4-112">Введите URL-адрес Marketing вашей организации в поле **Адрес сервера**.</span><span class="sxs-lookup"><span data-stu-id="a78a4-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="a78a4-113">В разделе **Учетная запись администратора сервера** выберите **Войти** и выберите учетную запись Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="a78a4-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="a78a4-114">Сопоставьте поле идентификатора клиента с идентификатором контакта Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a78a4-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="a78a4-115">Выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a78a4-115">Select **Next**.</span></span>

1. <span data-ttu-id="a78a4-116">Выберите один или несколько сегментов.</span><span class="sxs-lookup"><span data-stu-id="a78a4-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="a78a4-117">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a78a4-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a78a4-118">Экспорт данных</span><span class="sxs-lookup"><span data-stu-id="a78a4-118">Export the data</span></span>

<span data-ttu-id="a78a4-119">Вы можете [экспортировать данных по требованию](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a78a4-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a78a4-120">Экспорт также будет выполняться с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a78a4-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
