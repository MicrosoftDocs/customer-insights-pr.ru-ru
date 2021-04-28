---
title: Экспорт данных Customer Insights в Marketo
description: Узнайте, как настроить подключение и экспорт в Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759837"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="57152-103">Экспорт сегментов в Marketo (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="57152-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="57152-104">Экспортируйте сегменты унифицированных клиентских профилей для создания кампаний, проведения маркетинга по электронной почте и работы с определенными группами клиентов в Marketo.</span><span class="sxs-lookup"><span data-stu-id="57152-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="57152-105">Предварительные требования для подключения</span><span class="sxs-lookup"><span data-stu-id="57152-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="57152-106">У вас есть [учетная запись Marketo](https://login.marketo.com/) и соответствующие учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="57152-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="57152-107">В Marketo уже есть списки и соответствующие идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="57152-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="57152-108">Для получения дополнительных сведений посетите веб-сайт [Списки Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="57152-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="57152-109">У вас есть [настроенные сегменты](segments.md).</span><span class="sxs-lookup"><span data-stu-id="57152-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="57152-110">Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="57152-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="57152-111">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="57152-111">Known limitations</span></span>

- <span data-ttu-id="57152-112">До 1 миллиона профилей на экспорт в Marketo.</span><span class="sxs-lookup"><span data-stu-id="57152-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="57152-113">Экспорт в Marketo ограничен сегментами.</span><span class="sxs-lookup"><span data-stu-id="57152-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="57152-114">Экспорт сегментов с общим количеством профилей 1 миллион может занять до 3 часов.</span><span class="sxs-lookup"><span data-stu-id="57152-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="57152-115">Количество профилей, которые вы можете экспортировать в Marketo, зависит и ограничивается вашим контрактом с Marketo.</span><span class="sxs-lookup"><span data-stu-id="57152-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="57152-116">Настройка подключения к Marketo</span><span class="sxs-lookup"><span data-stu-id="57152-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="57152-117">Перейти в раздел **Администрирование** > **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="57152-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="57152-118">Выберите **Добавить подключение** и выберите **Marketo** для настройки подключения.</span><span class="sxs-lookup"><span data-stu-id="57152-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="57152-119">Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="57152-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="57152-120">Имя и тип подключения описывают это подключение.</span><span class="sxs-lookup"><span data-stu-id="57152-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="57152-121">Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.</span><span class="sxs-lookup"><span data-stu-id="57152-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="57152-122">Укажите, кто может использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="57152-122">Choose who can use this connection.</span></span> <span data-ttu-id="57152-123">Если вы не предпримете никаких действий, по умолчанию это будут администраторы.</span><span class="sxs-lookup"><span data-stu-id="57152-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="57152-124">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="57152-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="57152-125">Введите ваш **[Идентификатор клиента Marketo, секрет клиента и имя узла конечной точки REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="57152-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="57152-126">Выберите **Принимаю**, чтобы подтвердить **Соответствие и конфиденциальность данных** и выберите **Подключить** для инициализации подключения к Marketo.</span><span class="sxs-lookup"><span data-stu-id="57152-126">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="57152-127">Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="57152-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="57152-128">Выберите **Сохранить**, чтобы завершить подключение.</span><span class="sxs-lookup"><span data-stu-id="57152-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="57152-129">Настройка экспорта</span><span class="sxs-lookup"><span data-stu-id="57152-129">Configure an export</span></span>

<span data-ttu-id="57152-130">Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа.</span><span class="sxs-lookup"><span data-stu-id="57152-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="57152-131">Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="57152-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="57152-132">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="57152-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="57152-133">Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.</span><span class="sxs-lookup"><span data-stu-id="57152-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="57152-134">В поле **Подключение для экспорта** выберите подключение из раздела Marketo.</span><span class="sxs-lookup"><span data-stu-id="57152-134">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="57152-135">Если вы не видите название этого раздела, вам не доступны подключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="57152-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="57152-136">Введите ваш **[Идентификатор списка Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="57152-136">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="57152-137">В разделе **Сопоставление данных** в поле **Электронная почта** выберите унифицированный профиль клиента, который представляет адрес электронной почты клиента.</span><span class="sxs-lookup"><span data-stu-id="57152-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="57152-138">При желании вы можете экспортировать поля **Имя**, **Фамилия**, **Город**, **Штат** и **Страна/регион** для создания более персонализированных сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="57152-138">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="57152-139">Выберите **Добавить атрибут**, чтобы сопоставить эти поля.</span><span class="sxs-lookup"><span data-stu-id="57152-139">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="57152-140">Выберите сегменты, которые нужно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="57152-140">Select the segments you want to export.</span></span> <span data-ttu-id="57152-141">Всего в Marketo можно экспортировать до 1 миллиона профилей клиентов.</span><span class="sxs-lookup"><span data-stu-id="57152-141">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="57152-142">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="57152-142">Select **Save**.</span></span>

<span data-ttu-id="57152-143">Сохранение экспорта не запускает экспорт сразу.</span><span class="sxs-lookup"><span data-stu-id="57152-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="57152-144">Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="57152-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="57152-145">Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="57152-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="57152-146">Теперь в Marketo вы можете найти свои сегменты в [Списки Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="57152-146">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="57152-147">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="57152-147">Data privacy and compliance</span></span>

<span data-ttu-id="57152-148">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в Marketo, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="57152-148">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="57152-149">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией Marketo любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть.</span><span class="sxs-lookup"><span data-stu-id="57152-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="57152-150">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="57152-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="57152-151">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="57152-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]