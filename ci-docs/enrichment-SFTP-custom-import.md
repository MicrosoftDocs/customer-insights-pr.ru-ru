---
title: Обогащение профилей клиентов с помощью настраиваемого импорта SFTP (предварительная версия)
description: Общие сведения об обогащении настраиваемого импорта SFTP.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 831d1d3d3045379bbc5bcdcd4b05b8a147221f31
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237782"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>Обогащение профилей клиентов с помощью настраиваемого импорта SFTP (предварительная версия)

Настраиваемый импорт протокола SFTP позволяет импортировать данные, которые не должны проходить процесс объединения данных. Это гибкий, безопасный и простой способ ввода ваших данных. Настраиваемый импорт SFTP можно использовать в сочетании с [экспортом SFTP](export-sftp.md), что позволяет экспортировать данные профилей клиентов, необходимые для обогащения. Затем данные могут быть обработаны и обогащены, а настраиваемый импорт SFTP может использоваться для возврата обогащенных данных обратно в Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Предварительные условия

- Имя файла и расположение (путь) файла, который необходимо импортировать на узел SFTP, известны.

- Доступен файл *model.json*, в котором указана схема Common Data Model для импортируемых данных. Этот файл должен находиться в том же каталоге, что и импортируемый файл.

- [Подключение](connections.md) SFTP [настроено](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Пример схемы файла

Каталог, содержащий файл для импорта на сервере SFTP, также должен содержать файл *model.json*. Этот файл определяет схему, используемую для импорта данных. Схема должна использовать [Common Data Model](/common-data-model/), чтобы указать сопоставление полей. Простой пример файла model.json выглядит так:

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="configure-the-connection-for-sftp-custom-import"></a>Настройка подключения для пользовательского импорта по протоколу SFTP

Вы должны быть [администратором](permissions.md#admin) в Customer Insights и иметь учетные данные пользователя, URL-адрес и номер порта для местоположения SFTP, из которого вы хотите импортировать данные.

1. Выберите **Добавить подключение** при настройке обогащения или перейдите в раздел **Администрирование** > **Подключения** и выберите **Настроить** на плитке пользовательского импорта.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Страница настройки соединения пользовательского импорта.":::

1. Введите имя для подключения.

1. Введите действительное имя пользователя, пароль и URL-адрес узла для SFTP-сервера, на котором находятся импортируемые данные.

1. Ознакомьтесь с положениями [Соответствие и конфиденциальность данных](connections.md#data-privacy-and-compliance) и выберите **Принимаю**.

1. Выберите **Проверить** для проверки конфигурации, затем выберите **Сохранить**.

## <a name="configure-the-import"></a>Настройка импорта

1. Перейдите в раздел **Данные** > **Обогащение** и выберите вкладку **Обнаружить**.

1. Выберите **Обогатить мои данные** на плитке **Пользовательский импорт по протоколу SFTP**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Плитка настраиваемого импорта SFTP.":::

1. Просмотрите обзор и выберите **Далее**.

1. Выберите подключение. Свяжитесь с администратором, если подключение недоступно.

1. Выберите **Набор данных клиентов** и выберите профиль или сегмент, который требуется обогатить. Сущность *Клиент* обогащает все ваши профили клиентов, в том время как сегмент обогащает только профили клиентов, содержащиеся в этом сегменте.

1. Выберите **Далее**.

1. Введите **Путь** и **Имя файла** для файла данных, который вы хотите импортировать.

1. Выберите **Далее**.

1. Укажите **Имя** для обогащения и **Имя выходной сущности**.

1. Выберите **Сохранить обогащение** после просмотра вашего выбора.

1. Выберите **Выполнить**, чтобы начать процесс обогащения, или закройте, чтобы вернуться на страницу **Обогащения**.

## <a name="view-enrichment-results"></a>Просмотр результатов обогащения

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Следующие шаги

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
