---
title: Отношения между сущностями и путями сущностей
description: Создавайте и управляйте отношениями между сущностями из нескольких источников данных.
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595228"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="ef188-103">Отношения между сущностями</span><span class="sxs-lookup"><span data-stu-id="ef188-103">Relationships between entities</span></span>

<span data-ttu-id="ef188-104">Отношения помогает связывать сущности и генерировать график ваших данных, когда сущности имеют общий идентификатор (внешний ключ), с помощью которого можно ссылаться из одной сущности на другую.</span><span class="sxs-lookup"><span data-stu-id="ef188-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="ef188-105">Связанные сущности позволяют определять сегменты и меры на основе нескольких источников данных.</span><span class="sxs-lookup"><span data-stu-id="ef188-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="ef188-106">Существует два типа отношений.</span><span class="sxs-lookup"><span data-stu-id="ef188-106">There are two types of relationships.</span></span> <span data-ttu-id="ef188-107">Недоступные для редактирования системные отношения, которые создаются автоматически, и пользовательские отношения, создаваемые и настраиваемые пользователями.</span><span class="sxs-lookup"><span data-stu-id="ef188-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="ef188-108">Во время процессов поиска соответствия и слияния системные отношения создаются за кулисами на основе интеллектуального сопоставления.</span><span class="sxs-lookup"><span data-stu-id="ef188-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="ef188-109">Эти отношения помогают связать записи профиля клиента с записями других соответствующих сущностей.</span><span class="sxs-lookup"><span data-stu-id="ef188-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="ef188-110">Следующая диаграмма иллюстрирует создание трех системных отношений, когда сущность клиента сопоставляется с дополнительными сущностями для создания конечной сущности профиля клиента.</span><span class="sxs-lookup"><span data-stu-id="ef188-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ef188-111">![Создание отношения](media/relationships-entities-merge.png "Создание отношения")</span><span class="sxs-lookup"><span data-stu-id="ef188-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="ef188-112">**Отношение *CustomerToContact*** было создан между сущностью «Клиент» и сущностью «Контакт».</span><span class="sxs-lookup"><span data-stu-id="ef188-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="ef188-113">Сущность клиента получает ключевое поле **Contact_contactId** для связи с ключевым полем сущности контакта **ContactId**.</span><span class="sxs-lookup"><span data-stu-id="ef188-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="ef188-114">**Отношение *CustomerToAccount*** было создан между сущностью «Клиент» и сущностью «Организация».</span><span class="sxs-lookup"><span data-stu-id="ef188-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="ef188-115">Сущность клиента получает ключевое поле **Account_accountId** для связи с ключевым полем сущности организации **accountId**.</span><span class="sxs-lookup"><span data-stu-id="ef188-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="ef188-116">**Отношение *CustomerToWebAccount*** было создан между сущностью «Клиент» и сущностью «WebAccount».</span><span class="sxs-lookup"><span data-stu-id="ef188-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="ef188-117">Сущность клиента получает ключевое поле **WebAccount_webaccountId** для связи с ключевым полем сущности WebAccount **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="ef188-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="ef188-118">Создание отношения</span><span class="sxs-lookup"><span data-stu-id="ef188-118">Create a relationship</span></span>

<span data-ttu-id="ef188-119">Определите пользовательские отношения на странице **Отношения**.</span><span class="sxs-lookup"><span data-stu-id="ef188-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="ef188-120">Каждое отношение состоит из исходной сущности (сущности, которая содержит внешний ключ) и целевой сущности (сущности, на которую указывает внешний ключ исходной сущности).</span><span class="sxs-lookup"><span data-stu-id="ef188-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="ef188-121">В аналитике аудитории перейдите **Данные** > **Отношения**.</span><span class="sxs-lookup"><span data-stu-id="ef188-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="ef188-122">Выберите **Создать отношение**.</span><span class="sxs-lookup"><span data-stu-id="ef188-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="ef188-123">В области **Добавить отношение** укажите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="ef188-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ef188-124">![Ввод сведений об отношении](media/relationships-add.png "Ввод сведений об отношении")</span><span class="sxs-lookup"><span data-stu-id="ef188-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="ef188-125">**Имя отношения**: имя, которое отражает цель отношения (например, **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="ef188-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="ef188-126">**Описание**: описание отношения.</span><span class="sxs-lookup"><span data-stu-id="ef188-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="ef188-127">**Исходная сущность**: выберите сущность, которая используется в качестве источника в отношении (например, WebLog).</span><span class="sxs-lookup"><span data-stu-id="ef188-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="ef188-128">**Кратность**: выберите кратность записей исходной сущности.</span><span class="sxs-lookup"><span data-stu-id="ef188-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="ef188-129">Например, "много" означает, что несколько записей Weblog связаны с одной записью WebAccount.</span><span class="sxs-lookup"><span data-stu-id="ef188-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="ef188-130">**Исходное ключевое поле**: представляет поле внешнего ключа в исходной сущности.</span><span class="sxs-lookup"><span data-stu-id="ef188-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="ef188-131">Например, WebLog имеет поле внешнего ключа **accountId**.</span><span class="sxs-lookup"><span data-stu-id="ef188-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="ef188-132">**Целевая сущность**: выберите сущность, которая используется в качестве цели в отношении (например, WebAccount).</span><span class="sxs-lookup"><span data-stu-id="ef188-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="ef188-133">**Кратность целевого объекта**: выберите кратность записей целевой сущности.</span><span class="sxs-lookup"><span data-stu-id="ef188-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="ef188-134">Например, "один" означает, что несколько записей Weblog связаны с одной записью WebAccount.</span><span class="sxs-lookup"><span data-stu-id="ef188-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="ef188-135">**Целевое ключевое поле**: это поле представляет ключевое поле целевой сущности.</span><span class="sxs-lookup"><span data-stu-id="ef188-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="ef188-136">Например, WebAccount имеет ключевое поле **accountId**.</span><span class="sxs-lookup"><span data-stu-id="ef188-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="ef188-137">Поддерживаются только отношения многие-к-одному и один-к-одному.</span><span class="sxs-lookup"><span data-stu-id="ef188-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="ef188-138">Отношения "многие-ко-многим" могут быть созданы с использованием двух отношений "многие-к-одному" и промежуточной сущности (сущности, которая используется для соединения исходной и целевой сущностей).</span><span class="sxs-lookup"><span data-stu-id="ef188-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="ef188-139">Удаление отношения</span><span class="sxs-lookup"><span data-stu-id="ef188-139">Delete a relationship</span></span>

1. <span data-ttu-id="ef188-140">В аналитике аудитории перейдите **Данные** > **Отношения**.</span><span class="sxs-lookup"><span data-stu-id="ef188-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="ef188-141">Установите флажки для всех отношений, которые требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="ef188-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="ef188-142">Выберите **Удалить** вверху таблицы **Отношения**.</span><span class="sxs-lookup"><span data-stu-id="ef188-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="ef188-143">Подтвердите удаление.</span><span class="sxs-lookup"><span data-stu-id="ef188-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="ef188-144">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="ef188-144">Next step</span></span>

<span data-ttu-id="ef188-145">Системные и пользовательские отношения используются для создания сегментов на основе нескольких источников данных, которые больше не обособлены.</span><span class="sxs-lookup"><span data-stu-id="ef188-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="ef188-146">Дополнительные сведения см. в разделе [Сегменты](segments.md).</span><span class="sxs-lookup"><span data-stu-id="ef188-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]