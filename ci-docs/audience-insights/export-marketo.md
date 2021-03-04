---
title: Экспорт данных Customer Insights в Marketo
description: Узнайте, как настроить подключение к Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267097"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="857ae-103">Соединитель для Marketo (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="857ae-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="857ae-104">Экспортируйте сегменты унифицированных клиентских профилей для создания кампаний, проведения маркетинга по электронной почте и работы с определенными группами клиентов в Marketo.</span><span class="sxs-lookup"><span data-stu-id="857ae-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="857ae-105">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="857ae-105">Prerequisites</span></span>

-   <span data-ttu-id="857ae-106">У вас есть [учетная запись Marketo](https://login.marketo.com/) и соответствующие учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="857ae-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="857ae-107">В Marketo уже есть списки и соответствующие идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="857ae-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="857ae-108">Для получения дополнительных сведений посетите веб-сайт [Списки Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="857ae-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="857ae-109">У вас есть [настроенные сегменты](segments.md).</span><span class="sxs-lookup"><span data-stu-id="857ae-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="857ae-110">Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="857ae-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="857ae-111">Подключение к Marketo</span><span class="sxs-lookup"><span data-stu-id="857ae-111">Connect to Marketo</span></span>

1. <span data-ttu-id="857ae-112">Откройте **Администратор** > **Пункты назначения экспорта**.</span><span class="sxs-lookup"><span data-stu-id="857ae-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="857ae-113">Под **Marketo** выберите **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="857ae-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="857ae-114">Дайте вашему пункту назначения экспорта узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="857ae-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="857ae-115">Введите ваш **[Идентификатор клиента Marketo, секрет клиента и имя узла конечной точки REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="857ae-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="857ae-116">Введите ваш **[Идентификатор списка Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="857ae-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="857ae-117">Выберите **Принимаю**, чтобы подтвердить **Соответствие и конфиденциальность данных** и выберите **Подключить** для инициализации подключения к Marketo.</span><span class="sxs-lookup"><span data-stu-id="857ae-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="857ae-118">Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="857ae-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Снимок экрана экспорта подключения Marketo":::

1. <span data-ttu-id="857ae-120">Выберите **Далее**, чтобы настроить экспорт.</span><span class="sxs-lookup"><span data-stu-id="857ae-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="857ae-121">Настройка соединителя</span><span class="sxs-lookup"><span data-stu-id="857ae-121">Configure the connector</span></span>

1. <span data-ttu-id="857ae-122">В разделе **Сопоставление данных** в поле **Электронная почта** выберите унифицированный профиль клиента, который представляет адрес электронной почты клиента.</span><span class="sxs-lookup"><span data-stu-id="857ae-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="857ae-123">По желанию вы можете экспортировать **Имя**, **Фамилия**, **Город**, **Регион** и **Страна** в качестве дополнительных полей для создания более персонализированных писем.</span><span class="sxs-lookup"><span data-stu-id="857ae-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="857ae-124">Выберите **Добавить атрибут**, чтобы сопоставить эти поля.</span><span class="sxs-lookup"><span data-stu-id="857ae-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="857ae-125">Выберите сегменты, которые нужно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="857ae-125">Select the segments you want to export.</span></span> <span data-ttu-id="857ae-126">Всего в Marketo можно экспортировать до 1 миллиона профилей клиентов.</span><span class="sxs-lookup"><span data-stu-id="857ae-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Выберите поля и сегменты для экспорта в Marketo":::

1. <span data-ttu-id="857ae-128">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="857ae-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="857ae-129">Экспорт данных</span><span class="sxs-lookup"><span data-stu-id="857ae-129">Export the data</span></span>

<span data-ttu-id="857ae-130">Вы можете [экспортировать данных по требованию](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="857ae-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="857ae-131">Экспорт также будет выполняться с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="857ae-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="857ae-132">Теперь в Marketo вы можете найти свои сегменты в [Списки Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="857ae-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="857ae-133">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="857ae-133">Known limitations</span></span>

- <span data-ttu-id="857ae-134">До 1 миллиона профилей на экспорт в Marketo.</span><span class="sxs-lookup"><span data-stu-id="857ae-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="857ae-135">Экспорт в Marketo ограничен сегментами.</span><span class="sxs-lookup"><span data-stu-id="857ae-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="857ae-136">Экспорт сегментов с общим количеством профилей 1 миллион может занять до 3 часов.</span><span class="sxs-lookup"><span data-stu-id="857ae-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="857ae-137">Количество профилей, которые вы можете экспортировать в Marketo, зависит и ограничивается вашим контрактом с Marketo.</span><span class="sxs-lookup"><span data-stu-id="857ae-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="857ae-138">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="857ae-138">Data privacy and compliance</span></span>

<span data-ttu-id="857ae-139">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в Marketo, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="857ae-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="857ae-140">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией Marketo любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть.</span><span class="sxs-lookup"><span data-stu-id="857ae-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="857ae-141">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="857ae-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="857ae-142">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="857ae-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]