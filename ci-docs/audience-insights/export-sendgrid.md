---
title: Экспорт данных Customer Insights в SendGrid
description: Узнайте, как настроить подключение к SendGrid.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597297"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="268ab-103">Соединитель для SendGrid (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="268ab-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="268ab-104">Экспортируйте сегменты единых профилей клиентов в списки контактов SendGrid и используйте их для кампаний и маркетинга по электронной почте в SendGrid.</span><span class="sxs-lookup"><span data-stu-id="268ab-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="268ab-105">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="268ab-105">Prerequisites</span></span>

-   <span data-ttu-id="268ab-106">У вас есть [учетная запись SendGrid](https://sendgrid.com/) и соответствующие учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="268ab-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="268ab-107">В SendGrid уже есть списки контактов и соответствующие идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="268ab-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="268ab-108">Для получения дополнительной информации см. [SendGrid — Управление контактами](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="268ab-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="268ab-109">У вас есть [настроенные сегменты](segments.md) в аналитике аудитории.</span><span class="sxs-lookup"><span data-stu-id="268ab-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="268ab-110">Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="268ab-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="268ab-111">Подключение к SendGrid</span><span class="sxs-lookup"><span data-stu-id="268ab-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="268ab-112">Откройте **Администратор** > **Пункты назначения экспорта**.</span><span class="sxs-lookup"><span data-stu-id="268ab-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="268ab-113">В **SendGrid** выберите **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="268ab-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="268ab-114">Дайте вашему пункту назначения экспорта узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="268ab-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Панель конфигурации экспорта SendGrid.":::

1. <span data-ttu-id="268ab-116">Введите ваш **Ключ API SendGrid** [Ключ API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="268ab-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="268ab-117">Введите ваш **[Идентификатор списка SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="268ab-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="268ab-118">Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.</span><span class="sxs-lookup"><span data-stu-id="268ab-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="268ab-119">Выберите **Подключиться** для инициализации подключения к SendGrid.</span><span class="sxs-lookup"><span data-stu-id="268ab-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="268ab-120">Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="268ab-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="268ab-121">Выберите **Далее**, чтобы настроить экспорт.</span><span class="sxs-lookup"><span data-stu-id="268ab-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="268ab-122">Настройка соединителя</span><span class="sxs-lookup"><span data-stu-id="268ab-122">Configure the connector</span></span>

1. <span data-ttu-id="268ab-123">В разделе **Сопоставление данных** в поле **Электронная почта** выберите унифицированный профиль клиента, который представляет адрес электронной почты клиента.</span><span class="sxs-lookup"><span data-stu-id="268ab-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="268ab-124">Повторите те же шаги для других необязательных полей, таких как **Имя**, **Фамилия**, **Страна/регион**, **Область, республика, край, округ**, **Город** и **Почтовый индекс**.</span><span class="sxs-lookup"><span data-stu-id="268ab-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="268ab-125">Выберите сегменты, которые нужно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="268ab-125">Select the segments you want to export.</span></span> <span data-ttu-id="268ab-126">Мы настоятельно **рекомендуем не экспортировать в общей сложности более 100 000 профилей клиентов** в SendGrid.</span><span class="sxs-lookup"><span data-stu-id="268ab-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="268ab-127">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="268ab-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="268ab-128">Экспорт данных</span><span class="sxs-lookup"><span data-stu-id="268ab-128">Export the data</span></span>

<span data-ttu-id="268ab-129">Вы можете [экспортировать данных по требованию](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="268ab-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="268ab-130">Экспорт также будет выполняться с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="268ab-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="268ab-131">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="268ab-131">Known limitations</span></span>

- <span data-ttu-id="268ab-132">Всего в SendGrid до 100 000 профилей.</span><span class="sxs-lookup"><span data-stu-id="268ab-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="268ab-133">Экспорт в SendGrid ограничен сегментами.</span><span class="sxs-lookup"><span data-stu-id="268ab-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="268ab-134">Экспорт до 100 000 профилей в SendGrid может занять до нескольких часов.</span><span class="sxs-lookup"><span data-stu-id="268ab-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="268ab-135">Количество профилей, которые вы можете экспортировать в SendGrid, зависит и ограничивается вашим контрактом с SendGrid.</span><span class="sxs-lookup"><span data-stu-id="268ab-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="268ab-136">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="268ab-136">Data privacy and compliance</span></span>

<span data-ttu-id="268ab-137">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в SendGrid, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="268ab-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="268ab-138">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией SendGrid любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть.</span><span class="sxs-lookup"><span data-stu-id="268ab-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="268ab-139">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="268ab-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="268ab-140">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="268ab-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]