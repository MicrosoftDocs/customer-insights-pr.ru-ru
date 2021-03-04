---
title: Бот для Microsoft Teams
description: Смотрите единые профили клиентов в Microsoft Teams с помощью бота.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 03299610fd41a7e142e3c9723fad56ce7f90e083
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267968"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="17e68-103">Бот Teams для Dynamics 365 Customer Insights (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="17e68-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="17e68-104">Подключитесь с Microsoft Teams, чтобы бот мог искать унифицированные профили клиентов в каналах Teams.</span><span class="sxs-lookup"><span data-stu-id="17e68-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="17e68-105">![Бот Teams показывает запись клиента](media/teams-bot.png "Бот Teams показывает запись клиента")</span><span class="sxs-lookup"><span data-stu-id="17e68-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="17e68-106">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="17e68-106">Prerequisites</span></span>

<span data-ttu-id="17e68-107">Для настройки и конфигурации бота необходимо выполнить следующие предварительные условия:</span><span class="sxs-lookup"><span data-stu-id="17e68-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="17e68-108">Как минимум один [источник данных добавлен](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="17e68-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="17e68-109">[Процесса унификации](data-unification.md) завершен.</span><span class="sxs-lookup"><span data-stu-id="17e68-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="17e68-110">Поля добавлены в [индекс поиска и фильтрации](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="17e68-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="17e68-111">Customer Insights и Teams находятся в одной организации.</span><span class="sxs-lookup"><span data-stu-id="17e68-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="17e68-112">Настройка бота</span><span class="sxs-lookup"><span data-stu-id="17e68-112">Configure the bot</span></span>

1. <span data-ttu-id="17e68-113">В аналитике аудитории перейдите **Администрирование** > **Экспорт пунктов назначения**.</span><span class="sxs-lookup"><span data-stu-id="17e68-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="17e68-114">На плитке Microsoft Teams выберите **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="17e68-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="17e68-115">Вы будете перенаправлены в область **Приложения** в Teams.</span><span class="sxs-lookup"><span data-stu-id="17e68-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="17e68-116">Вы также можете открыть Teams и выбрать **Приложения** в левом нижнем углу или [получить его AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) непосредственно.</span><span class="sxs-lookup"><span data-stu-id="17e68-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="17e68-117">Найдите **Customer Insights** и выберите это приложение.</span><span class="sxs-lookup"><span data-stu-id="17e68-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="17e68-118">Выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="17e68-118">Select **Add**.</span></span>
1. <span data-ttu-id="17e68-119">После входа в Customer Insights в Teams вы увидите приветственное сообщение и сможете приступить к работе.</span><span class="sxs-lookup"><span data-stu-id="17e68-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="17e68-120">Что можно делать с помощью бота</span><span class="sxs-lookup"><span data-stu-id="17e68-120">Things you can do with the bot</span></span>

<span data-ttu-id="17e68-121">Бот предоставляет возможности поиска унифицированных профилей клиентов.</span><span class="sxs-lookup"><span data-stu-id="17e68-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="17e68-122">Введите **искать**, затем имя, адрес электронной почты или любое другое поле в унифицированном профиле клиента, которое добавляется в индекс поиска и фильтрации.</span><span class="sxs-lookup"><span data-stu-id="17e68-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="17e68-123">Вы получите карточку с максимум 15 полями из полученного профиля клиента.</span><span class="sxs-lookup"><span data-stu-id="17e68-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="17e68-124">Несколько совпадений возвращают список результатов, где вы можете выбрать профиль.</span><span class="sxs-lookup"><span data-stu-id="17e68-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="17e68-125">Вы можете добавить условие поиска в двойных кавычках, чтобы искать точное совпадение.</span><span class="sxs-lookup"><span data-stu-id="17e68-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="17e68-126">Если ваша организация поддерживает несколько сред Customer Insights в одной организации, вы можете ввести **switchinstance**, чтобы выбрать, к какой среде вы хотите подключить бота.</span><span class="sxs-lookup"><span data-stu-id="17e68-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="17e68-127">Введите **справка**, чтобы увидеть список доступных команд для бота.</span><span class="sxs-lookup"><span data-stu-id="17e68-127">Enter **help** to see a list of available commands for the bot.</span></span>  


[!INCLUDE[footer-include](../includes/footer-banner.md)]