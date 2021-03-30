---
title: Креирање сегмената и управљање њима
description: Направите сегменте клијената да бисте их груписали на основу различитих атрибута.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597076"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="5a3fe-103">Креирање сегмената и управљање њима</span><span class="sxs-lookup"><span data-stu-id="5a3fe-103">Create and manage segments</span></span>

<span data-ttu-id="5a3fe-104">Сегменти вам омогућавају да групишете клијенте на основу демографских, трансакционих или атрибута понашања.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="5a3fe-105">Можете да користите сегменте за циљање промотивних кампања, продајних активности и активности подршке клијената како бисте постигли своје пословне циљеве.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="5a3fe-106">Можете дефинисати сложене филтере око ентитета Профил клијента и с њим повезаних ентитета.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="5a3fe-107">Сваки сегмент након обраде креира скуп корисничких записа које можете да извозити и за које можете да предузимате неке кораке.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="5a3fe-108">Нека [ограничења услуга](service-limits.md) се примењују.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="5a3fe-109">Ако није другачије назначено, сви сегменти су **Динамички сегменти**, који се освежавају по редовном распореду.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="5a3fe-110">Следећи пример илуструје коришћење могућности сегментације.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="5a3fe-111">Дефинисали смо сегмент за клијенте који су наручили робу за најмање 500 USD у последњих 90 дана *и* који су били укључени у позив корисничке службе који је прослеђен.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5a3fe-112">![Више група](media/segmentation-group1-2.png "Више група")</span><span class="sxs-lookup"><span data-stu-id="5a3fe-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="5a3fe-113">Креирајте нови сегмент</span><span class="sxs-lookup"><span data-stu-id="5a3fe-113">Create a new segment</span></span>

<span data-ttu-id="5a3fe-114">Сегментима се управља на страници **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="5a3fe-115">У увидима о корисницима идите на страницу **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-115">In audience insights, go to the **Segments** page.</span></span>

1. <span data-ttu-id="5a3fe-116">Изаберите **Ново** > **Празан сегмент**.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-116">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="5a3fe-117">У окну **Нови сегмент** одаберите тип сегмента и наведите **Име**.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="5a3fe-118">Опционално, унесите име за приказ и опис који помаже у препознавању сегмента.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="5a3fe-119">Изаберите **Следеће** да дођете на страницу **Градитељ сегмената** на којој дефинишете групу.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="5a3fe-120">Група је скуп клијената.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-120">A group is a set of customers.</span></span>

1. <span data-ttu-id="5a3fe-121">Одаберите ентитет који обухвата атрибуте по којима желите да сегментирате.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-121">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="5a3fe-122">Одаберите атрибут по сегменту.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="5a3fe-123">Овај атрибут може имати један од четири типа вредности: нумерички, ниска, датум или логички.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="5a3fe-124">Одаберите оператор и вредност за изабрани атрибут.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5a3fe-125">![Прилагођени филтер групе](media/customer-group-numbers.png "Филтер групе клијената")</span><span class="sxs-lookup"><span data-stu-id="5a3fe-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="5a3fe-126">Број</span><span class="sxs-lookup"><span data-stu-id="5a3fe-126">Number</span></span> |<span data-ttu-id="5a3fe-127">Дефиниција</span><span class="sxs-lookup"><span data-stu-id="5a3fe-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="5a3fe-128">1</span><span class="sxs-lookup"><span data-stu-id="5a3fe-128">1</span></span>     |<span data-ttu-id="5a3fe-129">Entity</span><span class="sxs-lookup"><span data-stu-id="5a3fe-129">Entity</span></span>          |
   |<span data-ttu-id="5a3fe-130">2</span><span class="sxs-lookup"><span data-stu-id="5a3fe-130">2</span></span>     |<span data-ttu-id="5a3fe-131">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5a3fe-131">Attribute</span></span>          |
   |<span data-ttu-id="5a3fe-132">3</span><span class="sxs-lookup"><span data-stu-id="5a3fe-132">3</span></span>    |<span data-ttu-id="5a3fe-133">Оператор</span><span class="sxs-lookup"><span data-stu-id="5a3fe-133">Operator</span></span>         |
   |<span data-ttu-id="5a3fe-134">4</span><span class="sxs-lookup"><span data-stu-id="5a3fe-134">4</span></span>    |<span data-ttu-id="5a3fe-135">Вредност</span><span class="sxs-lookup"><span data-stu-id="5a3fe-135">Value</span></span>         |

8. <span data-ttu-id="5a3fe-136">Ако је ентитет повезан путем обједињеног ентитета клијента путем [односа](relationships.md), морате дефинисати путању односа да бисте креирали важећи сегмент.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="5a3fe-137">Додајте ентитете из путање односа док не будете могли да изаберете ентитет **Клијент: CustomerInsights** из падајуће листе.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="5a3fe-138">Затим одаберите **Сви записи** за сваки услов.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5a3fe-139">![Путања односа током креирања сегмента](media/segments-multiple-relationships.png "Путања односа током креирања сегмента")</span><span class="sxs-lookup"><span data-stu-id="5a3fe-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="5a3fe-140">Подразумевано, сегменти генеришу излазни ентитет који садржи све атрибуте корисничких профила који се подударају са дефинисаним филтерима.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-140">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="5a3fe-141">Ако се сегмент заснива на другим ентитетима осим на ентитету *Клијент*, излазном ентитету можете додати више атрибута из тих ентитета.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-141">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="5a3fe-142">Изаберите **Атрибути пројекта** да бисте одабрали атрибуте који ће бити додати излазном ентитету.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-142">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  

   
   <span data-ttu-id="5a3fe-143">Пример: Сегмент се заснива на ентитету који садржи податке о активностима клијената који су повезани са ентитетом *Клијент*.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-143">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="5a3fe-144">Сегмент тражи све клијенте који су позвали техничку подршку у последњих 60 дана.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-144">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="5a3fe-145">Можете одабрати да додате трајање позива и број позива свим подударним записима клијената у излазном ентитету.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-145">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="5a3fe-146">Ове информације могу бити корисне за слање е-поште са корисним везама до чланака помоћи на мрежи и често постављаних питања клијентима који су често звали.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-146">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

1. <span data-ttu-id="5a3fe-147">Изаберите **Сачувај** да бисте сачували сегмент.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-147">Select **Save** to save your segment.</span></span> <span data-ttu-id="5a3fe-148">Ваш сегмент ће бити сачуван и обрађен уколико су сви захтеви потврђени.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-148">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="5a3fe-149">У супротном, биће сачуван као радна верзија.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-149">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="5a3fe-150">Изаберите **Назад на сегменте** да бисте се вратили на страницу **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-150">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="5a3fe-151">Управљање постојећим сегментима</span><span class="sxs-lookup"><span data-stu-id="5a3fe-151">Manage existing segments</span></span>

<span data-ttu-id="5a3fe-152">На страници **Сегменти**, можете видети све сачуване сегменте и њима управљати.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-152">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="5a3fe-153">Сваки сегмент представљен је редом који садржи додатне информације о сегменту.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-153">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="5a3fe-154">Сегменте можете сортирати у колони одабиром наслова колоне.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-154">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="5a3fe-155">Користите поље **Претрага** у горњем десном углу да бисте филтрирали сегменте.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-155">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5a3fe-156">![Опције за управљање постојећим сегментом](media/segments-selected-segment.png "Опције за управљање постојећим сегментом")</span><span class="sxs-lookup"><span data-stu-id="5a3fe-156">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="5a3fe-157">Следећа радња је доступна када одаберете сегмент:</span><span class="sxs-lookup"><span data-stu-id="5a3fe-157">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="5a3fe-158">**Приказ** детаља сегмента, укључујући тренд броја чланова, преглед чланова сегмента.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-158">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="5a3fe-159">**Уредите** сегмент да бисте променили његова својства.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-159">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="5a3fe-160">**Направите дупликат** сегмента.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-160">**Create duplicate** of a segment.</span></span> <span data-ttu-id="5a3fe-161">Можете одабрати да уредите његова својства или једноставно сачувате дупликат.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-161">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="5a3fe-162">**Освежите** сегмент тако да укључује најновије податке.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-162">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="5a3fe-163">**Активирајте** или **Деактивирајте** сегмент.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-163">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="5a3fe-164">Сегменти имају два могућа стања - активно или неактивно.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-164">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="5a3fe-165">Ова стања добро дођу приликом уређивања сегмента.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-165">These states come in handy when editing a segment.</span></span> <span data-ttu-id="5a3fe-166">За неактивне сегменте дефиниција сегмента постоји, али још увек не садржи клијенте.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-166">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="5a3fe-167">Када активирате сегмент, његово стање се мења из „неактиван“ у „активан“ и он почиње да тражи клијенте који одговарају дефиницији сегмента.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-167">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="5a3fe-168">Ако је [заказано освежавање](system.md#schedule-tab) конфигурисано, неактивни сегменти имају **Статус** наведен као **Прескочено**, што указује да освежавање није ни покушано.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-168">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="5a3fe-169">Када се активира неактивни сегмент, освежиће се и биће укључен у заказана освежавања.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-169">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="5a3fe-170">Алтернативно, можете да користите функционалност **Испланирај за касније** у падајућој листи **Активирај/Деактивирај** да наведете будући датум и време за активацију и деактивацију одређеног сегмента.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-170">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="5a3fe-171">**Преименујте** сегмент.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-171">**Rename** the segment.</span></span>
- <span data-ttu-id="5a3fe-172">**Преузмите** листу чланова као .CSV датотеку.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-172">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="5a3fe-173">Опција **Додај у** шаље листу ID-ова клијената у сегменту на обраду у другој апликацији.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-173">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="5a3fe-174">**Избришите** сегмент.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-174">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="5a3fe-175">Освежавање сегмената</span><span class="sxs-lookup"><span data-stu-id="5a3fe-175">Refresh segments</span></span>

<span data-ttu-id="5a3fe-176">Можете да освежите све сегменте одједном ако изаберете **Освежите све** на страници **Сегменти**, а можете и да освежити један или више сегмената када их изаберете, па одаберете **Освежи** из опција.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-176">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="5a3fe-177">Алтернативно, можете конфигурисати понављајуће освежавање у одељку **Администратор** > **Систем** > **Распоред**.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-177">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="5a3fe-178">Постоји [шест врста статуса](system.md#status-types) за задатке/процесе.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-178">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="5a3fe-179">Уз то, већина процеса [зависи од других процеса на нижем току](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="5a3fe-179">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="5a3fe-180">Можете изабрати статус процеса да бисте видели детаље о току целог посла.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-180">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="5a3fe-181">Након избора опције **Види детаље** за један од задатака посла пронаћи ћете додатне информације: време обраде, датум последње обраде и све грешке и упозорења повезана са задатком.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-181">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="5a3fe-182">Преузимање и извоз сегмената</span><span class="sxs-lookup"><span data-stu-id="5a3fe-182">Download and export segments</span></span>

<span data-ttu-id="5a3fe-183">Можете преузети своје сегменте у CSV датотеку или их извести у Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-183">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="5a3fe-184">Преузмите сегменте у CSV датотеку</span><span class="sxs-lookup"><span data-stu-id="5a3fe-184">Download segments to a CSV file</span></span>

1. <span data-ttu-id="5a3fe-185">У увидима о корисницима идите на страницу **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-185">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="5a3fe-186">Изаберите три тачке на плочици одређеног сегмента.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-186">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="5a3fe-187">Изаберите **Преузми као CSV** са падајуће листе радњи.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-187">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="5a3fe-188">Извоз сегмената у Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="5a3fe-188">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="5a3fe-189">Пре извоза сегмената у Dynamics 365 Sales, администратор треба [креирај одредиште за извоз](export-destinations.md) за Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-189">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="5a3fe-190">У увидима о корисницима идите на страницу **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-190">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="5a3fe-191">Изаберите три тачке на плочици одређеног сегмента.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-191">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="5a3fe-192">Изаберите **Додај у** из падајуће листе радњи и изаберите одредиште за извоз у које желите да пошаљете податке.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-192">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="5a3fe-193">Режим радне верзије за сегменте</span><span class="sxs-lookup"><span data-stu-id="5a3fe-193">Draft mode for segments</span></span>

<span data-ttu-id="5a3fe-194">Ако нису испуњени сви захтеви за обраду сегмента, можете да сачувате сегмент као радну верзију и приступите му са странице **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-194">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="5a3fe-195">Биће сачуван као неактиван сегмент и нећете моћи да га активирате док не постане важећи.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-195">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="5a3fe-196">Додајте више услова групи</span><span class="sxs-lookup"><span data-stu-id="5a3fe-196">Add more conditions to a group</span></span>

<span data-ttu-id="5a3fe-197">Да бисте групи додали више услова, можете да користите два логичка оператора:</span><span class="sxs-lookup"><span data-stu-id="5a3fe-197">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="5a3fe-198">Оператор **И**: Оба услова морају да буду испуњена као део процеса сегментације.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-198">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="5a3fe-199">Ова опција је најкориснија када дефинишете услове у различитим ентитетима.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-199">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="5a3fe-200">Оператор **ИЛИ**: Било који од услова мора бити испуњен као део процеса сегментације.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-200">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="5a3fe-201">Ова опција је најкориснија када дефинишете више услова у истом ентитету.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-201">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5a3fe-202">![Оператор ИЛИ где је потребно испунити било који услов](media/segmentation-either-condition.png "Оператор ИЛИ где је потребно испунити било који услов")</span><span class="sxs-lookup"><span data-stu-id="5a3fe-202">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="5a3fe-203">Тренутно је могуће угнездити оператор **ИЛИ** унутар оператора **И**, али не и обрнуто.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-203">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="5a3fe-204">Комбиновање више група</span><span class="sxs-lookup"><span data-stu-id="5a3fe-204">Combine multiple groups</span></span>

<span data-ttu-id="5a3fe-205">Свака група производи одређени скуп клијената.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-205">Each group produces a specific set of customers.</span></span> <span data-ttu-id="5a3fe-206">Можете комбиновати ове групе да бисте укључили клијенте потребне за ваш предмет пословања.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-206">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="5a3fe-207">У увидима о клијентима идите на страницу **Сегменти** и изаберите сегмент.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-207">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="5a3fe-208">Изаберите **Додај групу**.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-208">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5a3fe-209">![Група клијената додај групу](media/customer-group-add-group.png "Група клијената додај групу")</span><span class="sxs-lookup"><span data-stu-id="5a3fe-209">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="5a3fe-210">Изаберите један од следећих скупа оператора: **Унија**, **Пресек** или **Изузимање**.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-210">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5a3fe-211">![Група клијената додај унију](media/customer-group-union.png "Група клијената додај унију")</span><span class="sxs-lookup"><span data-stu-id="5a3fe-211">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="5a3fe-212">Изаберите оператор скупа да бисте дефинисали нову групу.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-212">Select a set operator to define a new group.</span></span> <span data-ttu-id="5a3fe-213">Чување различитих група ради одређивања који подаци се задржавају:</span><span class="sxs-lookup"><span data-stu-id="5a3fe-213">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="5a3fe-214">**Унија** обједињује две групе.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-214">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="5a3fe-215">**Пресек** преклапа две групе.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-215">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="5a3fe-216">Само подаци који *су заједнички* за обе групе задржавају се у обједињеној групи.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-216">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="5a3fe-217">**Осим** комбинује две групе.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-217">**Except** combines the two groups.</span></span> <span data-ttu-id="5a3fe-218">Само подаци у групи А који *нису заједнички* са подацима из групе Б задржавају се.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-218">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="5a3fe-219">Погледајте историју обраде и чланове сегмента</span><span class="sxs-lookup"><span data-stu-id="5a3fe-219">View processing history and segment members</span></span>

<span data-ttu-id="5a3fe-220">Консолидоване податке о сегменту можете видети тако што ћете прегледати његове детаље.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-220">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="5a3fe-221">На страници **Сегменти** изаберите сегмент који желите да прегледате.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-221">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="5a3fe-222">Горњи део странице садржи графикон тренда који визуелно приказује промене у броју чланова.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-222">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="5a3fe-223">Задржите показивач изнад тачака података да бисте видели број чланова одређеног датума.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-223">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="5a3fe-224">Можете да ажурирате временски оквир визуелизације.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-224">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5a3fe-225">![Временски период сегмента](media/segment-time-range.png "Временски период сегмента")</span><span class="sxs-lookup"><span data-stu-id="5a3fe-225">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="5a3fe-226">Доњи део садржи листу чланова сегмента.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-226">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="5a3fe-227">Поља која се појављују на овој листи заснивају се на атрибутима ентитета вашег сегмента.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-227">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="5a3fe-228">Листа је преглед одговарајућих чланова сегмента и показује првих 100 записа вашег сегмента тако да га можете брзо проценити и прегледати његове дефиниције, ако је потребно.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-228">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="5a3fe-229">Да бисте видели све одговарајуће записе, морате да [извезете сегмент](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="5a3fe-229">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="5a3fe-230">Брзи сегменти</span><span class="sxs-lookup"><span data-stu-id="5a3fe-230">Quick segments</span></span>

<span data-ttu-id="5a3fe-231">Поред алатке за прављење сегмената, постоји још један пут за креирање сегмената.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-231">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="5a3fe-232">Брзи сегменти вам омогућавају да направите једноставне сегменте, са једним оператором, брзо и уз тренутне увиде.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-232">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="5a3fe-233">На страници **Сегменти** изаберите **Нова** > **Брзо креирајте од**.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-233">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="5a3fe-234">Изаберите опцију **Профили** за изградњу сегмента који је заснован на обједињеном ентитету Клијент.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-234">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="5a3fe-235">Изаберите опцију **Мере** за изградњу сегмента око сваке врсте мера атрибута клијента које сте претходно креирали на страници **Мере**.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-235">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="5a3fe-236">Изаберите опцију **Обавештавање** да изградите сегмент око једног од излазних ентитета које сте генерисали користећи могућности **Предвиђања** или **Прилагођени модели**.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-236">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="5a3fe-237">У дијалогу **Нови брзи сегмент** изаберите атрибут из падајуће листе **Поље**.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-237">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="5a3fe-238">Систем ће вам пружити неке додатне увиде који ће вам помоћи да створите боље сегменте својих клијената.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-238">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="5a3fe-239">За категоријска поља приказаћемо 10 главних бројева клијента.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-239">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="5a3fe-240">Одаберите **Вредност** и изабрали **Преглед**.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-240">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="5a3fe-241">За нумерички атрибут, систем ће показати која вредност атрибута спада испод сваког процента клијента.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-241">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="5a3fe-242">Одаберите **Оператор** и **Вредност**, а затим изаберите **Преглед**.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-242">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="5a3fe-243">Систем ће вам пружити **Процењену величину сегмента**.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-243">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="5a3fe-244">Можете одабрати да ли да генеришете сегмент који сте дефинисали или да га прво прегледате како бисте добили другу величину сегмента.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-244">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5a3fe-245">![Назив и процена за брзи сегмент](media/quick-segment-name.png "Назив и процена за брзи сегмент")</span><span class="sxs-lookup"><span data-stu-id="5a3fe-245">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="5a3fe-246">Наведите **Назив** за сегмент.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-246">Provide a **Name** for your segment.</span></span> <span data-ttu-id="5a3fe-247">Опционално, наведите **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-247">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="5a3fe-248">Изаберите **Сачувај** да бисте креирали сегмент.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-248">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="5a3fe-249">Након завршетка обраде сегмента, можете га прегледати као и било који други сегмент који сте креирали.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-249">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="5a3fe-250">За следеће сценарије, саветујемо употребу алата за прављење сегмената уместо препоручених могућности сегмената:</span><span class="sxs-lookup"><span data-stu-id="5a3fe-250">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="5a3fe-251">Стварање сегмената са филтерима на категоријским пољима где је оператор другачији од оператора **Да ли је**</span><span class="sxs-lookup"><span data-stu-id="5a3fe-251">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="5a3fe-252">Креирање сегмената са филтерима на нумеричким пољима где је оператор другачији од оператора **Између**, **Веће од** и **Мање од**</span><span class="sxs-lookup"><span data-stu-id="5a3fe-252">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="5a3fe-253">Креирање сегмената са филтерима на пољима типа датума</span><span class="sxs-lookup"><span data-stu-id="5a3fe-253">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="5a3fe-254">Следећи кораци</span><span class="sxs-lookup"><span data-stu-id="5a3fe-254">Next steps</span></span>

<span data-ttu-id="5a3fe-255">[Извезите сегмент](export-destinations.md) и истражите [картицу клијента](customer-card-add-in.md) и [конекторе](export-power-bi.md) да бисте добили увид на нивоу клијента.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-255">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]