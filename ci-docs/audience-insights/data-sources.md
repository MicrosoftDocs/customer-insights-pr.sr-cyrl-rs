---
title: Користите изворе података ради уноса података
description: Научите како да увезете податке из различитих извора.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3c0b4690e18285aa37eef481b3cfac951884ead6
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085548"
---
# <a name="data-sources-overview"></a><span data-ttu-id="1644b-103">Преглед извора података</span><span class="sxs-lookup"><span data-stu-id="1644b-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="1644b-104">Способност увида о корисницима у услузи Dynamics 365 Customer Insights повезује се са подацима из широког скупа извора.</span><span class="sxs-lookup"><span data-stu-id="1644b-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="1644b-105">Повезивање са извором података се често назива процесом *уношења података*.</span><span class="sxs-lookup"><span data-stu-id="1644b-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="1644b-106">Након уношења података, можете их [објединити](data-unification.md) и предузети радњу над њима.</span><span class="sxs-lookup"><span data-stu-id="1644b-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="1644b-107">Додавање извора података</span><span class="sxs-lookup"><span data-stu-id="1644b-107">Add a data source</span></span>

<span data-ttu-id="1644b-108">Погледајте детаљне чланке о томе како да додате извор података, у зависности од тога коју опцију сте изабрали.</span><span class="sxs-lookup"><span data-stu-id="1644b-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="1644b-109">Извор података можете додати на три главна начина:</span><span class="sxs-lookup"><span data-stu-id="1644b-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="1644b-110">Кроз десетине Power Query конектора</span><span class="sxs-lookup"><span data-stu-id="1644b-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="1644b-111">Из Common Data Model фасцикле</span><span class="sxs-lookup"><span data-stu-id="1644b-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="1644b-112">Из вашег сопственог Common Data Service језера</span><span class="sxs-lookup"><span data-stu-id="1644b-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="1644b-113">Додавање података из локалних извора података</span><span class="sxs-lookup"><span data-stu-id="1644b-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="1644b-114">Уношење података из локалних извора података у услугу Увиди у кориснике је подржано на основу Power Platform токова података.</span><span class="sxs-lookup"><span data-stu-id="1644b-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="1644b-115">Токови података се могу омогућити у услузи Customer Insights [навођењем URL адресе Microsoft Dataverse окружења](manage-environments.md#create-an-environment-in-an-existing-organization) приликом подешавања окружења.</span><span class="sxs-lookup"><span data-stu-id="1644b-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="1644b-116">Извори података који се креирају након повезивања Dataverse окружења са услугом Customer Insights ће подразумевано користити [Power Platform токове података](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365).</span><span class="sxs-lookup"><span data-stu-id="1644b-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="1644b-117">Токови података подржавају локалну повезаност помоћу мрежног пролаза за податке.</span><span class="sxs-lookup"><span data-stu-id="1644b-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="1644b-118">Уклоните и поново креирајте изворе података који су постојали пре него што је Dataverse окружење било повезано за [употребу локалних мрежних пролаза за податке](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span><span class="sxs-lookup"><span data-stu-id="1644b-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span></span>

<span data-ttu-id="1644b-119">Мрежни пролази за податке из постојећег Power BI или Power Apps окружења ће бити видљиви и можете поново да их користите у услузи Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1644b-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="1644b-120">Страница са изворима података приказује везе ка Power Platform окружењу у којем можете да прегледате и конфигуришете локалне мрежне пролазе за податке.</span><span class="sxs-lookup"><span data-stu-id="1644b-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="1644b-121">Преглед унетих података</span><span class="sxs-lookup"><span data-stu-id="1644b-121">Review ingested data</span></span>

<span data-ttu-id="1644b-122">Видећете назив сваког унетог извора података, његов статус и последњи пут када су подаци освежени за тај извор.</span><span class="sxs-lookup"><span data-stu-id="1644b-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="1644b-123">Списак извора података можете сортирати по свакој колони.</span><span class="sxs-lookup"><span data-stu-id="1644b-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1644b-124">![Извор података је додат](media/configure-data-datasource-added.png "Извор података је додат")</span><span class="sxs-lookup"><span data-stu-id="1644b-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="1644b-125">Статус</span><span class="sxs-lookup"><span data-stu-id="1644b-125">Status</span></span>  |<span data-ttu-id="1644b-126">Опис</span><span class="sxs-lookup"><span data-stu-id="1644b-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="1644b-127">Успешно</span><span class="sxs-lookup"><span data-stu-id="1644b-127">Successful</span></span>   |<span data-ttu-id="1644b-128">Извор података је успешно унет ако је време наведено у колони **Освежено**.</span><span class="sxs-lookup"><span data-stu-id="1644b-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="1644b-129">Није започето</span><span class="sxs-lookup"><span data-stu-id="1644b-129">Not started</span></span>   |<span data-ttu-id="1644b-130">Извор података још нема унетих података или је још увек у режиму радне верзије.</span><span class="sxs-lookup"><span data-stu-id="1644b-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="1644b-131">Освежавање</span><span class="sxs-lookup"><span data-stu-id="1644b-131">Refreshing</span></span>    |<span data-ttu-id="1644b-132">Унос података је у току.</span><span class="sxs-lookup"><span data-stu-id="1644b-132">Data ingestion is in progress.</span></span> <span data-ttu-id="1644b-133">Ову операцију можете отказати ако изаберете **Заустави освежавање** у колони **Радње**.</span><span class="sxs-lookup"><span data-stu-id="1644b-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="1644b-134">Заустављање освежавања извора података вратиће га у последње стање освежавања.</span><span class="sxs-lookup"><span data-stu-id="1644b-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="1644b-135">Неуспех</span><span class="sxs-lookup"><span data-stu-id="1644b-135">Failed</span></span>     |<span data-ttu-id="1644b-136">Унос података је наишао на грешке.</span><span class="sxs-lookup"><span data-stu-id="1644b-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="1644b-137">Изаберите вредност у колони **Статус** било ког извора података да бисте прегледали више детаља.</span><span class="sxs-lookup"><span data-stu-id="1644b-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="1644b-138">У окну **Детаљи напретка**, проширите ставку **Извори података**.</span><span class="sxs-lookup"><span data-stu-id="1644b-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="1644b-139">Изаберите **Погледај детаље** да бисте добили више информација о статусу освежавања, укључујући детаље о грешкама и надоградње процеса.</span><span class="sxs-lookup"><span data-stu-id="1644b-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="1644b-140">Учитавање података може да потраје.</span><span class="sxs-lookup"><span data-stu-id="1644b-140">Loading data can take some time.</span></span> <span data-ttu-id="1644b-141">Након успешног освежавања, унесени подаци могу се прегледати са странице **Ентитети**.</span><span class="sxs-lookup"><span data-stu-id="1644b-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="1644b-142">За више информација, погледајте чланак [Ентитети](entities.md).</span><span class="sxs-lookup"><span data-stu-id="1644b-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="1644b-143">Освежите извор података</span><span class="sxs-lookup"><span data-stu-id="1644b-143">Refresh a data source</span></span>

<span data-ttu-id="1644b-144">Извори података могу се освежавати по аутоматском распореду или ручно на захтев.</span><span class="sxs-lookup"><span data-stu-id="1644b-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="1644b-145">Идите на **Администратор** > **Систем** > [**Распоред**](system.md#schedule-tab) да бисте конфигурисали заказана освежавања свих унетих извора података.</span><span class="sxs-lookup"><span data-stu-id="1644b-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="1644b-146">Да бисте освежили извор података на захтев, следите ове кораке:</span><span class="sxs-lookup"><span data-stu-id="1644b-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="1644b-147">У увидима о корисницима идите на **Подаци** > **Извори података**</span><span class="sxs-lookup"><span data-stu-id="1644b-147">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="1644b-148">Изаберите вертикалну елипсу поред извора података који желите да освежите и изаберите **Освежи** са падајуће листе.</span><span class="sxs-lookup"><span data-stu-id="1644b-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="1644b-149">Извор података је сада активиран за ручно освежавање.</span><span class="sxs-lookup"><span data-stu-id="1644b-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="1644b-150">Освежавањем извора података ажурираће се и шема ентитета и подаци за све ентитете наведене у извору података.</span><span class="sxs-lookup"><span data-stu-id="1644b-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="1644b-151">Изаберите **Престаните са освежавањем** ако желите да откажете постојеће освежавање и извор података ће се вратити на свој последњи статус освежавања.</span><span class="sxs-lookup"><span data-stu-id="1644b-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="1644b-152">Избриши извор података</span><span class="sxs-lookup"><span data-stu-id="1644b-152">Delete a data source</span></span>

1. <span data-ttu-id="1644b-153">У увидима о корисницима идите на **Подаци** > **Извори података**.</span><span class="sxs-lookup"><span data-stu-id="1644b-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="1644b-154">Изаберите усправне три тачке поред извора података који желите да уклоните и изаберите **Избриши** из падајућег менија.</span><span class="sxs-lookup"><span data-stu-id="1644b-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="1644b-155">Потврдите брисање.</span><span class="sxs-lookup"><span data-stu-id="1644b-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
