---
title: Экспорт данных Customer Insights в AdRoll
description: Узнайте, как настроить подключение к AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697090"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="84b26-103">Соединитель для AdRoll (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="84b26-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="84b26-104">Экспортируйте сегменты унифицированных профилей клиентов в AdRoll и используйте их для рекламы.</span><span class="sxs-lookup"><span data-stu-id="84b26-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="84b26-105">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="84b26-105">Prerequisites</span></span>

-   <span data-ttu-id="84b26-106">У вас есть [учетная запись AdRoll](https://www.adroll.com/) и соответствующие учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="84b26-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="84b26-107">У вас есть [настроенные сегменты](segments.md) в аналитике аудитории.</span><span class="sxs-lookup"><span data-stu-id="84b26-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="84b26-108">Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="84b26-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="84b26-109">Подключение к AdRoll</span><span class="sxs-lookup"><span data-stu-id="84b26-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="84b26-110">Откройте **Администратор** > **Пункты назначения экспорта**.</span><span class="sxs-lookup"><span data-stu-id="84b26-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="84b26-111">В разделе **AdRoll** выберите **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="84b26-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="84b26-112">Дайте вашему пункту назначения экспорта узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="84b26-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Панель конфигурации для подключения AdRoll.":::

1. <span data-ttu-id="84b26-114">Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.</span><span class="sxs-lookup"><span data-stu-id="84b26-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="84b26-115">Выберите **Подключиться** для инициализации подключения к AdRoll.</span><span class="sxs-lookup"><span data-stu-id="84b26-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="84b26-116">Выберите **Авторизоваться в AdRoll** и укажите свои учетные данные AdRoll.</span><span class="sxs-lookup"><span data-stu-id="84b26-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="84b26-117">Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="84b26-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="84b26-118">Введите ваш **Идентификатор рекламодателя AdRoll** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="84b26-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="84b26-119">Выберите **Далее**, чтобы настроить экспорт.</span><span class="sxs-lookup"><span data-stu-id="84b26-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="84b26-120">Настройка соединителя</span><span class="sxs-lookup"><span data-stu-id="84b26-120">Configure the connector</span></span>

1. <span data-ttu-id="84b26-121">В разделе **Сопоставление данных** в поле **Электронная почта** выберите унифицированный профиль клиента, который представляет адрес электронной почты клиента.</span><span class="sxs-lookup"><span data-stu-id="84b26-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="84b26-122">Требуется экспортировать сегменты в AdRoll.</span><span class="sxs-lookup"><span data-stu-id="84b26-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="84b26-123">Выберите сегменты, которые нужно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="84b26-123">Select the segments you want to export.</span></span> <span data-ttu-id="84b26-124">Выберите сегмент, в котором не менее 100 участников.</span><span class="sxs-lookup"><span data-stu-id="84b26-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="84b26-125">Вы не можете экспортировать меньшие сегменты.</span><span class="sxs-lookup"><span data-stu-id="84b26-125">You can't export smaller segments.</span></span> <span data-ttu-id="84b26-126">Кроме того, максимальный размер экспортируемого сегмента составляет 250 000 участников для каждого экспорта.</span><span class="sxs-lookup"><span data-stu-id="84b26-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="84b26-127">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="84b26-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="84b26-128">Экспорт данных</span><span class="sxs-lookup"><span data-stu-id="84b26-128">Export the data</span></span>

<span data-ttu-id="84b26-129">Вы можете [экспортировать данных по требованию](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="84b26-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="84b26-130">Экспорт также будет выполняться с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="84b26-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="84b26-131">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="84b26-131">Known limitations</span></span>

- <span data-ttu-id="84b26-132">Всего в AdRoll можно экспортировать до 250 000 профилей.</span><span class="sxs-lookup"><span data-stu-id="84b26-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="84b26-133">Вы не можете экспортировать сегменты с менее чем 100 профилями в AdRoll.</span><span class="sxs-lookup"><span data-stu-id="84b26-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="84b26-134">Экспорт в AdRoll ограничен сегментами.</span><span class="sxs-lookup"><span data-stu-id="84b26-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="84b26-135">Экспорт до 250 000 профилей в AdRoll может занять до 10 минут.</span><span class="sxs-lookup"><span data-stu-id="84b26-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="84b26-136">Количество профилей, которые вы можете экспортировать в AdRoll ограничен вашим контрактом с AdRoll.</span><span class="sxs-lookup"><span data-stu-id="84b26-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="84b26-137">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="84b26-137">Data privacy and compliance</span></span>

<span data-ttu-id="84b26-138">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в AdRoll, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="84b26-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="84b26-139">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение AdRoll любых обязательств в отношении конфиденциальности или безопасности.</span><span class="sxs-lookup"><span data-stu-id="84b26-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="84b26-140">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="84b26-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="84b26-141">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="84b26-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
