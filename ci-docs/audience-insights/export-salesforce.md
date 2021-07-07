---
title: Экспорт данных Customer Insights в Salesforce Marketing Cloud
description: Узнайте, как настроить подключение и экспорт в Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314663"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="96094-103">Экспорт сегментов и других данных в Salesforce Marketing Cloud (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="96094-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="96094-104">Используйте данные своих клиентов в Salesforce Marketing Cloud, экспортируя их через расположение SFTP.</span><span class="sxs-lookup"><span data-stu-id="96094-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="96094-105">Предварительные требования для подключения</span><span class="sxs-lookup"><span data-stu-id="96094-105">Prerequisites for connection</span></span>

- <span data-ttu-id="96094-106">Наличие узла SFTP и соответствующих учетных данных администратора.</span><span class="sxs-lookup"><span data-stu-id="96094-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="96094-107">Как настроить местоположения SFTP для Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="96094-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="96094-108">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="96094-108">Known limitations</span></span>

- <span data-ttu-id="96094-109">Время выполнения экспорта зависит от производительности вашей системы.</span><span class="sxs-lookup"><span data-stu-id="96094-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="96094-110">Мы рекомендуем двухъядерный ЦП и 1 Гб памяти в качестве минимальной конфигурации вашего сервера.</span><span class="sxs-lookup"><span data-stu-id="96094-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="96094-111">При использовании рекомендованной минимальной конфигурации экспорт сущностей с профилями клиентов до 100 миллионов может занять 90 минут.</span><span class="sxs-lookup"><span data-stu-id="96094-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="96094-112">Настройте подключение к Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="96094-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="96094-113">Перейти в раздел **Администрирование** > **Подключения**.</span><span class="sxs-lookup"><span data-stu-id="96094-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="96094-114">Выберите **Добавить подключение** и выберите **Salesforce Marketing Cloud** для настройки подключения.</span><span class="sxs-lookup"><span data-stu-id="96094-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="96094-115">Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="96094-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="96094-116">Имя и тип подключения описывают это подключение.</span><span class="sxs-lookup"><span data-stu-id="96094-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="96094-117">Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.</span><span class="sxs-lookup"><span data-stu-id="96094-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="96094-118">Укажите, кто может использовать это подключение.</span><span class="sxs-lookup"><span data-stu-id="96094-118">Choose who can use this connection.</span></span> <span data-ttu-id="96094-119">Если вы не предпримете никаких действий, по умолчанию это будут администраторы.</span><span class="sxs-lookup"><span data-stu-id="96094-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="96094-120">Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="96094-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="96094-121">Обеспечьте **Имя пользователя**, **Пароль**, **Имя узла** и **Папка экспорта** для вашей учетной записи SFTP.</span><span class="sxs-lookup"><span data-stu-id="96094-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="96094-122">Выберите **Проверить**, чтобы протестировать соединение.</span><span class="sxs-lookup"><span data-stu-id="96094-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="96094-123">Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.</span><span class="sxs-lookup"><span data-stu-id="96094-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="96094-124">Выберите **Сохранить**, чтобы завершить подключение.</span><span class="sxs-lookup"><span data-stu-id="96094-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="96094-125">Настройка экспорта</span><span class="sxs-lookup"><span data-stu-id="96094-125">Configure an export</span></span>

<span data-ttu-id="96094-126">Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа.</span><span class="sxs-lookup"><span data-stu-id="96094-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="96094-127">Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="96094-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="96094-128">Перейдите в раздел **Данные** > **Экспорты**.</span><span class="sxs-lookup"><span data-stu-id="96094-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="96094-129">Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.</span><span class="sxs-lookup"><span data-stu-id="96094-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="96094-130">В поле **Подключение для экспорта** выберите подключение из раздела SFTP.</span><span class="sxs-lookup"><span data-stu-id="96094-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="96094-131">Если вы не видите название этого раздела, вам не доступны подключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="96094-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="96094-132">Выберите, хотите ли вы экспортировать свои данные как **Упаковано в формате GZip** или **Распаковано**, и **разделитель полей** для экспортируемых файлов.</span><span class="sxs-lookup"><span data-stu-id="96094-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="96094-133">Выберите сущности, например сегменты, которые нужно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="96094-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="96094-134">Каждая выбранная сущность будет разделена на пять выходных файлов при экспорте.</span><span class="sxs-lookup"><span data-stu-id="96094-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="96094-135">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="96094-135">Select **Save**.</span></span>

<span data-ttu-id="96094-136">Сохранение экспорта не запускает экспорт сразу.</span><span class="sxs-lookup"><span data-stu-id="96094-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="96094-137">Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="96094-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="96094-138">Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="96094-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="96094-139">Импорт данных Customer Insights из местоположения SFTP в Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="96094-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="96094-140">Создайте [расширения данных в Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) для импорта файла данных Customer Insights из расположения SFTP.</span><span class="sxs-lookup"><span data-stu-id="96094-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="96094-141">[Импортируйте данные из местоположения SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) в расширение данных Salesforce Marketing Cloud.</span><span class="sxs-lookup"><span data-stu-id="96094-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="96094-142">Настройте автоматизацию для импорта данных в расширения данных.</span><span class="sxs-lookup"><span data-stu-id="96094-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="96094-143">Узнать больше об [автоматизации переноса файлов и автоматизации по расписанию](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="96094-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="96094-144">Определите [автоматизацию переноса файлов](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) или [автоматизацию по расписанию](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="96094-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="96094-145">Вот пример [автоматизации с SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="96094-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="96094-146">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="96094-146">Data privacy and compliance</span></span>

<span data-ttu-id="96094-147">Когда вы включаете Dynamics 365 Customer Insights для передачи данных через SFTP, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="96094-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="96094-148">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией пунктом назначения экспорта любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть.</span><span class="sxs-lookup"><span data-stu-id="96094-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="96094-149">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="96094-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="96094-150">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="96094-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
