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
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896297"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="51951-103">Обогащение настраиваемого импорта пользовательскими данными (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="51951-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="51951-104">Пользовательский импорт по протоколу SFTP позволяет импортировать данные, которые не должны проходить процесс унификации данных.</span><span class="sxs-lookup"><span data-stu-id="51951-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that does not have to go through the process of data unification.</span></span> <span data-ttu-id="51951-105">Это гибкий, безопасный и простой способ ввода ваших данных.</span><span class="sxs-lookup"><span data-stu-id="51951-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="51951-106">Настраиваемый импорт SFTP можно использовать в сочетании с [экспортом SFTP](export-sftp.md), что позволяет экспортировать данные профилей клиентов, необходимые для обогащения.</span><span class="sxs-lookup"><span data-stu-id="51951-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="51951-107">Затем данные могут быть обработаны, обогащены, и настраиваемый импорт SFTP может использоваться для возврата обогащенных данных в аналитику аудитории Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="51951-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="51951-108">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="51951-108">Prerequisites</span></span>

<span data-ttu-id="51951-109">Для настройки настраиваемого импорта SFTP должны быть соблюдены следующие предварительные условия:</span><span class="sxs-lookup"><span data-stu-id="51951-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="51951-110">У вас есть имя файла и расположение (путь) файла, который нужно импортировать, на хосте SFTP.</span><span class="sxs-lookup"><span data-stu-id="51951-110">You have the filename and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="51951-111">Eсть файл *model.json*, который указывает [схему Common Data Model](/common-data-model/) для импортируемых данных.</span><span class="sxs-lookup"><span data-stu-id="51951-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="51951-112">Этот файл должен находиться в том же каталоге, что и импортируемый файл.</span><span class="sxs-lookup"><span data-stu-id="51951-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="51951-113">Подключение SFTP уже настроено администратором *или* у вас есть разрешения [администратора](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="51951-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="51951-114">Вам потребуются учетные данные пользователя, URL-адрес и номер порта для расположения SFTP, из которого вы хотите импортировать данные.</span><span class="sxs-lookup"><span data-stu-id="51951-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="51951-115">Настройка импорта</span><span class="sxs-lookup"><span data-stu-id="51951-115">Configure the import</span></span>

1. <span data-ttu-id="51951-116">Перейдите в раздел **Данные** > **Обогащение** и выберите вкладку **Обнаружить**.</span><span class="sxs-lookup"><span data-stu-id="51951-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="51951-117">На плитке **Пользовательский импорт по протоколу SFTP** выберите **Обогатить данные**, затем выберите **Начать**.</span><span class="sxs-lookup"><span data-stu-id="51951-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Плитка настраиваемого импорта SFTP.":::

1. <span data-ttu-id="51951-119">Выберите [подключение](connections.md) из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="51951-119">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="51951-120">Свяжитесь с администратором, если подключение недоступно.</span><span class="sxs-lookup"><span data-stu-id="51951-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="51951-121">Если вы администратор, вы можете создать подключение, выбрав **Добавить подключение** и выбрав **Пользовательский импорт по протоколу SFTP** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="51951-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the drop-down.</span></span>

1. <span data-ttu-id="51951-122">Выберите **Подключиться к пользовательскому импорту** для подтверждения выбранного подключения.</span><span class="sxs-lookup"><span data-stu-id="51951-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="51951-123">Выберите **Далее** и введите **Имя файла** и **Путь** файла данных, который вы хотите импортировать.</span><span class="sxs-lookup"><span data-stu-id="51951-123">Select **Next** and enter the **Filename** and **Path** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Снимок экрана при вводе местоположения данных.":::

1. <span data-ttu-id="51951-125">Выберите **Далее** и укажите имя для обогащения и имя для выходной сущности.</span><span class="sxs-lookup"><span data-stu-id="51951-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="51951-126">Выберите **Сохранить обогащение** после просмотра вашего выбора.</span><span class="sxs-lookup"><span data-stu-id="51951-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="51951-127">Настройка подключения для пользовательского импорта по протоколу SFTP</span><span class="sxs-lookup"><span data-stu-id="51951-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="51951-128">Чтобы настраивать подключения, вы должны быть администратором.</span><span class="sxs-lookup"><span data-stu-id="51951-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="51951-129">Выберите **Добавить подключение** при настройке обогащения *или* перейдите в раздел **Администрирование** > **Подключения** и выберите **Настроить** на плитке пользовательского импорта.</span><span class="sxs-lookup"><span data-stu-id="51951-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="51951-130">Введите имя для подключения в поле **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="51951-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="51951-131">Введите действительное имя пользователя, пароль и URL-адрес хоста для сервера STFP, на котором находятся импортируемые данные.</span><span class="sxs-lookup"><span data-stu-id="51951-131">Enter valid user name, password, and host URL for the STFP server the data to be imported resides on.</span></span>

1. <span data-ttu-id="51951-132">Изучите и предоставьте свое согласие на **Конфиденциальность данных и соответствие**, установив флажок **Принимаю**.</span><span class="sxs-lookup"><span data-stu-id="51951-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="51951-133">Выберите **Проверить** для проверки конфигурации.</span><span class="sxs-lookup"><span data-stu-id="51951-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="51951-134">После завершения проверки подключение можно сохранить, нажав **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="51951-134">Once the verification has completed, the connection can be saved by clicking **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="51951-135">![Страница настройки подключения Experian](media/enrichment-SFTP-connection.png "Страница настройки подключения Experian")</span><span class="sxs-lookup"><span data-stu-id="51951-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="51951-136">Определение сопоставлений полей</span><span class="sxs-lookup"><span data-stu-id="51951-136">Defining field mappings</span></span> 

<span data-ttu-id="51951-137">Каталог, содержащий файл для импорта на сервере SFTP, также должен содержать файл *model.json*.</span><span class="sxs-lookup"><span data-stu-id="51951-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="51951-138">Этот файл определяет схему, используемую для импорта данных.</span><span class="sxs-lookup"><span data-stu-id="51951-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="51951-139">Схема должна использовать [Common Data Model](/common-data-model/) для указания сопоставления полей.</span><span class="sxs-lookup"><span data-stu-id="51951-139">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="51951-140">Простой пример файла model.json выглядит так:</span><span class="sxs-lookup"><span data-stu-id="51951-140">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="51951-141">Результаты обогащения</span><span class="sxs-lookup"><span data-stu-id="51951-141">Enrichment results</span></span>

<span data-ttu-id="51951-142">Чтобы начать процесс обогащения, выберите **Выполнить** на панели команд.</span><span class="sxs-lookup"><span data-stu-id="51951-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="51951-143">Вы также можете позволить системе запускать обогащение автоматически как часть [запланированного обновления](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="51951-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="51951-144">Время обработки будет зависеть от объема импортируемых данных и подключения к серверу SFTP.</span><span class="sxs-lookup"><span data-stu-id="51951-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="51951-145">После завершения процесса обогащения вы можете просмотреть свои недавно импортированные настраиваемые данные обогащения в разделе **Мои обогащения**.</span><span class="sxs-lookup"><span data-stu-id="51951-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="51951-146">Кроме того, вы найдете время последнего обновления и количество обогащенных профилей.</span><span class="sxs-lookup"><span data-stu-id="51951-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="51951-147">Вы можете получить доступ к детализированному представлению каждого обогащенного профиля, выбрав **Просмотр обогащенных данных**.</span><span class="sxs-lookup"><span data-stu-id="51951-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="51951-148">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="51951-148">Next steps</span></span>

<span data-ttu-id="51951-149">Основывайтесь на ваших обогащенных данных клиентов.</span><span class="sxs-lookup"><span data-stu-id="51951-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="51951-150">Создайте [сегменты](segments.md), [меры](measures.md) и [экспортировать данные](export-destinations.md), чтобы предоставить вашим клиентам индивидуальный подход.</span><span class="sxs-lookup"><span data-stu-id="51951-150">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
