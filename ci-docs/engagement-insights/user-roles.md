---
title: Роли и разрешения
description: Обзор доступных ролей и разрешений для участников рабочей области.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6d7f4db4a130fc15a69b380c892538db5492d96d8e13f3c070c6a6b9bd098371
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036709"
---
# <a name="roles-and-permissions"></a>Роли и разрешения

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Рабочая область— это как вы храните и управляете событиями и отчетами. Участник — это пользователь, который может получить доступ к рабочей области. Вы можете назначать участников рабочей области и определять их роли и разрешения. Роли администраторов управляют рабочими областями и средами и настраивают аналитику вовлеченности для других пользователей. Роли участников предназначены для аналитиков, которым не нужно настраивать аналитику вовлеченности, но которые хотят создавать свои собственные отчеты, воронки или сегменты.

## <a name="permissions"></a>Разрешения
  
В следующей таблице указаны разрешения для каждой роли. 

| Разрешение | Администратор среды | Администратор рабочей области | Участник среды | Участник рабочей области | 
|--|--|--|--|--|
| Создавать среды (создатель автоматически становится администратором среды) | X* | X* | X* | X* |  
| Настроить среду (участники среды, удалить среду) | X |  |  |  |  
| Создание рабочих областей | X |  |  |  |  
| Настройка рабочих областей (участники рабочей области, удаление рабочей области) | X | X |  |  |  
| Настроить события и уточненные события | X | X | |  |  
| Просмотр событий и уточненных событий рабочей области | X | X | |  |  
| Просмотр ресурсов рабочей области (отчеты, сегменты и метрики)| X | X | X | X |  
| Создание пользовательских отчетов и воронок | X | X | X | X |  
| Создание базовых метрик и аналитик| X | X |  |  |  
| Создать сегменты| X | X | X | X |  

*Можно создавать только пробные среды в предварительной версии. 

## <a name="add-members"></a>Добавление участников

Вы можете добавлять и удалять участников из рабочих областей и сред. Для получения дополнительной информации см. [Среды и рабочие области](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]