---
title: Отношения между сущностями и путями сущностей
description: Создавайте и управляйте отношениями между сущностями из нескольких источников данных.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171180"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="de4cd-103">Отношения между сущностями</span><span class="sxs-lookup"><span data-stu-id="de4cd-103">Relationships between entities</span></span>

<span data-ttu-id="de4cd-104">Отношения соединяют сущности и определяют график ваших данных, когда сущности имеют общий идентификатор, внешний ключ.</span><span class="sxs-lookup"><span data-stu-id="de4cd-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="de4cd-105">На этот внешний ключ можно ссылаться от одной сущности к другой.</span><span class="sxs-lookup"><span data-stu-id="de4cd-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="de4cd-106">Связанные сущности позволяют определять сегменты и меры на основе нескольких источников данных.</span><span class="sxs-lookup"><span data-stu-id="de4cd-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="de4cd-107">Есть три типа отношений:</span><span class="sxs-lookup"><span data-stu-id="de4cd-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="de4cd-108">Нередактируемые системные отношения, созданные системой в рамках процесса объединения данных</span><span class="sxs-lookup"><span data-stu-id="de4cd-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="de4cd-109">Нередактируемые унаследованные отношения, которые создаются автоматически из источников данных</span><span class="sxs-lookup"><span data-stu-id="de4cd-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="de4cd-110">Редактируемые пользовательские отношения, созданные и настроенные пользователями</span><span class="sxs-lookup"><span data-stu-id="de4cd-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="de4cd-111">Нередактируемый системные отношения</span><span class="sxs-lookup"><span data-stu-id="de4cd-111">Non-editable system relationships</span></span>

<span data-ttu-id="de4cd-112">Во время объединения данных системные отношения создается автоматически на основе интеллектуального сопоставления.</span><span class="sxs-lookup"><span data-stu-id="de4cd-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="de4cd-113">Эти отношения помогают связать записи профиля клиента с соответствующими записями.</span><span class="sxs-lookup"><span data-stu-id="de4cd-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="de4cd-114">На следующей диаграмме показано создание трех системных отношений.</span><span class="sxs-lookup"><span data-stu-id="de4cd-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="de4cd-115">Сущности клиента сопоставляется с другими сущностями для производства единой сущности *Клиент*.</span><span class="sxs-lookup"><span data-stu-id="de4cd-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Диаграмма с путями отношений для сущности клиента с тремя отношениями 1-N.":::

- <span data-ttu-id="de4cd-117">\***CustomerToContact\*— отношение** было создано между сущностью *Клиент* и сущностью *Контакт*.</span><span class="sxs-lookup"><span data-stu-id="de4cd-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="de4cd-118">Сущность *Клиент* получает ключевое поле **Contact_contactID** для связи с ключевым полем сущности *Контакт* **contactID**.</span><span class="sxs-lookup"><span data-stu-id="de4cd-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="de4cd-119">***CustomerToAccount* — отношение** было создано между сущностью *Клиент* и сущностью *Организация*.</span><span class="sxs-lookup"><span data-stu-id="de4cd-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="de4cd-120">Сущность *Клиент* получает ключевое поле **Account_accountID** для связи с ключевым полем сущности *Организация* **accountID**.</span><span class="sxs-lookup"><span data-stu-id="de4cd-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="de4cd-121">\***CustomerToWebAccount\*— отношение** было создано между сущностью *Клиент* и сущностью *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="de4cd-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="de4cd-122">Сущность *Клиент* получает ключевое поле **WebAccount_webaccountID** для связи с ключевым полем сущности *WebAccount* **webaccountID**.</span><span class="sxs-lookup"><span data-stu-id="de4cd-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="de4cd-123">Нередактируемые унаследованные отношения</span><span class="sxs-lookup"><span data-stu-id="de4cd-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="de4cd-124">В процессе приема данных система проверяет источники данных на наличие отношений.</span><span class="sxs-lookup"><span data-stu-id="de4cd-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="de4cd-125">Если отношений не существует, система автоматически создает их.</span><span class="sxs-lookup"><span data-stu-id="de4cd-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="de4cd-126">Эти отношения также используются в последующих процессах.</span><span class="sxs-lookup"><span data-stu-id="de4cd-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="de4cd-127">Создание настраиваемого отношения</span><span class="sxs-lookup"><span data-stu-id="de4cd-127">Create a custom relationship</span></span>

<span data-ttu-id="de4cd-128">Отношения состоят из *исходной сущности*, содержащей внешний ключ, и *целевой сущности*, на которую указывает внешний ключ исходной сущности.</span><span class="sxs-lookup"><span data-stu-id="de4cd-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="de4cd-129">В аналитике аудитории перейдите **Данные** > **Отношения**.</span><span class="sxs-lookup"><span data-stu-id="de4cd-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="de4cd-130">Выберите **Создать отношение**.</span><span class="sxs-lookup"><span data-stu-id="de4cd-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="de4cd-131">В области **Новое отношение** укажите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="de4cd-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Боковая панель создания отношений с пустыми полями ввода.":::

   - <span data-ttu-id="de4cd-133">**Имя отношения**: имя, которое отражает цель отношений.</span><span class="sxs-lookup"><span data-stu-id="de4cd-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="de4cd-134">Пример: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="de4cd-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="de4cd-135">**Описание**: описание отношения.</span><span class="sxs-lookup"><span data-stu-id="de4cd-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="de4cd-136">**Исходная сущность**: сущность, которая используется в качестве источника в отношении.</span><span class="sxs-lookup"><span data-stu-id="de4cd-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="de4cd-137">Пример: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="de4cd-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="de4cd-138">**Целевая сущность**: сущность, которая используется в качестве цели в отношении.</span><span class="sxs-lookup"><span data-stu-id="de4cd-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="de4cd-139">Пример: Customer.</span><span class="sxs-lookup"><span data-stu-id="de4cd-139">Example: Customer.</span></span>
   - <span data-ttu-id="de4cd-140">**Кратность исходной сущности**: кратность исходной сущности.</span><span class="sxs-lookup"><span data-stu-id="de4cd-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="de4cd-141">Количество элементов описывает количество возможных элементов в наборе.</span><span class="sxs-lookup"><span data-stu-id="de4cd-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="de4cd-142">Это всегда относится к кратности исходной сущности.</span><span class="sxs-lookup"><span data-stu-id="de4cd-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="de4cd-143">Вы можете выбирать между **Один** и **Много**.</span><span class="sxs-lookup"><span data-stu-id="de4cd-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="de4cd-144">Поддерживаются только отношения многие-к-одному и один-к-одному.</span><span class="sxs-lookup"><span data-stu-id="de4cd-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="de4cd-145">Многие-к-одному: несколько исходных записей могут относиться к одной целевой записи.</span><span class="sxs-lookup"><span data-stu-id="de4cd-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="de4cd-146">Пример: несколько обращений в службу поддержки от одного клиента.</span><span class="sxs-lookup"><span data-stu-id="de4cd-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="de4cd-147">Один к одному: одна исходная запись связана с одной целевой записью.</span><span class="sxs-lookup"><span data-stu-id="de4cd-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="de4cd-148">Пример: один идентификатор лояльности для одного клиента.</span><span class="sxs-lookup"><span data-stu-id="de4cd-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="de4cd-149">Отношения "многие ко многим" можно создать с использованием двух отношений "многие ко многим" и связывающей сущности, которая соединяет исходную сущность и целевую сущность.</span><span class="sxs-lookup"><span data-stu-id="de4cd-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="de4cd-150">**Кратность целевого объекта**: выберите кратность записей целевой сущности.</span><span class="sxs-lookup"><span data-stu-id="de4cd-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="de4cd-151">**Поле исходного ключа**: поле внешнего ключа в исходной сущности.</span><span class="sxs-lookup"><span data-stu-id="de4cd-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="de4cd-152">Пример: SupportCase может использовать CaseID в качестве поля внешнего ключа.</span><span class="sxs-lookup"><span data-stu-id="de4cd-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="de4cd-153">**Целевое ключевое поле**: поле ключа целевой сущности.</span><span class="sxs-lookup"><span data-stu-id="de4cd-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="de4cd-154">Пример Customer может использовать ключевое поле **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="de4cd-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="de4cd-155">Нажмите кнопку **Сохранить**, чтобы сохранить настраиваемое отношение.</span><span class="sxs-lookup"><span data-stu-id="de4cd-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="de4cd-156">Просмотр отношений</span><span class="sxs-lookup"><span data-stu-id="de4cd-156">View relationships</span></span>

<span data-ttu-id="de4cd-157">На странице отношений перечислены все созданные отношения.</span><span class="sxs-lookup"><span data-stu-id="de4cd-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="de4cd-158">Каждая строка представляет отношение, которое также включает сведения об исходной сущности, целевой сущности и кратности.</span><span class="sxs-lookup"><span data-stu-id="de4cd-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Список отношений и параметров на панели действий на странице отношений.":::

<span data-ttu-id="de4cd-160">На этой странице предлагается набор параметров для существующего и нового отношения:</span><span class="sxs-lookup"><span data-stu-id="de4cd-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="de4cd-161">**Новые отношения**: [создайте настраиваемые отношения](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="de4cd-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="de4cd-162">**Визуализатор**: [изучите визуализатор отношений](#explore-the-relationship-visualizer), чтобы увидеть сетевую диаграмму существующих отношений и их кратность.</span><span class="sxs-lookup"><span data-stu-id="de4cd-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="de4cd-163">**Фильтровать по**: выберите тип отношений для отображения в списке.</span><span class="sxs-lookup"><span data-stu-id="de4cd-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="de4cd-164">**Искать отношения**: используйте текстовый поиск по свойствам отношений.</span><span class="sxs-lookup"><span data-stu-id="de4cd-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="de4cd-165">Изучите визуализатор отношений</span><span class="sxs-lookup"><span data-stu-id="de4cd-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="de4cd-166">Визуализатор отношений показывает сетевую диаграмму существующих отношений между подключенными сущностями и их кратность.</span><span class="sxs-lookup"><span data-stu-id="de4cd-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="de4cd-167">Чтобы настроить вид, вы можете изменить положение полей, перетащив их на холст.</span><span class="sxs-lookup"><span data-stu-id="de4cd-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Снимок экрана сетевой диаграммы визуализатора отношений со связями между подключенными сущностями.":::

<span data-ttu-id="de4cd-169">Доступные параметры:</span><span class="sxs-lookup"><span data-stu-id="de4cd-169">Available options:</span></span> 
- <span data-ttu-id="de4cd-170">**Экспорт как изображение**: сохранить текущий вид как файл изображения.</span><span class="sxs-lookup"><span data-stu-id="de4cd-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="de4cd-171">**Изменить на горизонтальный/вертикальный макет**: изменить выравнивание сущностей и отношений.</span><span class="sxs-lookup"><span data-stu-id="de4cd-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="de4cd-172">**Редактировать**: обновите свойства пользовательского отношения на панели редактирования и сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="de4cd-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="de4cd-173">Управлять существующим отношениями</span><span class="sxs-lookup"><span data-stu-id="de4cd-173">Manage existing relationships</span></span> 

<span data-ttu-id="de4cd-174">На странице отношений каждое отношение представлено строкой.</span><span class="sxs-lookup"><span data-stu-id="de4cd-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="de4cd-175">Выберите отношения и выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="de4cd-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="de4cd-176">**Редактировать**: обновите свойства пользовательского отношения на панели редактирования и сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="de4cd-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="de4cd-177">**Удалить**: удалить пользовательское отношение.</span><span class="sxs-lookup"><span data-stu-id="de4cd-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="de4cd-178">**Просмотр**: просмотреть созданное и унаследованное системное отношение.</span><span class="sxs-lookup"><span data-stu-id="de4cd-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="de4cd-179">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="de4cd-179">Next step</span></span>

<span data-ttu-id="de4cd-180">Системные и пользовательские отношения используются для [создания сегментов](segments.md) на основе нескольких источников данных, которые больше не обособлены.</span><span class="sxs-lookup"><span data-stu-id="de4cd-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
