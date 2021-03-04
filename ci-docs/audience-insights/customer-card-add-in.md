---
title: Установка и настройка надстройки карточек клиентов
description: Установка и настройка надстройки карточек клиентов для Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268060"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="d5c1b-103">Надстройка карточек клиентов (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="d5c1b-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="d5c1b-104">Получите полный обзор своих клиентов прямо в приложениях Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="d5c1b-105">Просматривайте демографические данные, статистические данные и графики активности с помощью надстройки "Карточка клиента".</span><span class="sxs-lookup"><span data-stu-id="d5c1b-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d5c1b-106">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="d5c1b-106">Prerequisites</span></span>

- <span data-ttu-id="d5c1b-107">Приложение Dynamics 365 (например, центр продаж или центр обслуживания клиентов) версии 9.0 и более поздней с включенным единым интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="d5c1b-108">Профили клиентов [получены из приложения Dynamics 365 с использованием Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="d5c1b-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="d5c1b-109">Пользователи надстройки карточек клиентов должны быть [добавлены как пользователи](permissions.md) в аналитику аудитории.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="d5c1b-110">[Настроенные возможности поиска и фильтрации](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="d5c1b-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="d5c1b-111">Демографический контроль: демографические поля (такие как возраст или пол) доступны в едином профиле клиента.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="d5c1b-112">Контроль обогащения: требуется активное [обогащение](enrichment-hub.md), примененное к профилям клиентов.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="d5c1b-113">Интеллектуальное управление: требуются данные, созданные с помощью машинного обучения Azure ([прогнозы](predictions.md) или [пользовательские модели](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="d5c1b-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="d5c1b-114">Контроль мер: требуются [настроенные меры](measures.md).</span><span class="sxs-lookup"><span data-stu-id="d5c1b-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="d5c1b-115">Контроль временной шкалы: требуются [настроенные действия](activities.md).</span><span class="sxs-lookup"><span data-stu-id="d5c1b-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="d5c1b-116">Установка надстройки карточек клиентов</span><span class="sxs-lookup"><span data-stu-id="d5c1b-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="d5c1b-117">Надстройка карточки клиента — это решение для приложений Customer Engagement в Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="d5c1b-118">Чтобы установить решение, перейдите в AppSource и найдите **Карточка клиента Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="d5c1b-119">Выберите [Настройка карточек клиента в AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) и выберите **Получить**.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="d5c1b-120">Вам может потребоваться войти в систему с учетными данными администратора для приложения Dynamics 365, чтобы установить решение.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="d5c1b-121">Установка решения в вашей среде может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="d5c1b-122">Настройка надстройки карточки клиента</span><span class="sxs-lookup"><span data-stu-id="d5c1b-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="d5c1b-123">В качестве администратора перейдите в раздел **Настройки** в Dynamics 365 и выберите **Решения**.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="d5c1b-124">Выберите ссылку **Отображаемое имя** для решения **Надстройка карточки клиента Dynamics 365 Customer Insights (предварительная версия)**.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d5c1b-125">![Выберите отображаемое имя](media/select-display-name.png "Выберите отображаемое имя")</span><span class="sxs-lookup"><span data-stu-id="d5c1b-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="d5c1b-126">Выберите **Войти** и введите учетные данные для учетной записи администратора, которую вы используете для настройки Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d5c1b-127">Убедитесь, что блокировщик всплывающих окон браузера не блокирует окно аутентификации при выборе кнопки **Войти**.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="d5c1b-128">Выберите среду, из которой вы хотите получить данные.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="d5c1b-129">Определите сопоставление полей с записями в приложении Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="d5c1b-130">Для сопоставления с контактом выберите поле в сущности "Клиент", которое соответствует идентификатору сущности вашего контакта.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="d5c1b-131">Для сопоставления с учетной записью выберите поле в сущности "Клиент", которое соответствует идентификатору сущности вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d5c1b-132">![Поле идентификатора контакта](media/contact-id-field.png "Поле идентификатора контакта")</span><span class="sxs-lookup"><span data-stu-id="d5c1b-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="d5c1b-133">Выберите **Сохранить конфигурацию**, чтобы сохранить настройки.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="d5c1b-134">Затем необходимо назначить роли безопасности в Dynamics 365, чтобы пользователи могли настраивать и просматривать карточку клиента.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="d5c1b-135">В Dynamics 365 перейдите в раздел **Параметры** > **Безопасность** > **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="d5c1b-136">Выберите пользователей для редактирования ролей пользователей и выберите **Управление ролями**.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="d5c1b-137">Назначьте роль **Настройщик карточек Customer Insights** для пользователей, которые будут настраивать содержимое, отображаемое на карточке, для всей организации.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="d5c1b-138">Добавление элементов управления карточкой клиента в формы</span><span class="sxs-lookup"><span data-stu-id="d5c1b-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="d5c1b-139">Чтобы добавить элементы управления карточки клиента в свою форму контакта, перейдите к пункту **Параметры** > **Настройки** в Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="d5c1b-140">Выберите **Настройка системы**.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="d5c1b-141">Перейдите к сущности **Контакт**, разверните ее и выберите **Формы**.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="d5c1b-142">Выберите форму контакта, к которой вы хотите добавить элементы управления карточки клиента.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d5c1b-143">![Выберите форму контакта](media/contact-active-forms.png "Выберите форму контакта")</span><span class="sxs-lookup"><span data-stu-id="d5c1b-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="d5c1b-144">Чтобы добавить элемент управления, в редакторе форм перетащите любое поле из **Обозревателя полей** в место, где вы хотите разместить этот элемент управления.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="d5c1b-145">Выберите только что добавленное поле в форме, затем выберите **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="d5c1b-146">Перейдите на вкладку **Элементы управления** и выберите **Добавить элемент управления**.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="d5c1b-147">Выберите один из доступных пользовательских элементов управления и выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="d5c1b-148">В диалоговом окне **Свойства поля** снимите флажок **Отображать метку в форме**.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="d5c1b-149">Выберите параметр **Интернет** для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="d5c1b-150">Для элемента управления обогащением выберите тип обогащения, который вы хотите отобразить, настроив поле **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="d5c1b-151">Добавьте отдельный элемент управления обогащения для каждого типа обогащения.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="d5c1b-152">Выбрать **Сохранить** и **Опубликовать**, чтобы опубликовать обновленную форму контакта.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="d5c1b-153">Перейдите к опубликованной форме контакта.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-153">Go to the published contact form.</span></span> <span data-ttu-id="d5c1b-154">Вы увидите недавно добавленный элемент управления.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-154">You'll see the newly added control.</span></span> <span data-ttu-id="d5c1b-155">Возможно, вам придется войти в систему при первом использовании.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="d5c1b-156">Чтобы настроить то, что вы хотите отображаться в пользовательском элементе управления, выберите кнопку редактирования в правом верхнем углу.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="d5c1b-157">Обновление надстройки карточек клиентов</span><span class="sxs-lookup"><span data-stu-id="d5c1b-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="d5c1b-158">Надстройка карточки клиента не обновляется автоматически.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="d5c1b-159">Чтобы выполнить обновление до последней версии, выполните эту процедуру в приложении Dynamics 365, в котором установлена надстройка.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="d5c1b-160">В приложении Dynamics 365 перейдите **Параметры** > **Настройка** и выберите **Решения**.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="d5c1b-161">В таблице надстроек найдите **CustomerInsightsCustomerCard** и выберите строку.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="d5c1b-162">Выберите **Применить обновление решения** на панели действий.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Обновите решение в области настройки приложений Dynamics 365":::

1. <span data-ttu-id="d5c1b-164">После запуска процесса обновления будет показан индикатор загрузки, пока обновление не будет завершено.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="d5c1b-165">Если более новой версии нет, при обновлении будет отображаться сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="d5c1b-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]