---
title: Извоз података из услуге Customer Insights
description: Управљајте извозима да бисте делили податке.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 28563e3a76535cb0c92bfcda4ef5037430d00cfa
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305496"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="db99f-103">Преглед извоза (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="db99f-103">Exports (preview) overview</span></span>

<span data-ttu-id="db99f-104">Страница **Извоз** приказује све конфигурисане извозе.</span><span class="sxs-lookup"><span data-stu-id="db99f-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="db99f-105">Извози деле одређене податке са разним апликацијама.</span><span class="sxs-lookup"><span data-stu-id="db99f-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="db99f-106">Могу да укључују корисничке профиле или ентитете, шеме и детаље о мапирању.</span><span class="sxs-lookup"><span data-stu-id="db99f-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="db99f-107">Сваки извоз захтева [везу коју је поставио администратор ради управљања потврдом идентитета и приступом](connections.md).</span><span class="sxs-lookup"><span data-stu-id="db99f-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="db99f-108">Идите на **Подаци** > **Извози** да бисте видели страницу извоза.</span><span class="sxs-lookup"><span data-stu-id="db99f-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="db99f-109">Све корисничке улоге могу прегледати конфигурисане извозе.</span><span class="sxs-lookup"><span data-stu-id="db99f-109">All user roles can view configured exports.</span></span> <span data-ttu-id="db99f-110">Користите поље за претрагу на командној траци да бисте пронашли извозе према њиховом називу, називу везе или типу везе.</span><span class="sxs-lookup"><span data-stu-id="db99f-110">Use the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="db99f-111">Подешавање новог извоза</span><span class="sxs-lookup"><span data-stu-id="db99f-111">Set up a new export</span></span>

<span data-ttu-id="db99f-112">Да бисте подесили или уредили извоз, морају вам бити доступне везе.</span><span class="sxs-lookup"><span data-stu-id="db99f-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="db99f-113">Везе зависе од ваше [корисничке улоге](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="db99f-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="db99f-114">Администратори имају приступ свим везама.</span><span class="sxs-lookup"><span data-stu-id="db99f-114">Administrators have access to all connections.</span></span> <span data-ttu-id="db99f-115">Они такође могу да креирају нове везе приликом подешавања извоза.</span><span class="sxs-lookup"><span data-stu-id="db99f-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="db99f-116">Сарадници могу имати приступ одређеним везама.</span><span class="sxs-lookup"><span data-stu-id="db99f-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="db99f-117">Они зависе од администратора да конфигуришу и деле везе.</span><span class="sxs-lookup"><span data-stu-id="db99f-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="db99f-118">Листа извоза у колони **Ваше дозволе** показује сарадницима да ли могу да уређују или само приказују извоз.</span><span class="sxs-lookup"><span data-stu-id="db99f-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="db99f-119">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="db99f-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="db99f-120">Гледаоци могу само да виде постојеће извозе, али не и да их креирају.</span><span class="sxs-lookup"><span data-stu-id="db99f-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="db99f-121">Дефинисање новог извоза</span><span class="sxs-lookup"><span data-stu-id="db99f-121">Define a new export</span></span>

1. <span data-ttu-id="db99f-122">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="db99f-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="db99f-123">Изаберите **Додај извоз** да бисте креирали нови извоз.</span><span class="sxs-lookup"><span data-stu-id="db99f-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="db99f-124">У окну **Подешавање извоза**, изаберите коју везу да користите.</span><span class="sxs-lookup"><span data-stu-id="db99f-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="db99f-125">[Везама](connections.md) управљају администратори.</span><span class="sxs-lookup"><span data-stu-id="db99f-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="db99f-126">Наведите потребне детаље и изаберите **Сачувати** да бисте креирали извоз.</span><span class="sxs-lookup"><span data-stu-id="db99f-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="db99f-127">Дефинишите нови извоз на основу постојећег извоза</span><span class="sxs-lookup"><span data-stu-id="db99f-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="db99f-128">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="db99f-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="db99f-129">На листи извоза, изаберите извоз који желите да дуплирате.</span><span class="sxs-lookup"><span data-stu-id="db99f-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="db99f-130">Изаберите **Направи дупликат** у командној траци да бисте отворили окно **Подешавање извоза** са детаљима изабраног извоза.</span><span class="sxs-lookup"><span data-stu-id="db99f-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="db99f-131">Прегледајте и прилагодите извоз и изаберите **Сачувај** да бисте креирали нови извоз.</span><span class="sxs-lookup"><span data-stu-id="db99f-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="db99f-132">Уређивање извоза</span><span class="sxs-lookup"><span data-stu-id="db99f-132">Edit an export</span></span>

1. <span data-ttu-id="db99f-133">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="db99f-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="db99f-134">На листи извоза, изаберите извоз који желите да уређујете.</span><span class="sxs-lookup"><span data-stu-id="db99f-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="db99f-135">На командној траци изаберите **Уреди**.</span><span class="sxs-lookup"><span data-stu-id="db99f-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="db99f-136">Промените вредности које желите да ажурирате и изаберите **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="db99f-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="db99f-137">Приказ извоза и детаљи о извозу</span><span class="sxs-lookup"><span data-stu-id="db99f-137">View exports and export details</span></span>

<span data-ttu-id="db99f-138">Након креирања одредишта за извоз, она су наведена на страници **Подаци** > **Извоз**.</span><span class="sxs-lookup"><span data-stu-id="db99f-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="db99f-139">Сви корисници могу видети који се подаци деле и који је њихов најновији статус.</span><span class="sxs-lookup"><span data-stu-id="db99f-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="db99f-140">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="db99f-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="db99f-141">Корисници без дозволе за уређивање бирају **Приказ** уместо **Уређивање** да видели детаље о извозу.</span><span class="sxs-lookup"><span data-stu-id="db99f-141">Users without edit permissions select **View** instead of **Edit** to see the export details.</span></span>

1. <span data-ttu-id="db99f-142">Бочно окно приказује конфигурацију извоза.</span><span class="sxs-lookup"><span data-stu-id="db99f-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="db99f-143">Без дозвола за уређивање не можете мењати вредности.</span><span class="sxs-lookup"><span data-stu-id="db99f-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="db99f-144">Изаберите **Затвори** да бисте се вратили на страницу извоза.</span><span class="sxs-lookup"><span data-stu-id="db99f-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="db99f-145">Планирање и покретање извоза</span><span class="sxs-lookup"><span data-stu-id="db99f-145">Schedule and run exports</span></span>

<span data-ttu-id="db99f-146">Сваки извоз који конфигуришете има распоред освежавања.</span><span class="sxs-lookup"><span data-stu-id="db99f-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="db99f-147">Током освежавања, систем тражи нове или ажуриране податке које ће укључити у извоз.</span><span class="sxs-lookup"><span data-stu-id="db99f-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="db99f-148">Подразумевано се извози као део сваког [заказаног освежавања система](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="db99f-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="db99f-149">Можете прилагодити распоред освежавања или га искључити за ручно покретање извоза.</span><span class="sxs-lookup"><span data-stu-id="db99f-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="db99f-150">Распореди извоза зависе од статуса вашег окружења.</span><span class="sxs-lookup"><span data-stu-id="db99f-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="db99f-151">Ако су у току ажурирања [зависних елемената](system.md#refresh-policies) када треба да започне планирани извоз, систем ће прво довршити ажурирања, а затим покренути извоз.</span><span class="sxs-lookup"><span data-stu-id="db99f-151">If there are updates in progress on [dependencies](system.md#refresh-policies) when a scheduled export should start, the system will first complete the updates and then run the export.</span></span> <span data-ttu-id="db99f-152">У колони **Освежено** можете видети када је извоз последњи пут освежен.</span><span class="sxs-lookup"><span data-stu-id="db99f-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="db99f-153">Распоред извоза</span><span class="sxs-lookup"><span data-stu-id="db99f-153">Schedule exports</span></span>

<span data-ttu-id="db99f-154">Можете да дефинишете прилагођене распореде освежавања за појединачне извозе или неколико извоза одједном.</span><span class="sxs-lookup"><span data-stu-id="db99f-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="db99f-155">Тренутно дефинисани распоред наведен је у колони **Распоред** листе извоза.</span><span class="sxs-lookup"><span data-stu-id="db99f-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="db99f-156">Дозвола за промену распореда је иста као и за [уређивање и дефинисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="db99f-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="db99f-157">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="db99f-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="db99f-158">Изаберите извоз који желите да закажете.</span><span class="sxs-lookup"><span data-stu-id="db99f-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="db99f-159">На командној траци изаберите **Закажи**.</span><span class="sxs-lookup"><span data-stu-id="db99f-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="db99f-160">У окну **Заказивање извоза**, подесите **Извршавање распореда** на **Укључено** да бисте аутоматски покретали извоз.</span><span class="sxs-lookup"><span data-stu-id="db99f-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="db99f-161">Подесите на **Искључено** да бисте га ручно освежавали.</span><span class="sxs-lookup"><span data-stu-id="db99f-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="db99f-162">Да бисте аутоматски освежавали извозе, одаберите вредност **Понављање** и наведите детаље за њу.</span><span class="sxs-lookup"><span data-stu-id="db99f-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="db99f-163">Дефинисано време се односи на све случајеве понављања.</span><span class="sxs-lookup"><span data-stu-id="db99f-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="db99f-164">То је време када би извоз требало да почне да се освежава.</span><span class="sxs-lookup"><span data-stu-id="db99f-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="db99f-165">Примените и активирајте промене избором **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="db99f-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="db99f-166">Када уређујете распоред за неколико извоза, потребно је да направите избор под **Задржите или измените распореде**:</span><span class="sxs-lookup"><span data-stu-id="db99f-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="db99f-167">**Задржите појединачне распореде**: Задржите претходно дефинисани распоред за изабране извозе и само их онемогућите или омогућите.</span><span class="sxs-lookup"><span data-stu-id="db99f-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="db99f-168">**Дефинишите нови распоред за све изабране извозе**: Измените постојеће распореде изабраних извоза.</span><span class="sxs-lookup"><span data-stu-id="db99f-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="db99f-169">Покретање извоза на захтев</span><span class="sxs-lookup"><span data-stu-id="db99f-169">Run exports on demand</span></span>

<span data-ttu-id="db99f-170">Да бисте извезли податке без чекања на заказано освежавање, идите на страницу **Подаци** > **Извоз**.</span><span class="sxs-lookup"><span data-stu-id="db99f-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="db99f-171">Да бисте покренули све извозе, изаберите **Покрени све** у командној траци.</span><span class="sxs-lookup"><span data-stu-id="db99f-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="db99f-172">Ова радња ће покретати само извозе који имају активан распоред.</span><span class="sxs-lookup"><span data-stu-id="db99f-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="db99f-173">Да бисте покренули један извоз, изаберите га на листи и изаберите **Покрени** у командној траци.</span><span class="sxs-lookup"><span data-stu-id="db99f-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="db99f-174">Тако покрећете извозе без активног распореда.</span><span class="sxs-lookup"><span data-stu-id="db99f-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="db99f-175">Уклањање извоза</span><span class="sxs-lookup"><span data-stu-id="db99f-175">Remove an Export</span></span>

1. <span data-ttu-id="db99f-176">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="db99f-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="db99f-177">Изаберите извоз који желите да уклоните.</span><span class="sxs-lookup"><span data-stu-id="db99f-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="db99f-178">Изаберите **Уклони** на командној траци.</span><span class="sxs-lookup"><span data-stu-id="db99f-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="db99f-179">Потврдите уклањање одабиром **Уклони** на екрану за потврду.</span><span class="sxs-lookup"><span data-stu-id="db99f-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
