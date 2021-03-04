---
title: Сопоставление сущностей для унификации данных
description: Сопоставьте данные для создания унифицированных профилей клиентов.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 0088daae0be0cb3e71f87387648430d2353081c9
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267051"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="4c645-103">Сопоставление сущностей и атрибутов</span><span class="sxs-lookup"><span data-stu-id="4c645-103">Map entities and attributes</span></span>

<span data-ttu-id="4c645-104">**Сопоставление** — это первый этап процесса унификации данных аналитики аудитории.</span><span class="sxs-lookup"><span data-stu-id="4c645-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="4c645-105">Сопоставление состоит из трех этапов:</span><span class="sxs-lookup"><span data-stu-id="4c645-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="4c645-106">*Выбор сущностей*: определите комбинированные сущности, которые приводят к набору данных с более полной информацией о ваших клиентах.</span><span class="sxs-lookup"><span data-stu-id="4c645-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="4c645-107">*Выбор атрибутов*: для каждой сущности определите столбцы, которые вы хотите объединить и согласовать на этапах *соответствие* и *объединение*.</span><span class="sxs-lookup"><span data-stu-id="4c645-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="4c645-108">Эти столбцы называются *Атрибуты*.</span><span class="sxs-lookup"><span data-stu-id="4c645-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="4c645-109">*Выбор первичного ключа и семантического типа*: для каждой сущности определите атрибут, который вы хотите определить как первичный ключ для этой сущности, и для каждого атрибута определите семантический тип, который лучше всего описывает этот атрибут.</span><span class="sxs-lookup"><span data-stu-id="4c645-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="4c645-110">Для получения дополнительной информации об общем потоке объединения данных см. раздел [Объединить](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="4c645-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="4c645-111">Выбор первых сущностей</span><span class="sxs-lookup"><span data-stu-id="4c645-111">Select the first entities</span></span>

1. <span data-ttu-id="4c645-112">В аналитике аудитории перейдите **Данные** > **Унификация** > **Сопоставление**.</span><span class="sxs-lookup"><span data-stu-id="4c645-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="4c645-113">Начните этап сопоставления с выбора пункта **Выбрать сущности**.</span><span class="sxs-lookup"><span data-stu-id="4c645-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="4c645-114">Выберите сущности и атрибуты, которые вы хотите использовать на фазах *поиск совпадений* и *слияние*.</span><span class="sxs-lookup"><span data-stu-id="4c645-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="4c645-115">Вы можете выбрать требуемые атрибуты индивидуально из сущности или включить все атрибуты из сущности, установив флажок **Включить все поля** на уровне сущности.</span><span class="sxs-lookup"><span data-stu-id="4c645-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="4c645-116">Мы рекомендуем выбрать по крайней мере две сущности, чтобы извлечь выгоду из процесса унификации данных.</span><span class="sxs-lookup"><span data-stu-id="4c645-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4c645-117">![Пример добавления сущностей](media/data-manager-configure-map-add-entities-example.png "Пример добавления сущностей")</span><span class="sxs-lookup"><span data-stu-id="4c645-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="4c645-118">В этом примере мы добавляем сущности **eCommerceContacts** и **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="4c645-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="4c645-119">Выбирая эти сущности, вы можете получить представление о том, какие из бизнес-клиентов в Интернете являются участниками программы лояльности.</span><span class="sxs-lookup"><span data-stu-id="4c645-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="4c645-120">Вы можете выполнять поиск по ключевым словам по всем атрибутам и сущностям, чтобы выбрать необходимые атрибуты, которые вы хотите сопоставить.</span><span class="sxs-lookup"><span data-stu-id="4c645-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4c645-121">![Пример полей поиска](media/data-manager-configure-map-search-fields-example.png "Пример полей поиска")</span><span class="sxs-lookup"><span data-stu-id="4c645-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="4c645-122">Выберите **Применить**, чтобы подтвердить свой выбор.</span><span class="sxs-lookup"><span data-stu-id="4c645-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="4c645-123">Выбор первичного ключа и семантического типа для атрибутов</span><span class="sxs-lookup"><span data-stu-id="4c645-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="4c645-124">После выбора ваших сущностей на странице **Сопоставление** перечислены выбранные сущности для вашего обзора.</span><span class="sxs-lookup"><span data-stu-id="4c645-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="4c645-125">Определите первичный ключ для сущности и определите семантический тип для атрибута в сущности.</span><span class="sxs-lookup"><span data-stu-id="4c645-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="4c645-126">**Первичный ключ**: выберите один атрибут в качестве первичного ключа для каждой из ваших сущностей.</span><span class="sxs-lookup"><span data-stu-id="4c645-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="4c645-127">Чтобы атрибут был действительным первичным ключом, он не должен включать повторяющиеся значения, отсутствующие значения или значения NULL.</span><span class="sxs-lookup"><span data-stu-id="4c645-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="4c645-128">Атрибуты типа данных String, Integer и GUID поддерживаются в качестве первичных ключей и будут отображаться в поле для выбора.</span><span class="sxs-lookup"><span data-stu-id="4c645-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="4c645-129">**Семантический тип атрибута**: категории атрибутов, такие как адрес электронной почты или имя.</span><span class="sxs-lookup"><span data-stu-id="4c645-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="4c645-130">Чтобы использовать модели ИИ для интеллектуального прогноза семантики, сэкономить время и повысить точность, установите для параметра **Интеллектуальное сопоставление** значение **ВКЛ.**</span><span class="sxs-lookup"><span data-stu-id="4c645-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="4c645-131">Интеллектуальное сопоставление подчеркивает рекомендации по семантике на основе ИИ в поле **Тип**.</span><span class="sxs-lookup"><span data-stu-id="4c645-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="4c645-132">Если вы установите для него значение **ВЫКЛ.**, вы увидите наши обычные рекомендации по сопоставлению.</span><span class="sxs-lookup"><span data-stu-id="4c645-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="4c645-133">Вы можете выбрать любой семантический тип из доступного списка вариантов и переопределить предложенный выбор.</span><span class="sxs-lookup"><span data-stu-id="4c645-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4c645-134">![Тип атрибута и семантический прогноз](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Тип атрибута и семантический прогноз")</span><span class="sxs-lookup"><span data-stu-id="4c645-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="4c645-135">Также возможно добавление пользовательского семантического типа.</span><span class="sxs-lookup"><span data-stu-id="4c645-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="4c645-136">Выберите поле типа для атрибута и введите имя пользовательского семантического типа.</span><span class="sxs-lookup"><span data-stu-id="4c645-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="4c645-137">Таким образом можно также изменить типы атрибутов, которые были идентифицированы системой.</span><span class="sxs-lookup"><span data-stu-id="4c645-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="4c645-138">Все атрибуты, для которых автоматически определяется семантический тип, сгруппированы в разделе **Просмотр сопоставленных полей**.</span><span class="sxs-lookup"><span data-stu-id="4c645-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="4c645-139">Просмотрите эти атрибуты и их семантические типы, потому что они будут использоваться для объединения ваших сущностей на этапе слияния при объединении данных.</span><span class="sxs-lookup"><span data-stu-id="4c645-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="4c645-140">Атрибуты, которые не сопоставляются автоматически семантическому типу, группируются в разделе **Определите данные в несопоставленных полях**.</span><span class="sxs-lookup"><span data-stu-id="4c645-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="4c645-141">Выберите поле семантического типа для несопоставленных атрибутов или введите имя настраиваемого типа атрибута.</span><span class="sxs-lookup"><span data-stu-id="4c645-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4c645-142">![Первичный ключ и тип атрибута](media/data-manager-configure-map-add-attributes.png "Первичный ключ и тип атрибута")</span><span class="sxs-lookup"><span data-stu-id="4c645-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="4c645-143">Одно поле должно соответствовать семантическому типу Person.FullName для заполнения имени клиента в карточке клиента.</span><span class="sxs-lookup"><span data-stu-id="4c645-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="4c645-144">В противном случае карточки клиента будут отображаться безымянными.</span><span class="sxs-lookup"><span data-stu-id="4c645-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="4c645-145">Добавление и удаление атрибутов и сущностей</span><span class="sxs-lookup"><span data-stu-id="4c645-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="4c645-146">В разделе **Объединить** > **Сопоставить** выберите **Редактировать поля**.</span><span class="sxs-lookup"><span data-stu-id="4c645-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="4c645-147">В области **Редактировать поля** добавьте или удалите атрибуты и сущности.</span><span class="sxs-lookup"><span data-stu-id="4c645-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="4c645-148">Используйте поиск или прокрутите, чтобы найти и выбрать интересующие вас атрибуты и сущности.</span><span class="sxs-lookup"><span data-stu-id="4c645-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="4c645-149">Вы не можете удалить атрибут или сущность, если она уже была сопоставлена.</span><span class="sxs-lookup"><span data-stu-id="4c645-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4c645-150">![Добавление или удаление атрибутов](media/configure-data-map-edit.png "Добавление или удаление атрибутов")</span><span class="sxs-lookup"><span data-stu-id="4c645-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="4c645-151">Выберите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="4c645-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="4c645-152">Добавление изображений в профили</span><span class="sxs-lookup"><span data-stu-id="4c645-152">Add images to profiles</span></span>

<span data-ttu-id="4c645-153">Если сущность содержит URL-адреса общедоступных изображений или логотипов профилей, вы можете добавить их в единый профиль клиента.</span><span class="sxs-lookup"><span data-stu-id="4c645-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="4c645-154">Выберите сущность и найдите поле, содержащее URL-адрес изображения профиля.</span><span class="sxs-lookup"><span data-stu-id="4c645-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="4c645-155">В поле ввода **Тип** введите вручную следующее значение:</span><span class="sxs-lookup"><span data-stu-id="4c645-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="4c645-156">Для человека: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="4c645-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="4c645-157">Для организации: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="4c645-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="4c645-158">Продолжите шаги по объединению и убедитесь, что атрибут, содержащий URL-адрес изображения, также добавлен в шаг [Объединить](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="4c645-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="4c645-159">Задание атрибутов для организаций</span><span class="sxs-lookup"><span data-stu-id="4c645-159">Set attributes for organizations</span></span>

<span data-ttu-id="4c645-160">Для организаций (предварительная версия) тип атрибута должен быть сопоставлен атрибуту "Organization.Name"</span><span class="sxs-lookup"><span data-stu-id="4c645-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="4c645-161">![Первичный ключ и тип атрибута B2B](media/configure-data-map-edit-b2b.png "Первичный ключ и тип атрибута B2B")</span><span class="sxs-lookup"><span data-stu-id="4c645-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="4c645-162">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="4c645-162">Next step</span></span>

<span data-ttu-id="4c645-163">В рамках процесса объединения данных перейдите на страницу **Соответствие**.</span><span class="sxs-lookup"><span data-stu-id="4c645-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="4c645-164">Перейдите в раздел [**Соответствие**](match-entities.md), чтобы узнать об этом этапе.</span><span class="sxs-lookup"><span data-stu-id="4c645-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="4c645-165">Ознакомьтесь со следующим видео: [Начало работы. Создание единого профиля клиента](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="4c645-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]