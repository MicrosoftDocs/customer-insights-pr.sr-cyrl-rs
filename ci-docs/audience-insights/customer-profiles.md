---
title: Приказ профила клијената
description: Стекните комбиновани приказ обједињених података о клијентима.
ms.date: 12/01/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 13308c2f40cda0d7e813b4d94ab47d53b5ce2115
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 12/01/2020
ms.locfileid: "4653908"
---
# <a name="customer-profiles"></a><span data-ttu-id="18566-103">Профили клијената</span><span class="sxs-lookup"><span data-stu-id="18566-103">Customer profiles</span></span>

<span data-ttu-id="18566-104">Страница **Клијенти** приказује комбиновани приказ ваших клијената на основу података са профила прикупљених из [свих извора података](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="18566-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="18566-105">Профили клијената су вам доступни након што сте [креирали обједињени ентитет Клијент](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="18566-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="18566-106">Обавезно довршите поступак обједињавања података да бисте стекли богатије погледе својих клијената.</span><span class="sxs-lookup"><span data-stu-id="18566-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="18566-107">Ова страница такође вам омогућава да претражујете клијенте.</span><span class="sxs-lookup"><span data-stu-id="18566-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="18566-108">Клијенти могу бити појединци или организације (преглед).</span><span class="sxs-lookup"><span data-stu-id="18566-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="18566-109">Сваки профил клијента или организације представљен је плочицом.</span><span class="sxs-lookup"><span data-stu-id="18566-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="18566-110">Изаберите плочицу да бисте видели додатне информације о том конкретном клијенту или организацији.</span><span class="sxs-lookup"><span data-stu-id="18566-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="18566-111">Употребите контроле за страничење на дну странице да бисте видели додатне записе.</span><span class="sxs-lookup"><span data-stu-id="18566-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="18566-112">![B2C профили клијената](media/profiles-customers.png "B2C профили клијената")</span><span class="sxs-lookup"><span data-stu-id="18566-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="18566-113">Организације (Преглед)</span><span class="sxs-lookup"><span data-stu-id="18566-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="18566-114">![B2B профили клијената](media/profile-customers-b2b.png "B2B профили клијената")</span><span class="sxs-lookup"><span data-stu-id="18566-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="18566-115">Ако не можете да видите плочице када изаберете **Клијенти** у навигацији, ваш администратор треба да [дефиниши барем један атрибут се може да се претражује](search-filter-index.md) у одељку **Индекс претраге и филтрирања**.</span><span class="sxs-lookup"><span data-stu-id="18566-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="18566-116">Претрага клијената</span><span class="sxs-lookup"><span data-stu-id="18566-116">Search for customers</span></span>

<span data-ttu-id="18566-117">Претражујте клијенте уносом имена или неког другог атрибута у поље за претрагу.</span><span class="sxs-lookup"><span data-stu-id="18566-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="18566-118">Претраживање функционише само у ентитету Профил клијента који је креиран током процеса обједињавања података.</span><span class="sxs-lookup"><span data-stu-id="18566-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="18566-119">Као администратор, можете конфигурисати атрибуте претраживања користећи страницу **Индекс претраге и филтрирања**.</span><span class="sxs-lookup"><span data-stu-id="18566-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="18566-120">За више информација, погледајте [Управљајте индексом претраге и филтрирања](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="18566-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="18566-121">Филтрирање клијената</span><span class="sxs-lookup"><span data-stu-id="18566-121">Filter customers</span></span>

<span data-ttu-id="18566-122">Можете филтрирати клијенте по пољима ентитета Профил клијента.</span><span class="sxs-lookup"><span data-stu-id="18566-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="18566-123">Слично претраживању, ваш администратор ће прво морати да дефинише поља тако да се могу филтрирати на страници **Индекс претраге и филтрирања**.</span><span class="sxs-lookup"><span data-stu-id="18566-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="18566-124">Изаберите **Филтер** на страници **Клијенти**.</span><span class="sxs-lookup"><span data-stu-id="18566-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="18566-125">Означите поља поред атрибута по којима желите да филтрирате клијенте.</span><span class="sxs-lookup"><span data-stu-id="18566-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="18566-126">![Профили клијената](media/profiles-customers3.png "Профили клијената")</span><span class="sxs-lookup"><span data-stu-id="18566-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="18566-127">Уклоните филтере избором **Обриши филтере** на страници **Клијенти**.</span><span class="sxs-lookup"><span data-stu-id="18566-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="18566-128">Страница са детаљима о клијентима</span><span class="sxs-lookup"><span data-stu-id="18566-128">Customer details page</span></span>

<span data-ttu-id="18566-129">Изаберите било коју плочицу клијента да бисте отворили **страницу са детаљима о клијенту**.</span><span class="sxs-lookup"><span data-stu-id="18566-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="18566-130">Овај приказ садржи обједињене информације за изабраног клијента.</span><span class="sxs-lookup"><span data-stu-id="18566-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="18566-131">Детаљи о клијенту обухватају:</span><span class="sxs-lookup"><span data-stu-id="18566-131">Customer details include:</span></span>

-   <span data-ttu-id="18566-132">**Плочица профила клијента:** Ова плочица приказује различите вредности из ентитета обједињеног профила клијента.</span><span class="sxs-lookup"><span data-stu-id="18566-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="18566-133">Ови детаљи могу да укључују адресу е-поште, име, град итд.</span><span class="sxs-lookup"><span data-stu-id="18566-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="18566-134">**Потенцијална интересовања, потенцијални брендови:** Показује да ли сте конфигурисали директно обогаћивање.</span><span class="sxs-lookup"><span data-stu-id="18566-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="18566-135">Представља потенцијална интересовања и афинитете за брендове које има клијент са профилом сличним овом клијенту.</span><span class="sxs-lookup"><span data-stu-id="18566-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="18566-136">За више информација, погледајте [Обогаћивање профила клијената афинитетима према брендовима и интересовањима](enrichment-microsoft-graph.md).</span><span class="sxs-lookup"><span data-stu-id="18566-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

-   <span data-ttu-id="18566-137">**Мере:** Показује да ли сте конфигурисали једну или више мера одређене врсте: мере атрибута клијента.</span><span class="sxs-lookup"><span data-stu-id="18566-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="18566-138">Укључују израчунате KPI-јеве око ваших клијената на нивоу појединачног клијента.</span><span class="sxs-lookup"><span data-stu-id="18566-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="18566-139">За више информација погледајте [Дефинисање и управљање мерама](measures.md).</span><span class="sxs-lookup"><span data-stu-id="18566-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="18566-140">**Временска оса активности:** Показује да ли сте конфигурисали активности.</span><span class="sxs-lookup"><span data-stu-id="18566-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="18566-141">Приказ временске осе садржи хронолошки сортиране активности овог клијента, почев од најновије активности.</span><span class="sxs-lookup"><span data-stu-id="18566-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="18566-142">За више информација погледајте [активности клијента](activities.md).</span><span class="sxs-lookup"><span data-stu-id="18566-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="18566-143">Изаберите **Повратак на клијенте** да бисте се вратили на страницу за претрагу клијената.</span><span class="sxs-lookup"><span data-stu-id="18566-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="18566-144">Следећи кораци</span><span class="sxs-lookup"><span data-stu-id="18566-144">Next steps</span></span>

<span data-ttu-id="18566-145">[Додајте још извора података](data-sources.md) или [креирајте сегменте клијената](segments.md).</span><span class="sxs-lookup"><span data-stu-id="18566-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>
