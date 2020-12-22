---
title: Экспорт данных Customer Insights в DotDigital
description: Узнайте, как настроить подключение к DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed6bd40e8575fc90258f79f60abffe54f136d274
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644464"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="485d7-103">Соединитель для DotDigital (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="485d7-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="485d7-104">Экспортируйте сегменты унифицированных профилей клиентов в адресные книги DotDigital и используйте их для кампаний, электронного маркетинга и создания клиентских сегментов с помощью DotDigital.</span><span class="sxs-lookup"><span data-stu-id="485d7-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="485d7-105">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="485d7-105">Prerequisites</span></span>

-   <span data-ttu-id="485d7-106">У вас есть [учетная запись DotDigital](https://dotdigital.com/) и соответствующие учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="485d7-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="485d7-107">В DotDigital уже есть адресные книги и соответствующие идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="485d7-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="485d7-108">Идентификатор можно найти в URL-адресе, когда вы выбираете и открываете адресную книгу.</span><span class="sxs-lookup"><span data-stu-id="485d7-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="485d7-109">Для получения дополнительной информации см. [Адресные книги DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="485d7-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="485d7-110">У вас есть [настроенные сегменты](segments.md) в аналитике аудитории.</span><span class="sxs-lookup"><span data-stu-id="485d7-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="485d7-111">Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="485d7-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="485d7-112">Подключение к DotDigital</span><span class="sxs-lookup"><span data-stu-id="485d7-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="485d7-113">Откройте **Администратор** > **Пункты назначения экспорта**.</span><span class="sxs-lookup"><span data-stu-id="485d7-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="485d7-114">Под **DotDigital** выберите **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="485d7-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="485d7-115">Дайте вашему пункту назначения экспорта узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="485d7-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Панель конфигурации для экспорта DotDigital.":::

1. <span data-ttu-id="485d7-117">Введите **имя пользователя DotDigital и пароль**.</span><span class="sxs-lookup"><span data-stu-id="485d7-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="485d7-118">Введите свой **[идентификатор адресной книги DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="485d7-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="485d7-119">Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.</span><span class="sxs-lookup"><span data-stu-id="485d7-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="485d7-120">Выберите **Подключиться** для инициализации подключения к DotDigital.</span><span class="sxs-lookup"><span data-stu-id="485d7-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="485d7-121">Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="485d7-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="485d7-122">Выберите **Далее**, чтобы настроить экспорт.</span><span class="sxs-lookup"><span data-stu-id="485d7-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="485d7-123">Настройка соединителя</span><span class="sxs-lookup"><span data-stu-id="485d7-123">Configure the connector</span></span>

1. <span data-ttu-id="485d7-124">В разделе **Сопоставление данных** в поле **Электронная почта** выберите унифицированный профиль клиента, который представляет адрес электронной почты клиента.</span><span class="sxs-lookup"><span data-stu-id="485d7-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="485d7-125">Повторите те же шаги для других необязательных полей, таких как **Имя**, **Фамилия**, **ФИО**, **Пол** и **Почтовый индекс**.</span><span class="sxs-lookup"><span data-stu-id="485d7-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="485d7-126">Выберите сегменты, которые нужно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="485d7-126">Select the segments you want to export.</span></span> <span data-ttu-id="485d7-127">Всего в DotDigital можно экспортировать до 1 миллиона профилей клиентов.</span><span class="sxs-lookup"><span data-stu-id="485d7-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="485d7-128">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="485d7-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="485d7-129">Экспорт данных</span><span class="sxs-lookup"><span data-stu-id="485d7-129">Export the data</span></span>

<span data-ttu-id="485d7-130">Вы можете [экспортировать данных по требованию](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="485d7-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="485d7-131">Экспорт также будет выполняться с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="485d7-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="485d7-132">В DotDigital теперь вы можете найти свои сегменты в [адресных книгах DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="485d7-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="485d7-133">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="485d7-133">Known limitations</span></span>

- <span data-ttu-id="485d7-134">До 1 миллиона профилей на экспорт в DotDigital.</span><span class="sxs-lookup"><span data-stu-id="485d7-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="485d7-135">Экспорт в DotDigital ограничен сегментами.</span><span class="sxs-lookup"><span data-stu-id="485d7-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="485d7-136">Экспорт сегментов с общим количеством профилей 1 миллион может занять до 3 часов из-за ограничений со стороны провайдера.</span><span class="sxs-lookup"><span data-stu-id="485d7-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="485d7-137">Количество профилей, которые вы можете экспортировать в DotDigital, зависит и ограничивается вашим контрактом с DotDigital.</span><span class="sxs-lookup"><span data-stu-id="485d7-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="485d7-138">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="485d7-138">Data privacy and compliance</span></span>

<span data-ttu-id="485d7-139">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в DotDigital, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="485d7-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="485d7-140">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией DotDigital любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть.</span><span class="sxs-lookup"><span data-stu-id="485d7-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="485d7-141">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="485d7-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="485d7-142">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="485d7-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
