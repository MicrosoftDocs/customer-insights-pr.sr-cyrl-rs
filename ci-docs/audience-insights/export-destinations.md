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
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253058"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="e94e7-103">Преглед извоза (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="e94e7-103">Exports (preview) overview</span></span>

<span data-ttu-id="e94e7-104">Страница **Извоз** приказује све конфигурисане извозе.</span><span class="sxs-lookup"><span data-stu-id="e94e7-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="e94e7-105">Извози деле одређене податке са разним апликацијама.</span><span class="sxs-lookup"><span data-stu-id="e94e7-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="e94e7-106">Могу да укључују корисничке профиле или ентитете, шеме и детаље о мапирању.</span><span class="sxs-lookup"><span data-stu-id="e94e7-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="e94e7-107">Сваки извоз захтева [везу коју је поставио администратор ради управљања потврдом идентитета и приступом](connections.md).</span><span class="sxs-lookup"><span data-stu-id="e94e7-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="e94e7-108">Идите на **Подаци** > **Извози** да бисте видели страницу извоза.</span><span class="sxs-lookup"><span data-stu-id="e94e7-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="e94e7-109">Све корисничке улоге имају приступ за приказ конфигурисаних извоза.</span><span class="sxs-lookup"><span data-stu-id="e94e7-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="e94e7-110">Користите поље за претрагу на командној траци да бисте проналазили извозе према њиховом називу, називу везе или типу везе.</span><span class="sxs-lookup"><span data-stu-id="e94e7-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="e94e7-111">Подешавање новог извоза</span><span class="sxs-lookup"><span data-stu-id="e94e7-111">Set up a new export</span></span>

<span data-ttu-id="e94e7-112">Да бисте подесили или уредили извоз, морају вам бити доступне везе.</span><span class="sxs-lookup"><span data-stu-id="e94e7-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="e94e7-113">Везе зависе од ваше [корисничке улоге](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="e94e7-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="e94e7-114">Администратори имају приступ свим везама.</span><span class="sxs-lookup"><span data-stu-id="e94e7-114">Administrators have access to all connections.</span></span> <span data-ttu-id="e94e7-115">Они такође могу да креирају нове везе приликом подешавања извоза.</span><span class="sxs-lookup"><span data-stu-id="e94e7-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="e94e7-116">Сарадници могу имати приступ одређеним везама.</span><span class="sxs-lookup"><span data-stu-id="e94e7-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="e94e7-117">Они зависе од администратора да конфигуришу и деле везе.</span><span class="sxs-lookup"><span data-stu-id="e94e7-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="e94e7-118">Листа извоза у колони **Ваше дозволе** показује сарадницима да ли могу да уређују или само приказују извоз.</span><span class="sxs-lookup"><span data-stu-id="e94e7-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="e94e7-119">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e94e7-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="e94e7-120">Гледаоци могу само да виде постојеће извозе, али не и да их креирају.</span><span class="sxs-lookup"><span data-stu-id="e94e7-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="e94e7-121">Дефинисање новог извоза</span><span class="sxs-lookup"><span data-stu-id="e94e7-121">Define a new export</span></span>

1. <span data-ttu-id="e94e7-122">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="e94e7-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e94e7-123">Изаберите **Додај извоз** да бисте креирали нови извоз.</span><span class="sxs-lookup"><span data-stu-id="e94e7-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="e94e7-124">У окну **Подешавање извоза**, изаберите коју везу да користите.</span><span class="sxs-lookup"><span data-stu-id="e94e7-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="e94e7-125">[Везама](connections.md) управљају администратори.</span><span class="sxs-lookup"><span data-stu-id="e94e7-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="e94e7-126">Наведите потребне детаље и изаберите **Сачувати** да бисте креирали извоз.</span><span class="sxs-lookup"><span data-stu-id="e94e7-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="e94e7-127">Дефинишите нови извоз на основу постојећег извоза</span><span class="sxs-lookup"><span data-stu-id="e94e7-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="e94e7-128">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="e94e7-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e94e7-129">На листи извоза, изаберите извоз који желите да дуплирате.</span><span class="sxs-lookup"><span data-stu-id="e94e7-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="e94e7-130">Изаберите **Направи дупликат** у командној траци да бисте отворили окно **Подешавање извоза** са детаљима изабраног извоза.</span><span class="sxs-lookup"><span data-stu-id="e94e7-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="e94e7-131">Прегледајте и прилагодите извоз и изаберите **Сачувај** да бисте креирали нови извоз.</span><span class="sxs-lookup"><span data-stu-id="e94e7-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="e94e7-132">Уређивање извоза</span><span class="sxs-lookup"><span data-stu-id="e94e7-132">Edit an export</span></span>

1. <span data-ttu-id="e94e7-133">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="e94e7-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e94e7-134">На листи извоза, изаберите извоз који желите да уређујете.</span><span class="sxs-lookup"><span data-stu-id="e94e7-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="e94e7-135">На командној траци изаберите **Уреди**.</span><span class="sxs-lookup"><span data-stu-id="e94e7-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="e94e7-136">Промените вредности које желите да ажурирате и изаберите **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="e94e7-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="e94e7-137">Приказ извоза и детаљи о извозу</span><span class="sxs-lookup"><span data-stu-id="e94e7-137">View exports and export details</span></span>

<span data-ttu-id="e94e7-138">Након креирања одредишта за извоз, она су наведена на страници **Подаци** > **Извоз**.</span><span class="sxs-lookup"><span data-stu-id="e94e7-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="e94e7-139">Сви корисници могу видети који се подаци деле и који је њихов најновији статус.</span><span class="sxs-lookup"><span data-stu-id="e94e7-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="e94e7-140">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="e94e7-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e94e7-141">Корисници без дозволе за уређивање бирају **Прикажи** уместо **Уреди** да би видели детаље о извозу.</span><span class="sxs-lookup"><span data-stu-id="e94e7-141">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="e94e7-142">Бочно окно приказује конфигурацију извоза.</span><span class="sxs-lookup"><span data-stu-id="e94e7-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="e94e7-143">Без дозвола за уређивање не можете мењати вредности.</span><span class="sxs-lookup"><span data-stu-id="e94e7-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="e94e7-144">Изаберите **Затвори** да бисте се вратили на страницу извоза.</span><span class="sxs-lookup"><span data-stu-id="e94e7-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="e94e7-145">Планирање и покретање извоза</span><span class="sxs-lookup"><span data-stu-id="e94e7-145">Schedule and run exports</span></span>

<span data-ttu-id="e94e7-146">Сваки извоз који конфигуришете има распоред освежавања.</span><span class="sxs-lookup"><span data-stu-id="e94e7-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="e94e7-147">Током освежавања, систем тражи нове или ажуриране податке које ће укључити у извоз.</span><span class="sxs-lookup"><span data-stu-id="e94e7-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="e94e7-148">Подразумевано се извози као део сваког [заказаног освежавања система](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e94e7-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e94e7-149">Можете прилагодити распоред освежавања или га искључити за ручно покретање извоза.</span><span class="sxs-lookup"><span data-stu-id="e94e7-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="e94e7-150">Распореди извоза зависе од статуса вашег окружења.</span><span class="sxs-lookup"><span data-stu-id="e94e7-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="e94e7-151">Ако постоје исправке [зависности](system.md#refresh-policies) у току када треба да започне планирани извоз, систем ће прво довршити зависности, а затим покренути извоз.</span><span class="sxs-lookup"><span data-stu-id="e94e7-151">If there are updates on [dependencies](system.md#refresh-policies) in progress when a scheduled export should start, the system will first complete the dependencies and then run the export.</span></span> <span data-ttu-id="e94e7-152">У колони **Освежено** можете видети када је извоз последњи пут освежен.</span><span class="sxs-lookup"><span data-stu-id="e94e7-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="e94e7-153">Распоред извоза</span><span class="sxs-lookup"><span data-stu-id="e94e7-153">Schedule exports</span></span>

<span data-ttu-id="e94e7-154">Можете да дефинишете прилагођене распореде освежавања за појединачне извозе или неколико извоза одједном.</span><span class="sxs-lookup"><span data-stu-id="e94e7-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="e94e7-155">Тренутно дефинисани распоред наведен је у колони **Распоред** листе извоза.</span><span class="sxs-lookup"><span data-stu-id="e94e7-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="e94e7-156">Дозвола за промену распореда је иста као и за [уређивање и дефинисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e94e7-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="e94e7-157">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="e94e7-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e94e7-158">Изаберите извоз који желите да закажете.</span><span class="sxs-lookup"><span data-stu-id="e94e7-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="e94e7-159">На командној траци изаберите **Закажи**.</span><span class="sxs-lookup"><span data-stu-id="e94e7-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="e94e7-160">У окну **Заказивање извоза**, подесите **Извршавање распореда** на **Укључено** да бисте аутоматски покретали извоз.</span><span class="sxs-lookup"><span data-stu-id="e94e7-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="e94e7-161">Подесите на **Искључено** да бисте га ручно освежавали.</span><span class="sxs-lookup"><span data-stu-id="e94e7-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="e94e7-162">Да бисте аутоматски освежавали извозе, одаберите вредност **Понављање** и наведите детаље за њу.</span><span class="sxs-lookup"><span data-stu-id="e94e7-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="e94e7-163">Дефинисано време се односи на све случајеве понављања.</span><span class="sxs-lookup"><span data-stu-id="e94e7-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="e94e7-164">То је време када би извоз требало да почне да се освежава.</span><span class="sxs-lookup"><span data-stu-id="e94e7-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="e94e7-165">Примените и активирајте промене избором **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="e94e7-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="e94e7-166">Када уређујете распоред за неколико извоза, потребно је да направите избор под **Задржите или измените распореде**:</span><span class="sxs-lookup"><span data-stu-id="e94e7-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="e94e7-167">**Задржите појединачне распореде**: Задржите претходно дефинисани распоред за изабране извозе и само их онемогућите или омогућите.</span><span class="sxs-lookup"><span data-stu-id="e94e7-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="e94e7-168">**Дефинишите нови распоред за све изабране извозе**: Измените постојеће распореде изабраних извоза.</span><span class="sxs-lookup"><span data-stu-id="e94e7-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="e94e7-169">Покретање извоза на захтев</span><span class="sxs-lookup"><span data-stu-id="e94e7-169">Run exports on demand</span></span>

<span data-ttu-id="e94e7-170">Да бисте извезли податке без чекања на заказано освежавање, идите на страницу **Подаци** > **Извоз**.</span><span class="sxs-lookup"><span data-stu-id="e94e7-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="e94e7-171">Да бисте покренули све извозе, изаберите **Покрени све** у командној траци.</span><span class="sxs-lookup"><span data-stu-id="e94e7-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="e94e7-172">Ова радња ће покретати само извозе који имају активан распоред.</span><span class="sxs-lookup"><span data-stu-id="e94e7-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="e94e7-173">Да бисте покренули један извоз, изаберите га на листи и изаберите **Покрени** у командној траци.</span><span class="sxs-lookup"><span data-stu-id="e94e7-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="e94e7-174">Тако покрећете извозе без активног распореда.</span><span class="sxs-lookup"><span data-stu-id="e94e7-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="e94e7-175">Уклањање извоза</span><span class="sxs-lookup"><span data-stu-id="e94e7-175">Remove an Export</span></span>

1. <span data-ttu-id="e94e7-176">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="e94e7-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e94e7-177">Изаберите извоз који желите да уклоните.</span><span class="sxs-lookup"><span data-stu-id="e94e7-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="e94e7-178">Изаберите **Уклони** на командној траци.</span><span class="sxs-lookup"><span data-stu-id="e94e7-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="e94e7-179">Потврдите уклањање одабиром **Уклони** на екрану за потврду.</span><span class="sxs-lookup"><span data-stu-id="e94e7-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
