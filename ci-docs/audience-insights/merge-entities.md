---
title: Обједињавање ентитета код обједињавања података
description: Обједините ентитете да бисте креирали обједињене профиле клијената.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 045fd8d8f65161b91caabed2ac52494dc4fb3910
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406873"
---
# <a name="merge-entities"></a><span data-ttu-id="d3913-103">Обједињавање ентитета</span><span class="sxs-lookup"><span data-stu-id="d3913-103">Merge entities</span></span>

<span data-ttu-id="d3913-104">Фаза спајања је последња фаза у процесу обједињавања података.</span><span class="sxs-lookup"><span data-stu-id="d3913-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="d3913-105">Његова сврха је усклађивање неусаглашених података.</span><span class="sxs-lookup"><span data-stu-id="d3913-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="d3913-106">Примери неусаглашених података могу укључивати корисничко име које се налази у два скупа података, али то се приказује мало другачије у сваком („Јован Дучић“ у односу на „Јово Дучић“) или телефонски број који се разликује у формату (нпр. 617-803-091 у односу на 617803091).</span><span class="sxs-lookup"><span data-stu-id="d3913-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="d3913-107">Спајање тих неусаглашених тачака података обавља се на основу поређења атрибута.</span><span class="sxs-lookup"><span data-stu-id="d3913-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="d3913-108">Када се доврши [фаза подударања](match-entities.md), фазу спајања започињете одабиром плочице **Обједини** на страници **Уједначавање**.</span><span class="sxs-lookup"><span data-stu-id="d3913-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="d3913-109">Преглед системских препорука</span><span class="sxs-lookup"><span data-stu-id="d3913-109">Review system recommendations</span></span>

<span data-ttu-id="d3913-110">На страници **Спајање** можете изабрати и искључити атрибуте који ће се спајати унутар обједињеног ентитета профила клијента (резултат поступка конфигурације).</span><span class="sxs-lookup"><span data-stu-id="d3913-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="d3913-111">Систем аутоматски спаја неке атрибуте.</span><span class="sxs-lookup"><span data-stu-id="d3913-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="d3913-112">Приказ спојених атрибута</span><span class="sxs-lookup"><span data-stu-id="d3913-112">View merged attributes</span></span>

<span data-ttu-id="d3913-113">Да бисте видели атрибуте који су укључени у један од ваших аутоматски спојених атрибута, изаберите тај спојени атрибут.</span><span class="sxs-lookup"><span data-stu-id="d3913-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="d3913-114">Два атрибута која чине тај спојени атрибут приказују се у два нова реда испод спојеног атрибута.</span><span class="sxs-lookup"><span data-stu-id="d3913-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d3913-115">![Избор спојеног атрибута](media/configure-data-merge-profile-attributes.png "Избор спојеног атрибута")</span><span class="sxs-lookup"><span data-stu-id="d3913-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="d3913-116">Одвајање спојених атрибута</span><span class="sxs-lookup"><span data-stu-id="d3913-116">Separate merged attributes</span></span>

<span data-ttu-id="d3913-117">Да бисте одвојили или раскинули било који од аутоматски спојених атрибута, пронађите атрибут у табели **Атрибути профила**.</span><span class="sxs-lookup"><span data-stu-id="d3913-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="d3913-118">Изаберите дугме са три тачке (...).</span><span class="sxs-lookup"><span data-stu-id="d3913-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="d3913-119">У падајућој листи изаберите **Одвоји поља**.</span><span class="sxs-lookup"><span data-stu-id="d3913-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="d3913-120">Уклањање спојених атрибута</span><span class="sxs-lookup"><span data-stu-id="d3913-120">Remove merged attributes</span></span>

<span data-ttu-id="d3913-121">Да бисте изузели атрибут из ентитета крајњег профила клијента, пронађите га у табели **Атрибути профила**.</span><span class="sxs-lookup"><span data-stu-id="d3913-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="d3913-122">Изаберите дугме са три тачке (...).</span><span class="sxs-lookup"><span data-stu-id="d3913-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="d3913-123">У падајућој листи изаберите **Не обједињуј**.</span><span class="sxs-lookup"><span data-stu-id="d3913-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="d3913-124">Атрибут је премештен у одељак **Уклоњено из евиденције корисника**.</span><span class="sxs-lookup"><span data-stu-id="d3913-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="d3913-125">Ручно додајте спојени атрибут</span><span class="sxs-lookup"><span data-stu-id="d3913-125">Manually add a merged attribute</span></span>

<span data-ttu-id="d3913-126">Да бисте додали спојени атрибут, идите на страницу **Спајање**.</span><span class="sxs-lookup"><span data-stu-id="d3913-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="d3913-127">Изаберите **Додавање спојеног атрибута**.</span><span class="sxs-lookup"><span data-stu-id="d3913-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="d3913-128">Наведите **Име** да га касније идентификујете на страници **Спајање**.</span><span class="sxs-lookup"><span data-stu-id="d3913-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="d3913-129">Опционално, наведите **Име за приказ** које ће се приказати у обједињеном ентитету Профил клијента.</span><span class="sxs-lookup"><span data-stu-id="d3913-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="d3913-130">Конфигуришите **Изаберите атрибуте дупликата** да бисте изабрали атрибуте које желите да спојите из подударних ентитета.</span><span class="sxs-lookup"><span data-stu-id="d3913-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="d3913-131">Такође можете да претражујете атрибуте.</span><span class="sxs-lookup"><span data-stu-id="d3913-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="d3913-132">Подесите **Поредак по важности** да један атрибут поставите изнад осталих.</span><span class="sxs-lookup"><span data-stu-id="d3913-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="d3913-133">На пример, ако ентитет *WebAccountCSV* укључује најтачније податке о атрибуту *Пуна имена*, можете дати предност том ентитету у односу на *ContactCSV* тако што ћете изабрати *WebAccountCSV*.</span><span class="sxs-lookup"><span data-stu-id="d3913-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="d3913-134">Као резултат, *WebAccountCSV* прелази на први приоритет, док *ContactCSV* прелази на други приоритет при повлачењу вредности за атрибут *Пуно име*.</span><span class="sxs-lookup"><span data-stu-id="d3913-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="d3913-135">Покрените своје спајање</span><span class="sxs-lookup"><span data-stu-id="d3913-135">Run your merge</span></span>

<span data-ttu-id="d3913-136">Без обзира да ли ручно спајате атрибуте или пуштате систем да их спаја, увек можете покренути спајање.</span><span class="sxs-lookup"><span data-stu-id="d3913-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="d3913-137">Изаберите **Покрени** на страници **Спајање** да започнете процес.</span><span class="sxs-lookup"><span data-stu-id="d3913-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d3913-138">![Спајање података Сачувај и Покрени](media/configure-data-merge-save-run.png "Спајање података Сачувај и Покрени")</span><span class="sxs-lookup"><span data-stu-id="d3913-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="d3913-139">Да бисте унели додатне измене и поново покренули корак, можете отказати обједињавање које је у току.</span><span class="sxs-lookup"><span data-stu-id="d3913-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="d3913-140">Изаберите текст **Освежавање у току...** и изаберите **Откажи посао** у бочном окну које се приказује.</span><span class="sxs-lookup"><span data-stu-id="d3913-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="d3913-141">Када се текст **Освежавање у току...** промени у **Успешно**, обједињавање је довршено и решило контрадикције у вашим подацима у складу са смерницама које сте дефинисали.</span><span class="sxs-lookup"><span data-stu-id="d3913-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="d3913-142">Обједињени и необједињени атрибути су укључени у обједињени ентитет профила.</span><span class="sxs-lookup"><span data-stu-id="d3913-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="d3913-143">Изузети атрибути нису укључени у обједињени ентитет профила.</span><span class="sxs-lookup"><span data-stu-id="d3913-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="d3913-144">Ако то није први пут да сте успешно извели обједињавање, сви процеси на нижем току, укључујући обогаћивање, сегментацију и мере, аутоматски ће се поново покренути.</span><span class="sxs-lookup"><span data-stu-id="d3913-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="d3913-145">Након што су сви процеси на нижем току поново покренути, профили клијената одражавају све ваше измене.</span><span class="sxs-lookup"><span data-stu-id="d3913-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="d3913-146">Постоји [шест врста статуса](system.md#status-types) за задатке/процесе.</span><span class="sxs-lookup"><span data-stu-id="d3913-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="d3913-147">Уз то, већина процеса [зависи од других процеса на нижем току](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="d3913-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="d3913-148">Можете изабрати статус процеса да бисте видели детаље о току целог посла.</span><span class="sxs-lookup"><span data-stu-id="d3913-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="d3913-149">Након избора опције **Види детаље** за један од задатака посла пронаћи ћете додатне информације: време обраде, датум последње обраде и све грешке и упозорења повезана са задатком.</span><span class="sxs-lookup"><span data-stu-id="d3913-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="d3913-150">Следећи корак</span><span class="sxs-lookup"><span data-stu-id="d3913-150">Next Step</span></span>

<span data-ttu-id="d3913-151">Конфигуришите [активности](activities.md), [обогаћивање](enrichment-microsoft-graph.md) или [релације](relationships.md) да бисте остварили бољи увид у клијенте.</span><span class="sxs-lookup"><span data-stu-id="d3913-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="d3913-152">Ако сте већ конфигурисали активности, обогаћивање или релације или ако сте дефинисали сегменте, они ће се аутоматски обрадити како би се користили најновији подаци о клијентима.</span><span class="sxs-lookup"><span data-stu-id="d3913-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>


