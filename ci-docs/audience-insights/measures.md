---
title: Креирање и уређивање мера
description: Дефинишите мере које се односе на клијента како бисте анализирали и одражавали перформансе одређених области пословања.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406876"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="95137-103">Дефинишите и управљајте мерама</span><span class="sxs-lookup"><span data-stu-id="95137-103">Define and manage measures</span></span>

<span data-ttu-id="95137-104">**Мере** представљају кључне показатеље перформанси (KPI) који одражавају перформансе и исправност одређених пословних области.</span><span class="sxs-lookup"><span data-stu-id="95137-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="95137-105">Увиди о корисницима пружају интуитивно искуство за изградњу различитих врста мера, користећи креатор упита који не захтева ручно кодирање или валидацију мера.</span><span class="sxs-lookup"><span data-stu-id="95137-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="95137-106">Можете пратити своје пословне мере на страници **Почетак**, погледајте мере за одређене клијенте на страници **Картица клијента** и користите мере за дефинисање сегмената корисника на страници **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="95137-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="95137-107">Креирање мере</span><span class="sxs-lookup"><span data-stu-id="95137-107">Create a measure</span></span>

<span data-ttu-id="95137-108">Овај одељак вас води кроз креирање мере испочетка.</span><span class="sxs-lookup"><span data-stu-id="95137-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="95137-109">Можете изградити мере помоћу података из више извора података који су повезани преко ентитета Клијента.</span><span class="sxs-lookup"><span data-stu-id="95137-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="95137-110">Нека [ограничења услуга](service-limits.md) се примењују.</span><span class="sxs-lookup"><span data-stu-id="95137-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="95137-111">У увидима о корисницима идите на **Мере**.</span><span class="sxs-lookup"><span data-stu-id="95137-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="95137-112">Изаберите **Нова мера**.</span><span class="sxs-lookup"><span data-stu-id="95137-112">Select **New measure**.</span></span>

3. <span data-ttu-id="95137-113">Одаберите **Тип** мере:</span><span class="sxs-lookup"><span data-stu-id="95137-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="95137-114">**Атрибут клијента**: Једно поље по клијенту које одражава резултат, вредност или стање за клијента.</span><span class="sxs-lookup"><span data-stu-id="95137-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="95137-115">Атрибути корисника креирају се као атрибути у новом системски генерираном ентитету који се зове **Customer_Measure**.</span><span class="sxs-lookup"><span data-stu-id="95137-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="95137-116">**Мера клијента**: Увид у понашање клијената са анализом по одабраним димензијама.</span><span class="sxs-lookup"><span data-stu-id="95137-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="95137-117">Креира се нови ентитет за сваку меру, потенцијално са више записа по кориснику.</span><span class="sxs-lookup"><span data-stu-id="95137-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="95137-118">**Пословна мера**: Прати ваше пословне резултате и стање вашег пословања.</span><span class="sxs-lookup"><span data-stu-id="95137-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="95137-119">Пословне мере могу имати два различита излаза: нумерички излаз који се приказује на страници **Почетак** или нови ентитет који ћете пронаћи на страници **Ентитети**.</span><span class="sxs-lookup"><span data-stu-id="95137-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="95137-120">Наведите **Име** и опционално **Име за приказ**, а затим изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="95137-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="95137-121">У одељку **Ентитет**, изаберите први ентитет са падајуће листе.</span><span class="sxs-lookup"><span data-stu-id="95137-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="95137-122">У овом тренутку, требало би да одлучите да ли су потребни додатни ентитети као део ваше дефиниције мера.</span><span class="sxs-lookup"><span data-stu-id="95137-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="95137-123">![Дефиниција мере](media/measure-definition.png "Дефиниција мере")</span><span class="sxs-lookup"><span data-stu-id="95137-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="95137-124">Да бисте додали још ентитета, изаберите **Додајте ентитет** и изаберите ентитете које желите да користите за меру.</span><span class="sxs-lookup"><span data-stu-id="95137-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="95137-125">Можете изабрати само оне ентитете који имају релацију са почетним ентитетом.</span><span class="sxs-lookup"><span data-stu-id="95137-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="95137-126">Више информација о дефинисању релација потражите у чланку [Релације](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="95137-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="95137-127">Опционално, можете да конфигуришете променљиве.</span><span class="sxs-lookup"><span data-stu-id="95137-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="95137-128">У одељку **Променљиве**, изаберите **Нова променљива**.</span><span class="sxs-lookup"><span data-stu-id="95137-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="95137-129">Променљиве су прорачуни који се обављају на свим изабраним записима.</span><span class="sxs-lookup"><span data-stu-id="95137-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="95137-130">На пример, сабирање продајног места (POS) и продаја путем интернета за све записе ваших клијената.</span><span class="sxs-lookup"><span data-stu-id="95137-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="95137-131">Наведите **Назив** за променљиву.</span><span class="sxs-lookup"><span data-stu-id="95137-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="95137-132">У области **Израз** одаберите поље за почетак израчунавања.</span><span class="sxs-lookup"><span data-stu-id="95137-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="95137-133">Унесите израз у област **Израз** док бирате више поља која ће се укључити у ваш прорачун.</span><span class="sxs-lookup"><span data-stu-id="95137-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="95137-134">Тренутно су подржани само аритметички изрази.</span><span class="sxs-lookup"><span data-stu-id="95137-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="95137-135">Поред тога, израчунавање променљивих није подржано за ентитете из различитих [путања ентитета](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="95137-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="95137-136">Изаберите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="95137-136">Select **Done**.</span></span>

11. <span data-ttu-id="95137-137">У одељку **Дефиниција мере**, дефинисаћете како се изабрани ентитети и израчунате променљиве агрегирају у нову целину или атрибут мере.</span><span class="sxs-lookup"><span data-stu-id="95137-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="95137-138">Изаберите **Нова димензија**.</span><span class="sxs-lookup"><span data-stu-id="95137-138">Select **New dimension**.</span></span> <span data-ttu-id="95137-139">О димензији можете размишљати као о функцији *групиши према*.</span><span class="sxs-lookup"><span data-stu-id="95137-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="95137-140">Излаз података вашег ентитета или атрибута Мера биће груписан по свим вашим дефинисаним димензијама.</span><span class="sxs-lookup"><span data-stu-id="95137-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="95137-141">![Изаберите агрегатни циклус](media/measures-businessreport-measure-definition2.png "Изаберите агрегатни циклус")</span><span class="sxs-lookup"><span data-stu-id="95137-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="95137-142">Изаберите или унесите следеће информације као део дефиниције ваше димензије:</span><span class="sxs-lookup"><span data-stu-id="95137-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="95137-143">**Ентитет**: Ако дефинишете ентитет Мера, он треба да садржи најмање један атрибут.</span><span class="sxs-lookup"><span data-stu-id="95137-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="95137-144">Ако дефинишете атрибут Мера, он ће подразумевано садржавати само један атрибут.</span><span class="sxs-lookup"><span data-stu-id="95137-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="95137-145">Овај избор се односи на избор ентитета који укључује тај атрибут.</span><span class="sxs-lookup"><span data-stu-id="95137-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="95137-146">**Поље**: Изаберите одређени атрибут који ће се укључити у вашу мерну јединицу или атрибут.</span><span class="sxs-lookup"><span data-stu-id="95137-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="95137-147">**Контејнер**: Изаберите да ли желите да обједините податке на дневној, месечној или годишњој основи.</span><span class="sxs-lookup"><span data-stu-id="95137-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="95137-148">То је обавезан избор само ако сте изабрали атрибут типа Датум.</span><span class="sxs-lookup"><span data-stu-id="95137-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="95137-149">**Као**: Дефинише име вашег новог поља.</span><span class="sxs-lookup"><span data-stu-id="95137-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="95137-150">**Име за приказ**: Дефинише име за приказ вашег поља.</span><span class="sxs-lookup"><span data-stu-id="95137-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="95137-151">Ваша пословна мера ће бити сачувана као ентитет с једним бројем и приказаће се на страници **Почетак** уколико у меру не додате више димензија.</span><span class="sxs-lookup"><span data-stu-id="95137-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="95137-152">Након додавања више димензија, мера се *неће* приказивати на страници **Почетак**.</span><span class="sxs-lookup"><span data-stu-id="95137-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="95137-153">Опционално, додајте функције агрегације.</span><span class="sxs-lookup"><span data-stu-id="95137-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="95137-154">Свако здруживање које створите резултира новом вредношћу унутар ентитета или атрибута Мере.</span><span class="sxs-lookup"><span data-stu-id="95137-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="95137-155">Подржане функције агрегације су: **Мин**, **Макс**, **Просек**, **Медијана**, **Збир**, **Број јединствених**, **Први** (узима први запис вредности димензије) и **Последњи** (узима последњи запис који је додан у димензију).</span><span class="sxs-lookup"><span data-stu-id="95137-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="95137-156">Изаберите **Сачувај** да бисте применили промене на меру.</span><span class="sxs-lookup"><span data-stu-id="95137-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="95137-157">Управљање мерама</span><span class="sxs-lookup"><span data-stu-id="95137-157">Manage your measures</span></span>

<span data-ttu-id="95137-158">Након што направите бар једну меру, видећете листу мера на страници **Мере**.</span><span class="sxs-lookup"><span data-stu-id="95137-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="95137-159">Пронаћи ћете информације о врсти мере, креатору, датуму и времену креирања, датуму и времену последње измене, статусу (да ли је мера активна, неактивна или неуспела) и последњем датуму и времену освежавања.</span><span class="sxs-lookup"><span data-stu-id="95137-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="95137-160">Када са листе изаберете меру, можете видети преглед њеног резултата.</span><span class="sxs-lookup"><span data-stu-id="95137-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="95137-161">Да бисте истовремено освежили све мере, изаберите **Освежите све** без избора одређене мере.</span><span class="sxs-lookup"><span data-stu-id="95137-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="95137-162">![Радње за управљање јединственим мерама](media/measure-actions.png "Радње за управљање јединственим мерама")</span><span class="sxs-lookup"><span data-stu-id="95137-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="95137-163">Алтернативно, изаберите меру са листе и извршите једну од следећих радњи:</span><span class="sxs-lookup"><span data-stu-id="95137-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="95137-164">Изаберите назив мере да бисте видели њене детаље.</span><span class="sxs-lookup"><span data-stu-id="95137-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="95137-165">**Уредите** конфигурацију мере.</span><span class="sxs-lookup"><span data-stu-id="95137-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="95137-166">**Преименујте** меру.</span><span class="sxs-lookup"><span data-stu-id="95137-166">**Rename** the measure.</span></span>
- <span data-ttu-id="95137-167">**Избришите** меру.</span><span class="sxs-lookup"><span data-stu-id="95137-167">**Delete** the measure.</span></span>
- <span data-ttu-id="95137-168">Изаберите три тачке (...), а затим **Освежи** да бисте започели поступак освежавања мере.</span><span class="sxs-lookup"><span data-stu-id="95137-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="95137-169">Изаберите три тачке (...), а затим **Преузми** да бисте преузели .CSV датотеку мере.</span><span class="sxs-lookup"><span data-stu-id="95137-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="95137-170">Постоји [шест врста статуса](system.md#status-types) за задатке/процесе.</span><span class="sxs-lookup"><span data-stu-id="95137-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="95137-171">Уз то, већина процеса [зависи од других процеса на нижем току](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="95137-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="95137-172">Можете изабрати статус процеса да бисте видели детаље о току целог посла.</span><span class="sxs-lookup"><span data-stu-id="95137-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="95137-173">Након избора опције **Види детаље** за један од задатака посла пронаћи ћете додатне информације: време обраде, датум последње обраде и све грешке и упозорења повезана са задатком.</span><span class="sxs-lookup"><span data-stu-id="95137-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="95137-174">Следећи корак</span><span class="sxs-lookup"><span data-stu-id="95137-174">Next step</span></span>

<span data-ttu-id="95137-175">Можете да користите постојеће мере да бисте креирали свој први сегмент корисника на страници **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="95137-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="95137-176">За више информација, погледајте чланак [Сегменти](segments.md).</span><span class="sxs-lookup"><span data-stu-id="95137-176">For more information, see [Segments](segments.md).</span></span>
