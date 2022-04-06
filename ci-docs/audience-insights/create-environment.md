---
title: Создание сегментов в Customer Insights
description: Шаги по созданию сред с лицензионной подпиской для Dynamics 365 Customer Insights.
ms.date: 03/28/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: a538237322615f69f0a5cb43d394275bf79af00b
ms.sourcegitcommit: ae02ac950810242e2505d7d371b80210dc8a0777
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/29/2022
ms.locfileid: "8491929"
---
# <a name="create-an-environment-in-audience-insights"></a>Создайте среду в аналитике аудитории

В этой статье объясняется, как создать новую среду после того, как ваша организация приобрела подписку на Dynamics 365 Customer Insights. 

Организации могут создавать *две* среды для каждой лицензии Customer Insights. Если ваша организация приобретает более одной лицензии, [свяжитесь с нашей службой поддержки](https://go.microsoft.com/fwlink/?linkid=2079641) для увеличения количества доступных сред. Для получения дополнительной информации о емкости и дополнительной емкости загрузите [Руководство по лицензированию Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Если вы хотите попробовать эту службу, см. [Настройка пробной среды](../trial-signup.md).

## <a name="create-a-new-environment"></a>Создать новую среду

После приобретения лицензии на подписку Customer Insights глобальный администратор клиента Microsoft 365 получает электронное письмо с приглашением создать среду. Для начала работы перейдите по адресу [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start). 

Пошаговые инструкции помогут вам собрать всю необходимую информацию для новой среды. Вам нужны [разрешения администратора](permissions.md) в аналитике аудитории для создания сред или управления ими.

1. В аналитике аудитории откройте средство выбора среды и выберите **+ Создать**.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="Выберите средство выбора среды.":::

1. Следуйте инструкциям, описанным в следующих разделах.

### <a name="step-1-provide-environment-information"></a>Шаг 1. Предоставьте информацию о среде

На шаге **Основная информация** выберите, хотите ли вы создать среду с нуля или копировать данные [из другой среды ](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Диалог для создания новой среды Customer Insights.":::

Укажите следующие данные:
   - **Имя**: имя этой среды. Это поле уже заполнено, если вы скопировали существующую среду, но вы можете изменить его.
   - **Выберите свой бизнес**: выберите основную аудиторию для новой среды. Вы можете работать с отдельными клиентами (B-to-C) или [корпоративными учетными записями](work-with-business-accounts.md) (B-to-B).
   - **Тип**: выберите, хотите ли вы создать рабочую среду или среду песочницы. Среды песочницы не позволяют обновлять данные по расписанию и предназначены для предварительной реализации и тестирования. Среды песочницы используют ту же основную аудиторию, что и выбранная в данный момент рабочая среда.
   - **Регион**: регион, в котором служба развернута и размещена.

### <a name="step-2-configure-data-storage"></a>Шаг 2. Настройте хранилище данных

На шаге **Хранилище данных** выберите, где хранить данные из аналитики аудитории.

У вас будет два варианта: **Хранилище Customer Insights** (Azure Data Lake под управлением рабочей группы Customer Insights) и **Azure Data Lake Storage** (ваше собственное Azure Data Lake Storage). По умолчанию выбран вариант хранилища Customer Insights.

:::image type="content" source="media/data-storage-environment.png" alt-text="Выберите Azure Data Lake Storage для хранения данных аналитики аудитории.":::

Сохраняя данные в Azure Data Lake Storage, вы соглашаетесь с тем, что данные будут передаваться и храниться в соответствующем географическом местоположении для этой учетной записи хранения Azure. Это место может отличаться от того, в котором хранятся данные в Dynamics 365 Customer Insights. Подробнее можно узнать в [центре управления безопасностью Microsoft](https://www.microsoft.com/trust-center).

> [!NOTE]
> В настоящее время Customer Insights поддерживает следующее:
> - Полученные сущности из потоков данных Power BI, которые хранятся в Data Lake под управлением Microsoft Dataverse.  
> - Учетные записи Azure Data Lake Storage из того же региона Azure, который вы выбрали при создании среды.
> - Учетные записи Azure Data Lake Storage Gen2, у которых включены *иерархические пространства имен*. Учетные записи хранения Azure Data Lake Gen1 не поддерживаются.

Для варианта Azure Data Lake Storage вы можете выбирать между вариантом на основе ресурсов и вариантом на основе подписки для аутентификации. Для получения дополнительной информации см. раздел [Подключение к учетной записи Azure Data Lake Storage с помощью субъекта-службы Azure](connect-service-principal.md). Имя **Контейнер** будет `customerinsights` и не может быть изменено.

Когда системные процессы, такие как прием данных, завершены, система создает соответствующие папки в указанной вами учетной записи хранения. Файлы данных и файлы *model.json* создаются и добавляются в папки на основе имени процесса.

Если вы создаете несколько сред Customer Insights и выбираете сохранение выходных сущностей из этих сред в свою учетную запись хранения, Customer Insights создает отдельные папки для каждой среды с `ci_environmentID` в контейнере.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Шаг 3. Подключитесь к Microsoft Dataverse
   
На шаге **Microsoft Dataverse** можно связать Customer Insights с вашей средой Dataverse.

Предоставьте свою собственную среду Microsoft Dataverse для обмена данными (профилями и аналитиками) с бизнес-приложениями на основе Dataverse, например Dynamics 365 Marketing или приложения на основе модели в Power Apps. Оставьте это поле пустым, если у вас нет своей среды Dataverse, и мы предоставим ее вам.

Подключение к вашему среде Dataverse также позволяет [принимать данные из локальных источников данных, используя Power Platform потоки данных и шлюзы](data-sources.md#add-data-from-on-premises-data-sources). Вы также можете использовать [готовые модели прогноза](predictions-overview.md?tabs=b2c#out-of-box-models) путем подключения к среде Dataverse.

> [!IMPORTANT]
> 1. Для обмена данными Customer Insights и Dataverse должны находиться в одном регионе.
> 1. У вас должна быть глобальная роль администратора в среде Dataverse. Проверьте, [связана ли среда Dataverse](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) с определенными группами безопасности, и убедитесь, что вы добавлены в эти группы безопасности.
> 1. Никакая существующая среда Customer Insights еще не связана с этой средой Dataverse. Узнайте, как [удалить существующее подключение к среде Dataverse](manage-environments.md#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="обмен данными с Microsoft Dataverse автоматически включен для новых экземпляров сети.":::

Для получения дополнительной информации о включении обмена данными с Microsoft Dataverse из собственного Azure Data Lake Storage, см. [Подключение к Microsoft Dataverse](manage-environments.md#connect-to-microsoft-dataverse).

Конфигурация Customer Insights не поддерживает следующие сценарии передачи данных:
- Если вы включите обмен данными с Dataverse, вы не сможете [создавать прогнозируемые или отсутствующие значения в сущности](predictions.md).

### <a name="step-4-finalize-the-settings"></a>Шаг 4. Завершение настройки

На шаге **Проверка** выполните все указанные настройки. Когда все будет выглядеть готовым, выберите **Создать**, чтобы настроить среду. 

Вы также можете изменить большинство настроек позже. Дополнительные сведения см. в статье [Управление средами](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Работа в новой среде

Ознакомьтесь со следующими статьями, которые помогут вам приступить к настройке Customer Insights: 

- [Добавьте дополнительных пользователей и назначьте разрешения](permissions.md).
- [Примите свои источники данных](data-sources.md) и обработайте их в [процессе объединения данных](data-unification.md), чтобы получить [единые профили клиентов](customer-profiles.md).
- [Обогатите единые профили клиентов](enrichment-hub.md) или [запустите прогнозные модели](predictions-overview.md).
- [Создайте сегменты](segments.md), чтобы группировать клиентов, и [меры](measures.md) для просмотра КПЭ.
- [Настройте подключения](connections.md) и [экспорты](export-destinations.md) для обработки подмножеств ваших данных в других приложениях.
