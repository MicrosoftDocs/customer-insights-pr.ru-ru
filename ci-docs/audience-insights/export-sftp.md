---
title: Экспорт данных Customer Insights в узлы SFTP
description: Узнайте, как настроить соединение с узлом SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643519"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="55fd7-103">Соединитель для протокола SFTP (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="55fd7-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="55fd7-104">Используйте данные своих клиентов в сторонних приложениях, экспортируя их на узел протокола SFTP.</span><span class="sxs-lookup"><span data-stu-id="55fd7-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="55fd7-105">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="55fd7-105">Prerequisites</span></span>

- <span data-ttu-id="55fd7-106">Доступность узла SFTP и соответствующих учетных данных.</span><span class="sxs-lookup"><span data-stu-id="55fd7-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="55fd7-107">Подключение к протоколу SFTP</span><span class="sxs-lookup"><span data-stu-id="55fd7-107">Connect to SFTP</span></span>

1. <span data-ttu-id="55fd7-108">Откройте **Администратор** > **Пункты назначения экспорта**.</span><span class="sxs-lookup"><span data-stu-id="55fd7-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="55fd7-109">В разделе **SFTP** выберите **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="55fd7-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="55fd7-110">Дайте вашему месту назначения узнаваемое имя в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="55fd7-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="55fd7-111">Обеспечьте **Имя пользователя**, **Пароль** и **Имя узла** для вашей учетной записи SFTP.</span><span class="sxs-lookup"><span data-stu-id="55fd7-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="55fd7-112">Пример: если корневой папкой вашего SFTP-сервера является /root/folder, и вы хотите, чтобы данные экспортировались в /root/folder/ci_export_destination_folder, узел должен быть sftp://<server_address>/ci_export_destination_folder".</span><span class="sxs-lookup"><span data-stu-id="55fd7-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="55fd7-113">Выберите **Проверить**, чтобы протестировать соединение.</span><span class="sxs-lookup"><span data-stu-id="55fd7-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="55fd7-114">После успешной проверки выберите, хотите ли вы экспортировать свои данные как **Сжатые** или **Не сжатые** и выберите **разделитель полей** для экспортируемых файлов.</span><span class="sxs-lookup"><span data-stu-id="55fd7-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="55fd7-115">Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.</span><span class="sxs-lookup"><span data-stu-id="55fd7-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="55fd7-116">Выберите **Далее**, чтобы начать настройку экспорта.</span><span class="sxs-lookup"><span data-stu-id="55fd7-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="55fd7-117">Настройка подключения</span><span class="sxs-lookup"><span data-stu-id="55fd7-117">Configure the connection</span></span>

1. <span data-ttu-id="55fd7-118">Выберите **пользовательские атрибуты**, которые нужно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="55fd7-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="55fd7-119">Вы можете экспортировать один или несколько атрибутов.</span><span class="sxs-lookup"><span data-stu-id="55fd7-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="55fd7-120">Выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="55fd7-120">Select **Next**.</span></span>

1. <span data-ttu-id="55fd7-121">Выберите сегменты, которые нужно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="55fd7-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="55fd7-122">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="55fd7-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="55fd7-123">Экспорт данных</span><span class="sxs-lookup"><span data-stu-id="55fd7-123">Export the data</span></span>

<span data-ttu-id="55fd7-124">Вы можете [экспортировать данных по требованию](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="55fd7-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="55fd7-125">Экспорт также будет выполняться с каждым [запланированным обновлением](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="55fd7-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="55fd7-126">Соответствие и конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="55fd7-126">Data privacy and compliance</span></span>

<span data-ttu-id="55fd7-127">Когда вы включаете Dynamics 365 Customer Insights для передачи данных через SFTP, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные.</span><span class="sxs-lookup"><span data-stu-id="55fd7-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="55fd7-128">Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией пунктом назначения экспорта любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть.</span><span class="sxs-lookup"><span data-stu-id="55fd7-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="55fd7-129">Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="55fd7-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="55fd7-130">Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.</span><span class="sxs-lookup"><span data-stu-id="55fd7-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
