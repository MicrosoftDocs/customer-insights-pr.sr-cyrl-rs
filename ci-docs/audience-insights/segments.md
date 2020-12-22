---
title: Креирање сегмената и управљање њима
description: Направите сегменте клијената да бисте их груписали на основу различитих атрибута.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 6931110c2ae93cd2792d319aa5a34f0df3088552
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406885"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="2097c-103">Креирање сегмената и управљање њима</span><span class="sxs-lookup"><span data-stu-id="2097c-103">Create and manage segments</span></span>

<span data-ttu-id="2097c-104">Сегменти вам омогућавају да групишете клијенте на основу демографских, трансакционих или атрибута понашања.</span><span class="sxs-lookup"><span data-stu-id="2097c-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="2097c-105">Можете да користите сегменте за циљање промотивних кампања, продајних активности и активности подршке клијената како бисте постигли своје пословне циљеве.</span><span class="sxs-lookup"><span data-stu-id="2097c-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="2097c-106">Можете дефинисати сложене филтере око ентитета Профил клијента и с њим повезаних ентитета.</span><span class="sxs-lookup"><span data-stu-id="2097c-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="2097c-107">Сваки сегмент након обраде креира скуп корисничких записа које можете да извозити и за које можете да предузимате неке кораке.</span><span class="sxs-lookup"><span data-stu-id="2097c-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="2097c-108">Нека [ограничења услуга](service-limits.md) се примењују.</span><span class="sxs-lookup"><span data-stu-id="2097c-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="2097c-109">Ако није другачије назначено, сви сегменти су **Динамички сегменти**, који се освежавају по редовном распореду.</span><span class="sxs-lookup"><span data-stu-id="2097c-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="2097c-110">Следећи пример илуструје коришћење могућности сегментације.</span><span class="sxs-lookup"><span data-stu-id="2097c-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="2097c-111">Дефинисали смо сегмент за клијенте који су наручили робу за најмање 500 USD у последњих 90 дана *и* који су били укључени у позив корисничке службе који је прослеђен.</span><span class="sxs-lookup"><span data-stu-id="2097c-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2097c-112">![Више група](media/segmentation-group1-2.png "Више група")</span><span class="sxs-lookup"><span data-stu-id="2097c-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="2097c-113">Креирајте нови сегмент</span><span class="sxs-lookup"><span data-stu-id="2097c-113">Create a new segment</span></span>

<span data-ttu-id="2097c-114">Сегментима се управља на страници **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="2097c-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="2097c-115">У увидима о корисницима идите на страницу **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="2097c-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="2097c-116">Изаберите **Ново** > **Празан сегмент**.</span><span class="sxs-lookup"><span data-stu-id="2097c-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="2097c-117">У окну **Нови сегмент** одаберите тип сегмента и наведите **Име**.</span><span class="sxs-lookup"><span data-stu-id="2097c-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="2097c-118">Опционално, унесите име за приказ и опис који помаже у препознавању сегмента.</span><span class="sxs-lookup"><span data-stu-id="2097c-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="2097c-119">Изаберите **Следеће** да дођете на страницу **Градитељ сегмената** на којој дефинишете групу.</span><span class="sxs-lookup"><span data-stu-id="2097c-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="2097c-120">Група је скуп клијената.</span><span class="sxs-lookup"><span data-stu-id="2097c-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="2097c-121">Одаберите ентитет који обухвата атрибуте по којима желите да сегментирате.</span><span class="sxs-lookup"><span data-stu-id="2097c-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="2097c-122">Одаберите атрибут по сегменту.</span><span class="sxs-lookup"><span data-stu-id="2097c-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="2097c-123">Овај атрибут може имати један од четири типа вредности: нумерички, ниска, датум или логички.</span><span class="sxs-lookup"><span data-stu-id="2097c-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="2097c-124">Одаберите оператор и вредност за изабрани атрибут.</span><span class="sxs-lookup"><span data-stu-id="2097c-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2097c-125">![Прилагођени филтер групе](media/customer-group-numbers.png "Филтер групе клијената")</span><span class="sxs-lookup"><span data-stu-id="2097c-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="2097c-126">Број</span><span class="sxs-lookup"><span data-stu-id="2097c-126">Number</span></span> |<span data-ttu-id="2097c-127">Дефиниција</span><span class="sxs-lookup"><span data-stu-id="2097c-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="2097c-128">1</span><span class="sxs-lookup"><span data-stu-id="2097c-128">1</span></span>     |<span data-ttu-id="2097c-129">Entity</span><span class="sxs-lookup"><span data-stu-id="2097c-129">Entity</span></span>          |
   |<span data-ttu-id="2097c-130">2</span><span class="sxs-lookup"><span data-stu-id="2097c-130">2</span></span>     |<span data-ttu-id="2097c-131">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2097c-131">Attribute</span></span>          |
   |<span data-ttu-id="2097c-132">3</span><span class="sxs-lookup"><span data-stu-id="2097c-132">3</span></span>    |<span data-ttu-id="2097c-133">Оператор</span><span class="sxs-lookup"><span data-stu-id="2097c-133">Operator</span></span>         |
   |<span data-ttu-id="2097c-134">4</span><span class="sxs-lookup"><span data-stu-id="2097c-134">4</span></span>    |<span data-ttu-id="2097c-135">Вредност</span><span class="sxs-lookup"><span data-stu-id="2097c-135">Value</span></span>         |

8. <span data-ttu-id="2097c-136">Ако је ентитет повезан путем обједињеног ентитета клијента путем [односа](relationships.md), морате дефинисати путању односа да бисте креирали важећи сегмент.</span><span class="sxs-lookup"><span data-stu-id="2097c-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="2097c-137">Додајте ентитете из путање односа док не будете могли да изаберете ентитет **Клијент: CustomerInsights** из падајуће листе.</span><span class="sxs-lookup"><span data-stu-id="2097c-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="2097c-138">Затим одаберите **Сви записи** за сваки услов.</span><span class="sxs-lookup"><span data-stu-id="2097c-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2097c-139">![Путања односа током креирања сегмента](media/segments-multiple-relationships.png "Путања односа током креирања сегмента")</span><span class="sxs-lookup"><span data-stu-id="2097c-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="2097c-140">Изаберите **Сачувај** да бисте сачували сегмент.</span><span class="sxs-lookup"><span data-stu-id="2097c-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="2097c-141">Ваш сегмент ће бити сачуван и обрађен уколико су сви захтеви потврђени.</span><span class="sxs-lookup"><span data-stu-id="2097c-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="2097c-142">У супротном, биће сачуван као радна верзија.</span><span class="sxs-lookup"><span data-stu-id="2097c-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="2097c-143">Изаберите **Назад на сегменте** да бисте се вратили на страницу **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="2097c-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="2097c-144">Управљање постојећим сегментима</span><span class="sxs-lookup"><span data-stu-id="2097c-144">Manage existing segments</span></span>

<span data-ttu-id="2097c-145">На страници **Сегменти**, можете видети све сачуване сегменте и њима управљати.</span><span class="sxs-lookup"><span data-stu-id="2097c-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="2097c-146">Сваки сегмент представљен је редом који садржи додатне информације о сегменту.</span><span class="sxs-lookup"><span data-stu-id="2097c-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="2097c-147">Сегменте можете сортирати у колони одабиром наслова колоне.</span><span class="sxs-lookup"><span data-stu-id="2097c-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="2097c-148">Користите поље **Претрага** у горњем десном углу да бисте филтрирали сегменте.</span><span class="sxs-lookup"><span data-stu-id="2097c-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2097c-149">![Опције за управљање постојећим сегментом](media/segments-selected-segment.png "Опције за управљање постојећим сегментом")</span><span class="sxs-lookup"><span data-stu-id="2097c-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="2097c-150">Следећа радња је доступна када одаберете сегмент:</span><span class="sxs-lookup"><span data-stu-id="2097c-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="2097c-151">**Приказ** детаља сегмента, укључујући тренд броја чланова, преглед чланова сегмента.</span><span class="sxs-lookup"><span data-stu-id="2097c-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="2097c-152">**Уредите** сегмент да бисте променили његова својства.</span><span class="sxs-lookup"><span data-stu-id="2097c-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="2097c-153">**Освежите** сегмент тако да укључује најновије податке.</span><span class="sxs-lookup"><span data-stu-id="2097c-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="2097c-154">**Активирајте** или **Деактивирајте** сегмент.</span><span class="sxs-lookup"><span data-stu-id="2097c-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="2097c-155">Сегменти имају два могућа стања - активно или неактивно.</span><span class="sxs-lookup"><span data-stu-id="2097c-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="2097c-156">Ова стања добро дођу приликом уређивања сегмента.</span><span class="sxs-lookup"><span data-stu-id="2097c-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="2097c-157">За неактивне сегменте дефиниција сегмента постоји, али још увек не садржи клијенте.</span><span class="sxs-lookup"><span data-stu-id="2097c-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="2097c-158">Када активирате сегмент, његово стање се мења из „неактиван“ у „активан“ и он почиње да тражи клијенте који одговарају дефиницији сегмента.</span><span class="sxs-lookup"><span data-stu-id="2097c-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="2097c-159">Ако је [заказано освежавање](system.md#schedule-tab) конфигурисано, неактивни сегменти имају **Статус** наведен као **Прескочено**, што указује да освежавање није ни покушано.</span><span class="sxs-lookup"><span data-stu-id="2097c-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="2097c-160">Када се активира неактивни сегмент, освежиће се и биће укључен у заказана освежавања.</span><span class="sxs-lookup"><span data-stu-id="2097c-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="2097c-161">Алтернативно, можете да користите функционалност **Испланирај за касније** у падајућој листи **Активирај/Деактивирај** да наведете будући датум и време за активацију и деактивацију одређеног сегмента.</span><span class="sxs-lookup"><span data-stu-id="2097c-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="2097c-162">**Преименујте** сегмент.</span><span class="sxs-lookup"><span data-stu-id="2097c-162">**Rename** the segment.</span></span>
- <span data-ttu-id="2097c-163">**Преузмите** листу чланова као .CSV датотеку.</span><span class="sxs-lookup"><span data-stu-id="2097c-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="2097c-164">Опција **Додај у** шаље листу ID-ова клијената у сегменту на обраду у другој апликацији.</span><span class="sxs-lookup"><span data-stu-id="2097c-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="2097c-165">**Избришите** сегмент.</span><span class="sxs-lookup"><span data-stu-id="2097c-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="2097c-166">Освежавање сегмената</span><span class="sxs-lookup"><span data-stu-id="2097c-166">Refresh segments</span></span>

<span data-ttu-id="2097c-167">Можете да освежите све сегменте одједном ако изаберете **Освежите све** на страници **Сегменти**, а можете и да освежити један или више сегмената када их изаберете, па одаберете **Освежи** из опција.</span><span class="sxs-lookup"><span data-stu-id="2097c-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="2097c-168">Алтернативно, можете конфигурисати понављајуће освежавање у одељку **Администратор** > **Систем** > **Распоред**.</span><span class="sxs-lookup"><span data-stu-id="2097c-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="2097c-169">Постоји [шест врста статуса](system.md#status-types) за задатке/процесе.</span><span class="sxs-lookup"><span data-stu-id="2097c-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="2097c-170">Уз то, већина процеса [зависи од других процеса на нижем току](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="2097c-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="2097c-171">Можете изабрати статус процеса да бисте видели детаље о току целог посла.</span><span class="sxs-lookup"><span data-stu-id="2097c-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="2097c-172">Након избора опције **Види детаље** за један од задатака посла пронаћи ћете додатне информације: време обраде, датум последње обраде и све грешке и упозорења повезана са задатком.</span><span class="sxs-lookup"><span data-stu-id="2097c-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="2097c-173">Преузимање и извоз сегмената</span><span class="sxs-lookup"><span data-stu-id="2097c-173">Download and export segments</span></span>

<span data-ttu-id="2097c-174">Можете преузети своје сегменте у CSV датотеку или их извести у Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="2097c-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="2097c-175">Преузмите сегменте у CSV датотеку</span><span class="sxs-lookup"><span data-stu-id="2097c-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="2097c-176">У увидима о корисницима идите на страницу **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="2097c-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="2097c-177">Изаберите три тачке на плочици одређеног сегмента.</span><span class="sxs-lookup"><span data-stu-id="2097c-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="2097c-178">Изаберите **Преузми као CSV** са падајуће листе радњи.</span><span class="sxs-lookup"><span data-stu-id="2097c-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="2097c-179">Извоз сегмената у Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="2097c-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="2097c-180">Пре извоза сегмената у Dynamics 365 Sales, администратор треба [креирај одредиште за извоз](export-destinations.md) за Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="2097c-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="2097c-181">У увидима о корисницима идите на страницу **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="2097c-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="2097c-182">Изаберите три тачке на плочици одређеног сегмента.</span><span class="sxs-lookup"><span data-stu-id="2097c-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="2097c-183">Изаберите **Додај у** из падајуће листе радњи и изаберите одредиште за извоз у које желите да пошаљете податке.</span><span class="sxs-lookup"><span data-stu-id="2097c-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="2097c-184">Режим радне верзије за сегменте</span><span class="sxs-lookup"><span data-stu-id="2097c-184">Draft mode for segments</span></span>

<span data-ttu-id="2097c-185">Ако нису испуњени сви захтеви за обраду сегмента, можете да сачувате сегмент као радну верзију и приступите му са странице **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="2097c-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="2097c-186">Биће сачуван као неактиван сегмент и нећете моћи да га активирате док не постане важећи.</span><span class="sxs-lookup"><span data-stu-id="2097c-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="2097c-187">Додајте више услова групи</span><span class="sxs-lookup"><span data-stu-id="2097c-187">Add more conditions to a group</span></span>

<span data-ttu-id="2097c-188">Да бисте групи додали више услова, можете да користите два логичка оператора:</span><span class="sxs-lookup"><span data-stu-id="2097c-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="2097c-189">Оператор **И**: Оба услова морају да буду испуњена као део процеса сегментације.</span><span class="sxs-lookup"><span data-stu-id="2097c-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="2097c-190">Ова опција је најкориснија када дефинишете услове у различитим ентитетима.</span><span class="sxs-lookup"><span data-stu-id="2097c-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="2097c-191">Оператор **ИЛИ**: Било који од услова мора бити испуњен као део процеса сегментације.</span><span class="sxs-lookup"><span data-stu-id="2097c-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="2097c-192">Ова опција је најкориснија када дефинишете више услова у истом ентитету.</span><span class="sxs-lookup"><span data-stu-id="2097c-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2097c-193">![Оператор ИЛИ где је потребно испунити било који услов](media/segmentation-either-condition.png "Оператор ИЛИ где је потребно испунити било који услов")</span><span class="sxs-lookup"><span data-stu-id="2097c-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="2097c-194">Тренутно је могуће угнездити оператор **ИЛИ** унутар оператора **И**, али не и обрнуто.</span><span class="sxs-lookup"><span data-stu-id="2097c-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="2097c-195">Комбиновање више група</span><span class="sxs-lookup"><span data-stu-id="2097c-195">Combine multiple groups</span></span>

<span data-ttu-id="2097c-196">Свака група производи одређени скуп клијената.</span><span class="sxs-lookup"><span data-stu-id="2097c-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="2097c-197">Можете комбиновати ове групе да бисте укључили клијенте потребне за ваш предмет пословања.</span><span class="sxs-lookup"><span data-stu-id="2097c-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="2097c-198">У увидима о клијентима идите на страницу **Сегменти** и изаберите сегмент.</span><span class="sxs-lookup"><span data-stu-id="2097c-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="2097c-199">Изаберите **Додај групу**.</span><span class="sxs-lookup"><span data-stu-id="2097c-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2097c-200">![Група клијената додај групу](media/customer-group-add-group.png "Група клијената додај групу")</span><span class="sxs-lookup"><span data-stu-id="2097c-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="2097c-201">Изаберите један од следећих скупа оператора: **Унија**, **Пресек** или **Изузимање**.</span><span class="sxs-lookup"><span data-stu-id="2097c-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2097c-202">![Група клијената додај унију](media/customer-group-union.png "Група клијената додај унију")</span><span class="sxs-lookup"><span data-stu-id="2097c-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="2097c-203">Изаберите оператор скупа да бисте дефинисали нову групу.</span><span class="sxs-lookup"><span data-stu-id="2097c-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="2097c-204">Чување различитих група ради одређивања који подаци се задржавају:</span><span class="sxs-lookup"><span data-stu-id="2097c-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="2097c-205">**Унија** обједињује две групе.</span><span class="sxs-lookup"><span data-stu-id="2097c-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="2097c-206">**Пресек** преклапа две групе.</span><span class="sxs-lookup"><span data-stu-id="2097c-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="2097c-207">Само подаци који *су заједнички* за обе групе задржавају се у обједињеној групи.</span><span class="sxs-lookup"><span data-stu-id="2097c-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="2097c-208">**Осим** комбинује две групе.</span><span class="sxs-lookup"><span data-stu-id="2097c-208">**Except** combines the two groups.</span></span> <span data-ttu-id="2097c-209">Само подаци у групи А који *нису заједнички* са подацима из групе Б задржавају се.</span><span class="sxs-lookup"><span data-stu-id="2097c-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="2097c-210">Погледајте историју обраде и чланове сегмента</span><span class="sxs-lookup"><span data-stu-id="2097c-210">View processing history and segment members</span></span>

<span data-ttu-id="2097c-211">Консолидоване податке о сегменту можете видети тако што ћете прегледати његове детаље.</span><span class="sxs-lookup"><span data-stu-id="2097c-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="2097c-212">На страници **Сегменти** изаберите сегмент који желите да прегледате.</span><span class="sxs-lookup"><span data-stu-id="2097c-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="2097c-213">Горњи део странице садржи графикон тренда који визуелно приказује промене у броју чланова.</span><span class="sxs-lookup"><span data-stu-id="2097c-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="2097c-214">Задржите показивач изнад тачака података да бисте видели број чланова одређеног датума.</span><span class="sxs-lookup"><span data-stu-id="2097c-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="2097c-215">Можете да ажурирате временски оквир визуелизације.</span><span class="sxs-lookup"><span data-stu-id="2097c-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2097c-216">![Временски период сегмента](media/segment-time-range.png "Временски период сегмента")</span><span class="sxs-lookup"><span data-stu-id="2097c-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="2097c-217">Доњи део садржи листу чланова сегмента.</span><span class="sxs-lookup"><span data-stu-id="2097c-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="2097c-218">Поља која се појављују на овој листи заснивају се на атрибутима ентитета вашег сегмента.</span><span class="sxs-lookup"><span data-stu-id="2097c-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="2097c-219">Листа је преглед одговарајућих чланова сегмента и показује првих 100 записа вашег сегмента тако да га можете брзо проценити и прегледати његове дефиниције, ако је потребно.</span><span class="sxs-lookup"><span data-stu-id="2097c-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="2097c-220">Да бисте видели све одговарајуће записе, морате да [извезете сегмент](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="2097c-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="2097c-221">Брзи сегменти</span><span class="sxs-lookup"><span data-stu-id="2097c-221">Quick segments</span></span>

<span data-ttu-id="2097c-222">Поред алатке за прављење сегмената, постоји још један пут за креирање сегмената.</span><span class="sxs-lookup"><span data-stu-id="2097c-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="2097c-223">Брзи сегменти вам омогућавају да направите једноставне сегменте, са једним оператором, брзо и уз тренутне увиде.</span><span class="sxs-lookup"><span data-stu-id="2097c-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="2097c-224">На страници **Сегменти** изаберите **Нова** > **Брзо креирајте од**.</span><span class="sxs-lookup"><span data-stu-id="2097c-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="2097c-225">Изаберите опцију **Профили** за изградњу сегмента који је заснован на обједињеном ентитету Клијент.</span><span class="sxs-lookup"><span data-stu-id="2097c-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="2097c-226">Изаберите опцију **Мере** за изградњу сегмента око сваке врсте мера атрибута клијента које сте претходно креирали на страници **Мере**.</span><span class="sxs-lookup"><span data-stu-id="2097c-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="2097c-227">Изаберите опцију **Обавештавање** да изградите сегмент око једног од излазних ентитета које сте генерисали користећи могућности **Предвиђања** или **Прилагођени модели**.</span><span class="sxs-lookup"><span data-stu-id="2097c-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="2097c-228">У дијалогу **Нови брзи сегмент** изаберите атрибут из падајуће листе **Поље**.</span><span class="sxs-lookup"><span data-stu-id="2097c-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="2097c-229">Систем ће вам пружити неке додатне увиде који ће вам помоћи да створите боље сегменте својих клијената.</span><span class="sxs-lookup"><span data-stu-id="2097c-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="2097c-230">За категоријска поља приказаћемо 10 главних бројева клијента.</span><span class="sxs-lookup"><span data-stu-id="2097c-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="2097c-231">Одаберите **Вредност** и изабрали **Преглед**.</span><span class="sxs-lookup"><span data-stu-id="2097c-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="2097c-232">За нумерички атрибут, систем ће показати која вредност атрибута спада испод сваког процента клијента.</span><span class="sxs-lookup"><span data-stu-id="2097c-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="2097c-233">Одаберите **Оператор** и **Вредност**, а затим изаберите **Преглед**.</span><span class="sxs-lookup"><span data-stu-id="2097c-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="2097c-234">Систем ће вам пружити **Процењену величину сегмента**.</span><span class="sxs-lookup"><span data-stu-id="2097c-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="2097c-235">Можете одабрати да ли да генеришете сегмент који сте дефинисали или да га прво прегледате како бисте добили другу величину сегмента.</span><span class="sxs-lookup"><span data-stu-id="2097c-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2097c-236">![Назив и процена за брзи сегмент](media/quick-segment-name.png "Назив и процена за брзи сегмент")</span><span class="sxs-lookup"><span data-stu-id="2097c-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="2097c-237">Наведите **Назив** за сегмент.</span><span class="sxs-lookup"><span data-stu-id="2097c-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="2097c-238">Опционално, наведите **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="2097c-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="2097c-239">Изаберите **Сачувај** да бисте креирали сегмент.</span><span class="sxs-lookup"><span data-stu-id="2097c-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="2097c-240">Након завршетка обраде сегмента, можете га прегледати као и било који други сегмент који сте креирали.</span><span class="sxs-lookup"><span data-stu-id="2097c-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="2097c-241">За следеће сценарије, саветујемо употребу алата за прављење сегмената уместо препоручених могућности сегмената:</span><span class="sxs-lookup"><span data-stu-id="2097c-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="2097c-242">Стварање сегмената са филтерима на категоријским пољима где је оператор другачији од оператора **Да ли је**</span><span class="sxs-lookup"><span data-stu-id="2097c-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="2097c-243">Креирање сегмената са филтерима на нумеричким пољима где је оператор другачији од оператора **Између**, **Веће од** и **Мање од**</span><span class="sxs-lookup"><span data-stu-id="2097c-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="2097c-244">Креирање сегмената са филтерима на пољима типа датума</span><span class="sxs-lookup"><span data-stu-id="2097c-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="2097c-245">Следећи кораци</span><span class="sxs-lookup"><span data-stu-id="2097c-245">Next steps</span></span>

<span data-ttu-id="2097c-246">[Извезите сегмент](export-destinations.md) и истражите [картицу клијента](customer-card-add-in.md) и [конекторе](export-power-bi.md) да бисте добили увид на нивоу клијента.</span><span class="sxs-lookup"><span data-stu-id="2097c-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>
