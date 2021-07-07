---
title: Обједињавање ентитета код обједињавања података
description: Обједините ентитете да бисте креирали обједињене корисничке профиле.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305672"
---
# <a name="merge-entities"></a><span data-ttu-id="a9403-103">Обједињавање ентитета</span><span class="sxs-lookup"><span data-stu-id="a9403-103">Merge entities</span></span>

<span data-ttu-id="a9403-104">Фаза спајања је последња фаза у процесу обједињавања података.</span><span class="sxs-lookup"><span data-stu-id="a9403-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="a9403-105">Његова сврха је усклађивање неусаглашених података.</span><span class="sxs-lookup"><span data-stu-id="a9403-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="a9403-106">Примери неусаглашених података могу укључивати корисничко име које се налази у два скупа података, али то се приказује мало другачије у сваком („Јован Дучић“ у односу на „Јово Дучић“) или телефонски број који се разликује у формату (нпр. 617-803-091 у односу на 617803091).</span><span class="sxs-lookup"><span data-stu-id="a9403-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="a9403-107">Спајање тих неусаглашених тачака података обавља се на основу поређења атрибута.</span><span class="sxs-lookup"><span data-stu-id="a9403-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Страница обједињавања у процесу уједначавања података која приказује табелу са обједињеним пољима која дефинишу уједначени кориснички профил.":::

<span data-ttu-id="a9403-109">Када се доврши [фаза подударања](match-entities.md), фазу спајања започињете одабиром плочице **Обједини** на страници **Уједначавање**.</span><span class="sxs-lookup"><span data-stu-id="a9403-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="a9403-110">Преглед системских препорука</span><span class="sxs-lookup"><span data-stu-id="a9403-110">Review system recommendations</span></span>

<span data-ttu-id="a9403-111">У менију **Подаци** > **Уједначавање** > **Обједињавање**, бирате и изузимате атрибуте за обједињавање у оквиру вашег уједначеног ентитета корисничког профила.</span><span class="sxs-lookup"><span data-stu-id="a9403-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="a9403-112">Уједначени кориснички профил је резултат процеса уједначавања података.</span><span class="sxs-lookup"><span data-stu-id="a9403-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="a9403-113">Систем аутоматски спаја неке атрибуте.</span><span class="sxs-lookup"><span data-stu-id="a9403-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="a9403-114">Да бисте видели атрибуте који су укључени у један од ваших аутоматски обједињених атрибута, одаберите тај обједињени атрибут на картици **Поља за клијенте** табеле.</span><span class="sxs-lookup"><span data-stu-id="a9403-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="a9403-115">Атрибути који чине тај обједињени атрибут приказаће се у два нова реда испод обједињеног атрибута.</span><span class="sxs-lookup"><span data-stu-id="a9403-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="a9403-116">Одвојите, преименујте, изузмите и уредите обједињена поља</span><span class="sxs-lookup"><span data-stu-id="a9403-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="a9403-117">Можете да промените начин на који систем обрађује обједињене атрибуте да генерише уједначени кориснички профил.</span><span class="sxs-lookup"><span data-stu-id="a9403-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="a9403-118">Изаберите **Прикажи више** и изаберите шта желите да промените.</span><span class="sxs-lookup"><span data-stu-id="a9403-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Опције у падајућем менију „Прикажи још“ за управљање обједињеним атрибутима.":::

<span data-ttu-id="a9403-120">Погледајте следеће одељке за више информација.</span><span class="sxs-lookup"><span data-stu-id="a9403-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="a9403-121">Раздвајање обједињених поља</span><span class="sxs-lookup"><span data-stu-id="a9403-121">Separate merged fields</span></span>

<span data-ttu-id="a9403-122">Да бисте раздвојили обједињена поља, пронађите атрибут у табели.</span><span class="sxs-lookup"><span data-stu-id="a9403-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="a9403-123">Раздвојена поља се приказују као појединачне тачке података на обједињеном корисничком профилу.</span><span class="sxs-lookup"><span data-stu-id="a9403-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="a9403-124">Изаберите обједињено поље.</span><span class="sxs-lookup"><span data-stu-id="a9403-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="a9403-125">Изаберите **Прикажи више** и бирајте **Раздвоји поља**.</span><span class="sxs-lookup"><span data-stu-id="a9403-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="a9403-126">Потврдите раздвајање.</span><span class="sxs-lookup"><span data-stu-id="a9403-126">Confirm the separation.</span></span>

1. <span data-ttu-id="a9403-127">Изаберите **Сачувај** и **Покрени** да бисте обрадили промене.</span><span class="sxs-lookup"><span data-stu-id="a9403-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="a9403-128">Преименовање обједињених поља</span><span class="sxs-lookup"><span data-stu-id="a9403-128">Rename merged fields</span></span>

<span data-ttu-id="a9403-129">Промените име за приказ обједињених атрибута.</span><span class="sxs-lookup"><span data-stu-id="a9403-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="a9403-130">Не можете да промените назив излазног ентитета.</span><span class="sxs-lookup"><span data-stu-id="a9403-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="a9403-131">Изаберите обједињено поље.</span><span class="sxs-lookup"><span data-stu-id="a9403-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="a9403-132">Изаберите **Прикажи више** и бирајте **Преименуј**.</span><span class="sxs-lookup"><span data-stu-id="a9403-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="a9403-133">Потврдите промењено име за приказ.</span><span class="sxs-lookup"><span data-stu-id="a9403-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="a9403-134">Изаберите **Сачувај** и **Покрени** да бисте обрадили промене.</span><span class="sxs-lookup"><span data-stu-id="a9403-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="a9403-135">Изузимање обједињених поља</span><span class="sxs-lookup"><span data-stu-id="a9403-135">Exclude merged fields</span></span>

<span data-ttu-id="a9403-136">Изузмите атрибут из уједначеног корисничког профила.</span><span class="sxs-lookup"><span data-stu-id="a9403-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="a9403-137">Ако се поље користи у другим процесима, на пример у сегменту, уклоните га из тих процеса пре него што га изузмете из корисничког профила.</span><span class="sxs-lookup"><span data-stu-id="a9403-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="a9403-138">Изаберите обједињено поље.</span><span class="sxs-lookup"><span data-stu-id="a9403-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="a9403-139">Изаберите **Прикажи више** и бирајте **Изузми**.</span><span class="sxs-lookup"><span data-stu-id="a9403-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="a9403-140">Потврдите изузимање.</span><span class="sxs-lookup"><span data-stu-id="a9403-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="a9403-141">Изаберите **Сачувај** и **Покрени** да бисте обрадили промене.</span><span class="sxs-lookup"><span data-stu-id="a9403-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="a9403-142">На страници **Обједињавање**, изаберите **Изузета поља** да бисте видели листу свих изузетих поља.</span><span class="sxs-lookup"><span data-stu-id="a9403-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="a9403-143">Ово окно вам омогућава да поново додате изузета поља.</span><span class="sxs-lookup"><span data-stu-id="a9403-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="a9403-144">Ручно комбиновање поља</span><span class="sxs-lookup"><span data-stu-id="a9403-144">Manually combine fields</span></span>

<span data-ttu-id="a9403-145">Ручно наведите обједињени атрибут.</span><span class="sxs-lookup"><span data-stu-id="a9403-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="a9403-146">На страници **Обједињавање**, изаберите **Комбинуј поља**.</span><span class="sxs-lookup"><span data-stu-id="a9403-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="a9403-147">Наведите **Назив** и један **Назив излазног поља**.</span><span class="sxs-lookup"><span data-stu-id="a9403-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="a9403-148">Одаберите поље које желите да додате.</span><span class="sxs-lookup"><span data-stu-id="a9403-148">Choose a field to add.</span></span> <span data-ttu-id="a9403-149">Изаберите **Додај поља** да бисте комбиновали више поља.</span><span class="sxs-lookup"><span data-stu-id="a9403-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="a9403-150">Потврдите изузимање.</span><span class="sxs-lookup"><span data-stu-id="a9403-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="a9403-151">Изаберите **Сачувај** и **Покрени** да бисте обрадили промене.</span><span class="sxs-lookup"><span data-stu-id="a9403-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="a9403-152">Промена редоследа поља</span><span class="sxs-lookup"><span data-stu-id="a9403-152">Change the order of fields</span></span>

<span data-ttu-id="a9403-153">Неки ентитети садрже више детаља од других.</span><span class="sxs-lookup"><span data-stu-id="a9403-153">Some entities contain more details than others.</span></span> <span data-ttu-id="a9403-154">Ако ентитет укључује најновије податке о пољу, можете му дати приоритет над осталим ентитетима при обједињавању вредности.</span><span class="sxs-lookup"><span data-stu-id="a9403-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="a9403-155">Изаберите обједињено поље.</span><span class="sxs-lookup"><span data-stu-id="a9403-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="a9403-156">Изаберите **Прикажи више** и бирајте **Уреди**.</span><span class="sxs-lookup"><span data-stu-id="a9403-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="a9403-157">У окну **Комбинуј поља**, изаберите **Помери нагоре/надоле** да бисте поставили редослед или их превуците и испустите у жељени положај.</span><span class="sxs-lookup"><span data-stu-id="a9403-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="a9403-158">Потврдите промену.</span><span class="sxs-lookup"><span data-stu-id="a9403-158">Confirm the change.</span></span>

1. <span data-ttu-id="a9403-159">Изаберите **Сачувај** и **Покрени** да бисте обрадили промене.</span><span class="sxs-lookup"><span data-stu-id="a9403-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="a9403-160">Покрените своје спајање</span><span class="sxs-lookup"><span data-stu-id="a9403-160">Run your merge</span></span>

<span data-ttu-id="a9403-161">Без обзира да ли ручно спајате атрибуте или пуштате систем да их спаја, увек можете покренути спајање.</span><span class="sxs-lookup"><span data-stu-id="a9403-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="a9403-162">Изаберите **Покрени** на страници **Спајање** да започнете процес.</span><span class="sxs-lookup"><span data-stu-id="a9403-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a9403-163">![Спајање података Сачувај и Покрени](media/configure-data-merge-save-run.png "Спајање података Сачувај и Покрени")</span><span class="sxs-lookup"><span data-stu-id="a9403-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="a9403-164">Одаберите **Покрени само обједињавање** ако желите да се излаз одрази само у уједначеном ентитету клијента.</span><span class="sxs-lookup"><span data-stu-id="a9403-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="a9403-165">Последични процеси ће се освежити као [дефинисани у распореду освежавања](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a9403-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="a9403-166">Одаберите **Покрени обједињавање и последичне процесе** да освежите систем са вашим променама.</span><span class="sxs-lookup"><span data-stu-id="a9403-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="a9403-167">Сви процеси, укључујући обогаћивање, сегменте и мере аутоматски ће се поново покренути.</span><span class="sxs-lookup"><span data-stu-id="a9403-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="a9403-168">По завршетку свих последичних процеса, кориснички профили одражавају све промене које сте направили.</span><span class="sxs-lookup"><span data-stu-id="a9403-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="a9403-169">Да бисте унели више промена и поново покренули корак, можете да откажете обједињавање у току.</span><span class="sxs-lookup"><span data-stu-id="a9403-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="a9403-170">Изаберите текст **Освежавање у току...** и изаберите **Откажи посао** у бочном окну које се приказује.</span><span class="sxs-lookup"><span data-stu-id="a9403-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="a9403-171">Постоји [шест врста статуса](system.md#status-types) за задатке/процесе.</span><span class="sxs-lookup"><span data-stu-id="a9403-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="a9403-172">Уз то, већина процеса [зависи од других процеса на нижем току](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="a9403-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="a9403-173">Можете изабрати статус процеса да бисте видели детаље о току целог посла.</span><span class="sxs-lookup"><span data-stu-id="a9403-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="a9403-174">Након избора опције **Види детаље** за један од задатака посла пронаћи ћете додатне информације: време обраде, датум последње обраде и све грешке и упозорења повезана са задатком.</span><span class="sxs-lookup"><span data-stu-id="a9403-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="a9403-175">Следећи корак</span><span class="sxs-lookup"><span data-stu-id="a9403-175">Next Step</span></span>

<span data-ttu-id="a9403-176">Конфигуришите [активности](activities.md), [обогаћивање](enrichment-hub.md) или [релације](relationships.md) да бисте остварили бољи увид у клијенте.</span><span class="sxs-lookup"><span data-stu-id="a9403-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="a9403-177">Ако сте већ конфигурисали активности, обогаћивање или сегменте, они ће се аутоматски обрадити како би се користили најновији подаци о клијентима.</span><span class="sxs-lookup"><span data-stu-id="a9403-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
