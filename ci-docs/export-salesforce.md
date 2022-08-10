---
title: Экспорт данных в Salesforce Marketing Cloud (предварительная версия)
description: Узнайте, как настроить подключение и экспорт в Salesforce Marketing Cloud.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197054"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Экспорт данных в Salesforce Marketing Cloud (предварительная версия)

Используйте данные своих клиентов в Salesforce Marketing Cloud, экспортируя их через расположение SFTP.

## <a name="prerequisites"></a>Предварительные условия

- [Узел SFTP для Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) и соответствующие учетные данные администратора.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Настройте подключение к Salesforce Marketing Cloud

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Перейти в раздел **Администрирование** > **Подключения**.

1. Выберите **Добавить подключение** и выберите **Salesforce Marketing Cloud**.

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. Укажите, кто может использовать это подключение. По умолчанию это только администраторы. Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Обеспечьте **Имя пользователя**, **Пароль**, **Имя узла** и **Папка экспорта** для вашей учетной записи SFTP.

1. Выберите **Проверить**, чтобы протестировать соединение.

1. Ознакомьтесь с положениями [Соответствие и конфиденциальность данных](connections.md#data-privacy-and-compliance) и выберите **Принимаю**.

1. Выберите **Сохранить**, чтобы завершить подключение.

## <a name="configure-an-export"></a>Настройка экспорта

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Выберите **Добавить экспорт**.

1. В поле **Подключение для экспорта** выберите подключение из раздела SFTP. Свяжитесь с администратором, если подключение недоступно.

1. Введите имя экспорта.

1. Выберите, хотите ли вы экспортировать свои данные как **Упаковано в формате GZip** или **Распаковано**, и **разделитель полей** для экспортируемых файлов.

1. Выберите сущности, например сегменты, которые нужно экспортировать.

   > [!NOTE]
   > Каждая выбранная сущность будет разделена максимум на пять выходных файлов при экспорте.

1. Выберите **Сохранить**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Импорт данных Customer Insights из местоположения SFTP в Salesforce Marketing Cloud

1. Создайте [расширения данных в Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) для импорта файла данных Customer Insights из расположения SFTP.

2. [Импортируйте данные из местоположения SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) в расширение данных Salesforce Marketing Cloud.

3. Настройте автоматизацию для импорта данных в расширения данных. Узнать больше об [автоматизации переноса файлов и автоматизации по расписанию](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Определите [автоматизацию переноса файлов](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) или [автоматизацию по расписанию](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

Вот пример [автоматизации с SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
