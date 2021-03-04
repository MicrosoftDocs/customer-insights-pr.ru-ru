---
title: Обогащение за счет настраиваемого импорта SFTP
description: Общие сведения об обогащении настраиваемого импорта SFTP.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f25dcc08d96d36507e47af0d7b184003ae095819
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269622"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="f5776-103">Обогащение настраиваемого импорта пользовательскими данными (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="f5776-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="f5776-104">Настраиваемый импорт протокола SFTP позволяет импортировать данные, которые не должны проходить процесс объединения данных.</span><span class="sxs-lookup"><span data-stu-id="f5776-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="f5776-105">Это гибкий, безопасный и простой способ ввода ваших данных.</span><span class="sxs-lookup"><span data-stu-id="f5776-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="f5776-106">Настраиваемый импорт SFTP можно использовать в сочетании с [экспортом SFTP](export-sftp.md), что позволяет экспортировать данные профилей клиентов, необходимые для обогащения.</span><span class="sxs-lookup"><span data-stu-id="f5776-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="f5776-107">Затем данные могут быть обработаны, обогащены, и настраиваемый импорт SFTP может использоваться для возврата обогащенных данных в аналитику аудитории Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f5776-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f5776-108">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="f5776-108">Prerequisites</span></span>

<span data-ttu-id="f5776-109">Для настройки настраиваемого импорта SFTP должны быть соблюдены следующие предварительные условия:</span><span class="sxs-lookup"><span data-stu-id="f5776-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="f5776-110">У вас есть учетные данные пользователя (имя пользователя и пароль) для расположения SFTP, из которого будут импортированы данные.</span><span class="sxs-lookup"><span data-stu-id="f5776-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="f5776-111">У вас есть URL-адрес и адрес порта (обычно 22) для узла STFP.</span><span class="sxs-lookup"><span data-stu-id="f5776-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="f5776-112">У вас есть имя файла и расположение файла, который нужно импортировать на узел SFTP.</span><span class="sxs-lookup"><span data-stu-id="f5776-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="f5776-113">Есть файл *model.json*, в котором указана схема импортируемых данных.</span><span class="sxs-lookup"><span data-stu-id="f5776-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="f5776-114">Этот файл должен находиться в том же каталоге, что и импортируемый файл.</span><span class="sxs-lookup"><span data-stu-id="f5776-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="f5776-115">У вас есть разрешение [Администратор](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="f5776-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="f5776-116">Настройка</span><span class="sxs-lookup"><span data-stu-id="f5776-116">Configuration</span></span>

1. <span data-ttu-id="f5776-117">Перейдите в раздел **Данные** > **Обогащение** и выберите вкладку **Обнаружить**.</span><span class="sxs-lookup"><span data-stu-id="f5776-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="f5776-118">На **плитке настраиваемого импорта SFTP** выберите **Обогатить мои данные**.</span><span class="sxs-lookup"><span data-stu-id="f5776-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f5776-119">![Плитка настраиваемого импорта SFTP](media/SFTP_Custom_Import_tile.png "Плитка настраиваемого импорта SFTP")</span><span class="sxs-lookup"><span data-stu-id="f5776-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="f5776-120">Выберите **Начать** и укажите учетные данные и адрес SFTP-сервера.</span><span class="sxs-lookup"><span data-stu-id="f5776-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="f5776-121">Например, sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="f5776-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="f5776-122">Введите имя файла, который содержит данные, и путь к файлу на сервере SFTP, если он не находится в корневой папке.</span><span class="sxs-lookup"><span data-stu-id="f5776-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="f5776-123">Подтвердите все вводы, выбрав **Подключиться к настраиваемому импорту**.</span><span class="sxs-lookup"><span data-stu-id="f5776-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f5776-124">![Всплывающее меню конфигурации настраиваемого импорта SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Всплывающее меню конфигурации настраиваемого импорта SFTP")</span><span class="sxs-lookup"><span data-stu-id="f5776-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="f5776-125">Определение сопоставлений полей</span><span class="sxs-lookup"><span data-stu-id="f5776-125">Defining field mappings</span></span> 

<span data-ttu-id="f5776-126">Каталог, содержащий файл для импорта на сервере SFTP, также должен содержать файл *model.json*.</span><span class="sxs-lookup"><span data-stu-id="f5776-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="f5776-127">Этот файл определяет схему, используемую для импорта данных.</span><span class="sxs-lookup"><span data-stu-id="f5776-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="f5776-128">Схема должна использовать [Common Data Model](https://docs.microsoft.com/common-data-model/) для указания сопоставления полей.</span><span class="sxs-lookup"><span data-stu-id="f5776-128">The schema has to use [the Common Data Model](https://docs.microsoft.com/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="f5776-129">Простой пример файла model.json выглядит так:</span><span class="sxs-lookup"><span data-stu-id="f5776-129">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="f5776-130">Результаты обогащения</span><span class="sxs-lookup"><span data-stu-id="f5776-130">Enrichment results</span></span>

<span data-ttu-id="f5776-131">Чтобы начать процесс обогащения, выберите **Выполнить** на панели команд.</span><span class="sxs-lookup"><span data-stu-id="f5776-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="f5776-132">Вы также можете позволить системе запускать обогащение автоматически как часть [запланированного обновления](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f5776-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f5776-133">Время обработки будет зависеть от объема импортируемых данных и подключения к серверу SFTP.</span><span class="sxs-lookup"><span data-stu-id="f5776-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="f5776-134">После завершения процесса обогащения вы можете просмотреть свои недавно импортированные настраиваемые данные обогащения в разделе **Мои обогащения**.</span><span class="sxs-lookup"><span data-stu-id="f5776-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="f5776-135">Кроме того, вы найдете время последнего обновления и количество обогащенных профилей.</span><span class="sxs-lookup"><span data-stu-id="f5776-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="f5776-136">Вы можете получить доступ к детализированному представлению каждого обогащенного профиля, выбрав **Просмотр обогащенных данных**.</span><span class="sxs-lookup"><span data-stu-id="f5776-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f5776-137">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="f5776-137">Next steps</span></span>

<span data-ttu-id="f5776-138">Основывайтесь на ваших обогащенных данных клиентов.</span><span class="sxs-lookup"><span data-stu-id="f5776-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="f5776-139">Создайте [сегменты](segments.md), [меры](measures.md) и [экспортировать данные](export-destinations.md), чтобы предоставить вашим клиентам индивидуальный подход.</span><span class="sxs-lookup"><span data-stu-id="f5776-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]