---
title: Экспорт сегментов в Constant Contact (предварительная версия)
description: Узнайте, как настроить подключение и экспорт в Constant Contact.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c0affd3ed45f462696850813bd50331061dde780
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724517"
---
# <a name="export-segments-to-constant-contact-preview"></a>Экспорт сегментов в Constant Contact (предварительная версия)

Экспортируйте сегменты унифицированных профилей клиентов в Constant Contact и используйте их для маркетинговых действий.

## <a name="prerequisites"></a>Предварительные условия

- [Учетная запись Constant Contact](https://www.constantcontact.com/account-home) и соответствующие учетные данные администратора.
- [ИД списка Constant Contact](https://app.constantcontact.com/pages/contacts/ui#lists). Откройте список в Constant Contact, чтобы найти идентификатор списка в URL-адресе.
- [Настроенные сегменты](segments.md) в Customer Insights.
- Унифицированные профили клиентов в экспортированных сегментах содержат поле, представляющее адрес электронной почты.

## <a name="known-limitations"></a>Известные ограничения

- Приватный канал в сочетании с использованием собственного хранилища (BYOS) не поддерживается.
- До 1 млн профилей клиентов на экспорт в Constant Contact, что может занять до 1 часа. Количество профилей клиентов, которые вы можете экспортировать в Constant Contact, зависит от вашего контракта с Constant Contact.
- Только сегменты.

## <a name="set-up-connection-to-constant-contact"></a>Настройка подключения к Constant Contact

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Перейти в раздел **Администрирование** > **Подключения**.

1. Выберите **Добавить подключение** и выберите **Constant Contact**.

1. Дайте вашему подключению узнаваемое имя в поле **Отображаемое имя**. Имя и тип подключения описывают это подключение. Мы рекомендуем выбрать имя, которое объясняет назначение и цель подключения.

1. Укажите, кто может использовать это подключение. По умолчанию это только администраторы. Дополнительные сведения см. в разделе [Разрешение участникам использовать подключение для экспорта](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ознакомьтесь с положениями [Соответствие и конфиденциальность данных](connections.md#data-privacy-and-compliance) и выберите **Принимаю**.

1. Выберите **Подключиться** для инициализации подключения.

1. Выберите **Проверка подлинности в Constant Contact** и укажите свои учетные данные администратора для Constant Contact.

1. Выберите **Добавить себя в качестве пользователя экспорта** и предоставьте свои учетные данные Customer Insights.

1. Выберите **Сохранить**, чтобы завершить подключение.

## <a name="configure-an-export"></a>Настройка экспорта

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Перейдите в раздел **Данные** > **Экспорты**.

1. Выберите **Добавить экспорт**.

1. В поле **Подключение для экспорта** выберите подключение из раздела Constant Contact. Свяжитесь с администратором, если подключение недоступно.

1. Введите имя экспорта.

1. Введите свой **ИД списка Constant Contact**.

1. В разделе **Сопоставление данных** в поле **Эл. почта** выберите поле, которое представляет адрес электронной почты клиента.

1. По желанию экспортируйте **Имя** и **Фамилия** в качестве дополнительных полей для создания более персонализированных писем. Выберите **Добавить атрибут**, чтобы сопоставить эти поля.

1. Выберите сегменты, которые нужно экспортировать.

1. Выберите **Сохранить**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
