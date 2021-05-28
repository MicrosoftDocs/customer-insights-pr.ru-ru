---
title: Надстройка карточек клиентов для приложений Dynamics 365
description: Отображайте данные из аналитики аудитории в приложениях Dynamics 365 с помощью этой надстройки.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059604"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="b38ef-103">Надстройка карточек клиентов (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="b38ef-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="b38ef-104">Получите полный обзор своих клиентов прямо в приложениях Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="b38ef-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="b38ef-105">Установив надстройку карточек клиентов в поддерживаемом приложении Dynamics 365, вы можете выбрать отображение демографических данных, аналитических данных и временных шкал действий.</span><span class="sxs-lookup"><span data-stu-id="b38ef-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="b38ef-106">Надстройка будет извлекать данные из Customer Insights, не влияя на данные в подключенном приложении Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="b38ef-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="b38ef-107">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="b38ef-107">Prerequisites</span></span>

- <span data-ttu-id="b38ef-108">Надстройка работает только с приложениями на основе модели Dynamics 365, такими как Sales или Customer Service версии 9.0 и новее.</span><span class="sxs-lookup"><span data-stu-id="b38ef-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="b38ef-109">Чтобы ваши данные Dynamics 365 сопоставлялись профилям клиентов в аналитике аудитории, они должны быть [приняты из приложения Dynamics 365 с помощью соединителя Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="b38ef-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="b38ef-110">Все пользователи Dynamics 365 надстройки карточки клиента должны быть [добавлены как пользователи](permissions.md) в аналитике аудитории, чтобы видеть данные.</span><span class="sxs-lookup"><span data-stu-id="b38ef-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="b38ef-111">[Настроенные возможности поиска и фильтрации](search-filter-index.md) в аналитике аудитории необходимы для работы подстановки данных.</span><span class="sxs-lookup"><span data-stu-id="b38ef-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="b38ef-112">Каждый элемент управления надстройки основан на определенных данных в аналитике аудитории:</span><span class="sxs-lookup"><span data-stu-id="b38ef-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="b38ef-113">Контроль мер: требуются [настроенные меры](measures.md).</span><span class="sxs-lookup"><span data-stu-id="b38ef-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="b38ef-114">Интеллектуальный контроль: требуются данные, созданные с использованием [прогнозов](predictions.md) или [пользовательских моделей](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="b38ef-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="b38ef-115">Демографический контроль: демографические поля (такие как возраст или пол) доступны в едином профиле клиента.</span><span class="sxs-lookup"><span data-stu-id="b38ef-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="b38ef-116">Контроль обогащения: требуется активное [обогащение](enrichment-hub.md), примененное к профилям клиентов.</span><span class="sxs-lookup"><span data-stu-id="b38ef-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="b38ef-117">Контроль временной шкалы: требуются [настроенные действия](activities.md).</span><span class="sxs-lookup"><span data-stu-id="b38ef-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="b38ef-118">Установка надстройки карточек клиентов</span><span class="sxs-lookup"><span data-stu-id="b38ef-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="b38ef-119">Надстройка карточки клиента — это решение для приложений Customer Engagement в Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="b38ef-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="b38ef-120">Чтобы установить решение, перейдите в AppSource и найдите **Карточка клиента Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="b38ef-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="b38ef-121">Выберите [Настройка карточек клиента в AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) и выберите **Получить**.</span><span class="sxs-lookup"><span data-stu-id="b38ef-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="b38ef-122">Вам может потребоваться войти в систему с учетными данными администратора для приложения Dynamics 365, чтобы установить решение.</span><span class="sxs-lookup"><span data-stu-id="b38ef-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="b38ef-123">Установка решения в вашей среде может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="b38ef-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="b38ef-124">Настройка надстройки карточки клиента</span><span class="sxs-lookup"><span data-stu-id="b38ef-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="b38ef-125">В качестве администратора перейдите в раздел **Настройки** в Dynamics 365 и выберите **Решения**.</span><span class="sxs-lookup"><span data-stu-id="b38ef-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="b38ef-126">Выберите ссылку **Отображаемое имя** для решения **Надстройка карточки клиента Dynamics 365 Customer Insights (предварительная версия)**.</span><span class="sxs-lookup"><span data-stu-id="b38ef-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b38ef-127">![Выберите отображаемое имя](media/select-display-name.png "Выберите отображаемое имя")</span><span class="sxs-lookup"><span data-stu-id="b38ef-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="b38ef-128">Выберите **Войти** и введите учетные данные для учетной записи администратора, которую вы используете для настройки Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b38ef-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b38ef-129">Убедитесь, что блокировщик всплывающих окон браузера не блокирует окно аутентификации при выборе кнопки **Войти**.</span><span class="sxs-lookup"><span data-stu-id="b38ef-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="b38ef-130">Выберите среду Customer Insights, из которой вы хотите получить данные.</span><span class="sxs-lookup"><span data-stu-id="b38ef-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="b38ef-131">Определите сопоставление полей с записями в приложении Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="b38ef-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="b38ef-132">В зависимости от ваших данных в Customer Insights вы можете выбрать отображение следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="b38ef-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="b38ef-133">Для сопоставления с контактом выберите поле в сущности "Клиент", которое соответствует идентификатору сущности вашего контакта.</span><span class="sxs-lookup"><span data-stu-id="b38ef-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="b38ef-134">Для сопоставления с учетной записью выберите поле в сущности "Клиент", которое соответствует идентификатору сущности вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="b38ef-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b38ef-135">![Поле идентификатора контакта](media/contact-id-field.png "Поле идентификатора контакта")</span><span class="sxs-lookup"><span data-stu-id="b38ef-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="b38ef-136">Выберите **Сохранить конфигурацию**, чтобы сохранить настройки.</span><span class="sxs-lookup"><span data-stu-id="b38ef-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="b38ef-137">Затем необходимо назначить роли безопасности в Dynamics 365, чтобы пользователи могли настраивать и просматривать карточку клиента.</span><span class="sxs-lookup"><span data-stu-id="b38ef-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="b38ef-138">В Dynamics 365 перейдите в раздел **Параметры** > **Безопасность** > **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="b38ef-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="b38ef-139">Выберите пользователей для редактирования ролей пользователей и выберите **Управление ролями**.</span><span class="sxs-lookup"><span data-stu-id="b38ef-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="b38ef-140">Назначьте роль **Настройщик карточек Customer Insights** для пользователей, которые будут настраивать содержимое, отображаемое на карточке, для всей организации.</span><span class="sxs-lookup"><span data-stu-id="b38ef-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="b38ef-141">Добавление элементов управления карточкой клиента в формы</span><span class="sxs-lookup"><span data-stu-id="b38ef-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="b38ef-142">Чтобы добавить элементы управления карточки клиента в свою форму контакта, перейдите к пункту **Параметры** > **Настройки** в Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="b38ef-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="b38ef-143">Выберите **Настройка системы**.</span><span class="sxs-lookup"><span data-stu-id="b38ef-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="b38ef-144">Перейдите к сущности **Контакт**, разверните ее и выберите **Формы**.</span><span class="sxs-lookup"><span data-stu-id="b38ef-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="b38ef-145">Выберите форму контакта, к которой вы хотите добавить элементы управления карточки клиента.</span><span class="sxs-lookup"><span data-stu-id="b38ef-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b38ef-146">![Выберите форму контакта](media/contact-active-forms.png "Выберите форму контакта")</span><span class="sxs-lookup"><span data-stu-id="b38ef-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="b38ef-147">Чтобы добавить элемент управления, в редакторе форм перетащите любое поле из **Обозревателя полей** в место, где вы хотите разместить этот элемент управления.</span><span class="sxs-lookup"><span data-stu-id="b38ef-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="b38ef-148">Выберите только что добавленное поле в форме, затем выберите **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="b38ef-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="b38ef-149">Перейдите на вкладку **Элементы управления** и выберите **Добавить элемент управления**.</span><span class="sxs-lookup"><span data-stu-id="b38ef-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="b38ef-150">Выберите один из доступных пользовательских элементов управления и выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b38ef-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="b38ef-151">В диалоговом окне **Свойства поля** снимите флажок **Отображать метку в форме**.</span><span class="sxs-lookup"><span data-stu-id="b38ef-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="b38ef-152">Выберите параметр **Интернет** для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b38ef-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="b38ef-153">Для элемента управления обогащением выберите тип обогащения, который вы хотите отобразить, настроив поле **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="b38ef-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="b38ef-154">Добавьте отдельный элемент управления обогащения для каждого типа обогащения.</span><span class="sxs-lookup"><span data-stu-id="b38ef-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="b38ef-155">Выбрать **Сохранить** и **Опубликовать**, чтобы опубликовать обновленную форму контакта.</span><span class="sxs-lookup"><span data-stu-id="b38ef-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="b38ef-156">Перейдите к опубликованной форме контакта.</span><span class="sxs-lookup"><span data-stu-id="b38ef-156">Go to the published contact form.</span></span> <span data-ttu-id="b38ef-157">Вы увидите недавно добавленный элемент управления.</span><span class="sxs-lookup"><span data-stu-id="b38ef-157">You'll see the newly added control.</span></span> <span data-ttu-id="b38ef-158">Возможно, вам придется войти в систему при первом использовании.</span><span class="sxs-lookup"><span data-stu-id="b38ef-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="b38ef-159">Чтобы настроить то, что вы хотите отображаться в пользовательском элементе управления, выберите кнопку редактирования в правом верхнем углу.</span><span class="sxs-lookup"><span data-stu-id="b38ef-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="b38ef-160">Обновление надстройки карточек клиентов</span><span class="sxs-lookup"><span data-stu-id="b38ef-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="b38ef-161">Надстройка карточки клиента не обновляется автоматически.</span><span class="sxs-lookup"><span data-stu-id="b38ef-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="b38ef-162">Чтобы выполнить обновление до последней версии, выполните эту процедуру в приложении Dynamics 365, в котором установлена надстройка.</span><span class="sxs-lookup"><span data-stu-id="b38ef-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="b38ef-163">В приложении Dynamics 365 перейдите **Параметры** > **Настройка** и выберите **Решения**.</span><span class="sxs-lookup"><span data-stu-id="b38ef-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="b38ef-164">В таблице надстроек найдите **CustomerInsightsCustomerCard** и выберите строку.</span><span class="sxs-lookup"><span data-stu-id="b38ef-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="b38ef-165">Выберите **Применить обновление решения** на панели действий.</span><span class="sxs-lookup"><span data-stu-id="b38ef-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Обновите решение в области настройки приложений Dynamics 365":::

1. <span data-ttu-id="b38ef-167">После запуска процесса обновления будет показан индикатор загрузки, пока обновление не будет завершено.</span><span class="sxs-lookup"><span data-stu-id="b38ef-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="b38ef-168">Если более новой версии нет, при обновлении будет отображаться сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="b38ef-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
