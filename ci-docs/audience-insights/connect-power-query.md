---
title: Унос података путем Power Query конектора
description: Конектори за изворе података засноване на решењу Power Query.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: b9a1b30e37c3792aa7bdfcfc177da9e8a32c324d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596931"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="ee2d2-103">Повезивање са Power Query извором података</span><span class="sxs-lookup"><span data-stu-id="ee2d2-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="ee2d2-104">Power Query нуди широк скуп конектора за унос података.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="ee2d2-105">Већину ових конектора подржава Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="ee2d2-106">Додавање извора података на основу Power Query конектора углавном следи кораке наведене у следећем одељку.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="ee2d2-107">Међутим, у зависности од конектора који користите, потребне су различите информације.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="ee2d2-108">За више информација погледајте документацију о појединачним конекторима у [референци Power Query конектора](/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="ee2d2-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="ee2d2-109">Креирање новог извора података</span><span class="sxs-lookup"><span data-stu-id="ee2d2-109">Create a new data source</span></span>

1. <span data-ttu-id="ee2d2-110">У увидима о корисницима идите на **Подаци** > **Извори података**.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="ee2d2-111">Изаберите **Додај извор података**.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="ee2d2-112">Одаберите метод **Увоза података** и изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="ee2d2-113">Наведите **Назив** за извор података, па изаберите **Следеће** како бисте креирали извор података.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="ee2d2-114">Смернице за називе:</span><span class="sxs-lookup"><span data-stu-id="ee2d2-114">Name guidelines:</span></span> 
   - <span data-ttu-id="ee2d2-115">Започните словом.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-115">Start with a letter.</span></span>
   - <span data-ttu-id="ee2d2-116">Користите само слова и бројеве.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-116">Use letters and numbers only.</span></span> <span data-ttu-id="ee2d2-117">Посебни знакови и размаци нису дозвољени.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="ee2d2-118">Користите између 3 и 64 знака.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="ee2d2-119">Одаберите један од [доступних конектора](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="ee2d2-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="ee2d2-120">За овај пример бирамо **Текст/CSV** конектор.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="ee2d2-121">Унесите потребне детаље у **Подешавања везе** за изабрани конектор и изаберите **Следеће** да бисте видели преглед података.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="ee2d2-122">Изаберите **Трансформација података**.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-122">Select **Transform data**.</span></span> <span data-ttu-id="ee2d2-123">У овом кораку ћете додати ентитете свом извору података.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="ee2d2-124">Ентитети су скупови података.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-124">Entities are datasets.</span></span> <span data-ttu-id="ee2d2-125">Ако имате базу података која укључује више скупова података, сваки скуп података је свој сопствени ентитет.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="ee2d2-126">Дијалог **Power Query – Уређивање профила** вам омогућава да прегледате и прецизирате податке.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="ee2d2-127">Ентитети које су системи идентификовали у вашем изабраном извору података приказују се у левом окну.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ee2d2-128">![Дијалог за уређивање упита](media/data-manager-configure-edit-queries.png "Дијалог за уређивање упита")</span><span class="sxs-lookup"><span data-stu-id="ee2d2-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="ee2d2-129">Такође можете да трансформишете своје податке.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-129">You can also transform your data.</span></span> <span data-ttu-id="ee2d2-130">Изаберите ентитет за уређивање или трансформисање.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="ee2d2-131">Користите опције у Power Query прозору како бисте применили трансформације.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="ee2d2-132">Свака трансформација се наводи у оквиру **Примењених корака**.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="ee2d2-133">Power Query пружа бројне унапред направљене могућности трансформације.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="ee2d2-134">За више информација, погледајте [Power Query трансформације](/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="ee2d2-134">For more information, see [Power Query Transformations](/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="ee2d2-135">Можете додати додатне ентитете у извор података ако изаберете **Преузми податке** у дијалогу **Уређивање упита**.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="ee2d2-136">Ове трансформације се изричито препоручују:</span><span class="sxs-lookup"><span data-stu-id="ee2d2-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="ee2d2-137">Ако уносите податке из CSV датотеке, први ред често садржи заглавља.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="ee2d2-138">Идите на **Трансформација табеле** и изаберите **Користи заглавља као први ред**.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="ee2d2-139">Уверите се да је тип података подешен на одговарајући начин.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="ee2d2-140">Изаберите **Сачувај** у доњем углу Power Query прозора да бисте сачували трансформације.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="ee2d2-141">Након чувања, пронаћи ћете свој извор података у оквиру **Подаци** > **Извори података**.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="ee2d2-142">На страници **Извори података**, приметићете да је нови извор података у статусу **Освежавање**.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="ee2d2-143">Доступни Power Query извори података</span><span class="sxs-lookup"><span data-stu-id="ee2d2-143">Available Power Query data sources</span></span>

<span data-ttu-id="ee2d2-144">Погледајте [референцу Power Query конектора](/power-query/connectors/) за ажурирану листу конектора које можете изабрати за увоз података у Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-144">See the [Power Query connector reference](/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="ee2d2-145">Конектори са знаком потврде у колони **Customer Insights (токови података)** су доступни за креирање нових извора података заснованих на решењу Power Query.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="ee2d2-146">Прегледајте документацију одређеног конектора да бисте сазнали више о његовим предусловима, ограничењима и осталим детаљима.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="ee2d2-147">Уређивање Power Query извора података</span><span class="sxs-lookup"><span data-stu-id="ee2d2-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="ee2d2-148">Можда неће бити могуће извршити промене извора података који се тренутно користе у једном од процеса апликације (нпр. *сегментација*, *подударање* или *спајање*).</span><span class="sxs-lookup"><span data-stu-id="ee2d2-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="ee2d2-149">Помоћу странице **Подешавања**, можете пратити напредак сваког активног процеса.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="ee2d2-150">Када се процес доврши, можете се вратити на страницу **Извори података** и унети измене.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="ee2d2-151">У увидима о корисницима идите на **Подаци** > **Извори података**.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="ee2d2-152">Изаберите усправне три тачке поред извора података који желите да промените и изаберите **Уреди** из падајућег менија.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ee2d2-153">![Уређивање опције](media/edit-option-data-sources.png "Уређивање опције")</span><span class="sxs-lookup"><span data-stu-id="ee2d2-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="ee2d2-154">Примените промене и трансформације у дијалогу **Power Query – уређивање упита** као што је описано у одељку [Креирање новог извора података](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="ee2d2-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="ee2d2-155">Како бисте сачували измене, изаберите **Сачувај** у решењу Power Query након што довршите уређивања.</span><span class="sxs-lookup"><span data-stu-id="ee2d2-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]