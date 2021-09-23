---
title: Управление рабочими областями и средами
description: Как создавать, переименовывать и удалять рабочие области и среды.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 09/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: a5b48db5ae23ea65bf608d67348d493bfdc7678f
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486051"
---
# <a name="manage-environments-and-workspaces"></a>Управление средами и рабочими областями

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Обзор

Рабочая область— это пространство для хранения и управления событиями и отчетами. Здесь вы можете просматривать активность пользователей в режиме реального времени. При создании рабочей области вы выбираете тип данных для отправки в рабочую область. В настоящее время поддерживаются веб-данные и мобильные приложения.

Среда — это пространство, в котором вы управляете своими рабочими областями и подключениями. То, как вы используете среды, зависит от вашей организации и вашего случая. Например, можно создать:

-   Одна среда.
-   Отдельные среды для тестовых и рабочих целей.
-   Отдельные среды для определенных групп или отделов в вашей организации, которые содержат соответствующие события для каждой аудитории.
-   Отдельные среды для разных глобальных подразделений компании.
-   Подключения к аналитике аудитории Customer Insights.

## <a name="choose-an-environment-and-create-a-workspace"></a>Выберите среду и создайте рабочую область 

Каждое рабочая область должна быть в среде. Вы можете выбрать уже существующую среду или создать новую при создании рабочей области. Затем вы можете добавить участников рабочей области и начать сбор данных.

**Чтобы создать вашу первую рабочую область**

1. В аналитике вовлеченности выберите **Создать** из переключателя рабочей области. 

   :::image type="content" source="media/New-workspace.png" alt-text="Средство выбора рабочей области страницы Customer Insights.":::

1. Выберите среду из списка или выберите **Создать новую среду**.

1. Введите имя в **Имя рабочей области**. 

1. Выберите тип среды, которую вы хотите создать, в зависимости от того, хотите ли вы измерить, что происходит на веб-сайте или в мобильном приложении. 

1. Вы можете добавлять участников и назначать их уровень разрешений из список **Роль**. Затем выберите **Готово** для создания рабочей области или **Далее**, чтобы установить код. 

1. Установите фрагмент кода, чтобы начать получать данные, а затем выберите **Готово**. 

## <a name="manage-a-workspace"></a>Управление рабочей областью

Вы можете одновременно поддерживать несколько рабочих областей в среде. Ваша [роль](user-roles.md) определяет, как вы можете в них работать. 

 - Вы должны быть администратором среды или администратором рабочей области, чтобы управлять рабочей областью.
 - Как администратор рабочей области вы можете переименовывать существующие рабочие области или удалять их. 

### <a name="edit-a-workspace-name"></a>Изменить имя рабочей области

1. Перейдите к **Администратор** > **Рабочая область** и выберите **Параметры**.

1. В поле **Имя рабочей области** введите новое имя.

1. Нажмите кнопку **Сохранить**, чтобы применить изменения.

### <a name="delete-a-workspace"></a>Удаление рабочей области

При удалении рабочей области будет безвозвратно потеряно все ее содержимое, данные, параметры и разрешения. Отменить это действие будет невозможно. Отменить это действие невозможно.

1. Перейдите к **Администратор** > **Рабочая область** и выберите **Параметры**.

1. Выберите **Удалить рабочую область**. 

1. В диалоговом окне **Удалить рабочую область** введите **ПОДТВЕРДИТЬ УДАЛЕНИЕ**. 

1. Выберите **Удалить**, чтобы удалить рабочую область без возможности восстановления.

### <a name="manage-workspace-members"></a>Управление участниками рабочей области

1. Перейдите к **Администратор** > **Рабочая область** и выберите **Участники**.

1. Выберите **Добавить участников**, чтобы предоставить доступ и [назначать роли](user-roles.md). В настоящее время только **Администратор рабочей области** доступен.

1. Выберите **Добавить участников** чтобы добавить их в вашу рабочую область.

## <a name="manage-an-environment"></a>Управление средой

Как администратор среды, вы можете получить доступ к среде с левой панели навигации. Вы можете настроить параметры среды, других администраторов среды и рабочие области. Выбирайте вкладки, чтобы перемещаться между разными областями в центре администрирования.

:::image type="content" source="media/New-environment.png" alt-text="Центр администрирования среды.":::

### <a name="create-an-environment"></a>Создание среды

1. В средстве выбора рабочей области выберите **+Создать**.

1. В управляемом опыте откройте раскрывающееся меню **Среда** и выберите **Создать новую среду**. 

1. Укажите **Имя среды**.

   :::image type="content" source="media/create-environment.png" alt-text="Войдите в управляемый опыт, чтобы указать сведения о среде.":::

1. Выберите **Регион** и выберите **Далее**. 

1. Укажите имя рабочей области и выберите, какой тип рабочей области вы хотите создать. 

1.  При желании добавьте участников и скопируйте фрагмент кода, чтобы завершить процесс создания.

### <a name="rename-an-environment"></a>Переименование среды

1. Перейдите к **Администратор** > **Среда** и выберите **Параметры**.

1. Обновите **Имя среды** и выберите **Сохранить** чтобы применить ваши изменения.

### <a name="manage-environment-members"></a>Управление участниками среды

1. Перейдите к **Администратор** > **Среда** и выберите **Участники**.

1. Выберите **Добавить участников**, чтобы обновить участников и [назначать роли](user-roles.md). В настоящее время только **Администратор среды** доступен.

1. Выберите **Добавить участников** чтобы добавить их в вашу среду.

### <a name="delete-an-environment"></a>Удаление среды

Администраторы среды могут удалять среды. Прежде чем вы сможете удалить среду, вы должны удалить все находящиеся в ней рабочие области.

1. Перейдите к **Администратор** > **Среда** и выберите **Параметры**.

1. Выберите **Удалить среду**. 

1. В диалоговом окне **Удалить рабочую область** введите **ПОДТВЕРДИТЬ УДАЛЕНИЕ**. 

1. Выберите **Удалить**, чтобы удалить среду без возможности восстановления.

## <a name="manage-connections"></a>Управление подключениями

Установив подключения с аналитиками аудитории, вы сможете просматривать отчеты в аналитике вовлеченности на основе унифицированных профилей клиентов. 

Дополнительные сведения см. в разделе [Создание связи между аналитикой аудитории и аналитикой взаимодействий](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Управление личными данными

Чтобы защитить личные данные вашего клиента, вы можете удалить или экспортировать данные, позволяющие идентифицировать конечного пользователя.

Дополнительные сведения см. в [Удаление и экспорт данных события, содержащих личные сведения](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]