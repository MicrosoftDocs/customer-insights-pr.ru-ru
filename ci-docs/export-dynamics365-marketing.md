---
title: Экспорт сегментов в Dynamics 365 Marketing (предварительная версия)
description: Узнайте, как настроить подключение и экспорт в Dynamics 365 Marketing.
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
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196640"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Экспорт сегментов в Dynamics 365 Marketing (предварительная версия)

Используйте [сегменты](segments.md) для создания кампаний и связи с определенными группами клиентов с помощью [Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Если вы используете новые возможности Dynamics 365 Marketing для оркестрации в реальном времени циклов взаимодействия с клиентами в организации Dataverse, вам не нужно создавать стандартный экспорт в Dynamics 365 Marketing. Контакты и сегменты из Customer Insights доступны непосредственно в Dynamics 365 Marketing после подключения Marketing и Customer Insights. Прежде чем удалять существующие экспорты, просмотрите документацию о том, [как подключить оркестрацию циклов взаимодействия с клиентом Customer Insights и Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>Необходимые условия

Записи контактов должны присутствовать в Dynamics 365 Marketing, прежде чем вы сможете экспортировать сегмент из Customer Insights в Marketing. См. дополнительные сведения о загрузке контактов в [Dynamics 365 Marketing с помощью Microsoft Dataverse](connect-dataverse-managed-lake.md).

> [!NOTE]
> Экспорт сегментов из Customer Insights в Marketing не приведет к созданию новых записей контактов в экземплярах Marketing. Записи контактов из Marketing должны быть приняты в Customer Insights и могут использоваться как источник данных. Их также необходимо включить в объединенную сущность «Клиент», чтобы сопоставить идентификаторы клиентов с идентификаторами контактов, прежде чем сегменты можно будет экспортировать.

## <a name="set-up-connection-to-marketing"></a>Настройка подключения к Marketing

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Перейти в раздел **Администрирование** > **Подключения**.

1. Выберите **Добавить подключение** и выберите **Dynamics 365 Marketing**.

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. Укажите, кто может использовать это подключение. По умолчанию это только администраторы. Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введите URL-адрес Marketing вашей организации в поле **Адрес сервера**.

1. В разделе **Учетная запись администратора сервера** выберите **Войти** и выберите учетную запись Dynamics 365 Marketing.

1. Сопоставьте поле "Идентификатор контакта" в сущности "Клиент" с идентификатором контакта Dynamics 365.

1. Ознакомьтесь с положениями [Соответствие и конфиденциальность данных](connections.md#data-privacy-and-compliance) и выберите **Принимаю**.

1. Выберите **Сохранить**, чтобы завершить подключение.

## <a name="configure-an-export"></a>Настройка экспорта

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Выберите **Добавить экспорт**.

1. В поле **Подключение для экспорта** выберите подключение из раздела Dynamics 365 Marketing. Свяжитесь с администратором, если подключение недоступно.

1. Введите имя экспорта.

1. Выберите поле "Идентификатор контакта" в сущности "Клиент" с идентификатором контакта Dynamics 365.

1. Выберите сегменты, которые нужно экспортировать.

1. Выберите **Сохранить**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
