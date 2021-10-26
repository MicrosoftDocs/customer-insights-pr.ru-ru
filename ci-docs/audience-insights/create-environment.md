---
title: Создание сегментов в Customer Insights
description: Шаги по созданию сред с лицензионной подпиской для Dynamics 365 Customer Insights.
ms.date: 10/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 95afd1fedb98a451e4978ee66be2ea98ad7a4a76
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645722"
---
# <a name="create-an-environment-in-audience-insights"></a>Создайте среду в аналитике аудитории

В этой статье объясняется, как создать новую среду после того, как ваша организация приобрела подписку на Dynamics 365 Customer Insights. 

Организации могут создавать *две* среды для каждой лицензии Customer Insights. Если ваша организация приобретает более одной лицензии, [свяжитесь с нашей службой поддержки](https://go.microsoft.com/fwlink/?linkid=2079641) для увеличения количества доступных сред. Для получения дополнительной информации о емкости и дополнительной емкости загрузите [Руководство по лицензированию Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Если вы хотите попробовать эту службу, см. [Настройка пробной среды](../trial-signup.md).

## <a name="create-a-new-environment"></a>Создать новую среду

После покупки лицензии на подписку на Customer Insights глобальный администратор клиента Microsoft 365 получает электронное письмо с предложением создать среду. Для начала работы перейдите по адресу [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start). 

Пошаговые инструкции помогут вам собрать всю необходимую информацию для новой среды. Вам нужны [разрешения администратора](permissions.md) в аналитике аудитории для создания сред или управления ими.

1. В аналитике аудитории откройте средство выбора среды и выберите **+ Создать**.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="Выберите средство выбора среды.":::

1. Следуйте инструкциям, описанным в следующих разделах.

### <a name="step-1-provide-environment-information"></a>Шаг 1. Предоставьте информацию о среде

На шаге **Основная информация** выберите, хотите ли вы создать среду с нуля или копировать данные [ из другой среды ](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Диалог для создания новой среды Customer Insights.":::

Укажите следующие данные:
   - **Имя**: имя этой среды. Это поле уже заполнено, если вы скопировали существующую среду, но вы можете изменить его.
   - **Выберите свой бизнес**: выберите основную аудиторию для новой среды. Вы можете работать с отдельными клиентами (B2C) или [организациями](work-with-business-accounts.md) (B2B).
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
> - Учетные записи Azure Data Lake Storage, у которых включены *иерархические пространства имен*.

Для варианта Azure Data Lake Storage вы можете выбирать между вариантом на основе ресурсов и вариантом на основе подписки для аутентификации. Для получения дополнительной информации см. [Подключение аналитики аудитории к учетной записи Azure Data Lake Storage Gen2 с помощью субъекта-службы Azure](connect-service-principal.md). Имя **Контейнер** будет `customerinsights` и не может быть изменено.

Когда системные процессы, такие как прием данных, завершены, система создает соответствующие папки в указанной вами учетной записи хранения. Файлы данных и файлы *model.json* создаются и добавляются в папки на основе имени процесса.

Если вы создаете несколько сред Customer Insights и выбираете сохранение выходных сущностей из этих сред в свою учетную запись хранения, Customer Insights создает отдельные папки для каждой среды с `ci_environmentID` в контейнере.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Шаг 3. Подключитесь к Microsoft Dataverse
   
На шаге **Microsoft Dataverse** можно связать Customer Insights с вашей средой Dataverse.

Чтобы использовать [готовые модели прогноза](predictions-overview.md#out-of-box-models), настройте обмен данными с Dataverse. Или вы можете включить прием данных из локальных источников данных, предоставив URL-адрес среды Microsoft Dataverse, которую администрирует ваша организация. Выберите **Включить обмен данными**, чтобы поделиться выходными данными Customer Insights с Dataverse Managed Data Lake.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Параметры конфигурации для включения обмена данными с Microsoft Dataverse.":::

> [!NOTE]
> Конфигурация Customer Insights не поддерживает следующие сценарии передачи данных:
> - Если вы сохраните все данные в свою Azure Data Lake Storage, вы не сможете включить обмен данными с управляемым Data Lake Microsoft Dataverse.
> - Если вы включите обмен данными с управляемым Data Lake Microsoft Dataverse, вы не сможете [создавать прогнозируемые или отсутствующие значения в сущности](predictions.md).

### <a name="step-4-finalize-the-settings"></a>Шаг 4. Завершение настройки

На шаге **Проверка** выполните все указанные настройки. Когда все будет выглядеть готовым, выберите **Создать**, чтобы настроить среду. 

Вы также можете изменить большинство настроек позже. Дополнительные сведения см. в статье [Управление средами](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Работа в новой среде

Ознакомьтесь со следующими статьями, которые помогут вам приступить к настройке Customer Insights. 

- [Добавьте дополнительных пользователей и назначьте разрешения](permissions.md).
- [Примите свои источники данных](data-sources.md) и обработайте их в [процессе объединения данных](data-unification.md), чтобы получить [единые профили клиентов](customer-profiles.md).
- [Обогатите единые профили клиентов](enrichment-hub.md) или [запустите прогнозные модели](predictions-overview.md).
- [Создайте сегменты](segments.md), чтобы группировать клиентов, и [меры](measures.md) для просмотра КПЭ.
- [Настройте подключения](connections.md) и [экспорты](export-destinations.md) для обработки подмножеств ваших данных в других приложениях.
