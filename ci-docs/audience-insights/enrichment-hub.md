---
title: Обогащение унифицированных профилей клиентов
description: Используйте возможности для обогащения данных о ваших клиентах.
ms.date: 11/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 36e6f7f8fcd64fc2591e913910918b83bf27567b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597711"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Обогащение профилей клиентов (предварительная версия)

Используйте данные из таких источников, как Microsoft и другие партнеры, чтобы обогатить данные ваших клиентов.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Страница центра обогащения":::

В аналитике аудитории перейдите **Данные** > **Обогащение**, чтобы открыть параметры обогащения.    
У вас должны быть разрешения участника или администратора для создания или редактирования обогащений. Дополнительные сведения см. [Разрешения](permissions.md).

На вкладке **Обнаружить** вы найдете следующие обогащения:

- [Торговые марки](enrichment-microsoft-graph.md) предоставлены Microsoft Graph
- [Интересы](enrichment-microsoft-graph.md) предоставлены Microsoft Graph
- [Данные компании](enrichment-leadspace.md) предоставлены Leadspace
- [Демографические данные](enrichment-experian.md) предоставлены Experian
- [Данные расположения](enrichment-here.md) предоставлены HERE Technologies
- [Пользовательские данные](enrichment-SFTP-custom-import.md) через протокол SFTP

На вкладке **Мои обогащения** можно увидеть обогащения, которые вы настроили, и отредактировать их свойства.

## <a name="manage-existing-enrichments"></a>Управление существующими обогащениями

Перейдите в раздел **Мои обогащения**, чтобы увидеть все настроенные обогащения. Каждое обогащение представлено в виде строки, которая включает дополнительную информацию об обогащении.

Выберите обогащение, чтобы увидеть доступные параметры. Кроме того, вы можете выбрать многоточие (...) в элементе списка, чтобы просмотреть параметры.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Параметры для управления обогащениями в списке обогащений":::

- **Просмотр** сведений об обогащении с рядом обогащенных профилей клиентов.
- **Изменение** конфигурации обогащения.
- **Выполните** обогащение для обновления профилей клиентов последними данными.
- **Деактивирование** существующего обогащения, чтобы оно не обновлялось автоматически при каждом запланированном обновлении. Данные последнего успешного обновления будут по-прежнему доступны. **Активирование** неактивного обогащения для перезапуска автоматического обновления при каждом запланированном обновлении.
- **Удалите** обогащение.

Вы можете запустить или деактивировать несколько обогащений одновременно, выбрав их в списке. Параметры просмотра и редактирования недоступны как массовые действия и работают только для одного обогащения за раз.


[!INCLUDE[footer-include](../includes/footer-banner.md)]