---
title: Начало работы с Dynamics 365 Customer Insights
description: Обзор ресурсов справки Customer Insights поможет быстро приступить к работе.
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 1c925110f40319df77940d1c32f24a99504d6ec6
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011995"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Начало работы с Dynamics 365 Customer Insights

Customer Insights может помочь вам лучше понять своих клиентов. Соедините данные из различных транзакционных, поведенческих и наблюдательных источников, чтобы создать полное представление о клиентах. Используйте эти аналитические данные для создания взаимодействия и процессов, ориентированных на клиентов. Унифицируйте и анализируйте данные о клиентах и используйте их для интеллектуального анализа и действий.

## <a name="step-1-create-an-environment"></a>Шаг 1. Создание среды

Сначала создайте среду для работы. Если ваша организация уже приобрела лицензию, см. [Создайте среду](create-environment.md). Чтобы начать пробную версию Customer Insights, см. [Настройка пробной среды](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>Шаг 2. Изучите Customer Insights

При первом входе в Customer Insights настройте параметры и изучите продукт.

1. [Войдите в Customer Insights](https://home.ci.ai.dynamics.com) с помощью своей учетной записи Microsoft Azure Active Directory (AAD).

1. Измените среду, чтобы увидеть демонстрационные данные и [изучить Customer Insights](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Шаг 3. Принятие, унификация и настройка отношений для своих данных

Унифицированные профили — это основа для получения аналитической информации и выполнения действий с данными. Переносите данные из различных источников и запускайте процесс объединения данных для объединения единых профилей. Укажите связь между принимаемыми сущностями и используйте функции обогащения для добавления информации в профили.

1. Принимайте данные путем создания источников данных из нескольких вариантов. Выберите между [Azure Data Lake Storage, включая Common Data Model](connect-common-data-model.md), [Azure Synapse Analytics](connect-synapse.md), [Microsoft Dataverse](connect-dataverse-managed-lake.md) или [соединителями Power Query](connect-power-query.md).

1. Запустите [процесс объединения данных](data-unification.md) путем определения [исходных полей](map-entities.md), удаления [повторяющихся данных](remove-duplicates.md), [условий сопоставления](match-entities.md) и [объединяющих полей](merge-entities.md).

1. Познакомьтесь с [сущностями, создаваемыми системой](entities.md) и создайте [отношения между принятыми сущностями](relationships.md).

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Шаг 4. Расширьте единые профили с помощью прогнозов, действий и показателей

Настроив унифицированные профили, обогатите данные, чтобы еще больше увеличить объем информации, которую они предоставляют.

1. Выберите из расширяющейся библиотеки поставщиков услуг обогащения, чтобы [обогатить данные ваших клиентов](enrichment-hub.md).

1. Используйте [готовые модели](predictions-overview.md) для прогнозирования вероятности оттока клиентов или ожидаемых доходов.

1. [Настройте действия](activities.md) на основе принятых данных и визуализируйте взаимодействия с вашими клиентами на хронологической временной шкале.

1. [Создайте меры](measures.md), чтобы оценить ваши бизнес-цели и ключевые показатели эффективности.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Шаг 5. Создание сегментов и активирование данных с помощью различных параметров экспорта

Теперь, когда ваши данные являются полными и содержат широкий спектр информации о ваших клиентах, найдите способ выполнить какие-либо действия с этими данными.

1. [Создайте сегменты](segments.md) (подмножества вашей клиентской базы), чтобы ваши действия были актуальны для целевых клиентов.

1. Просмотрите расширяющийся каталог [параметров экспорта](export-destinations.md), где вы можете использовать данные клиентов. Например, вы можете использовать данные для управления рекламными акциями и использования цифрового маркетинга.

1. Просмотрите варианты интеграции, например, с другими приложениями Dynamics 365 с [Надстройка Карточка клиента](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]
