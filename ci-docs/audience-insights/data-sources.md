---
title: Користите изворе података ради уноса података
description: Научите како да увезете податке из различитих извора.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 68aa1b56fb634da80a0c64db72f778d57507104d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269716"
---
# <a name="data-sources-overview"></a><span data-ttu-id="c82ee-103">Преглед извора података</span><span class="sxs-lookup"><span data-stu-id="c82ee-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="c82ee-104">Способност увида о корисницима у услузи Dynamics 365 Customer Insights повезује се са подацима из широког скупа извора.</span><span class="sxs-lookup"><span data-stu-id="c82ee-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="c82ee-105">Повезивање са извором података се често назива процесом *уношења података*.</span><span class="sxs-lookup"><span data-stu-id="c82ee-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="c82ee-106">Након уношења података, можете их [објединити](data-unification.md) и предузети радњу над њима.</span><span class="sxs-lookup"><span data-stu-id="c82ee-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="c82ee-107">Додавање извора података</span><span class="sxs-lookup"><span data-stu-id="c82ee-107">Add a data source</span></span>

<span data-ttu-id="c82ee-108">Погледајте детаљне чланке о томе како да додате извор података, у зависности од тога коју опцију сте изабрали.</span><span class="sxs-lookup"><span data-stu-id="c82ee-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="c82ee-109">Извор података можете додати на три главна начина:</span><span class="sxs-lookup"><span data-stu-id="c82ee-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="c82ee-110">Кроз десетине Power Query конектора</span><span class="sxs-lookup"><span data-stu-id="c82ee-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="c82ee-111">Из Common Data Model фасцикле</span><span class="sxs-lookup"><span data-stu-id="c82ee-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="c82ee-112">Из вашег сопственог Common Data Service језера</span><span class="sxs-lookup"><span data-stu-id="c82ee-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="c82ee-113">Још не можете да додате податке из локалних извора података.</span><span class="sxs-lookup"><span data-stu-id="c82ee-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="c82ee-114">Преглед унетих података</span><span class="sxs-lookup"><span data-stu-id="c82ee-114">Review ingested data</span></span>

<span data-ttu-id="c82ee-115">Видећете назив сваког унетог извора података, његов статус и последњи пут када су подаци освежени за тај извор.</span><span class="sxs-lookup"><span data-stu-id="c82ee-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="c82ee-116">Списак извора података можете сортирати по свакој колони.</span><span class="sxs-lookup"><span data-stu-id="c82ee-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c82ee-117">![Извор података је додат](media/configure-data-datasource-added.png "Извор података је додат")</span><span class="sxs-lookup"><span data-stu-id="c82ee-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="c82ee-118">Статус</span><span class="sxs-lookup"><span data-stu-id="c82ee-118">Status</span></span>  |<span data-ttu-id="c82ee-119">Опис</span><span class="sxs-lookup"><span data-stu-id="c82ee-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="c82ee-120">Успешно</span><span class="sxs-lookup"><span data-stu-id="c82ee-120">Successful</span></span>   |<span data-ttu-id="c82ee-121">Извор података је успешно унет ако је време наведено у колони **Освежено**.</span><span class="sxs-lookup"><span data-stu-id="c82ee-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="c82ee-122">Није започето</span><span class="sxs-lookup"><span data-stu-id="c82ee-122">Not started</span></span>   |<span data-ttu-id="c82ee-123">Извор података још нема унетих података или је још увек у режиму радне верзије.</span><span class="sxs-lookup"><span data-stu-id="c82ee-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="c82ee-124">Освежавање</span><span class="sxs-lookup"><span data-stu-id="c82ee-124">Refreshing</span></span>    |<span data-ttu-id="c82ee-125">Унос података је у току.</span><span class="sxs-lookup"><span data-stu-id="c82ee-125">Data ingestion is in progress.</span></span> <span data-ttu-id="c82ee-126">Ову операцију можете отказати ако изаберете **Заустави освежавање** у колони **Радње**.</span><span class="sxs-lookup"><span data-stu-id="c82ee-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="c82ee-127">Заустављање освежавања извора података вратиће га у последње стање освежавања.</span><span class="sxs-lookup"><span data-stu-id="c82ee-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="c82ee-128">Неуспех</span><span class="sxs-lookup"><span data-stu-id="c82ee-128">Failed</span></span>     |<span data-ttu-id="c82ee-129">Унос података је наишао на грешке.</span><span class="sxs-lookup"><span data-stu-id="c82ee-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="c82ee-130">Изаберите вредност у колони **Статус** било ког извора података да бисте прегледали више детаља.</span><span class="sxs-lookup"><span data-stu-id="c82ee-130">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="c82ee-131">У окну **Детаљи напретка**, проширите ставку **Извори података**.</span><span class="sxs-lookup"><span data-stu-id="c82ee-131">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="c82ee-132">Изаберите **Погледај детаље** да бисте добили више информација о статусу освежавања, укључујући детаље о грешкама и надоградње процеса.</span><span class="sxs-lookup"><span data-stu-id="c82ee-132">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="c82ee-133">Учитавање података може да потраје.</span><span class="sxs-lookup"><span data-stu-id="c82ee-133">Loading data can take some time.</span></span> <span data-ttu-id="c82ee-134">Након успешног освежавања, унесени подаци могу се прегледати са странице **Ентитети**.</span><span class="sxs-lookup"><span data-stu-id="c82ee-134">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="c82ee-135">За више информација, погледајте чланак [Ентитети](entities.md).</span><span class="sxs-lookup"><span data-stu-id="c82ee-135">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="c82ee-136">Освежите извор података</span><span class="sxs-lookup"><span data-stu-id="c82ee-136">Refresh a data source</span></span>

<span data-ttu-id="c82ee-137">Извори података могу се освежавати по аутоматском распореду или ручно на захтев.</span><span class="sxs-lookup"><span data-stu-id="c82ee-137">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="c82ee-138">Идите на **Администратор** > **Систем** > [**Распоред**](system.md#schedule-tab) да бисте конфигурисали заказана освежавања свих унетих извора података.</span><span class="sxs-lookup"><span data-stu-id="c82ee-138">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="c82ee-139">Да бисте освежили извор података на захтев, следите ове кораке:</span><span class="sxs-lookup"><span data-stu-id="c82ee-139">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="c82ee-140">У увидима о корисницима идите на **Подаци** > **Извори података**</span><span class="sxs-lookup"><span data-stu-id="c82ee-140">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="c82ee-141">Изаберите вертикалну елипсу поред извора података који желите да освежите и изаберите **Освежи** са падајуће листе.</span><span class="sxs-lookup"><span data-stu-id="c82ee-141">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="c82ee-142">Извор података је сада активиран за ручно освежавање.</span><span class="sxs-lookup"><span data-stu-id="c82ee-142">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="c82ee-143">Освежавањем извора података ажурираће се обе шеме ентитета као и подаци за све ентитете наведене у извору података.</span><span class="sxs-lookup"><span data-stu-id="c82ee-143">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="c82ee-144">Изаберите **Престаните са освежавањем** ако желите да откажете постојеће освежавање и извор података ће се вратити на свој последњи статус освежавања.</span><span class="sxs-lookup"><span data-stu-id="c82ee-144">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="c82ee-145">Избриши извор података</span><span class="sxs-lookup"><span data-stu-id="c82ee-145">Delete a data source</span></span>

1. <span data-ttu-id="c82ee-146">У увидима о корисницима идите на **Подаци** > **Извори података**.</span><span class="sxs-lookup"><span data-stu-id="c82ee-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="c82ee-147">Изаберите усправне три тачке поред извора података који желите да уклоните и изаберите **Избриши** из падајућег менија.</span><span class="sxs-lookup"><span data-stu-id="c82ee-147">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="c82ee-148">Потврдите брисање.</span><span class="sxs-lookup"><span data-stu-id="c82ee-148">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]