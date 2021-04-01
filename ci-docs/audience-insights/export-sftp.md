---
title: Экспорт данных Customer Insights в узлы SFTP
description: Узнайте, как настроить соединение с узлом SFTP.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598401"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="032a7-103">Соединитель для протокола SFTP (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="032a7-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="032a7-104">Используйте данные своих клиентов в сторонних приложениях, экспортируя их на узел протокола SFTP.</span><span class="sxs-lookup"><span data-stu-id="032a7-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="032a7-105">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="032a7-105">Prerequisites</span></span>

- <span data-ttu-id="032a7-106">Наличие узла SFTP и соответствующих учетных данных.</span><span class="sxs-lookup"><span data-stu-id="032a7-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="032a7-107">Подключение к SFTP</span><span class="sxs-lookup"><span data-stu-id="032a7-107">Connect to SFTP</span></span>

1. <span data-ttu-id="032a7-108">Откройте **Администратор** > **Пункты назначения экспорта**.</span><span class="sxs-lookup"><span data-stu-id="032a7-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="032a7-109">В разделе **SFTP** выберите **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="032a7-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="032a7-110">Дайте вашему месту назначения узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="032a7-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="032a7-111">Обеспечьте **Имя пользователя**, **Пароль**, **Имя узла** и **Папка экспорта** для вашей учетной записи SFTP.</span><span class="sxs-lookup"><span data-stu-id="032a7-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="032a7-112">Выберите **Проверить**, чтобы протестировать соединение.</span><span class="sxs-lookup"><span data-stu-id="032a7-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="032a7-113">После успешной проверки выберите, хотите ли вы экспортировать свои данные **Упаковано в формате GZip** или **Распаковано**, и выберите **разделитель полей** для экспортируемых файлов.</span><span class="sxs-lookup"><span data-stu-id="032a7-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="032a7-114">Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.</span><span class="sxs-lookup"><span data-stu-id="032a7-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="032a7-115">Выберите **Далее**, чтобы начать настройку экспорта.</span><span class="sxs-lookup"><span data-stu-id="032a7-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="032a7-116">Настроить экспорт</span><span class="sxs-lookup"><span data-stu-id="032a7-116">Configure the export</span></span>

1. <span data-ttu-id="032a7-117">Выберите сущности, например сегменты, которые нужно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="032a7-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="032a7-118">При экспорте для каждой выбранной сущности будет до пяти выходных файлов.</span><span class="sxs-lookup"><span data-stu-id="032a7-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="032a7-119">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="032a7-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="032a7-120">Экспорт данных</span><span class="sxs-lookup"><span data-stu-id="032a7-120">Export the data</span></span>

<span data-ttu-id="032a7-121">Вы можете [экспортировать данных по требованию](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="032a7-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="032a7-122">Экспорт также будет выполняться с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="032a7-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="032a7-123">Известные ограничения</span><span class="sxs-lookup"><span data-stu-id="032a7-123">Known limitations</span></span>

- <span data-ttu-id="032a7-124">Время выполнения экспорта зависит от производительности вашей системы.</span><span class="sxs-lookup"><span data-stu-id="032a7-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="032a7-125">Мы рекомендуем двухъядерный ЦП и 1 Гб памяти в качестве минимальной конфигурации вашего сервера.</span><span class="sxs-lookup"><span data-stu-id="032a7-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="032a7-126">Экспорт сущностей с количеством профилей клиентов до 100 млн может занять 90 минут при использовании рекомендованной минимальной конфигурации из двухъядерного ЦП и 1 ГБ памяти.</span><span class="sxs-lookup"><span data-stu-id="032a7-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="032a7-127">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="032a7-127">Data privacy and compliance</span></span>

<span data-ttu-id="032a7-128">Когда вы включаете Dynamics 365 Customer Insights для передачи данных через SFTP, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="032a7-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="032a7-129">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией пунктом назначения экспорта любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть.</span><span class="sxs-lookup"><span data-stu-id="032a7-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="032a7-130">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="032a7-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="032a7-131">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="032a7-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]