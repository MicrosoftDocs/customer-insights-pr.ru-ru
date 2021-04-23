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
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Бот Teams для Dynamics 365 Customer Insights (предварительная версия)

Подключитесь с Microsoft Teams, чтобы бот мог искать унифицированные профили клиентов в каналах Teams.

> [!div class="mx-imgBorder"]
> ![Бот Teams показывает запись клиента](media/teams-bot.png "Бот Teams показывает запись клиента")

## <a name="prerequisites"></a>Предварительные условия

Для настройки и конфигурации бота необходимо выполнить следующие предварительные условия:

- Как минимум один [источник данных добавлен](data-sources.md).
- [Процесса унификации](data-unification.md) завершен.
- Поля добавлены в [индекс поиска и фильтрации](search-filter-index.md).
- Customer Insights и Teams находятся в одной организации.

## <a name="configure-the-bot"></a>Настройка бота

1. В аналитике аудитории перейдите **Администрирование** > **Экспорт пунктов назначения**.
1. На плитке Microsoft Teams выберите **Настроить**.
1. Вы будете перенаправлены в область **Приложения** в Teams. Вы также можете открыть Teams и выбрать **Приложения** в левом нижнем углу или [получить его AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) непосредственно.
1. Найдите **Customer Insights** и выберите это приложение.
1. Выберите **Добавить**.
1. После входа в Customer Insights в Teams вы увидите приветственное сообщение и сможете приступить к работе.

## <a name="things-you-can-do-with-the-bot"></a>Что можно делать с помощью бота

Бот предоставляет возможности поиска унифицированных профилей клиентов.

- Введите **искать**, затем имя, адрес электронной почты или любое другое поле в унифицированном профиле клиента, которое добавляется в индекс поиска и фильтрации.

  Вы получите карточку с максимум 15 полями из полученного профиля клиента. Несколько совпадений возвращают список результатов, где вы можете выбрать профиль. Вы можете добавить условие поиска в двойных кавычках, чтобы искать точное совпадение.

- Если ваша организация поддерживает несколько сред Customer Insights в одной организации, вы можете ввести **switchinstance**, чтобы выбрать, к какой среде вы хотите подключить бота.

- Введите **справка**, чтобы увидеть список доступных команд для бота.  


[!INCLUDE[footer-include](../includes/footer-banner.md)]