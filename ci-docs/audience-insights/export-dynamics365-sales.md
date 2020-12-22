---
title: Экспорт данных Customer Insights в Dynamics 365 Sales
description: Узнайте, как настроить подключение к Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643834"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="a5e92-103">Соединитель для Dynamics 365 Sales (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="a5e92-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a5e92-104">Используйте свои данные о клиентах для создания маркетинговых списков, бизнес-процессов для дальнейших действий, а также рассылки предложений с помощью Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="a5e92-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="a5e92-105">Необходимые условия</span><span class="sxs-lookup"><span data-stu-id="a5e92-105">Prerequisite</span></span>

<span data-ttu-id="a5e92-106">Записи контактов, [полученные из Dynamics 365 Sales с помощью Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="a5e92-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="a5e92-107">Настройка соединителя для Sales</span><span class="sxs-lookup"><span data-stu-id="a5e92-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="a5e92-108">В аналитике аудитории перейдите **Администрирование** > **Экспорт пунктов назначения**.</span><span class="sxs-lookup"><span data-stu-id="a5e92-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a5e92-109">В пункте **Dynamics 365 Sales** выберите **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="a5e92-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="a5e92-110">Дайте вашему пункту назначения экспорта узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="a5e92-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="a5e92-111">Введите URL-адрес Sales вашей организации в поле **Адрес сервера**.</span><span class="sxs-lookup"><span data-stu-id="a5e92-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="a5e92-112">В разделе **Учетная запись администратора сервера** выберите **Войти** и выберите учетную запись Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="a5e92-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="a5e92-113">Сопоставьте поле идентификатора клиента с идентификатором контакта Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a5e92-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="a5e92-114">Выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a5e92-114">Select **Next**.</span></span>

1. <span data-ttu-id="a5e92-115">Выберите один или несколько сегментов.</span><span class="sxs-lookup"><span data-stu-id="a5e92-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="a5e92-116">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a5e92-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a5e92-117">Экспорт данных</span><span class="sxs-lookup"><span data-stu-id="a5e92-117">Export the data</span></span>

<span data-ttu-id="a5e92-118">Вы можете [экспортировать данных по требованию](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a5e92-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a5e92-119">Экспорт также будет выполняться с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a5e92-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
