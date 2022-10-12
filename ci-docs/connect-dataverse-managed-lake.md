---
title: Подключение к данным в озере данных, управляемом Microsoft Dataverse
description: Импортируйте данные из управляемого озера данных Microsoft Dataverse.
ms.date: 08/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 0d9612525344c8ac99b6e3edfe33a426dc0a474b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609812"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Подключение к данным в озере данных, управляемом Microsoft Dataverse

Пользователи Microsoft Dataverse могут быстро подключаться к аналитическим сущностям в озере, управляемом Microsoft Dataverse. Только один источник данных среды может одновременно использовать это и то же управляемое озеро Dataverse.

> [!NOTE]
> Для выполнения описанных здесь действий и просмотра списка сущностей, доступных в управляемом озере, должны быть администратором Dataverse организации.

## <a name="prerequisites"></a>Предварительные условия

- Данные, хранящиеся в онлайн-сервисах, например Azure Data Lake Storage, могут храниться в другом месте, отличном от места, где данные обрабатываются или хранятся в Dynamics 365 Customer Insights. Импортируя данные или подключаясь к данным, хранящимся в веб-службах, вы соглашаетесь с тем, что данные могут быть переданы и сохранены в Dynamics 365 Customer Insights.  [Подробнее см. в Центре управления безопасностью Майкрософт](https://www.microsoft.com/trust-center).

- Видны только сущности Dataverse с включенным [отслеживанием изменений](/power-platform/admin/enable-change-tracking-control-data-synchronization). Эти сущности можно экспортировать в озеро данных под управлением Dataverse и использовать в Customer Insights. В готовых таблицах Dataverse по умолчанию включено отслеживание изменений. Вам необходимо включить отслеживание изменений для пользовательских таблиц. Чтобы проверить, включено ли отслеживание изменений для таблицы Dataverse, перейдите в [Power Apps](https://make.powerapps.com) > **Данные** > **Таблицы**. Найдите интересующую вас таблицу и выберите ее. Перейдите в **Настройки** > **Дополнительные параметры** и проверьте параметр **Отслеживать изменения**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Подключение к озеру, управляемому Dataverse

1. Перейдите в раздел **Данные** > **Источники данных**.

1. Выберите **Добавить источник данных**.

1. Выберите параметр **Microsoft Dataverse**.

1. Введите **Имя** для источника данных и, при желании, **Описание**.

1. Укажите **Адрес сервера** для организации Dataverse и выберите **Войти**.

1. Выберите таблицы, которые вы хотите добавить как сущности в Customer Insights, из доступного списка.

   > [!NOTE]
   > Если некоторые таблицы уже выбраны, они могут использоваться другими приложениями Dynamics 365 (такими как Dynamics 365 Sales Insights или Customer Service Insights). Вы не можете изменить выбор. Эти таблицы будут доступны как сущности после создания источника данных.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Диалоговое окно со списком сущностей в среде Dataverse.":::

1. Сохраните свой выбор, чтобы начать синхронизацию выбранных таблиц из Dataverse. Вы найдете недавно добавленное соединение на странице **Источники данных**. Она будет поставлена в очередь на обновление и будет показывать счетчик сущностей как 0, пока все выбранные таблицы не будут синхронизированы.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Загрузка данных может занять время. После успешного обновления принятые данные можно проверить на странице [**Сущности**](entities.md).

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Изменение источника данных озера, управляемого Dataverse

Вы редактируете выбор сущности только после создания источника данных. Например, если дополнительные сущности были добавлены в Dataverse и вы тоже хотите их импортировать.
Чтобы подключиться к другому озеру данных Dataverse Data Lake, [создайте новый источник данных](#connect-to-a-dataverse-managed-lake).

1. Перейдите в раздел **Данные** > **Источники данных**.

1. Рядом с источником данных, который необходимо обновить, выберите **Изменить**.

1. Выберите дополнительные сущности из доступного списка сущностей.

1. Нажмите **Сохранить**, чтобы применить изменения и вернуться на страницу **Источники данных**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupted-data"></a>Распространенные причины ошибок приема или повреждения данных

Следующие проверки выполняются с принятыми данными, чтобы выявить поврежденные записи:

- Значение поля не соответствует типу данных его столбца.
- Поля содержат символы, из-за которых столбцы не соответствуют ожидаемой схеме. Например: неправильно отформатированные кавычки, неэкранированные кавычки или символы новой строки.
- Если есть столбцы datetime/date/datetimeoffset, их формат необходимо указать в модели, если он не соответствует стандартному формату ISO.

### <a name="schema-or-data-type-mismatch"></a>Несоответствие схемы или типа данных

Если данные не соответствуют схеме, записи классифицируются как поврежденные. Исправьте либо исходные данные, либо схему, и повторите прием данных.

### <a name="datetime-fields-in-the-wrong-format"></a>Поля даты и времени в неправильном формате

Поля даты и времени в сущности не в форматах ISO или en-US. Формат даты и времени по умолчанию в Customer Insights — формат en-US. Все поля даты и времени в сущности должны быть в одном и том же формате. Customer Insights поддерживает другие форматы при условии, что аннотации или характеристики создаются на уровне источника или сущности в файле model или manifest.json. Например: 

**Model.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  В файле manifest.json формат даты и времени можно указать на уровне сущности или на уровне атрибута. На уровне сущности используйте «exhibitsTraits» в сущности в *.manifest.cdm.json, чтобы определить формат даты и времени. На уровне атрибута используйте «appliedTraits» в атрибуте в entityname.cdm.json.

**Manifest.json на уровне сущности**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**Entity.json на уровне атрибута**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]
