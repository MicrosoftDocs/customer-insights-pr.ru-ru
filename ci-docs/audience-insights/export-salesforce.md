---
title: Экспорт данных Customer Insights в Salesforce Marketing Cloud
description: Узнайте, как настроить подключение и экспорт в Salesforce Marketing Cloud.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 17a608a64433cdc395e0b503a42b6290db5c39ec
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230220"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a>Экспорт сегментов и других данных в Salesforce Marketing Cloud (предварительная версия)

Используйте данные своих клиентов в Salesforce Marketing Cloud, экспортируя их через расположение SFTP.

## <a name="prerequisites-for-connection"></a>Предварительные требования для подключения

- Наличие узла SFTP и соответствующих учетных данных администратора. [Как настроить местоположения SFTP для Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Настройте подключение к Salesforce Marketing Cloud

1. Перейти в раздел **Администрирование** > **Подключения**.

1. Выберите **Добавить подключение** и выберите **Salesforce Marketing Cloud** для настройки подключения.

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. Укажите, кто может использовать это подключение. Если вы не предпримете никаких действий, по умолчанию это будут администраторы. Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Обеспечьте **Имя пользователя**, **Пароль**, **Имя узла** и **Папка экспорта** для вашей учетной записи SFTP.

1. Выберите **Проверить**, чтобы протестировать соединение.

1. Выберите **Принимаю**, чтобы подтвердить **конфиденциальность данных и соответствие**.

1. Выберите **Сохранить**, чтобы завершить подключение.

## <a name="configure-an-export"></a>Настройка экспорта

Вы можете настроить этот экспорт, если у вас есть доступ к подключению этого типа. Дополнительные сведения см. в разделе [Разрешения, необходимые для настройки экспорта](export-destinations.md#set-up-a-new-export).

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Чтобы создать новый экспорт, выберите **Добавить пункт назначения**.

1. В поле **Подключение для экспорта** выберите подключение из раздела SFTP. Если вы не видите название этого раздела, вам не доступны подключения этого типа.

1. Выберите, хотите ли вы экспортировать свои данные как **Упаковано в формате GZip** или **Распаковано**, и **разделитель полей** для экспортируемых файлов.

1. Выберите сущности, например сегменты, которые нужно экспортировать.

   > [!NOTE]
   > Каждая выбранная сущность будет разделена на пять выходных файлов при экспорте. 

1. Нажмите кнопку **Сохранить**.

Сохранение экспорта не запускает экспорт сразу.

Экспорт выполняется с каждым [запланированным обновлением](system.md#schedule-tab). Вы также можете [экспортировать данные по запросу](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Импорт данных Customer Insights из местоположения SFTP в Salesforce Marketing Cloud

1. Создайте [расширения данных в Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) для импорта файла данных Customer Insights из расположения SFTP.

2. [Импортируйте данные из местоположения SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) в расширение данных Salesforce Marketing Cloud. 

3. Настройте автоматизацию для импорта данных в расширения данных. Узнать больше об [автоматизации переноса файлов и автоматизации по расписанию](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Определите [автоматизацию переноса файлов](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) или [автоматизацию по расписанию](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

Вот пример [автоматизации с SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Соответствие и конфиденциальность данных

Когда вы включаете Dynamics 365 Customer Insights для передачи данных через SFTP, вы разрешаете передачу данных за пределы обеспечения соответствия для Dynamics 365 Customer Insights, включая потенциально конфиденциальные данные, такие как личные данные. Microsoft передаст такие данные по вашему указанию, но вы несете ответственность за соблюдение компанией пунктом назначения экспорта любых обязательств в отношении конфиденциальности или безопасности, которые могут у вас возникнуть. Дополнительные сведения см. в разделе [Заявление о конфиденциальности корпорации Майкрософт](https://go.microsoft.com/fwlink/?linkid=396732).
Ваш администратор Dynamics 365 Customer Insights может в любое время удалить этот пункт назначения, чтобы прекратить использование этой функции.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
