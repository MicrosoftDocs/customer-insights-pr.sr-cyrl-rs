---
title: Инкрементално освежавање за изворе података засноване на услузи Power Query
description: Освежите нове и ажуриране податке за велике изворе података на основу услуге Power Query.
ms.date: 09/28/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 03f76bcfc7336d8430146e8a26ffa649c6a17db0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596839"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="df421-103">Инкрементално освежавање за изворе података засноване на услузи Power Query</span><span class="sxs-lookup"><span data-stu-id="df421-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="df421-104">Инкрементално освежавање извора података пружа следеће предности:</span><span class="sxs-lookup"><span data-stu-id="df421-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="df421-105">**Бржа освежавања** – Освежавају се само подаци који су промењени.</span><span class="sxs-lookup"><span data-stu-id="df421-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="df421-106">На пример, можете да освежите само протеклих пет дана скупа података из претходног периода.</span><span class="sxs-lookup"><span data-stu-id="df421-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="df421-107">**Повећана поузданост** – Уз мање освежавања, не морате дуго да одржавате везе са системима са променљивим изворима, смањујући ризик од проблема са повезивањем.</span><span class="sxs-lookup"><span data-stu-id="df421-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="df421-108">**Смањена потрошња ресурса** – Освежавање само подскупа укупних података доводи до ефикаснијег коришћења рачунарских ресурса и смањења утицаја на животну средину.</span><span class="sxs-lookup"><span data-stu-id="df421-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="df421-109">Конфигурисање постепеног освежавања</span><span class="sxs-lookup"><span data-stu-id="df421-109">Configure incremental refresh</span></span>

<span data-ttu-id="df421-110">Увиди о корисницима омогућавају инкрементално освежавање за изворе података увезене преко услуге Power Query која подржава инкрементални унос.</span><span class="sxs-lookup"><span data-stu-id="df421-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="df421-111">На пример, Azure SQL базе података са пољима датума и времена, која показују када су записи датума последњи пут ажурирани.</span><span class="sxs-lookup"><span data-stu-id="df421-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="df421-112">[Направите нови извор података на основу услуге Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="df421-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="df421-113">Наведите назив за извор података.</span><span class="sxs-lookup"><span data-stu-id="df421-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="df421-114">Изаберите извор података који подржава постепено освежавање, као што је Azure SQL база података.</span><span class="sxs-lookup"><span data-stu-id="df421-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="df421-115">Изаберите ентитете или табеле за унос.</span><span class="sxs-lookup"><span data-stu-id="df421-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="df421-116">Довршите кораке трансформације и изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="df421-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="df421-117">У дијалогу **Подесите постепено освежавање** изаберите **Подеси** да отворите **Подешавања постепеног освежавања**.</span><span class="sxs-lookup"><span data-stu-id="df421-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="df421-118">Ако изаберете **Прескочи**, извор података ће освежити целокупни скуп података.</span><span class="sxs-lookup"><span data-stu-id="df421-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="df421-119">Касније можете применити и постепено освежавање уређивањем постојећег извора података.</span><span class="sxs-lookup"><span data-stu-id="df421-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="df421-120">У **подешавањима постепеног освежавања**, конфигурисаћете постепено освежавање за све ентитете које сте изабрали приликом креирања извора података.</span><span class="sxs-lookup"><span data-stu-id="df421-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="df421-121">![Конфигурисање ентитета у извору података за постепено освежавање](media/incremental-refresh-settings.png "Конфигурисање ентитета у извору података за постепено освежавање")</span><span class="sxs-lookup"><span data-stu-id="df421-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="df421-122">Изаберите ентитет и наведите следеће детаље:</span><span class="sxs-lookup"><span data-stu-id="df421-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="df421-123">**Дефинишите примарни кључ**: Изаберите примарни кључ ентитета или табеле.</span><span class="sxs-lookup"><span data-stu-id="df421-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="df421-124">**Дефинишите поље „последњи пут ажурирано“**: Ово поље ће приказивати само атрибуте типа датума или времена.</span><span class="sxs-lookup"><span data-stu-id="df421-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="df421-125">Изаберите атрибут који показује када су записи последњи пут ажурирани.</span><span class="sxs-lookup"><span data-stu-id="df421-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="df421-126">Користиће се за идентификацију записа који спадају у временски оквир за инкрементално освежавање.</span><span class="sxs-lookup"><span data-stu-id="df421-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="df421-127">**Провери да ли постоје исправке на сваких**: Наведите колико дуг временски оквир за постепено освежавање желите да буде.</span><span class="sxs-lookup"><span data-stu-id="df421-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="df421-128">Изаберите **Сачувај** да бисте довршили креирање извора података.</span><span class="sxs-lookup"><span data-stu-id="df421-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="df421-129">Почетно освежавање података биће потпуно освежење.</span><span class="sxs-lookup"><span data-stu-id="df421-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="df421-130">Након тога, инкрементално освежавање података дешава се као што је конфигурисано у претходном кораку.</span><span class="sxs-lookup"><span data-stu-id="df421-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]