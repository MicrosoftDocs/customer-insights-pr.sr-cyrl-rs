---
title: Сегменти у увидима у циљну групу
description: Преглед сегмената и начин креирања и управљања њима.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 336cab8619c0b80b7b8a38035cae99620baf2873
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306275"
---
# <a name="segments-overview"></a><span data-ttu-id="afaa9-103">Преглед сегмената</span><span class="sxs-lookup"><span data-stu-id="afaa9-103">Segments overview</span></span>

<span data-ttu-id="afaa9-104">Сегменти вам омогућавају да групишете клијенте на основу демографских, трансакционих или атрибута понашања.</span><span class="sxs-lookup"><span data-stu-id="afaa9-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="afaa9-105">Можете да користите сегменте за циљање промотивних кампања, продајних активности и активности подршке клијената како бисте постигли своје пословне циљеве.</span><span class="sxs-lookup"><span data-stu-id="afaa9-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="afaa9-106">Кориснички профили који се подударају са филтерима дефиниције сегмента називају се *члановима* сегмента.</span><span class="sxs-lookup"><span data-stu-id="afaa9-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="afaa9-107">Нека [ограничења услуга](service-limits.md) се примењују.</span><span class="sxs-lookup"><span data-stu-id="afaa9-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="afaa9-108">Креирајте нови сегмент</span><span class="sxs-lookup"><span data-stu-id="afaa9-108">Create a new segment</span></span>

<span data-ttu-id="afaa9-109">Постоји више начина за креирање новог сегмента:</span><span class="sxs-lookup"><span data-stu-id="afaa9-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="afaa9-110">Сложени сегмент са креатором сегмената: [Празан сегмент](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="afaa9-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="afaa9-111">Једноставни сегменти са једним оператором: [Брзи сегмент](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="afaa9-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="afaa9-112">Начин омогућен вештачком интелигенцијом за проналажење сличних клијената: [Слични клијенти](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="afaa9-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="afaa9-113">Предлози омогућени вештачком интелигенцијом засновани на мерама или атрибутима: [Предложени сегменти за побољшање мера](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="afaa9-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="afaa9-114">Предлози засновани на активностима: [Предложени сегменти на основу активности клијената](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="afaa9-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="afaa9-115">Управљање постојећим сегментима</span><span class="sxs-lookup"><span data-stu-id="afaa9-115">Manage existing segments</span></span>

<span data-ttu-id="afaa9-116">Идите на страницу **Сегменти** да бисте приказали све сачуване сегменте и управљали њима.</span><span class="sxs-lookup"><span data-stu-id="afaa9-116">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="afaa9-117">Сваки сегмент представљен је редом који садржи додатне информације о сегменту.</span><span class="sxs-lookup"><span data-stu-id="afaa9-117">Each segment is represented by a row that includes additional information about the segment.</span></span>

:::image type="content" source="media/segments-selected-segment.png" alt-text="Изабрани сегмент са падајућом листом опција и доступним опцијама.":::

<span data-ttu-id="afaa9-119">Следећа радња је доступна када одаберете сегмент:</span><span class="sxs-lookup"><span data-stu-id="afaa9-119">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="afaa9-120">**Приказ** детаља сегмента, укључујући тренд броја чланова, преглед чланова сегмента.</span><span class="sxs-lookup"><span data-stu-id="afaa9-120">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="afaa9-121">**Уредите** сегмент да бисте променили његова својства.</span><span class="sxs-lookup"><span data-stu-id="afaa9-121">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="afaa9-122">**Направите дупликат** сегмента.</span><span class="sxs-lookup"><span data-stu-id="afaa9-122">**Create duplicate** of a segment.</span></span> <span data-ttu-id="afaa9-123">Можете одабрати да уредите његова својства или једноставно сачувате дупликат.</span><span class="sxs-lookup"><span data-stu-id="afaa9-123">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="afaa9-124">**Освежите** сегмент тако да укључује најновије податке.</span><span class="sxs-lookup"><span data-stu-id="afaa9-124">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="afaa9-125">**Активирајте** или **Деактивирајте** сегмент.</span><span class="sxs-lookup"><span data-stu-id="afaa9-125">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="afaa9-126">Сегменти имају два могућа стања - активно или неактивно.</span><span class="sxs-lookup"><span data-stu-id="afaa9-126">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="afaa9-127">Ова стања добро дођу приликом уређивања сегмента.</span><span class="sxs-lookup"><span data-stu-id="afaa9-127">These states come in handy when editing a segment.</span></span> <span data-ttu-id="afaa9-128">За неактивне сегменте дефиниција сегмента постоји, али још увек не садржи клијенте.</span><span class="sxs-lookup"><span data-stu-id="afaa9-128">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="afaa9-129">Када активирате сегмент, његово стање се мења из „неактиван“ у „активан“ и он почиње да тражи клијенте који одговарају дефиницији сегмента.</span><span class="sxs-lookup"><span data-stu-id="afaa9-129">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="afaa9-130">Ако је [заказано освежавање](system.md#schedule-tab) конфигурисано, неактивни сегменти имају **Статус** наведен као **Прескочено**, што указује да освежавање није ни покушано.</span><span class="sxs-lookup"><span data-stu-id="afaa9-130">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="afaa9-131">Када се активира неактивни сегмент, освежиће се и биће укључен у заказана освежавања.</span><span class="sxs-lookup"><span data-stu-id="afaa9-131">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="afaa9-132">Алтернативно, можете да користите функционалност **Испланирај за касније** у падајућој листи **Активирај/Деактивирај** да наведете будући датум и време за активацију и деактивацију одређеног сегмента.</span><span class="sxs-lookup"><span data-stu-id="afaa9-132">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="afaa9-133">**Преименујте** сегмент.</span><span class="sxs-lookup"><span data-stu-id="afaa9-133">**Rename** the segment.</span></span>
- <span data-ttu-id="afaa9-134">**Преузмите** листу чланова као .CSV датотеку.</span><span class="sxs-lookup"><span data-stu-id="afaa9-134">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="afaa9-135">**Управљање извозима** да бисте видели сегмент повезан са извозом и управљали њиме.</span><span class="sxs-lookup"><span data-stu-id="afaa9-135">**Manage exports** to see exports related segment and manage them.</span></span> [<span data-ttu-id="afaa9-136">Сазнајте више о извозима.</span><span class="sxs-lookup"><span data-stu-id="afaa9-136">Learn more about exports.</span></span>](export-destinations.md)
- <span data-ttu-id="afaa9-137">**Избришите** сегмент.</span><span class="sxs-lookup"><span data-stu-id="afaa9-137">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="afaa9-138">Освежавање сегмената</span><span class="sxs-lookup"><span data-stu-id="afaa9-138">Refresh segments</span></span>

<span data-ttu-id="afaa9-139">Можете да освежите све сегменте одједном ако изаберете **Освежите све** на страници **Сегменти**, а можете и да освежити један или више сегмената када их изаберете, па одаберете **Освежи** из опција.</span><span class="sxs-lookup"><span data-stu-id="afaa9-139">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="afaa9-140">Алтернативно, можете конфигурисати понављајуће освежавање у одељку **Администратор** > **Систем** > **Распоред**.</span><span class="sxs-lookup"><span data-stu-id="afaa9-140">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="afaa9-141">Постоји [шест врста статуса](system.md#status-types) за задатке/процесе.</span><span class="sxs-lookup"><span data-stu-id="afaa9-141">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="afaa9-142">Уз то, већина процеса [зависи од других процеса на нижем току](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="afaa9-142">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="afaa9-143">Можете изабрати статус процеса да бисте видели детаље о току целог посла.</span><span class="sxs-lookup"><span data-stu-id="afaa9-143">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="afaa9-144">Након избора опције **Види детаље** за један од задатака посла пронаћи ћете додатне информације: време обраде, датум последње обраде и све грешке и упозорења повезана са задатком.</span><span class="sxs-lookup"><span data-stu-id="afaa9-144">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="export-segments"></a><span data-ttu-id="afaa9-145">Извоз сегмената</span><span class="sxs-lookup"><span data-stu-id="afaa9-145">Export segments</span></span>

<span data-ttu-id="afaa9-146">Сегмент можете извести са странице сегмената или [страница извоза](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="afaa9-146">You can export a segment from the segments page or the [exports page](export-destinations.md).</span></span> 

1. <span data-ttu-id="afaa9-147">Идите на страницу **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="afaa9-147">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="afaa9-148">Изаберите **Прикажи још [...]** за сегмент који желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="afaa9-148">Select **Show more [...]** for the segment you want to export.</span></span>

1. <span data-ttu-id="afaa9-149">Изаберите **Управљање извозом** са падајуће листе радњи.</span><span class="sxs-lookup"><span data-stu-id="afaa9-149">Select **Manage exports** from the actions dropdown list.</span></span>

1. <span data-ttu-id="afaa9-150">Отвара се страница **Извози (преглед) за сегмент**.</span><span class="sxs-lookup"><span data-stu-id="afaa9-150">The page **Exports (preview) for segment** opens.</span></span> <span data-ttu-id="afaa9-151">Можете да видите све конфигурисане извозе груписане према извозима који садрже тренутни сегмент или га не садрже.</span><span class="sxs-lookup"><span data-stu-id="afaa9-151">You can see all configured exports grouped by by exports that contain the current segment or don't contain it.</span></span>

   1. <span data-ttu-id="afaa9-152">Да бисте изабрани сегмент додали у извоз, изаберите извоз на листи и изаберите **Додај сегмент**.</span><span class="sxs-lookup"><span data-stu-id="afaa9-152">To add the selected segment to an export, select the export in the list and select **Add segment**.</span></span>

   1. <span data-ttu-id="afaa9-153">Да бисте креирали нови извоз са изабраним сегментом, изаберите **Додај извоз**.</span><span class="sxs-lookup"><span data-stu-id="afaa9-153">To create a new export with the selected segment, select **Add export**.</span></span> <span data-ttu-id="afaa9-154">За више информација о креирању извоза, погледајте [Подешавање новог извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="afaa9-154">For more information about creating exports, see [Set up a new export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="afaa9-155">Изаберите **Назад** да се вратите на главну страницу за сегменте.</span><span class="sxs-lookup"><span data-stu-id="afaa9-155">Select **Back** to return to the main page for segments.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="afaa9-156">Погледајте историју обраде и чланове сегмента</span><span class="sxs-lookup"><span data-stu-id="afaa9-156">View processing history and segment members</span></span>

<span data-ttu-id="afaa9-157">Консолидоване податке о сегменту можете видети тако што ћете прегледати његове детаље.</span><span class="sxs-lookup"><span data-stu-id="afaa9-157">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="afaa9-158">На страници **Сегменти** изаберите сегмент који желите да прегледате.</span><span class="sxs-lookup"><span data-stu-id="afaa9-158">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="afaa9-159">Горњи део странице садржи графикон тренда који визуелно приказује промене у броју чланова.</span><span class="sxs-lookup"><span data-stu-id="afaa9-159">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="afaa9-160">Задржите показивач изнад тачака података да бисте видели број чланова одређеног датума.</span><span class="sxs-lookup"><span data-stu-id="afaa9-160">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="afaa9-161">Можете да ажурирате временски оквир визуелизације.</span><span class="sxs-lookup"><span data-stu-id="afaa9-161">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="afaa9-162">![Временски период сегмента](media/segment-time-range.png "Временски период сегмента")</span><span class="sxs-lookup"><span data-stu-id="afaa9-162">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="afaa9-163">Доњи део садржи листу чланова сегмента.</span><span class="sxs-lookup"><span data-stu-id="afaa9-163">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="afaa9-164">Поља која се појављују на овој листи заснивају се на атрибутима ентитета вашег сегмента.</span><span class="sxs-lookup"><span data-stu-id="afaa9-164">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="afaa9-165">Листа је преглед одговарајућих чланова сегмента и показује првих 100 записа вашег сегмента тако да га можете брзо проценити и прегледати његове дефиниције, ако је потребно.</span><span class="sxs-lookup"><span data-stu-id="afaa9-165">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="afaa9-166">Да бисте видели све одговарајуће записе, морате да [извезете сегмент](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="afaa9-166">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
