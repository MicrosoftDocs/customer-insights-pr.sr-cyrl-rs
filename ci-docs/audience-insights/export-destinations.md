---
title: Извоз података из услуге Customer Insights
description: Управљајте извозима да бисте делили податке.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016654"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="9e892-103">Преглед извоза (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="9e892-103">Exports (preview) overview</span></span>

<span data-ttu-id="9e892-104">Страница **Извоз** приказује све конфигурисане извозе.</span><span class="sxs-lookup"><span data-stu-id="9e892-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="9e892-105">Извози деле одређене податке са разним апликацијама.</span><span class="sxs-lookup"><span data-stu-id="9e892-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="9e892-106">Могу да укључују корисничке профиле или ентитете, шеме и детаље о мапирању.</span><span class="sxs-lookup"><span data-stu-id="9e892-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="9e892-107">Сваки извоз захтева [везу коју је поставио администратор ради управљања потврдом идентитета и приступом](connections.md).</span><span class="sxs-lookup"><span data-stu-id="9e892-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="9e892-108">Идите на **Подаци** > **Извози** да бисте видели страницу извоза.</span><span class="sxs-lookup"><span data-stu-id="9e892-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="9e892-109">Све корисничке улоге имају приступ за приказ конфигурисаних извоза.</span><span class="sxs-lookup"><span data-stu-id="9e892-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="9e892-110">Користите поље за претрагу на командној траци да бисте проналазили извозе према њиховом називу, називу везе или типу везе.</span><span class="sxs-lookup"><span data-stu-id="9e892-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="9e892-111">Подешавање новог извоза</span><span class="sxs-lookup"><span data-stu-id="9e892-111">Set up a new export</span></span>

<span data-ttu-id="9e892-112">Да бисте подесили или уредили извоз, морају вам бити доступне везе.</span><span class="sxs-lookup"><span data-stu-id="9e892-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="9e892-113">Везе зависе од ваше [корисничке улоге](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="9e892-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="9e892-114">Администратори имају приступ свим везама.</span><span class="sxs-lookup"><span data-stu-id="9e892-114">Administrators have access to all connections.</span></span> <span data-ttu-id="9e892-115">Они такође могу да креирају нове везе приликом подешавања извоза.</span><span class="sxs-lookup"><span data-stu-id="9e892-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="9e892-116">Сарадници могу имати приступ одређеним везама.</span><span class="sxs-lookup"><span data-stu-id="9e892-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="9e892-117">Они зависе од администратора да конфигуришу и деле везе.</span><span class="sxs-lookup"><span data-stu-id="9e892-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="9e892-118">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="9e892-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="9e892-119">Гледаоци могу само да виде постојеће извозе, али не и да их креирају.</span><span class="sxs-lookup"><span data-stu-id="9e892-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="9e892-120">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="9e892-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9e892-121">Изаберите **Додај извоз** да бисте креирали ново одредиште за извоз.</span><span class="sxs-lookup"><span data-stu-id="9e892-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="9e892-122">У окну **Подешавање извоза**, изаберите коју везу да користите.</span><span class="sxs-lookup"><span data-stu-id="9e892-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="9e892-123">[Везама](connections.md) управљају администратори.</span><span class="sxs-lookup"><span data-stu-id="9e892-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="9e892-124">Наведите потребне детаље и изаберите **Сачувати** да бисте креирали извоз.</span><span class="sxs-lookup"><span data-stu-id="9e892-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="9e892-125">Уређивање извоза</span><span class="sxs-lookup"><span data-stu-id="9e892-125">Edit an export</span></span>

1. <span data-ttu-id="9e892-126">Изаберите вертикалне три тачке за одредиште за извоз које желите да уређујете.</span><span class="sxs-lookup"><span data-stu-id="9e892-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="9e892-127">У падајућем менију изаберите **Уреди**.</span><span class="sxs-lookup"><span data-stu-id="9e892-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="9e892-128">Промените вредности које желите да ажурирате и изаберите **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="9e892-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="9e892-129">Приказ извоза и детаљи о извозу</span><span class="sxs-lookup"><span data-stu-id="9e892-129">View Exports and export details</span></span>

<span data-ttu-id="9e892-130">Након креирања одредишта за извоз, она су наведена на страници **Подаци** > **Извоз**.</span><span class="sxs-lookup"><span data-stu-id="9e892-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="9e892-131">Сви корисници могу видети који се подаци деле и који је њихов најновији статус.</span><span class="sxs-lookup"><span data-stu-id="9e892-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="9e892-132">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="9e892-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9e892-133">Корисници без дозволе за уређивање бирају **Прикажи** уместо **Уреди** да би видели детаље о извозу.</span><span class="sxs-lookup"><span data-stu-id="9e892-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="9e892-134">Ово бочно окно приказује подешавање овог извоза.</span><span class="sxs-lookup"><span data-stu-id="9e892-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="9e892-135">Без дозвола за уређивање не можете мењати вредности.</span><span class="sxs-lookup"><span data-stu-id="9e892-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="9e892-136">Изаберите **Затвори** да бисте се вратили на страницу извоза.</span><span class="sxs-lookup"><span data-stu-id="9e892-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="9e892-137">Покретање извоза на захтев</span><span class="sxs-lookup"><span data-stu-id="9e892-137">Run exports on demand</span></span>

<span data-ttu-id="9e892-138">Након конфигурисања, извоз ће се покренути са сваким [заказаним освежавањем](system.md#schedule-tab) све док има функционалну везу.</span><span class="sxs-lookup"><span data-stu-id="9e892-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="9e892-139">Да бисте извезли податке без чекања на заказано освежавање, идите на страницу **Подаци** > **Извоз**.</span><span class="sxs-lookup"><span data-stu-id="9e892-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="9e892-140">На располагању су вам две опције:</span><span class="sxs-lookup"><span data-stu-id="9e892-140">You have two options:</span></span>

- <span data-ttu-id="9e892-141">Да бисте покренули све извозе, изаберите **Покрени све** у командној траци.</span><span class="sxs-lookup"><span data-stu-id="9e892-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="9e892-142">Да бисте покренули појединачни извоз, изаберите три тачке (...) на ставци листе, а затим одаберите **Покрени**.</span><span class="sxs-lookup"><span data-stu-id="9e892-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="9e892-143">Уклањање извоза</span><span class="sxs-lookup"><span data-stu-id="9e892-143">Remove an Export</span></span>

1. <span data-ttu-id="9e892-144">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="9e892-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9e892-145">Одаберите вертикалне три тачке за извоз који желите да уклоните.</span><span class="sxs-lookup"><span data-stu-id="9e892-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="9e892-146">Изаберите **Уклони** из падајућег менија.</span><span class="sxs-lookup"><span data-stu-id="9e892-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="9e892-147">Потврдите уклањање одабиром **Уклони** на екрану за потврду.</span><span class="sxs-lookup"><span data-stu-id="9e892-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
