---
title: Бот для Microsoft Teams
description: Смотрите единые профили клиентов в Microsoft Teams с помощью бота.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 45ea23fbefe5f1d44c3961183b76d2cc5c45355e
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406752"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="7e204-103">Бот Teams для Dynamics 365 Customer Insights (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="7e204-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="7e204-104">Подключитесь с Microsoft Teams, чтобы бот мог искать унифицированные профили клиентов в каналах Teams.</span><span class="sxs-lookup"><span data-stu-id="7e204-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7e204-105">![Бот Teams показывает запись клиента](media/teams-bot.png "Бот Teams показывает запись клиента")</span><span class="sxs-lookup"><span data-stu-id="7e204-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7e204-106">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="7e204-106">Prerequisites</span></span>

<span data-ttu-id="7e204-107">Для настройки и конфигурации бота необходимо выполнить следующие предварительные условия:</span><span class="sxs-lookup"><span data-stu-id="7e204-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="7e204-108">Как минимум один [источник данных добавлен](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="7e204-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="7e204-109">[Процесса унификации](data-unification.md) завершен.</span><span class="sxs-lookup"><span data-stu-id="7e204-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="7e204-110">Поля добавлены в [индекс поиска и фильтрации](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="7e204-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="7e204-111">Customer Insights и Teams находятся в одной организации.</span><span class="sxs-lookup"><span data-stu-id="7e204-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="7e204-112">Настройка бота</span><span class="sxs-lookup"><span data-stu-id="7e204-112">Configure the bot</span></span>

1. <span data-ttu-id="7e204-113">В аналитике аудитории перейдите **Администрирование** > **Экспорт пунктов назначения**.</span><span class="sxs-lookup"><span data-stu-id="7e204-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="7e204-114">На плитке Microsoft Teams выберите **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="7e204-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="7e204-115">Вы будете перенаправлены в область **Приложения** в Teams.</span><span class="sxs-lookup"><span data-stu-id="7e204-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="7e204-116">Вы также можете открыть Teams и выбрать **Приложения** в левом нижнем углу или [получить его AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) непосредственно.</span><span class="sxs-lookup"><span data-stu-id="7e204-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="7e204-117">Найдите **Customer Insights** и выберите это приложение.</span><span class="sxs-lookup"><span data-stu-id="7e204-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="7e204-118">Выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="7e204-118">Select **Add**.</span></span>
1. <span data-ttu-id="7e204-119">После входа в Customer Insights в Teams вы увидите приветственное сообщение и сможете приступить к работе.</span><span class="sxs-lookup"><span data-stu-id="7e204-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="7e204-120">Что можно делать с помощью бота</span><span class="sxs-lookup"><span data-stu-id="7e204-120">Things you can do with the bot</span></span>

<span data-ttu-id="7e204-121">Бот предоставляет возможности поиска унифицированных профилей клиентов.</span><span class="sxs-lookup"><span data-stu-id="7e204-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="7e204-122">Введите **искать**, затем имя, адрес электронной почты или любое другое поле в унифицированном профиле клиента, которое добавляется в индекс поиска и фильтрации.</span><span class="sxs-lookup"><span data-stu-id="7e204-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="7e204-123">Вы получите карточку с максимум 15 полями из полученного профиля клиента.</span><span class="sxs-lookup"><span data-stu-id="7e204-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="7e204-124">Несколько совпадений возвращают список результатов, где вы можете выбрать профиль.</span><span class="sxs-lookup"><span data-stu-id="7e204-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="7e204-125">Вы можете добавить условие поиска в двойных кавычках, чтобы искать точное совпадение.</span><span class="sxs-lookup"><span data-stu-id="7e204-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="7e204-126">Если ваша организация поддерживает несколько сред Customer Insights в одной организации, вы можете ввести **switchinstance**, чтобы выбрать, к какой среде вы хотите подключить бота.</span><span class="sxs-lookup"><span data-stu-id="7e204-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="7e204-127">Введите **справка**, чтобы увидеть список доступных команд для бота.</span><span class="sxs-lookup"><span data-stu-id="7e204-127">Enter **help** to see a list of available commands for the bot.</span></span>  
