---
title: Обогащение за счет настраиваемого импорта SFTP
description: Общие сведения об обогащении настраиваемого импорта SFTP.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304666"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="dffdc-103">Обогащение настраиваемого импорта пользовательскими данными (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="dffdc-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="dffdc-104">Настраиваемый импорт протокола SFTP позволяет импортировать данные, которые не должны проходить процесс объединения данных.</span><span class="sxs-lookup"><span data-stu-id="dffdc-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="dffdc-105">Это гибкий, безопасный и простой способ ввода ваших данных.</span><span class="sxs-lookup"><span data-stu-id="dffdc-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="dffdc-106">Настраиваемый импорт SFTP можно использовать в сочетании с [экспортом SFTP](export-sftp.md), что позволяет экспортировать данные профилей клиентов, необходимые для обогащения.</span><span class="sxs-lookup"><span data-stu-id="dffdc-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="dffdc-107">Затем данные можно обрабатывать и обогащать, а настраиваемый импорт SFTP можно использовать для возврата обогащенных данных в аналитику аудитории Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="dffdc-107">The data can then be processed and enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dffdc-108">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="dffdc-108">Prerequisites</span></span>

<span data-ttu-id="dffdc-109">Для настройки настраиваемого импорта SFTP должны быть соблюдены следующие предварительные условия:</span><span class="sxs-lookup"><span data-stu-id="dffdc-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="dffdc-110">У вас есть имя файла и расположение (путь) файла, который нужно импортировать на узле SFTP.</span><span class="sxs-lookup"><span data-stu-id="dffdc-110">You have the file name and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="dffdc-111">Eсть файл *model.json*, который указывает [схему Common Data Model](/common-data-model/) для импортируемых данных.</span><span class="sxs-lookup"><span data-stu-id="dffdc-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="dffdc-112">Этот файл должен находиться в том же каталоге, что и импортируемый файл.</span><span class="sxs-lookup"><span data-stu-id="dffdc-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="dffdc-113">Подключение SFTP уже настроено администратором *или* у вас есть разрешения [администратора](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="dffdc-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="dffdc-114">Вам потребуются учетные данные пользователя, URL-адрес и номер порта для расположения SFTP, из которого вы хотите импортировать данные.</span><span class="sxs-lookup"><span data-stu-id="dffdc-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="dffdc-115">Настройка импорта</span><span class="sxs-lookup"><span data-stu-id="dffdc-115">Configure the import</span></span>

1. <span data-ttu-id="dffdc-116">Перейдите в раздел **Данные** > **Обогащение** и выберите вкладку **Обнаружить**.</span><span class="sxs-lookup"><span data-stu-id="dffdc-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="dffdc-117">На плитке **Пользовательский импорт по протоколу SFTP** выберите **Обогатить данные**, затем выберите **Начать**.</span><span class="sxs-lookup"><span data-stu-id="dffdc-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Плитка настраиваемого импорта SFTP.":::

1. <span data-ttu-id="dffdc-119">Выберите [подключение](connections.md) из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="dffdc-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="dffdc-120">Свяжитесь с администратором, если подключение недоступно.</span><span class="sxs-lookup"><span data-stu-id="dffdc-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="dffdc-121">Если вы администратор, вы можете создать соединение, выбрав **Добавить подключение** и выбрав **Настраиваемый импорт SFTP** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="dffdc-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the dropdown list.</span></span>

1. <span data-ttu-id="dffdc-122">Выберите **Подключиться к пользовательскому импорту** для подтверждения выбранного подключения.</span><span class="sxs-lookup"><span data-stu-id="dffdc-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="dffdc-123">Выберите **Далее** и введите **Путь** и **Имя файла** файла данных, который вы хотите импортировать.</span><span class="sxs-lookup"><span data-stu-id="dffdc-123">Select **Next** and enter the **Path** and **Filename** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Снимок экрана при вводе местоположения данных.":::

1. <span data-ttu-id="dffdc-125">Выберите **Далее** и укажите имя для обогащения и имя для выходной сущности.</span><span class="sxs-lookup"><span data-stu-id="dffdc-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="dffdc-126">Выберите **Сохранить обогащение** после просмотра вашего выбора.</span><span class="sxs-lookup"><span data-stu-id="dffdc-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="dffdc-127">Настройка подключения для пользовательского импорта по протоколу SFTP</span><span class="sxs-lookup"><span data-stu-id="dffdc-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="dffdc-128">Чтобы настраивать подключения, вы должны быть администратором.</span><span class="sxs-lookup"><span data-stu-id="dffdc-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="dffdc-129">Выберите **Добавить подключение** при настройке обогащения *или* перейдите в раздел **Администрирование** > **Подключения** и выберите **Настроить** на плитке пользовательского импорта.</span><span class="sxs-lookup"><span data-stu-id="dffdc-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="dffdc-130">Введите имя для подключения в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="dffdc-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="dffdc-131">Введите действительное имя пользователя, пароль и URL-адрес узла для SFTP-сервера, на котором находятся импортируемые данные.</span><span class="sxs-lookup"><span data-stu-id="dffdc-131">Enter a valid username, password, and host URL for the SFTP server that the data to be imported resides on.</span></span>

1. <span data-ttu-id="dffdc-132">Изучите и предоставьте свое согласие на **Конфиденциальность данных и соответствие**, установив флажок **Принимаю**.</span><span class="sxs-lookup"><span data-stu-id="dffdc-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="dffdc-133">Выберите **Проверить** для проверки конфигурации.</span><span class="sxs-lookup"><span data-stu-id="dffdc-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="dffdc-134">После завершения проверки соединение можно сохранить, выбрав **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="dffdc-134">Once the verification has completed, the connection can be saved by selecting **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dffdc-135">![Страница настройки подключения Experian](media/enrichment-SFTP-connection.png "Страница настройки подключения Experian")</span><span class="sxs-lookup"><span data-stu-id="dffdc-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="dffdc-136">Определение сопоставлений полей</span><span class="sxs-lookup"><span data-stu-id="dffdc-136">Defining field mappings</span></span> 

<span data-ttu-id="dffdc-137">Каталог, содержащий файл для импорта на сервере SFTP, также должен содержать файл *model.json*.</span><span class="sxs-lookup"><span data-stu-id="dffdc-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="dffdc-138">Этот файл определяет схему, используемую для импорта данных.</span><span class="sxs-lookup"><span data-stu-id="dffdc-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="dffdc-139">Схема должна использовать [Common Data Model](/common-data-model/), чтобы указать сопоставление полей.</span><span class="sxs-lookup"><span data-stu-id="dffdc-139">The schema has to use [Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="dffdc-140">Простой пример файла model.json выглядит так:</span><span class="sxs-lookup"><span data-stu-id="dffdc-140">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="dffdc-141">Результаты обогащения</span><span class="sxs-lookup"><span data-stu-id="dffdc-141">Enrichment results</span></span>

<span data-ttu-id="dffdc-142">Чтобы начать процесс обогащения, выберите **Выполнить** на панели команд.</span><span class="sxs-lookup"><span data-stu-id="dffdc-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="dffdc-143">Вы также можете позволить системе запускать обогащение автоматически как часть [запланированного обновления](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dffdc-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="dffdc-144">Время обработки будет зависеть от объема импортируемых данных и подключения к серверу SFTP.</span><span class="sxs-lookup"><span data-stu-id="dffdc-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="dffdc-145">После завершения процесса обогащения вы можете просмотреть свои недавно импортированные настраиваемые данные обогащения в разделе **Мои обогащения**.</span><span class="sxs-lookup"><span data-stu-id="dffdc-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="dffdc-146">Кроме того, вы найдете время последнего обновления и количество обогащенных профилей.</span><span class="sxs-lookup"><span data-stu-id="dffdc-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="dffdc-147">Вы можете получить доступ к детализированному представлению каждого обогащенного профиля, выбрав **Просмотр обогащенных данных**.</span><span class="sxs-lookup"><span data-stu-id="dffdc-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dffdc-148">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="dffdc-148">Next steps</span></span>

<span data-ttu-id="dffdc-149">Основывайтесь на ваших обогащенных данных клиентов.</span><span class="sxs-lookup"><span data-stu-id="dffdc-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="dffdc-150">Создайте [сегменты](segments.md) и [меры](measures.md), и [экспортируйте данные](export-destinations.md), чтобы предоставить вашим клиентам индивидуальный подход.</span><span class="sxs-lookup"><span data-stu-id="dffdc-150">Create [segments](segments.md) and [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
