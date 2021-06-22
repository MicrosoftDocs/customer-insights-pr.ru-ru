---
title: Экспорт данных Customer Insights в DotDigital
description: Узнайте, как настроить подключение и экспорт в DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8b0bda638c9bc7bb9cb2fdb01be11489b44f28a5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124427"
---
# <a name="export-segments-to-dotdigital-preview"></a><span data-ttu-id="841a4-103">Экспорт сегментов в DotDigital (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="841a4-103">Export segments to DotDigital (preview)</span></span>

<span data-ttu-id="841a4-104">Экспортируйте сегменты унифицированных профилей клиентов в адресные книги DotDigital и используйте их для кампаний, электронного маркетинга и создания клиентских сегментов с помощью DotDigital.</span><span class="sxs-lookup"><span data-stu-id="841a4-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="841a4-105">Предварительные требования для подключения</span><span class="sxs-lookup"><span data-stu-id="841a4-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="841a4-106">У вас есть [учетная запись DotDigital](https://dotdigital.com/) и соответствующие учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="841a4-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="841a4-107">В DotDigital уже есть адресные книги и соответствующие идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="841a4-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="841a4-108">Идентификатор можно найти в URL-адресе, когда вы выбираете и открываете адресную книгу.</span><span class="sxs-lookup"><span data-stu-id="841a4-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="841a4-109">Для получения дополнительной информации см. [Адресные книги DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="841a4-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="841a4-110">У вас есть [настроенные сегменты](segments.md) в аналитике аудитории.</span><span class="sxs-lookup"><span data-stu-id="841a4-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="841a4-111">Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="841a4-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="841a4-112">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="841a4-112">Known limitations</span></span>

- <span data-ttu-id="841a4-113">До 1 миллиона профилей на экспорт в DotDigital.</span><span class="sxs-lookup"><span data-stu-id="841a4-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="841a4-114">Экспорт в DotDigital ограничен сегментами.</span><span class="sxs-lookup"><span data-stu-id="841a4-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="841a4-115">Экспорт сегментов с общим количеством профилей 1 миллион может занять до 3 часов из-за ограничений со стороны провайдера.</span><span class="sxs-lookup"><span data-stu-id="841a4-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="841a4-116">Количество профилей, которые вы можете экспортировать в DotDigital, зависит и ограничивается вашим контрактом с DotDigital.</span><span class="sxs-lookup"><span data-stu-id="841a4-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="841a4-117">Настройка подключения к DotDigital</span><span class="sxs-lookup"><span data-stu-id="841a4-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="841a4-118">Перейти в раздел **Администрирование** > **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="841a4-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="841a4-119">Выберите **Добавить подключение** и выберите **DotDigital** для настройки подключения.</span><span class="sxs-lookup"><span data-stu-id="841a4-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="841a4-120">Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="841a4-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="841a4-121">Имя и тип подключения описывают это подключение.</span><span class="sxs-lookup"><span data-stu-id="841a4-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="841a4-122">Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.</span><span class="sxs-lookup"><span data-stu-id="841a4-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="841a4-123">Укажите, кто может использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="841a4-123">Choose who can use this connection.</span></span> <span data-ttu-id="841a4-124">Если вы не предпримете никаких действий, по умолчанию это будут администраторы.</span><span class="sxs-lookup"><span data-stu-id="841a4-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="841a4-125">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="841a4-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="841a4-126">Введите **имя пользователя DotDigital и пароль**.</span><span class="sxs-lookup"><span data-stu-id="841a4-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="841a4-127">Введите свой **[идентификатор адресной книги DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="841a4-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="841a4-128">Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.</span><span class="sxs-lookup"><span data-stu-id="841a4-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="841a4-129">Выберите **Подключиться** для инициализации подключения к DotDigital.</span><span class="sxs-lookup"><span data-stu-id="841a4-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="841a4-130">Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="841a4-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="841a4-131">Выберите **Сохранить**, чтобы завершить подключение.</span><span class="sxs-lookup"><span data-stu-id="841a4-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="841a4-132">Настройка экспорта</span><span class="sxs-lookup"><span data-stu-id="841a4-132">Configure an export</span></span>

<span data-ttu-id="841a4-133">Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа.</span><span class="sxs-lookup"><span data-stu-id="841a4-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="841a4-134">Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="841a4-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="841a4-135">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="841a4-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="841a4-136">Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.</span><span class="sxs-lookup"><span data-stu-id="841a4-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="841a4-137">В поле **Подключение для экспорта** выберите подключение из раздела DotDigital.</span><span class="sxs-lookup"><span data-stu-id="841a4-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="841a4-138">Если вы не видите название этого раздела, вам не доступны подключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="841a4-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="841a4-139">В разделе **Сопоставление данных** в поле **Электронная почта** выберите унифицированный профиль клиента, который представляет адрес электронной почты клиента.</span><span class="sxs-lookup"><span data-stu-id="841a4-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="841a4-140">Повторите те же шаги для других необязательных полей, таких как **Имя**, **Фамилия**, **ФИО**, **Пол** и **Почтовый индекс**.</span><span class="sxs-lookup"><span data-stu-id="841a4-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="841a4-141">Выберите сегменты, которые нужно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="841a4-141">Select the segments you want to export.</span></span> <span data-ttu-id="841a4-142">Всего в DotDigital можно экспортировать до 1 миллиона профилей клиентов.</span><span class="sxs-lookup"><span data-stu-id="841a4-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="841a4-143">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="841a4-143">Select **Save**.</span></span>

<span data-ttu-id="841a4-144">Сохранение экспорта не запускает экспорт сразу.</span><span class="sxs-lookup"><span data-stu-id="841a4-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="841a4-145">Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="841a4-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="841a4-146">Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="841a4-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="841a4-147">В DotDigital теперь вы можете найти свои сегменты в [адресных книгах DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="841a4-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="841a4-148">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="841a4-148">Data privacy and compliance</span></span>

<span data-ttu-id="841a4-149">Когда вы включаете Dynamics 365 Customer Insights для передачи данных в DotDigital, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="841a4-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="841a4-150">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией DotDigital любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть.</span><span class="sxs-lookup"><span data-stu-id="841a4-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="841a4-151">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="841a4-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="841a4-152">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="841a4-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
