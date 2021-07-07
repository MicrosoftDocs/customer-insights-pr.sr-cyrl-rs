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
ms.openlocfilehash: 54dd7b629d4b4e7f640b932b0f9246e0602f46bd
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304714"
---
# <a name="data-sources-overview"></a><span data-ttu-id="39582-103">Преглед извора података</span><span class="sxs-lookup"><span data-stu-id="39582-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="39582-104">Способност увида о корисницима у услузи Dynamics 365 Customer Insights повезује се са подацима из широког скупа извора.</span><span class="sxs-lookup"><span data-stu-id="39582-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="39582-105">Повезивање са извором података се често назива процесом *уношења података*.</span><span class="sxs-lookup"><span data-stu-id="39582-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="39582-106">Након уношења података, можете их [објединити](data-unification.md) и предузети радњу над њима.</span><span class="sxs-lookup"><span data-stu-id="39582-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="39582-107">Додавање извора података</span><span class="sxs-lookup"><span data-stu-id="39582-107">Add a data source</span></span>

<span data-ttu-id="39582-108">Погледајте детаљне чланке о томе како да додате извор података, у зависности од тога коју опцију сте изабрали.</span><span class="sxs-lookup"><span data-stu-id="39582-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="39582-109">Извор података можете додати на три главна начина:</span><span class="sxs-lookup"><span data-stu-id="39582-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="39582-110">Кроз десетине Power Query конектора</span><span class="sxs-lookup"><span data-stu-id="39582-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="39582-111">Из Common Data Model фасцикле</span><span class="sxs-lookup"><span data-stu-id="39582-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="39582-112">Из вашег сопственог Microsoft Dataverse језера</span><span class="sxs-lookup"><span data-stu-id="39582-112">From your own Microsoft Dataverse lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="39582-113">Додавање података из локалних извора података</span><span class="sxs-lookup"><span data-stu-id="39582-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="39582-114">Уношење података из локалних извора података у услугу Увиди у кориснике подржано је на основу Microsoft Power Platform токова података.</span><span class="sxs-lookup"><span data-stu-id="39582-114">Ingesting data from on-premises data sources in audience insights is supported based on Microsoft Power Platform dataflows.</span></span> <span data-ttu-id="39582-115">Токови података се могу омогућити у услузи Customer Insights [навођењем URL адресе Microsoft Dataverse окружења](manage-environments.md#create-an-environment-in-an-existing-organization) приликом подешавања окружења.</span><span class="sxs-lookup"><span data-stu-id="39582-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="39582-116">Извори података који се креирају након повезивања Dataverse окружења са услугом Customer Insights ће подразумевано користити [Power Platform токове података](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365).</span><span class="sxs-lookup"><span data-stu-id="39582-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="39582-117">Токови података подржавају локалну повезаност помоћу мрежног пролаза за податке.</span><span class="sxs-lookup"><span data-stu-id="39582-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="39582-118">Уклоните и поново креирајте изворе података који су постојали пре него што је Dataverse окружење било повезано за [употребу локалних мрежних пролаза за податке](/data-integration/gateway/service-gateway-app.md).</span><span class="sxs-lookup"><span data-stu-id="39582-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/data-integration/gateway/service-gateway-app.md).</span></span>

<span data-ttu-id="39582-119">Мрежни пролази за податке из постојећег Power BI или Power Apps окружења ће бити видљиви и можете поново да их користите у услузи Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="39582-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="39582-120">Страница са изворима података приказује везе до Microsoft Power Platform окружења у којем можете да прегледате и локалне мрежне пролазе за податке.</span><span class="sxs-lookup"><span data-stu-id="39582-120">The data sources page shows links to go to the Microsoft Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="39582-121">Преглед унетих података</span><span class="sxs-lookup"><span data-stu-id="39582-121">Review ingested data</span></span>

<span data-ttu-id="39582-122">Видећете назив сваког унетог извора података, његов статус и последњи пут када су подаци освежени за тај извор.</span><span class="sxs-lookup"><span data-stu-id="39582-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="39582-123">Списак извора података можете сортирати по свакој колони.</span><span class="sxs-lookup"><span data-stu-id="39582-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="39582-124">![Извор података је додат](media/configure-data-datasource-added.png "Извор података је додат")</span><span class="sxs-lookup"><span data-stu-id="39582-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="39582-125">Статус</span><span class="sxs-lookup"><span data-stu-id="39582-125">Status</span></span>  |<span data-ttu-id="39582-126">Опис</span><span class="sxs-lookup"><span data-stu-id="39582-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="39582-127">Успешно</span><span class="sxs-lookup"><span data-stu-id="39582-127">Successful</span></span>   |<span data-ttu-id="39582-128">Извор података је успешно унет ако је време наведено у колони **Освежено**.</span><span class="sxs-lookup"><span data-stu-id="39582-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="39582-129">Није започето</span><span class="sxs-lookup"><span data-stu-id="39582-129">Not started</span></span>   |<span data-ttu-id="39582-130">Извор података још нема унетих података или је још увек у режиму радне верзије.</span><span class="sxs-lookup"><span data-stu-id="39582-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="39582-131">Освежавање</span><span class="sxs-lookup"><span data-stu-id="39582-131">Refreshing</span></span>    |<span data-ttu-id="39582-132">Унос података је у току.</span><span class="sxs-lookup"><span data-stu-id="39582-132">Data ingestion is in progress.</span></span> <span data-ttu-id="39582-133">Ову операцију можете отказати ако изаберете **Заустави освежавање** у колони **Радње**.</span><span class="sxs-lookup"><span data-stu-id="39582-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="39582-134">Заустављање освежавања извора података вратиће га у последње стање освежавања.</span><span class="sxs-lookup"><span data-stu-id="39582-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="39582-135">Неуспех</span><span class="sxs-lookup"><span data-stu-id="39582-135">Failed</span></span>     |<span data-ttu-id="39582-136">Унос података је наишао на грешке.</span><span class="sxs-lookup"><span data-stu-id="39582-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="39582-137">Изаберите вредност у колони **Статус** било ког извора података да бисте прегледали више детаља.</span><span class="sxs-lookup"><span data-stu-id="39582-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="39582-138">У окну **Детаљи напретка**, проширите ставку **Извори података**.</span><span class="sxs-lookup"><span data-stu-id="39582-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="39582-139">Изаберите **Погледај детаље** да бисте добили више информација о статусу освежавања, укључујући детаље о грешкама и надоградње процеса.</span><span class="sxs-lookup"><span data-stu-id="39582-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="39582-140">Учитавање података може потрајати.</span><span class="sxs-lookup"><span data-stu-id="39582-140">Loading data can take time.</span></span> <span data-ttu-id="39582-141">Након успешног освежавања, унесени подаци могу се прегледати са странице **Ентитети**.</span><span class="sxs-lookup"><span data-stu-id="39582-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="39582-142">За више информација, погледајте чланак [Ентитети](entities.md).</span><span class="sxs-lookup"><span data-stu-id="39582-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="39582-143">Освежите извор података</span><span class="sxs-lookup"><span data-stu-id="39582-143">Refresh a data source</span></span>

<span data-ttu-id="39582-144">Извори података могу се освежавати по аутоматском распореду или ручно на захтев.</span><span class="sxs-lookup"><span data-stu-id="39582-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="39582-145">Идите на **Администратор** > **Систем** > [**Распоред**](system.md#schedule-tab) да бисте конфигурисали заказана освежавања свих унетих извора података.</span><span class="sxs-lookup"><span data-stu-id="39582-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="39582-146">Да бисте освежили извор података на захтев, следите ове кораке:</span><span class="sxs-lookup"><span data-stu-id="39582-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="39582-147">У увидима о корисницима идите на **Подаци** > **Извори података**.</span><span class="sxs-lookup"><span data-stu-id="39582-147">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="39582-148">Изаберите вертикалне три тачке поред извора података које желите да освежите и изаберите **Освежи** из падајуће листе.</span><span class="sxs-lookup"><span data-stu-id="39582-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the dropdown list.</span></span>

3. <span data-ttu-id="39582-149">Извор података је сада активиран за ручно освежавање.</span><span class="sxs-lookup"><span data-stu-id="39582-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="39582-150">Освежавањем извора података ажурираће се и шема ентитета и подаци за све ентитете наведене у извору података.</span><span class="sxs-lookup"><span data-stu-id="39582-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="39582-151">Изаберите **Престаните са освежавањем** ако желите да откажете постојеће освежавање и извор података ће се вратити на свој последњи статус освежавања.</span><span class="sxs-lookup"><span data-stu-id="39582-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="39582-152">Избриши извор података</span><span class="sxs-lookup"><span data-stu-id="39582-152">Delete a data source</span></span>

1. <span data-ttu-id="39582-153">У увидима о корисницима идите на **Подаци** > **Извори података**.</span><span class="sxs-lookup"><span data-stu-id="39582-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="39582-154">Изаберите вертикалне три тачке поред извора података које желите да уклоните и изаберите **Избриши** из падајућег менија.</span><span class="sxs-lookup"><span data-stu-id="39582-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the dropdown menu.</span></span>

3. <span data-ttu-id="39582-155">Потврдите брисање.</span><span class="sxs-lookup"><span data-stu-id="39582-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
