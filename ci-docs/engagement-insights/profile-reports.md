---
title: Включить готовые отчеты о профиле
description: Как создавать готовые отчеты о профиле, сгруппированные по полу, возрасту и округу или региону происхождения.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bf2ec67c9fb99918b87841d3c0b131934e31b58b
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486136"
---
# <a name="out-of-box-profile-reports"></a>Готовые отчеты о профиле

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Отчет — это коллекция визуализаций данных, которые помогают вам понимать поведение пользователей. При подключении к аналитике аудитории Customer Insights, аналитика вовлеченности может отображать отчет с информацией об унифицированных профилях клиентов. Этот отчет включает количество ваших профилей, сгруппированных по полу, возрасту и географическому расположению.

## <a name="prerequisites"></a>Предварительные условия

Среда аналитики аудитории должна хранить данные в управляемой клиентом учетная запись Azure Data Lake Storage.

Если вы используете пробную версию возможности аналитики аудитории или среду в управляемом Customer Insights озере данных, [свяжитесь с нами](https://go.microsoft.com/fwlink/?linkid=2145734), чтобы получить помощь.  


## <a name="enable-the-customer-profile-report"></a>Включить отчет о профиле клиента

Администратор среды должен [связать аналитику взаимодействия и аналитику аудитории](integrate-audience-insights-engagement-insights.md).

После указания сведений о подключении администратор может предоставить доступ другим людям в организации для просмотра отчета. Администратор среды, который настраивает подключение, автоматически имеет доступ к отчету. 

После завершения подключения функция **Профили** будет доступна на левой панели навигации. 

- Перейдите к **Обнаружение данных** > **Профили**, чтобы просмотреть отчет.

Отчет **Профили** содержит визуализацию пола, возраста и географического расположения подключенных профилей клиентов.

:::image type="content" source="media/customer-profiles.png" alt-text="Отчет о профиле клиента.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]