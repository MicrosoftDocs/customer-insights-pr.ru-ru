---
title: Запросы субъектов данных (DSR) в соответствии с GDPR | Документация Майкрософт
description: Отреагируйте на запросы субъекта данных для возможности аналитики аудитории Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed9aa09fba938606611c6ce86c2b250c5e19c606
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268702"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="08f03-103">Запросы субъектов данных (DSR) в соответствии с GDPR</span><span class="sxs-lookup"><span data-stu-id="08f03-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="08f03-104">Реагирование на запросы удаления субъекта данных GDPR для возможности аналитики аудитории Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="08f03-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="08f03-105">"Право на удаление" персональных данных из данных клиентов организации — одно из основных прав, предусмотренных Общим регламентом по защите данных (GDPR).</span><span class="sxs-lookup"><span data-stu-id="08f03-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="08f03-106">Под удалением персональных данных понимается удаление всех персональных данных и формируемых системой журналов, за исключением информации журнала аудита.</span><span class="sxs-lookup"><span data-stu-id="08f03-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="08f03-107">Управление запросами на удаление от субъектов данных</span><span class="sxs-lookup"><span data-stu-id="08f03-107">Manage data subject delete requests</span></span>

<span data-ttu-id="08f03-108">Аналитика аудитории предлагает следующие встроенные в продукт возможности удаления личных данных для конкретного клиента или пользователя:</span><span class="sxs-lookup"><span data-stu-id="08f03-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="08f03-109">**Управление запросами на удаление данных клиента**: данные клиента в Customer Insights поступают из исходных источников данных, внешних по отношению к Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="08f03-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="08f03-110">Все запросы GDPR на удаление должны быть выполнены в оригинальном источнике данных.</span><span class="sxs-lookup"><span data-stu-id="08f03-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="08f03-111">**Управление запросами на удаление пользовательских данных Customer Insights**: данные для пользователей создаются Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="08f03-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="08f03-112">Все запросы GDPR на удаление данных должны быть выполнены в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="08f03-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="08f03-113">Управление запросами на удаление данных клиента</span><span class="sxs-lookup"><span data-stu-id="08f03-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="08f03-114">Администратор Customer Insights может выполнить следующие действия, чтобы удалить данные клиента, которые были удалены в источнике данных:</span><span class="sxs-lookup"><span data-stu-id="08f03-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="08f03-115">Выполните вход в Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="08f03-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="08f03-116">В аналитике аудитории перейдите **Данные** > **Источники данных**</span><span class="sxs-lookup"><span data-stu-id="08f03-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="08f03-117">Для каждого источника данных в списке, который содержит удаленные данные клиента:</span><span class="sxs-lookup"><span data-stu-id="08f03-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="08f03-118">Выберите (...), затем выберите **обновить**.</span><span class="sxs-lookup"><span data-stu-id="08f03-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="08f03-119">Проверьте состояние источника данных в разделе **Состояние**.</span><span class="sxs-lookup"><span data-stu-id="08f03-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="08f03-120">Галочка означает, что обновление прошло успешно.</span><span class="sxs-lookup"><span data-stu-id="08f03-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="08f03-121">Предупреждающий треугольник означает, что что-то пошло не так.</span><span class="sxs-lookup"><span data-stu-id="08f03-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="08f03-122">Если отображается предупреждающий треугольник, свяжитесь с D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="08f03-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="08f03-123">![Обработка запросов GDPR на удаление данных клиента](media/gdpr-data-sources.png "Обработка запросов GDPR на удаление данных клиента")</span><span class="sxs-lookup"><span data-stu-id="08f03-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="08f03-124">Управление запросами на удаление данных пользователей</span><span class="sxs-lookup"><span data-stu-id="08f03-124">Manage delete requests for user data</span></span>

<span data-ttu-id="08f03-125">Администратор Customer Insights может выполнить следующие действия для удаления данных пользователя Customer Insights:</span><span class="sxs-lookup"><span data-stu-id="08f03-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="08f03-126">Выполните вход в Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="08f03-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="08f03-127">В аналитике аудитории перейдите **Администрирование** > **Разрешения**.</span><span class="sxs-lookup"><span data-stu-id="08f03-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="08f03-128">Установите флажок для пользователя, которого необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="08f03-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="08f03-129">Выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="08f03-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="08f03-130">![Управление запросами на удаление GDPR для данных пользователей](media/gdpr-permissions.png "Управление запросами на удаление GDPR для данных пользователей")</span><span class="sxs-lookup"><span data-stu-id="08f03-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="08f03-131">Ответ на запросы GDPR экспорта данных от субъектов данных</span><span class="sxs-lookup"><span data-stu-id="08f03-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="08f03-132">В рамках нашего обязательства сотрудничать с вами на пути к Общему регламенту по защите данных (GDPR) мы разработали документацию, которая поможет вам подготовиться.</span><span class="sxs-lookup"><span data-stu-id="08f03-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="08f03-133">В этой документации описаны шаги, которые вы можете предпринять сегодня, чтобы обеспечить соответствие GDPR при использовании аналитики аудитории.</span><span class="sxs-lookup"><span data-stu-id="08f03-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="08f03-134">Управление запросами на экспорт и просмотр</span><span class="sxs-lookup"><span data-stu-id="08f03-134">Manage export and view requests</span></span>

<span data-ttu-id="08f03-135">Право на переносимость данных гарантирует субъектам данных возможность запросить копию своих персональных данных в электронном формате ("структурированный, широко распространенный, машиночитаемый и совместимый с разными системами формат данных"), которая может быть передана другому управляющему данными.</span><span class="sxs-lookup"><span data-stu-id="08f03-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="08f03-136">Экспорт данных клиентов (администратор клиента)</span><span class="sxs-lookup"><span data-stu-id="08f03-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="08f03-137">Для экспорта данных администратор клиента может выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="08f03-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="08f03-138">Отправить электронное письмо на адрес D365CI@microsoft.com, указав адрес электронной почты клиента в запросе.</span><span class="sxs-lookup"><span data-stu-id="08f03-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="08f03-139">Рабочая группа Customer Insights отправит электронное письмо на зарегистрированный адрес электронной почты администратора клиента с просьбой подтвердить экспорт данных.</span><span class="sxs-lookup"><span data-stu-id="08f03-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="08f03-140">Подтвердите подтверждение экспорта данных для запрошенного клиента.</span><span class="sxs-lookup"><span data-stu-id="08f03-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="08f03-141">Получите экспортированные данные через адрес электронной почты администратора клиента.</span><span class="sxs-lookup"><span data-stu-id="08f03-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="08f03-142">Экспорт данных пользователей (администратор клиента)</span><span class="sxs-lookup"><span data-stu-id="08f03-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="08f03-143">Отправить электронное письмо на адрес D365CI@microsoft.com, указав адрес электронной почты пользователя в запросе.</span><span class="sxs-lookup"><span data-stu-id="08f03-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="08f03-144">Рабочая группа Customer Insights отправит электронное письмо на зарегистрированный адрес электронной почты администратора клиента с просьбой подтвердить экспорт данных.</span><span class="sxs-lookup"><span data-stu-id="08f03-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="08f03-145">Подтвердите подтверждение экспорта данных для запрошенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="08f03-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="08f03-146">Получите экспортированные данные через адрес электронной почты администратора клиента.</span><span class="sxs-lookup"><span data-stu-id="08f03-146">Receive the exported data through the tenant admin email address.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]