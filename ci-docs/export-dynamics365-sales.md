---
title: Экспорт сегментов в Dynamics 365 Sales (предварительная версия)
description: Узнайте, как настроить подключение и экспорт в Dynamics 365 Sales.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: c3497f4625cada49ae33c6987e58994a15536f9b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195997"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Экспорт сегментов в Dynamics 365 Sales (предварительная версия)

Используйте свои данные о клиентах для создания маркетинговых списков, бизнес-процессов для дальнейших действий, а также рассылки предложений с помощью Dynamics 365 Sales.

## <a name="prerequisites"></a>Предварительные условия

Записи контактов должны присутствовать в Dynamics 365 Sales, прежде чем вы сможете экспортировать сегмент из Customer Insights в Sales. Подробнее о том, как принять контакты из [Dynamics 365 Sales с помощью Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Экспорт сегментов из Customer Insights в Sales не приведет к созданию новых записей контактов в экземплярах Sales. Записи контактов из Sales должны быть приняты в Customer Insights и могут использоваться как источник данных. Их также необходимо включить в объединенную сущность «Клиент», чтобы сопоставить идентификаторы клиентов с идентификаторами контактов, прежде чем сегменты можно будет экспортировать.

## <a name="known-limitations"></a>Известные ограничения

Экспорт в Dynamics 365 Sales ограничен 100 000 на сегмент, что может занять до 3 часов.

## <a name="set-up-connection-to-sales"></a>Настройка подключения к Sales

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Перейти в раздел **Администрирование** > **Подключения**.

1. Выберите **Добавить подключение** и выберите **Dynamics 365 Sales**.

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. Укажите, кто может использовать это подключение. По умолчанию это только администраторы. Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введите URL-адрес Sales вашей организации в поле **Адрес сервера**.

1. В разделе **Учетная запись администратора сервера** выберите **Войти** и выберите учетную запись Dynamics 365 Sales.

1. Сопоставьте поле идентификатора клиента с идентификатором контакта Dynamics 365.

1. Ознакомьтесь с положениями [Соответствие и конфиденциальность данных](connections.md#data-privacy-and-compliance) и выберите **Принимаю**.

1. Выберите **Сохранить**, чтобы завершить подключение.

## <a name="configure-an-export"></a>Настройка экспорта

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Выберите **Добавить экспорт**.

1. В поле **Подключение для экспорта** выберите подключение из раздела Dynamics 365 Sales. Свяжитесь с администратором, если подключение недоступно.

1. Введите имя экспорта.

1. Выберите поле "Идентификатор контакта" в сущности "Клиент" с идентификатором контакта Dynamics 365.

1. Выберите сегменты, которые нужно экспортировать.

1. Выберите **Сохранить**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
