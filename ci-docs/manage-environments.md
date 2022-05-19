---
title: Создание сред и управление ими
description: Узнайте, как зарегистрироваться для службы и как управлять средами.
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 599cbaf4e19c3a7331e92bfc54c701fefe6c69b3
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741057"
---
# <a name="manage-environments"></a>Управление средами

## <a name="switch-environments"></a>Переключить среды

Выберите элемент управления **Среда** в верхнем правом углу страницы для изменения сред.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Снимок экрана элемента управления для переключения сред.":::

Администраторы могут [создавать](create-environment.md) среды и управлять ими.

## <a name="edit-an-existing-environment"></a>Изменение существующей среды

Вы можете редактировать некоторые сведения существующих сред.

1.  Выберите **Среда** в заголовке приложения.

2.  Выберите значок **Правка**.

3. В поле **Редактировать среду** вы можете обновить настройки среды.

Дополнительные сведения о параметрах среды см. в разделе [Создание новой среды](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Подключиться к Microsoft Dataverse
   
На шаге **Microsoft Dataverse** можно связать Customer Insights с вашей средой Dataverse. 

Предоставьте свою собственную среду Microsoft Dataverse для обмена данными (профилями и аналитиками) с бизнес-приложениями на основе Dataverse, например Dynamics 365 Marketing или приложения на основе модели в Power Apps.

Чтобы использовать [готовые модели прогноза](predictions-overview.md#out-of-box-models), настройте обмен данными с Dataverse. Или вы можете включить прием данных из локальных источников данных, предоставив URL-адрес среды Microsoft Dataverse, которую администрирует ваша организация.

При включении обмена данными с Microsoft Dataverse путем установки флажка общего доступа к данным будет выполнено однократное полное обновление ваших источников данных и всех других процессов.

> [!IMPORTANT]
> 1. Для обмена данными Customer Insights и Dataverse должны находиться в одном регионе.
> 1. У вас должна быть глобальная роль администратора в среде Dataverse. Проверьте, [связана ли среда Dataverse](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) с определенными группами безопасности, и убедитесь, что вы добавлены в эти группы безопасности.
> 1. Никакая существующая среда Customer Insights еще не связана с этой средой Dataverse. Узнайте, как [удалить существующее подключение к среде Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Параметры конфигурации для включения обмена данными с Microsoft Dataverse.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Включить обмен данными с Dataverse из собственного Azure Data Lake Storage (предварительная версия)

Если ваша среда настроена на использование собственного Azure Data Lake Storage для хранения данных Customer Insights, для включения обмена данными с Microsoft Dataverse требуется дополнительная настройка.

1. Создайте две группы безопасности в своей подписке Azure — одну группу безопасности **Читатель** и одну группу безопасности **Участник** и задайте службу Microsoft Dataverse в качестве владельца обеих групп безопасности.
2. Управляйте списком управления доступом (ACL) в контейнере CustomerInsights в своей учетной записи хранения с помощью этих групп безопасности. Добавьте службу Microsoft Dataverse и любые бизнес-приложения на основе Dataverse, такие как Dynamics 365 Marketing, в группу безопасности **Читатель** с разрешениями **только для чтения**. Добавьте *только* приложение Customers Insights для группы безопасности **Участник** для предоставления разрешений на **чтение и запись**, чтобы записывать профили и аналитику.
   
#### <a name="prerequisites"></a>Предварительные условия

Для выполнения сценариев PowerShell вам необходимо импортировать следующие три модуля. 

1. Установите последнюю версию [Azure Active Directory PowerShell для Graph](/powershell/azure/active-directory/install-adv2).
   1. На ПК нажмите клавишу Windows на клавиатуре и выполните поиск **Windows PowerShell**, затем выберите **Запуск от имени администратора**.
   1. В открывшемся окне PowerShell введите `Install-Module AzureAD`.
2. Импортируйте три модуля.
    1. В окне Powershell введите `Install-Module -Name Az.Accounts` и выполните следующее. 
    1. Повторите для `Install-Module -Name Az.Resources` и `Install-Module -Name Az.Storage`.

#### <a name="configuration-steps"></a>Шаги настройки

1. Загрузите два сценария PowerShell, которые вам нужно запустить, из [репозитория GitHub](https://github.com/trin-msft/byol) нашего специалиста.
    1. `CreateSecurityGroups.ps1`
       - Чтобы выполнит этот сценарий PowerShell, требуются разрешения *администратора клиента*. 
       - Этот сценарий PowerShell создает две группы безопасности в вашей подписке Azure. Один для группы Читатель, а другой для группы Участник и делает службу Microsoft Dataverse владельцем обеих этих групп безопасности.
       - Выполните этот сценарий PowerShell в Windows PowerShell, указав идентификатор подписки Azure, содержащий ваш Azure Data Lake Storage. Откройте сценарий PowerShell в редакторе, чтобы просмотреть дополнительную информацию и реализованную логику.
       - Сохраните оба значения ID группы безопасности, сгенерированные этим сценарием, потому что мы будем использовать их в сценарии `ByolSetup.ps1`.
       
        > [!NOTE]
        > Создание группы безопасности можно отключить в вашем клиенте. В этом случае потребуется ручная настройка, и ваш администратор Azure AD должен был [включить создание групп безопасности](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Вам нужны разрешения *Владелец данных BLOB-объектов хранилища* на уровне учетной записи хранения/контейнера для запуска этого сценария или этот сценарий создаст его для вас. Ваше назначение роли может быть удалено вручную после успешного запуска сценария.
        - Этот сценарий PowerShell добавляет необходимое управление доступом на основе ролей (RBAC) для службы Microsoft Dataverse и любых бизнес-приложений на основе Dataverse. Это также обновляет список управления доступом (ACL) в контейнере CustomerInsights для групп безопасности, созданных с помощью сценария `CreateSecurityGroups.ps1`. Группа Участник будет иметь разрешение *rwx*, а группа Читатели будут иметь только разрешение *r-x*.
        - Выполните этот сценарий PowerShell в Windows PowerShell, указав идентификатор подписки Azure, содержащий ваш Azure Data Lake Storage, имя учетной записи хранения, имя группы ресурсов и значения идентификаторов группы безопасности Читатель и Участник. Откройте сценарий PowerShell в редакторе, чтобы просмотреть дополнительную информацию и реализованную логику.
        - Скопируйте выходную строку после успешного запуска сценария. Выходная строка выглядит следующим образом: `https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. Введите выходную строку, скопированную вверху, в поле **Идентификатор разрешений** на шаге настройки среды для Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Параметры конфигурации, позволяющие включить обмен данными с вашими собственными Azure Data Lake Storage с Microsoft Dataverse.":::

Конфигурация Customer Insights не поддерживает следующие сценарии передачи данных:
- Если вы включите обмен данными с Dataverse, вы не сможете [создавать прогнозируемые или отсутствующие значения в сущности](predictions.md).
- Если вы включите обмен данными с Dataverse, вы не сможете просматривать дополнительные отчеты PowerBI Embedded в своей среде Customer Insights.

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Удаление существующего подключения к среде Dataverse

При подключении к среде Dataverse сообщение об ошибке **Эта организация CDS уже подключена к другому экземпляру Customer Insights** означает, что среда Dataverse уже используется в среде Customer Insights. Вы можете удалить существующее соединение как глобальный администратор в среде Dataverse. Внесение изменений может занять несколько часов.

1. Перейдите к [Power Apps](https://make.powerapps.com).
1. Выберите среду из средства выбора сред.
1. Перейдите в **Решения**
1. Удалите решение с именем **Надстройка карточек клиентов Dynamics 365 Customer Insights (предварительная версия)**.

ИЛИ 

1. Откройте свою среду Dataverse.
1. Перейдите в раздел **Дополнительные параметры** > **Решения**.
1. Удалите решение **CustomerInsightsCustomerCard**.

## <a name="copy-the-environment-configuration"></a>Копирование конфигурации среды

Как администратор вы можете скопировать конфигурацию из существующей среды при создании новой. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Снимок экрана с параметрами настроек в параметрах среды.":::

Вы увидите список всех доступных сред в вашей организации, откуда вы можете копировать данные.

Копируются следующие параметры конфигурации:

- Полученные/импортированные источники данных
- Конфигурация объединения данных
- Segments
- Меры (Measures)
- Связи
- Процедуры
- Индекс поиска и фильтра
- Пункты назначения экспорта
- Запланированное обновление
- Обогащения
- Управление моделями
- Назначения ролей

## <a name="set-up-a-copied-environment"></a>Настройка скопированной среды

Когда вы копируете конфигурацию среды, следующие данные *не* копируются:

- Профили клиентов.
- Учетные данные источника данных. Вам нужно будет предоставить учетные данные для каждого источник данных и обновить источники данных вручную.
- Источники данных из папки Common Data Model и управляемое Dataverse озеро данных Data Lake. Вам нужно будет создать эти источники данных вручную с тем же именем, что и в исходной среде.
- Секреты подключения, которые используются для экспорта и обогащений. Вы должны повторно аутентифицировать соединения, а затем повторно активировать обогащения и экспорт. 

При копировании среды вы увидите подтверждающее сообщение о том, что новая среда была создана. Выберите **Перейти к источникам данных**, чтобы увидеть список источников данных.

Все источники данных покажут состояние **Требуются учетные данные**. Отредактируйте источники данных и введите учетные данные, чтобы обновить их.

:::image type="content" source="media/data-sources-copied.png" alt-text="Список источников данных, которые были скопированы и нуждаются в аутентификации.":::

После обновления источников данных перейдите к **Данные** > **Унификация**. Здесь вы найдете параметры из исходной среды. Отредактируйте их по мере необходимости или выберите **Запустить**, чтобы начать процесс унификации данных и создать единую сущность клиента.

Когда унификация данных будет завершена, перейдите к пунктам **Меры** и **Сегменты**, чтобы обновить их тоже.

Перед повторной активацией экспорта и обогащений перейдите в **Администратор** > **Подключения** для повторной аутентификации подключений в новой среде.

## <a name="change-the-owner-of-an-environment"></a>Изменить владельца среды

Хотя права администратора в Customer Insights могут быть у нескольких пользователей, только один пользователь является владельцем среды. По умолчанию изначально среду создает администратор. Как администратор среды, вы можете передать право собственности другому пользователю с правами администратора.

1. Выберите **Среда** в заголовке приложения.

1. Выберите значок **Правка**.

1. В поле **Изменить среду** перейдите к шагу **Основная информация**.

1. В поле **Изменить владельца среды** выберите нового владельца среды.  

1. Выберите **Просмотреть и завершить**, затем **Обновить**, чтобы применить изменения. 

## <a name="claim-ownership-of-an-environment"></a>Заявить права на владение средой

Если владелец среды покинет организацию или его учетная запись пользователя будет удалена, у среды не будет владельца. Пользователь с правами администратора может заявить права собственности и стать новым владельцем. Они могут продолжать владеть средой или [изменить право собственности на другого администратора](#change-the-owner-of-an-environment). 

Чтобы заявить право собственности, выберите кнопку **Стать владельцем**, которая отображается в верхней части каждой страницы Customer Insights, когда первоначальный владелец покинул организацию.

## <a name="reset-an-existing-environment"></a>Сбросить существующую среду

Как владелец среды, вы можете сбросить среду до пустого состояния, если хотите удалить все конфигурации и импортированные данные.

1.  Выберите **Среда** в заголовке приложения. 

2.  Выберите среду, которую вы хотите сбросить, и выберите многоточие (**...**). 

3. Выберите вариант **Сбросить**. 

4.  Чтобы подтвердить удаление, введите имя среды и выберите **Сброс**.

## <a name="delete-an-existing-environment"></a>Удаление существующей среды

Как владелец среды, вы можете удалить среду, администрируемую вами.

1.  Выберите **Среда** в заголовке приложения.

2.  Выберите среду, которую вы хотите сбросить, и выберите многоточие (**...**). 

3. Выберите вариант **Удалить**. 

4.  Чтобы подтвердить удаление, введите имя среды и выберите **Удалить**.

> [!NOTE]
> Удаление среды не удаляет связь со средой Dataverse. Узнайте, как [удалить существующее подключение к среде Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).


[!INCLUDE [footer-include](includes/footer-banner.md)]