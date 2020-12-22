---
title: Power Apps конектор
description: Повежите се са услугама Power Apps и Power Automate.
ms.date: 08/21/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b6ec103e29e218b2f27bfc1193300ea793a6b30b
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406835"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="4f003-103">Microsoft Power Apps конектор (преглед)</span><span class="sxs-lookup"><span data-stu-id="4f003-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="4f003-104">Уведите обједињене корисничке профиле у своје персонализоване апликације помоћу програма Power Apps.</span><span class="sxs-lookup"><span data-stu-id="4f003-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="4f003-105">Повежите Power Apps и Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="4f003-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="4f003-106">Customer Insights је један од многих [доступних извора за податке у програму Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="4f003-106">Customer Insights is one of the many [available sources for data in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="4f003-107">Погледајте Power Apps документацију да бисте сазнали како да [додате пренос података у апликацију](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="4f003-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="4f003-108">Препоручујемо да такође прегледате [како Power Apps користи делегирање за обраду великих скупова података у апликацијама са подлогом](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="4f003-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="4f003-109">Доступни ентитети</span><span class="sxs-lookup"><span data-stu-id="4f003-109">Available entities</span></span>

<span data-ttu-id="4f003-110">Када додате услугу Customer Insights као везу за пренос података, можете изабрати следеће ентитете у програму Power Apps:</span><span class="sxs-lookup"><span data-stu-id="4f003-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="4f003-111">Клијент: да користите податке из [обједињеног профила клијента](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="4f003-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="4f003-112">Активност обједињеног клијента: да приказујете [временску осу активности](activities.md) у апликацији.</span><span class="sxs-lookup"><span data-stu-id="4f003-112">Unified Customer Activity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="4f003-113">Ограничења</span><span class="sxs-lookup"><span data-stu-id="4f003-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="4f003-114">Повратни ентитети</span><span class="sxs-lookup"><span data-stu-id="4f003-114">Retrievable entities</span></span>

<span data-ttu-id="4f003-115">Можете да повратите само ентитете **Клијент**, **Обједињена активност** и **Сегменти** кроз Power Apps конектор.</span><span class="sxs-lookup"><span data-stu-id="4f003-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="4f003-116">Други ентитети се приказују јер их основни конектор подржава кроз окидаче у услузи Power Automate.</span><span class="sxs-lookup"><span data-stu-id="4f003-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="4f003-117">Делегирање</span><span class="sxs-lookup"><span data-stu-id="4f003-117">Delegation</span></span>

<span data-ttu-id="4f003-118">Делегирање ради за ентитет Клијент и ентитет Обједињена активност.</span><span class="sxs-lookup"><span data-stu-id="4f003-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="4f003-119">Делегирање за ентитет **Клијент**: Да бисте користили делегирање за овај ентитет, поља треба индексирати у одељку [Индекс претраге и филтрирања](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="4f003-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="4f003-120">Делегирање за ентитет **Обједињена активност**: Делегирање за овај ентитет ради само за поља **ActivityId** и **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="4f003-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="4f003-121">За више информација о делегирању, погледајте [Power Apps преносиве функције и операције](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="4f003-121">For more information about delegation, see [Power Apps delegable functions and operations](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="4f003-122">Пример контроле галерије</span><span class="sxs-lookup"><span data-stu-id="4f003-122">Example gallery control</span></span>

<span data-ttu-id="4f003-123">На пример, додајете профиле клијената у [контролу галерије](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="4f003-123">For example, you add customer profiles to a [gallery control](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="4f003-124">Додајте контролу **Галерија** у апликацију коју градите.</span><span class="sxs-lookup"><span data-stu-id="4f003-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4f003-125">![Додајте елемент галерије](media/connector-powerapps9.png "Додајте елемент галерије")</span><span class="sxs-lookup"><span data-stu-id="4f003-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="4f003-126">Изаберите **Клијент** као извор података за ставке.</span><span class="sxs-lookup"><span data-stu-id="4f003-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="4f003-127">![Изаберите извор података](media/choose-datasource-powerapps.png "Изаберите извор података")</span><span class="sxs-lookup"><span data-stu-id="4f003-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="4f003-128">Можете да промените таблу са подацима на десној страни да бисте изабрали поље које ће ентитет Клијент приказати у галерији.</span><span class="sxs-lookup"><span data-stu-id="4f003-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="4f003-129">Ако желите да у галерији прикажете било које поље одабраног клијента, попуните својство Текст ознаке: **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="4f003-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="4f003-130">Пример: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="4f003-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="4f003-131">Да бисте приказали обједињену временску осу за клијента, додајте елемент Галерија и додајте својство Ставке: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="4f003-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="4f003-132">Пример: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="4f003-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>
