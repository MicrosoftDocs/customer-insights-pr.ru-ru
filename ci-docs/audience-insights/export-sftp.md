---
title: Экспорт данных Customer Insights в узлы SFTP
description: Узнайте, как настроить подключение и экспорт в местоположение SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3663a48955f0b1db8a96e25403e5f8947bc6a220
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976955"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a><span data-ttu-id="46e36-103">Экспорт списков сегментов и других данных по протоколу SFTP (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="46e36-103">Export segment lists and other data to SFTP (preview)</span></span>

<span data-ttu-id="46e36-104">Используйте данные своих клиентов в сторонних приложениях, экспортируя их в расположение по протоколу SFTP.</span><span class="sxs-lookup"><span data-stu-id="46e36-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="46e36-105">Предварительные требования для подключения</span><span class="sxs-lookup"><span data-stu-id="46e36-105">Prerequisites for connection</span></span>

- <span data-ttu-id="46e36-106">Наличие узла SFTP и соответствующих учетных данных.</span><span class="sxs-lookup"><span data-stu-id="46e36-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="46e36-107">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="46e36-107">Known limitations</span></span>

- <span data-ttu-id="46e36-108">Время выполнения экспорта зависит от производительности вашей системы.</span><span class="sxs-lookup"><span data-stu-id="46e36-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="46e36-109">Мы рекомендуем двухъядерный ЦП и 1 Гб памяти в качестве минимальной конфигурации вашего сервера.</span><span class="sxs-lookup"><span data-stu-id="46e36-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="46e36-110">Экспорт сущностей с количеством профилей клиентов до 100 млн может занять 90 минут при использовании рекомендованной минимальной конфигурации из двухъядерного ЦП и 1 ГБ памяти.</span><span class="sxs-lookup"><span data-stu-id="46e36-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="46e36-111">Настройка подключения по протоколу SFTP</span><span class="sxs-lookup"><span data-stu-id="46e36-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="46e36-112">Перейти в раздел **Администрирование** > **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="46e36-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="46e36-113">Выберите **Добавить подключение** и выберите **SFTP** для настройки подключения.</span><span class="sxs-lookup"><span data-stu-id="46e36-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="46e36-114">Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="46e36-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="46e36-115">Имя и тип подключения описывают это подключение.</span><span class="sxs-lookup"><span data-stu-id="46e36-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="46e36-116">Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.</span><span class="sxs-lookup"><span data-stu-id="46e36-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="46e36-117">Укажите, кто может использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="46e36-117">Choose who can use this connection.</span></span> <span data-ttu-id="46e36-118">Если вы не предпримете никаких действий, по умолчанию это будут администраторы.</span><span class="sxs-lookup"><span data-stu-id="46e36-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="46e36-119">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="46e36-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="46e36-120">Обеспечьте **Имя пользователя**, **Пароль**, **Имя узла** и **Папка экспорта** для вашей учетной записи SFTP.</span><span class="sxs-lookup"><span data-stu-id="46e36-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="46e36-121">Выберите **Проверить**, чтобы протестировать соединение.</span><span class="sxs-lookup"><span data-stu-id="46e36-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="46e36-122">Выберите, хотите ли вы экспортировать свои данные как **Упаковано в формате GZip** или **Распаковано**, и **разделитель полей** для экспортируемых файлов.</span><span class="sxs-lookup"><span data-stu-id="46e36-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="46e36-123">Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.</span><span class="sxs-lookup"><span data-stu-id="46e36-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="46e36-124">Выберите **Сохранить**, чтобы завершить подключение.</span><span class="sxs-lookup"><span data-stu-id="46e36-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="46e36-125">Настройка экспорта</span><span class="sxs-lookup"><span data-stu-id="46e36-125">Configure an export</span></span>

<span data-ttu-id="46e36-126">Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа.</span><span class="sxs-lookup"><span data-stu-id="46e36-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="46e36-127">Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="46e36-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="46e36-128">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="46e36-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="46e36-129">Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.</span><span class="sxs-lookup"><span data-stu-id="46e36-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="46e36-130">В поле **Подключение для экспорта** выберите подключение из раздела SFTP.</span><span class="sxs-lookup"><span data-stu-id="46e36-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="46e36-131">Если вы не видите название этого раздела, вам не доступны подключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="46e36-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="46e36-132">Выберите сущности, например сегменты, которые нужно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="46e36-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="46e36-133">Каждая выбранная сущность будет разделена на пять выходных файлов при экспорте.</span><span class="sxs-lookup"><span data-stu-id="46e36-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="46e36-134">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="46e36-134">Select **Save**.</span></span>

<span data-ttu-id="46e36-135">Сохранение экспорта не запускает экспорт сразу.</span><span class="sxs-lookup"><span data-stu-id="46e36-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="46e36-136">Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="46e36-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="46e36-137">Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="46e36-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="46e36-138">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="46e36-138">Data privacy and compliance</span></span>

<span data-ttu-id="46e36-139">Когда вы включаете Dynamics 365 Customer Insights для передачи данных через SFTP, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="46e36-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="46e36-140">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией пунктом назначения экспорта любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть.</span><span class="sxs-lookup"><span data-stu-id="46e36-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="46e36-141">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="46e36-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="46e36-142">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="46e36-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
