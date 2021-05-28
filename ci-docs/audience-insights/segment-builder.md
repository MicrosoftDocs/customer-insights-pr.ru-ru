---
title: Создание и управление сегментами
description: Создайте сегменты клиентов, чтобы сгруппировать их на основе различных атрибутов.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064953"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="ff505-103">Создание и управление сегментами</span><span class="sxs-lookup"><span data-stu-id="ff505-103">Create and manage segments</span></span>

<span data-ttu-id="ff505-104">Определите сложные фильтры вокруг единой сущности клиента и связанных с ней сущностей.</span><span class="sxs-lookup"><span data-stu-id="ff505-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="ff505-105">Каждый сегмент после обработки создает набор записей о клиентах, которые можно экспортировать и выполнять действия с ними.</span><span class="sxs-lookup"><span data-stu-id="ff505-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="ff505-106">Сегменты управляются на странице **Сегменты**.</span><span class="sxs-lookup"><span data-stu-id="ff505-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="ff505-107">В следующем примере показано использование возможностей сегментации.</span><span class="sxs-lookup"><span data-stu-id="ff505-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="ff505-108">Мы определили сегмент для клиентов, которые заказали товаров как минимум на 500 долларов США за последние 90 дней *и* которые были вовлечены в вызов обслуживание клиентов, который был передан на более высокий уровень.</span><span class="sxs-lookup"><span data-stu-id="ff505-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Снимок экрана пользовательского интерфейса построителя сегментов с двумя группами, определяющими сегмент клиентов.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="ff505-110">Создание нового сегмента</span><span class="sxs-lookup"><span data-stu-id="ff505-110">Create a new segment</span></span>

<span data-ttu-id="ff505-111">Существуют несколько способов создания нового сегмента.</span><span class="sxs-lookup"><span data-stu-id="ff505-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="ff505-112">В этом разделе описывается, как создать *пустой сегмент* с нуля.</span><span class="sxs-lookup"><span data-stu-id="ff505-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="ff505-113">Вы также можете создать *быстрый сегмент* на основе существующих сущностей или использовать модели машинного обучения, чтобы получить *предлагаемые сегменты*.</span><span class="sxs-lookup"><span data-stu-id="ff505-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="ff505-114">Подробнее: [Обзор сегментов](segments.md).</span><span class="sxs-lookup"><span data-stu-id="ff505-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="ff505-115">Создавая сегмент, вы можете сохранить черновик.</span><span class="sxs-lookup"><span data-stu-id="ff505-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="ff505-116">Он будет сохранен как неактивный сегмент и не может быть активирован, пока не будет завершен с допустимой конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="ff505-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="ff505-117">Перейдите на страницу **Сегменты**.</span><span class="sxs-lookup"><span data-stu-id="ff505-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="ff505-118">Выберите **Создать** > **Пустой сегмент**.</span><span class="sxs-lookup"><span data-stu-id="ff505-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="ff505-119">В области **Новый сегмент** выберите тип сегмента:</span><span class="sxs-lookup"><span data-stu-id="ff505-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="ff505-120">**Динамические сегменты** [обновляются](segments.md#refresh-segments) по повторяющемуся графику.</span><span class="sxs-lookup"><span data-stu-id="ff505-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="ff505-121">**Статические сегменты** запускаются один раз, когда вы его создаете.</span><span class="sxs-lookup"><span data-stu-id="ff505-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="ff505-122">Укажите **Имя выходной сущности** для сегмента.</span><span class="sxs-lookup"><span data-stu-id="ff505-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="ff505-123">При желании укажите отображаемое имя и описание, которое поможет идентифицировать сегмент.</span><span class="sxs-lookup"><span data-stu-id="ff505-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="ff505-124">Выберите **Далее**, чтобы перейти на страницу **Конструктор сегментов**, где вы определяете группу.</span><span class="sxs-lookup"><span data-stu-id="ff505-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="ff505-125">Группа — это набор клиентов.</span><span class="sxs-lookup"><span data-stu-id="ff505-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="ff505-126">Выберите сущность, которая содержит атрибут, по которому требуется выполнить сегментацию.</span><span class="sxs-lookup"><span data-stu-id="ff505-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="ff505-127">Выберите атрибут для сегментирования.</span><span class="sxs-lookup"><span data-stu-id="ff505-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="ff505-128">Этот атрибут может иметь один из четырех типов значений: числовое, строковое, дата или логическое значение.</span><span class="sxs-lookup"><span data-stu-id="ff505-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="ff505-129">Выберите оператор и значение для выбранного атрибута.</span><span class="sxs-lookup"><span data-stu-id="ff505-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ff505-130">![Пользовательский фильтр группы](media/customer-group-numbers.png "Фильтр группы пользователей")</span><span class="sxs-lookup"><span data-stu-id="ff505-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="ff505-131">Число</span><span class="sxs-lookup"><span data-stu-id="ff505-131">Number</span></span> |<span data-ttu-id="ff505-132">Определение</span><span class="sxs-lookup"><span data-stu-id="ff505-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="ff505-133">1</span><span class="sxs-lookup"><span data-stu-id="ff505-133">1</span></span>     |<span data-ttu-id="ff505-134">Entity</span><span class="sxs-lookup"><span data-stu-id="ff505-134">Entity</span></span>          |
   |<span data-ttu-id="ff505-135">2</span><span class="sxs-lookup"><span data-stu-id="ff505-135">2</span></span>     |<span data-ttu-id="ff505-136">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ff505-136">Attribute</span></span>          |
   |<span data-ttu-id="ff505-137">3</span><span class="sxs-lookup"><span data-stu-id="ff505-137">3</span></span>    |<span data-ttu-id="ff505-138">Оператор</span><span class="sxs-lookup"><span data-stu-id="ff505-138">Operator</span></span>         |
   |<span data-ttu-id="ff505-139">4</span><span class="sxs-lookup"><span data-stu-id="ff505-139">4</span></span>    |<span data-ttu-id="ff505-140">значение</span><span class="sxs-lookup"><span data-stu-id="ff505-140">Value</span></span>         |

   1. <span data-ttu-id="ff505-141">Чтобы добавить больше условий в группу, вы можете использовать два логических оператора:</span><span class="sxs-lookup"><span data-stu-id="ff505-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="ff505-142">Оператор **И**: оба условия должны быть выполнены как часть процесса сегментации.</span><span class="sxs-lookup"><span data-stu-id="ff505-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="ff505-143">Эта опция наиболее полезна, когда вы определяете условия для разных сущностей.</span><span class="sxs-lookup"><span data-stu-id="ff505-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="ff505-144">Оператор **ИЛИ**: любое из условий должно быть выполнено как часть процесса сегментации.</span><span class="sxs-lookup"><span data-stu-id="ff505-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="ff505-145">Эта опция наиболее полезна, когда вы определяете несколько условий для одной сущности.</span><span class="sxs-lookup"><span data-stu-id="ff505-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="ff505-146">![Оператор "ИЛИ", где должно быть выполнено любое из условий](media/segmentation-either-condition.png "Оператор &quot;ИЛИ&quot;, где должно быть выполнено любое из условий")</span><span class="sxs-lookup"><span data-stu-id="ff505-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="ff505-147">В настоящее время можно вложить оператор **ИЛИ** в оператор **И**, но не наоборот.</span><span class="sxs-lookup"><span data-stu-id="ff505-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="ff505-148">Каждая группа соответствует набору клиентов.</span><span class="sxs-lookup"><span data-stu-id="ff505-148">Each group matches set of customers.</span></span> <span data-ttu-id="ff505-149">Вы можете объединять группы, чтобы включать клиентов, необходимых для вашего бизнес-случая.</span><span class="sxs-lookup"><span data-stu-id="ff505-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="ff505-150">Выберите **Добавить группу**.</span><span class="sxs-lookup"><span data-stu-id="ff505-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="ff505-151">![Добавление группы в группу клиентов](media/customer-group-add-group.png "Добавление группы в группу клиентов")</span><span class="sxs-lookup"><span data-stu-id="ff505-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="ff505-152">Выберите один из операторов набора: **Объединение**, **Пересечение** или **Исключение**.</span><span class="sxs-lookup"><span data-stu-id="ff505-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ff505-153">![Добавление объединения в группу клиентов](media/customer-group-union.png "Добавление объединения в группу клиентов")</span><span class="sxs-lookup"><span data-stu-id="ff505-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="ff505-154">**Объединение** объединяет две группы.</span><span class="sxs-lookup"><span data-stu-id="ff505-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="ff505-155">**Пересечение** перекрывает две группы.</span><span class="sxs-lookup"><span data-stu-id="ff505-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="ff505-156">Только данные, которые *общие* в обеих группах, сохраняются в унифицированной группе.</span><span class="sxs-lookup"><span data-stu-id="ff505-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="ff505-157">**За исключением** объединяет две группы.</span><span class="sxs-lookup"><span data-stu-id="ff505-157">**Except** combines the two groups.</span></span> <span data-ttu-id="ff505-158">Только данные в группе "А", которые *не общие* для данных в группе "Б", сохраняются.</span><span class="sxs-lookup"><span data-stu-id="ff505-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="ff505-159">Если сущность связана с объединенной сущностью клиента через [отношения](relationships.md), вам нужно определить путь отношения, чтобы создать действительный сегмент.</span><span class="sxs-lookup"><span data-stu-id="ff505-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="ff505-160">Добавьте сущности из пути отношений, пока не сможете выбрать сущность **Клиент : CustomerInsights** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="ff505-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="ff505-161">Затем выберите **Все записи** для каждого шага.</span><span class="sxs-lookup"><span data-stu-id="ff505-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ff505-162">![Путь отношений при создании сегмента](media/segments-multiple-relationships.png "Путь отношений при создании сегмента")</span><span class="sxs-lookup"><span data-stu-id="ff505-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="ff505-163">По умолчанию сегменты генерируют выходную сущность, содержащую все атрибуты профилей клиентов, которые соответствуют определенным фильтрам.</span><span class="sxs-lookup"><span data-stu-id="ff505-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="ff505-164">Если сегмент основан на других сущностях, кроме сущности *Клиент*, вы можете добавить дополнительные атрибуты из этих сущностей в выходную сущность.</span><span class="sxs-lookup"><span data-stu-id="ff505-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="ff505-165">Укажите **Атрибуты проекта** для выбора атрибутов, которые будут добавлены к выходной сущности.</span><span class="sxs-lookup"><span data-stu-id="ff505-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="ff505-166">Пример: сегмент основан на сущности, которая содержит данные о действиях клиента, которые связаны с сущностью *Клиент*.</span><span class="sxs-lookup"><span data-stu-id="ff505-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="ff505-167">Сегмент выполняет поиск всех клиентов, которые обращались в службу поддержки за последние 60 дней.</span><span class="sxs-lookup"><span data-stu-id="ff505-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="ff505-168">Вы можете добавить продолжительность звонка и количество звонков ко всем совпадающим записям клиентов в выходной сущности.</span><span class="sxs-lookup"><span data-stu-id="ff505-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="ff505-169">Эта информация может быть полезна для отправки часто звонящим клиентам сообщений электронной почты с полезными ссылками на статьи справки и раздел "Часто задаваемые вопросы".</span><span class="sxs-lookup"><span data-stu-id="ff505-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="ff505-170">Проецированные атрибуты работают только для сущностей, которые имеют отношение "один ко многим" с сущностью клиента.</span><span class="sxs-lookup"><span data-stu-id="ff505-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="ff505-171">Например, у одного клиента может быть несколько подписок.</span><span class="sxs-lookup"><span data-stu-id="ff505-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="ff505-172">Вы можете проецировать атрибуты только из сущности, которая используется в каждой создаваемой вами группе запросов сегментов.</span><span class="sxs-lookup"><span data-stu-id="ff505-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="ff505-173">Спроецированные атрибуты учитываются при использовании операторов множества.</span><span class="sxs-lookup"><span data-stu-id="ff505-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="ff505-174">Выберите **Сохранить**, чтобы сохранить сегмент.</span><span class="sxs-lookup"><span data-stu-id="ff505-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="ff505-175">Ваш сегмент будет сохранен и обработан, если все требования будут подтверждены.</span><span class="sxs-lookup"><span data-stu-id="ff505-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="ff505-176">В противном случае он будет сохранен как черновик.</span><span class="sxs-lookup"><span data-stu-id="ff505-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="ff505-177">Выберите **Назад к сегментам**, чтобы вернуться к странице **Сегменты**.</span><span class="sxs-lookup"><span data-stu-id="ff505-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="ff505-178">Быстрые сегменты</span><span class="sxs-lookup"><span data-stu-id="ff505-178">Quick segments</span></span>

<span data-ttu-id="ff505-179">Быстрые сегменты позволяют быстро создавать простые сегменты с помощью одного оператора для более быстрого анализа.</span><span class="sxs-lookup"><span data-stu-id="ff505-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="ff505-180">На странице **Сегменты** выберите **Создать** > **Создать из**.</span><span class="sxs-lookup"><span data-stu-id="ff505-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="ff505-181">Выберите параметр **Профили** для построения сегмента на основе сущности *единого клиента*.</span><span class="sxs-lookup"><span data-stu-id="ff505-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="ff505-182">Выберите параметр **Меры**, чтобы построить сегмент вокруг ранее созданных мер.</span><span class="sxs-lookup"><span data-stu-id="ff505-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="ff505-183">Выберите параметр **Аналитика**, чтобы построить сегмент вокруг одной из выходных сущностей, которые вы сгенерировали, используя возможности **Прогнозы** или **Пользовательские модели**.</span><span class="sxs-lookup"><span data-stu-id="ff505-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="ff505-184">В диалоговом окне **Создать быстрый сегмент** выберите атрибут из раскрывающегося списка **Поле**.</span><span class="sxs-lookup"><span data-stu-id="ff505-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="ff505-185">Система предоставит некоторые дополнительные сведения, которые помогут вам создать лучшие сегменты ваших клиентов.</span><span class="sxs-lookup"><span data-stu-id="ff505-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="ff505-186">Для категориальных полей мы покажем количество 10 лучших клиентов.</span><span class="sxs-lookup"><span data-stu-id="ff505-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="ff505-187">Выберите **Значение** и выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="ff505-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="ff505-188">Для числового атрибута система покажет, какое значение атрибута попадает под процентиль каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="ff505-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="ff505-189">Выберите **Оператор** и **Значение**, затем выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="ff505-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="ff505-190">Система предоставит вам **Расчетный размер сегмента**.</span><span class="sxs-lookup"><span data-stu-id="ff505-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="ff505-191">Вы можете выбрать, создавать ли определенный вами сегмент или сначала вернуться к нему, чтобы получить другой размер сегмента.</span><span class="sxs-lookup"><span data-stu-id="ff505-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ff505-192">![Название и оценка для быстрого сегмента](media/quick-segment-name.png "Название и оценка для быстрого сегмента")</span><span class="sxs-lookup"><span data-stu-id="ff505-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="ff505-193">Задайте **Имя** для сегмента.</span><span class="sxs-lookup"><span data-stu-id="ff505-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="ff505-194">Если требуется, укажите **Отображаемое имя**.</span><span class="sxs-lookup"><span data-stu-id="ff505-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="ff505-195">Нажмите **Сохранить**, чтобы создать сегмент.</span><span class="sxs-lookup"><span data-stu-id="ff505-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="ff505-196">После того как обработка сегмента завершена, вы можете просмотреть его, как и любой другой созданный вами сегмент.</span><span class="sxs-lookup"><span data-stu-id="ff505-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ff505-197">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="ff505-197">Next steps</span></span>

<span data-ttu-id="ff505-198">[Экспортируйте сегмент](export-destinations.md) и изучите [Карту клиента](customer-card-add-in.md) и [Соединители](export-power-bi.md), чтобы получить представление об уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="ff505-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
