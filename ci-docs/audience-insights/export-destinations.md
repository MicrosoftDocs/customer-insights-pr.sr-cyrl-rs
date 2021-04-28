---
title: Извоз података из услуге Customer Insights
description: Управљајте извозима да бисте делили податке.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896161"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="b99c2-103">Преглед извоза (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="b99c2-103">Exports (preview) overview</span></span>

<span data-ttu-id="b99c2-104">Страница **Извоз** приказује све конфигурисане извозе.</span><span class="sxs-lookup"><span data-stu-id="b99c2-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="b99c2-105">Извози деле одређене податке са разним апликацијама.</span><span class="sxs-lookup"><span data-stu-id="b99c2-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="b99c2-106">Могу да укључују профиле клијената или ентитете, шеме и детаље о мапирању.</span><span class="sxs-lookup"><span data-stu-id="b99c2-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="b99c2-107">Сваки извоз захтева [везу коју је поставио администратор ради управљања потврдом идентитета и приступом](connections.md).</span><span class="sxs-lookup"><span data-stu-id="b99c2-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b99c2-108">До марта 2021. године, извози су аутоматски креирали везу са одговарајућом услугом.</span><span class="sxs-lookup"><span data-stu-id="b99c2-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="b99c2-109">Извози сада захтевају [везу коју креира и дели администратор](connections.md) пре него што будете могли да их креирате.</span><span class="sxs-lookup"><span data-stu-id="b99c2-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="b99c2-110">Идите на **Подаци** > **Извози** да бисте видели страницу извоза.</span><span class="sxs-lookup"><span data-stu-id="b99c2-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="b99c2-111">Све корисничке улоге имају приступ за приказ конфигурисаних извоза.</span><span class="sxs-lookup"><span data-stu-id="b99c2-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="b99c2-112">Користите поље за претрагу на командној траци да бисте проналазили извозе према њиховом називу, називу везе или типу везе.</span><span class="sxs-lookup"><span data-stu-id="b99c2-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="b99c2-113">Подешавање новог извоза</span><span class="sxs-lookup"><span data-stu-id="b99c2-113">Set up a new export</span></span>

<span data-ttu-id="b99c2-114">Да бисте подесили или уредили извоз, морају вам бити доступне везе.</span><span class="sxs-lookup"><span data-stu-id="b99c2-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="b99c2-115">Везе зависе од ваше [корисничке улоге](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="b99c2-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="b99c2-116">Администратори имају приступ свим везама.</span><span class="sxs-lookup"><span data-stu-id="b99c2-116">Administrators have access to all connections.</span></span> <span data-ttu-id="b99c2-117">Они такође могу да креирају нове везе приликом подешавања извоза.</span><span class="sxs-lookup"><span data-stu-id="b99c2-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="b99c2-118">Сарадници могу имати приступ одређеним везама.</span><span class="sxs-lookup"><span data-stu-id="b99c2-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="b99c2-119">Они зависе од администратора да конфигуришу и деле везе.</span><span class="sxs-lookup"><span data-stu-id="b99c2-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="b99c2-120">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b99c2-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="b99c2-121">Гледаоци могу само да виде постојеће извозе, али не и да их креирају.</span><span class="sxs-lookup"><span data-stu-id="b99c2-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="b99c2-122">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="b99c2-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b99c2-123">Изаберите **Додај извоз** да бисте креирали ново одредиште за извоз.</span><span class="sxs-lookup"><span data-stu-id="b99c2-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="b99c2-124">У окну **Подешавање извоза**, изаберите коју везу да користите.</span><span class="sxs-lookup"><span data-stu-id="b99c2-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="b99c2-125">[Везама](connections.md) управљају администратори.</span><span class="sxs-lookup"><span data-stu-id="b99c2-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="b99c2-126">Наведите потребне детаље и изаберите **Сачувати** да бисте креирали извоз.</span><span class="sxs-lookup"><span data-stu-id="b99c2-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="b99c2-127">Уређивање извоза</span><span class="sxs-lookup"><span data-stu-id="b99c2-127">Edit an export</span></span>

1. <span data-ttu-id="b99c2-128">Изаберите вертикалне три тачке за одредиште за извоз које желите да уређујете.</span><span class="sxs-lookup"><span data-stu-id="b99c2-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="b99c2-129">У падајућем менију изаберите **Уреди**.</span><span class="sxs-lookup"><span data-stu-id="b99c2-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="b99c2-130">Промените вредности које желите да ажурирате и изаберите **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="b99c2-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="b99c2-131">Приказ извоза и детаљи о извозу</span><span class="sxs-lookup"><span data-stu-id="b99c2-131">View Exports and export details</span></span>

<span data-ttu-id="b99c2-132">Након креирања одредишта за извоз, она су наведена на страници **Подаци** > **Извоз**.</span><span class="sxs-lookup"><span data-stu-id="b99c2-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="b99c2-133">Сви корисници могу видети који се подаци деле и који је њихов најновији статус.</span><span class="sxs-lookup"><span data-stu-id="b99c2-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="b99c2-134">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="b99c2-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b99c2-135">Корисници без дозволе за уређивање бирају **Прикажи** уместо **Уреди** да би видели детаље о извозу.</span><span class="sxs-lookup"><span data-stu-id="b99c2-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="b99c2-136">Ово бочно окно приказује подешавање овог извоза.</span><span class="sxs-lookup"><span data-stu-id="b99c2-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="b99c2-137">Без дозвола за уређивање не можете мењати вредности.</span><span class="sxs-lookup"><span data-stu-id="b99c2-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="b99c2-138">Изаберите **Затвори** да бисте се вратили на страницу извоза.</span><span class="sxs-lookup"><span data-stu-id="b99c2-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="b99c2-139">Покретање извоза на захтев</span><span class="sxs-lookup"><span data-stu-id="b99c2-139">Run exports on demand</span></span>

<span data-ttu-id="b99c2-140">Након конфигурисања, извоз ће се покренути са сваким [заказаним освежавањем](system.md#schedule-tab) све док има функционалну везу.</span><span class="sxs-lookup"><span data-stu-id="b99c2-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="b99c2-141">Да бисте извезли податке без чекања на заказано освежавање, идите на страницу **Подаци** > **Извоз**.</span><span class="sxs-lookup"><span data-stu-id="b99c2-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="b99c2-142">На располагању су вам две опције:</span><span class="sxs-lookup"><span data-stu-id="b99c2-142">You have two options:</span></span>

- <span data-ttu-id="b99c2-143">Да бисте покренули све извозе, изаберите **Покрени све** у командној траци.</span><span class="sxs-lookup"><span data-stu-id="b99c2-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="b99c2-144">Да бисте покренули појединачни извоз, изаберите три тачке (...) на ставци листе, а затим одаберите **Покрени**.</span><span class="sxs-lookup"><span data-stu-id="b99c2-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="b99c2-145">Уклањање извоза</span><span class="sxs-lookup"><span data-stu-id="b99c2-145">Remove an Export</span></span>

1. <span data-ttu-id="b99c2-146">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="b99c2-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b99c2-147">Одаберите вертикалне три тачке за извоз који желите да уклоните.</span><span class="sxs-lookup"><span data-stu-id="b99c2-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="b99c2-148">Изаберите **Уклони** из падајућег менија.</span><span class="sxs-lookup"><span data-stu-id="b99c2-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="b99c2-149">Потврдите уклањање одабиром **Уклони** на екрану за потврду.</span><span class="sxs-lookup"><span data-stu-id="b99c2-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
