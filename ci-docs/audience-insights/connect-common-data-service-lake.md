---
title: Подключение к объектам в управляемом озере Common Data Service
description: Импортируйте данные из управляемого Data Lake Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 18b6cd3fdaf5b738877a73b520b91dbc6ded40de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267830"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Подключение к данным в озере данных, управляемом Common Data Service

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

В этой статье представлена информация о том, как существующие клиенты Dynamics 365 могут быстро подключиться к своим аналитическим сущностям в управляемом озере Common Data Service. Вы должны быть администратором организации Common Data Service, чтобы продолжить и просмотреть список сущностей, доступных в управляемом озере.

## <a name="important-considerations"></a>Важные замечания

Данные, хранящиеся в онлайн-сервисах, например Azure Data Lake Storage, могут храниться в другом месте, отличном от места, где данные обрабатываются или хранятся в Dynamics 365 Customer Insights. Импортируя данные или подключаясь к данным, хранящимся в онлайн-сервисах, вы соглашаетесь с тем, что данные могут быть переданы и сохранены в Dynamics 365 Customer Insights.  [Подробнее см. в центре обеспечения безопасности Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Подключение к озеру, управляемому Common Data Service

1. В аналитике аудитории перейдите **Данные** > **Источники данных**.

2. Выберите **Добавить источник данных**.

3. Выберите **Подключиться к Common Data Service** и выберите **Далее**.

4. Введите **Имя** для источника данных, затем выберите **Далее**. Рекомендации по названию: 
   - Начните с буквы.
   - Используйте только буквы и цифры. Использовать специальные символы и пробелы не разрешается.
   - Используйте от 3 до 64 символов.

5. Укажите **Адрес сервера** для вашей организации Common Data Service и выберите **Войти**.

   > [!div class="mx-imgBorder"]
   > ![Диалоговое окно для ввода адреса сервера Common Data Service](media/enter-CDS-org-details.png)

6. Выберите сущности, которые нужно принимать, в доступном списке.    

   > [!NOTE]
   > Если некоторые сущности уже выбраны, они могут использоваться другими приложениями Dynamics 365 (например, Dynamics 365 Sales Insights или Customer Service Insights). Вы не можете изменить выбор. Эти сущности будут доступны после создания источника данных.

   > [!div class="mx-imgBorder"]
   > ![Диалоговое окно со списком сущностей в организации Common Data Service](media/select-analytical-entities.png)

7. Сохраните свой выбор, чтобы начать синхронизацию выбранных сущностей с озером, управляемым Common Data Service. Вы найдете недавно добавленное соединение на странице **Источники данных**. Оно будет поставлено в очередь для обновления и покажет количество сущностей равным 0, пока все сущности не будут синхронизированы.

Только один источник данных среды может одновременно использовать это и то же управляемое озеро Common Data Service.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Изменение источника данных озера, управляемого Common Data Service

Вы редактируете выбор сущности только после создания источника данных. Например, если дополнительные сущности были добавлены в Common Data Service и вы тоже хотите их импортировать.    
Чтобы подключиться к другому Common Data Service, [создайте новый источник данных](#connect-to-a-common-data-service-managed-lake).

1. В аналитике аудитории перейдите **Данные** > **Источники данных**.

2. Рядом с источником данных, который вы хотите обновить, выберите многоточие.

3. Выберите вариант **Изменить** из списка.

4. Выберите дополнительные сущности из доступного списка сущностей и выберите **Сохранить**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]