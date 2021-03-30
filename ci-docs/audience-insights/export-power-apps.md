---
title: Power Apps конектор
description: Повежите се са услугама Power Apps и Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3fa91553fd50a22ab62b5a2b1e3f13b9483776a8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598173"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="2fa79-103">Microsoft Power Apps конектор (преглед)</span><span class="sxs-lookup"><span data-stu-id="2fa79-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="2fa79-104">Уведите обједињене корисничке профиле у своје персонализоване апликације помоћу програма Power Apps.</span><span class="sxs-lookup"><span data-stu-id="2fa79-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="2fa79-105">Повежите Power Apps и Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="2fa79-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="2fa79-106">Customer Insights је један од многих [доступних извора за податке у програму Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="2fa79-106">Customer Insights is one of the many [available sources for data in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="2fa79-107">Погледајте Power Apps документацију да бисте сазнали како да [додате пренос података у апликацију](/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="2fa79-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="2fa79-108">Препоручујемо да такође прегледате [како Power Apps користи делегирање за обраду великих скупова података у апликацијама са подлогом](/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="2fa79-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="2fa79-109">Доступни ентитети</span><span class="sxs-lookup"><span data-stu-id="2fa79-109">Available entities</span></span>

<span data-ttu-id="2fa79-110">Када додате услугу Customer Insights као везу за пренос података, можете изабрати следеће ентитете у програму Power Apps:</span><span class="sxs-lookup"><span data-stu-id="2fa79-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="2fa79-111">Клијент: да користите податке из [обједињеног профила клијента](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="2fa79-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="2fa79-112">UnifiedActivity: да приказујете [временску осу активности](activities.md) у апликацији.</span><span class="sxs-lookup"><span data-stu-id="2fa79-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="2fa79-113">Ограничења</span><span class="sxs-lookup"><span data-stu-id="2fa79-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="2fa79-114">Повратни ентитети</span><span class="sxs-lookup"><span data-stu-id="2fa79-114">Retrievable entities</span></span>

<span data-ttu-id="2fa79-115">Можете да повратите само ентитете **Клијент**, **Обједињена активност** и **Сегменти** кроз Power Apps конектор.</span><span class="sxs-lookup"><span data-stu-id="2fa79-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="2fa79-116">Други ентитети се приказују јер их основни конектор подржава кроз окидаче у услузи Power Automate.</span><span class="sxs-lookup"><span data-stu-id="2fa79-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="2fa79-117">Делегирање</span><span class="sxs-lookup"><span data-stu-id="2fa79-117">Delegation</span></span>

<span data-ttu-id="2fa79-118">Делегирање ради за ентитет Клијент и ентитет Обједињена активност.</span><span class="sxs-lookup"><span data-stu-id="2fa79-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="2fa79-119">Делегирање за ентитет **Клијент**: Да бисте користили делегирање за овај ентитет, поља треба индексирати у одељку [Индекс претраге и филтрирања](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="2fa79-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="2fa79-120">Делегирање за ентитет **Обједињена активност**: Делегирање за овај ентитет ради само за поља **ActivityId** и **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="2fa79-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="2fa79-121">За више информација о делегирању, погледајте [Power Apps преносиве функције и операције](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="2fa79-121">For more information about delegation, see [Power Apps delegable functions and operations](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="2fa79-122">Пример контроле галерије</span><span class="sxs-lookup"><span data-stu-id="2fa79-122">Example gallery control</span></span>

<span data-ttu-id="2fa79-123">На пример, додајете профиле клијената у [контролу галерије](/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="2fa79-123">For example, you add customer profiles to a [gallery control](/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="2fa79-124">Додајте контролу **Галерија** у апликацију коју градите.</span><span class="sxs-lookup"><span data-stu-id="2fa79-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2fa79-125">![Додајте елемент галерије](media/connector-powerapps9.png "Додајте елемент галерије")</span><span class="sxs-lookup"><span data-stu-id="2fa79-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="2fa79-126">Изаберите **Клијент** као извор података за ставке.</span><span class="sxs-lookup"><span data-stu-id="2fa79-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2fa79-127">![Изаберите извор података](media/choose-datasource-powerapps.png "Изаберите извор података")</span><span class="sxs-lookup"><span data-stu-id="2fa79-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="2fa79-128">Можете да промените таблу са подацима на десној страни да бисте изабрали поље које ће ентитет Клијент приказати у галерији.</span><span class="sxs-lookup"><span data-stu-id="2fa79-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="2fa79-129">Ако желите да у галерији прикажете било које поље одабраног клијента, попуните својство Текст ознаке: **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="2fa79-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="2fa79-130">Пример: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="2fa79-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="2fa79-131">Да бисте приказали обједињену временску осу за клијента, додајте елемент Галерија и додајте својство Ставке: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="2fa79-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="2fa79-132">Пример: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="2fa79-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]