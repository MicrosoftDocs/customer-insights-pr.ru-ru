---
title: Экспорт данных Customer Insights в Dynamics 365 Marketing
description: Узнайте, как настроить подключение и экспорт в Dynamics 365 Marketing.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 7227f3f9e7699a9b5ad546789de5e568b56da579
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646486"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Использование сегментов в Dynamics 365 Marketing (предварительная версия)



Используйте [сегменты](segments.md) для создания кампаний и связи с определенными группами клиентов с помощью Dynamics 365 Marketing. Дополнительные сведения см. в [Использование сегментов из Dynamics 365 Customer Insights с Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Если вы используете новые возможности Dynamics 365 Marketing для оркестрации в реальном времени циклов взаимодействия с клиентами в организации Dataverse, вам не нужно создавать стандартный экспорт в Dynamics 365 Marketing. Контакты и сегменты из Customer Insights доступны непосредственно в Dynamics 365 Marketing после подключения Marketing и Customer Insights. Прежде чем удалять существующие экспорты, просмотрите документацию о том, [как подключить оркестрацию циклов взаимодействия с клиентом Customer Insights и Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Предварительное требование для подключения

- Записи контактов должны присутствовать в Dynamics 365 Marketing, прежде чем вы сможете экспортировать сегмент из Customer Insights в Marketing. См. дополнительные сведения о загрузке контактов в [Dynamics 365 Marketing с помощью Microsoft Dataverse](connect-dataverse-managed-lake.md).

  > [!NOTE]
  > Экспорт сегментов из Customer Insights в Marketing не приведет к созданию новых записей контактов в экземплярах Marketing. Записи контактов из Marketing должны быть приняты в Customer Insights и могут использоваться как источник данных. Их также необходимо включить в объединенную сущность «Клиент», чтобы сопоставить идентификаторы клиентов с идентификаторами контактов, прежде чем сегменты можно будет экспортировать.

## <a name="set-up-connection-to-marketing"></a>Настройка подключения к Marketing

1. Перейти в раздел **Администрирование** > **Подключения**.

1. Выберите **Добавить подключение** и выберите **Dynamics 365 Marketing** для настройки подключения.

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. Укажите, кто может использовать это подключение. Если вы не предпримете никаких действий, по умолчанию это будут администраторы. Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введите URL-адрес Marketing вашей организации в поле **Адрес сервера**.

1. В разделе **Учетная запись администратора сервера** выберите **Войти** и выберите учетную запись Dynamics 365 Marketing.

1. Сопоставьте поле "Идентификатор контакта" в сущности "Клиент" с идентификатором контакта Dynamics 365.

1. Выберите **Сохранить**, чтобы завершить подключение. 

## <a name="configure-an-export"></a>Настройка экспорта

Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа. Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.

1. В поле **Подключение для экспорта** выберите подключение из раздела Dynamics 365 Marketing. Если вы не видите название этого раздела, вам не доступны подключения этого типа.

1. Выберите один или несколько сегментов.

1. Нажмите кнопку **Сохранить**.

Сохранение экспорта не запускает экспорт сразу.

Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab). Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand). 

[!INCLUDE [footer-include](includes/footer-banner.md)]