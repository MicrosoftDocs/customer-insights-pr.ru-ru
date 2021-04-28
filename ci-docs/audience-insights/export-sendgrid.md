---
title: Экспорт данных Customer Insights в SendGrid
description: Узнайте, как настроить подключение и экспорт в SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a4c64cf77c682e07f3d0759c43355336b5806fc8
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759781"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="333d6-103">Экспорт сегментов в SendGrid (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="333d6-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="333d6-104">Экспортируйте сегменты единых профилей клиентов в списки контактов SendGrid и используйте их для кампаний и маркетинга по электронной почте в SendGrid.</span><span class="sxs-lookup"><span data-stu-id="333d6-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="333d6-105">Предварительные требования для подключения</span><span class="sxs-lookup"><span data-stu-id="333d6-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="333d6-106">У вас есть [учетная запись SendGrid](https://sendgrid.com/) и соответствующие учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="333d6-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="333d6-107">В SendGrid уже есть списки контактов и соответствующие идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="333d6-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="333d6-108">Для получения дополнительной информации см. [SendGrid — Управление контактами](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="333d6-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="333d6-109">У вас есть [настроенные сегменты](segments.md) в аналитике аудитории.</span><span class="sxs-lookup"><span data-stu-id="333d6-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="333d6-110">Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="333d6-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="333d6-111">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="333d6-111">Known limitations</span></span>

- <span data-ttu-id="333d6-112">Всего в SendGrid до 100 000 профилей.</span><span class="sxs-lookup"><span data-stu-id="333d6-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="333d6-113">Экспорт в SendGrid ограничен сегментами.</span><span class="sxs-lookup"><span data-stu-id="333d6-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="333d6-114">Экспорт до 100 000 профилей в SendGrid может занять до нескольких часов.</span><span class="sxs-lookup"><span data-stu-id="333d6-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="333d6-115">Количество профилей, которые вы можете экспортировать в SendGrid, зависит и ограничивается вашим контрактом с SendGrid.</span><span class="sxs-lookup"><span data-stu-id="333d6-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="333d6-116">Настройка подключения к SendGrid</span><span class="sxs-lookup"><span data-stu-id="333d6-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="333d6-117">Перейти в раздел **Администрирование** > **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="333d6-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="333d6-118">Выберите **Добавить подключение** и выберите **SendGrid** для настройки подключения.</span><span class="sxs-lookup"><span data-stu-id="333d6-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="333d6-119">Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="333d6-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="333d6-120">Имя и тип подключения описывают это подключение.</span><span class="sxs-lookup"><span data-stu-id="333d6-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="333d6-121">Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.</span><span class="sxs-lookup"><span data-stu-id="333d6-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="333d6-122">Укажите, кто может использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="333d6-122">Choose who can use this connection.</span></span> <span data-ttu-id="333d6-123">Если вы не предпримете никаких действий, по умолчанию это будут администраторы.</span><span class="sxs-lookup"><span data-stu-id="333d6-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="333d6-124">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="333d6-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="333d6-125">Введите ваш **Ключ API SendGrid** [Ключ API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="333d6-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="333d6-126">Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.</span><span class="sxs-lookup"><span data-stu-id="333d6-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="333d6-127">Выберите **Подключиться** для инициализации подключения к SendGrid.</span><span class="sxs-lookup"><span data-stu-id="333d6-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="333d6-128">Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="333d6-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="333d6-129">Выберите **Сохранить**, чтобы завершить подключение.</span><span class="sxs-lookup"><span data-stu-id="333d6-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="333d6-130">Настройка экспорта</span><span class="sxs-lookup"><span data-stu-id="333d6-130">Configure an export</span></span>

<span data-ttu-id="333d6-131">Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа.</span><span class="sxs-lookup"><span data-stu-id="333d6-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="333d6-132">Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="333d6-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="333d6-133">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="333d6-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="333d6-134">Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.</span><span class="sxs-lookup"><span data-stu-id="333d6-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="333d6-135">В поле **Подключение для экспорта** выберите подключение из раздела SendGrid.</span><span class="sxs-lookup"><span data-stu-id="333d6-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="333d6-136">Если вы не видите название этого раздела, вам не доступны подключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="333d6-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="333d6-137">Введите ваш **[Идентификатор списка SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="333d6-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="333d6-138">В разделе **Сопоставление данных** в поле **Электронная почта** выберите унифицированный профиль клиента, который представляет адрес электронной почты клиента.</span><span class="sxs-lookup"><span data-stu-id="333d6-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="333d6-139">Повторите те же шаги для других необязательных полей, таких как **Имя**, **Фамилия**, **Страна/регион**, **Область, республика, край, округ**, **Город** и **Почтовый индекс**.</span><span class="sxs-lookup"><span data-stu-id="333d6-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="333d6-140">Выберите сегменты, которые нужно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="333d6-140">Select the segments you want to export.</span></span> <span data-ttu-id="333d6-141">Мы настоятельно **рекомендуем не экспортировать в общей сложности более 100 000 профилей клиентов** в SendGrid.</span><span class="sxs-lookup"><span data-stu-id="333d6-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="333d6-142">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="333d6-142">Select **Save**.</span></span>

<span data-ttu-id="333d6-143">Сохранение экспорта не запускает экспорт сразу.</span><span class="sxs-lookup"><span data-stu-id="333d6-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="333d6-144">Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="333d6-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="333d6-145">Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="333d6-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="333d6-146">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="333d6-146">Data privacy and compliance</span></span>

<span data-ttu-id="333d6-147">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в SendGrid, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="333d6-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="333d6-148">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией SendGrid любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть.</span><span class="sxs-lookup"><span data-stu-id="333d6-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="333d6-149">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="333d6-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="333d6-150">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="333d6-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]