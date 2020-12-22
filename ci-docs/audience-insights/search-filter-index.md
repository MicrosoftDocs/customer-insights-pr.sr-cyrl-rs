---
title: Претрага и филтрирање профила клијената
description: Брзо пронађите информације о обједињеним профилима клијената и филтрирајте према одређеним атрибутима.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406880"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="f3b3f-103">Профили клијената: Индекс за претраживање и филтрирање</span><span class="sxs-lookup"><span data-stu-id="f3b3f-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="f3b3f-104">Резултат обједињавања података о клијентима је ентитет профила клијента који пружа јединствен поглед на вашу укупну корисничку базу.</span><span class="sxs-lookup"><span data-stu-id="f3b3f-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="f3b3f-105">Да бисте брзо [пронашли информације о одређеном клијенту или групи клијената](customer-profiles.md), можете да конфигуришете могућности **претраге** и **филтрирања** на страници **Клијенти**.</span><span class="sxs-lookup"><span data-stu-id="f3b3f-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="f3b3f-106">Читајте даље како бисте сазнали како администратори могу да уређују атрибуте на страници **Индекс претраге и филтрирања**, које су на располагању корисницима за претраживање и филтрирање.</span><span class="sxs-lookup"><span data-stu-id="f3b3f-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f3b3f-107">![Филтер претраге](media/search-filter.png "Филтер претраге")</span><span class="sxs-lookup"><span data-stu-id="f3b3f-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="f3b3f-108">Додајте поља и одредите атрибуте</span><span class="sxs-lookup"><span data-stu-id="f3b3f-108">Add fields and specify attributes</span></span>

<span data-ttu-id="f3b3f-109">Ако као администратор први пут дефинишете атрибуте који се могу претраживати, прво морате дефинисати индексирана поља.</span><span class="sxs-lookup"><span data-stu-id="f3b3f-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="f3b3f-110">Предлажемо вам да одаберете све атрибуте по којима корисници могу да претражују и филтрирају клијенте на страници **Клијенти**.</span><span class="sxs-lookup"><span data-stu-id="f3b3f-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="f3b3f-111">Можете одредити само оне атрибуте који постоје у ентитету Профил клијента који сте креирали током поступка обједињавања података.</span><span class="sxs-lookup"><span data-stu-id="f3b3f-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="f3b3f-112">Отворите страницу **Клијенти** и изаберите **Индекс претраге и филтрирања**.</span><span class="sxs-lookup"><span data-stu-id="f3b3f-112">Open the **Customers** page and select **Search & filter index**.</span></span>

> [!NOTE]
> <span data-ttu-id="f3b3f-113">Креирамо подразумевану конфигурацију индекса претраге за доступне атрибуте у ентитету клијента из следећих семантичких типова који су дефинисани на страници Мапа.</span><span class="sxs-lookup"><span data-stu-id="f3b3f-113">We create a default search index configuration on the available attributes in the Customer entity from the following semantic types as defined on the Map page.</span></span>
> - <span data-ttu-id="f3b3f-114">Име, презиме, средње име, пуно име особе</span><span class="sxs-lookup"><span data-stu-id="f3b3f-114">Person First name, Last name, Middle name, Full Name</span></span>
> - <span data-ttu-id="f3b3f-115">Име организације</span><span class="sxs-lookup"><span data-stu-id="f3b3f-115">Organization Name</span></span>
> - <span data-ttu-id="f3b3f-116">Е-адреса</span><span class="sxs-lookup"><span data-stu-id="f3b3f-116">Email address</span></span>
> - <span data-ttu-id="f3b3f-117">Број телефона</span><span class="sxs-lookup"><span data-stu-id="f3b3f-117">Phone number</span></span>
> - <span data-ttu-id="f3b3f-118">Информације о локацији</span><span class="sxs-lookup"><span data-stu-id="f3b3f-118">Location information</span></span>

2. <span data-ttu-id="f3b3f-119">Изаберите **+ Додај** да бисте навели индексирана поља.</span><span class="sxs-lookup"><span data-stu-id="f3b3f-119">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="f3b3f-120">Изаберите атрибуте у листи коју желите да додате као индексирана поља.</span><span class="sxs-lookup"><span data-stu-id="f3b3f-120">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="f3b3f-121">Увек можете додати више атрибута ако изаберете **Додај**.</span><span class="sxs-lookup"><span data-stu-id="f3b3f-121">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="f3b3f-122">Такође можете уклонити све одабране атрибуте ако изаберете симбол **Уклони**.</span><span class="sxs-lookup"><span data-stu-id="f3b3f-122">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="f3b3f-123">Истражите табелу са индексираним пољима клијената</span><span class="sxs-lookup"><span data-stu-id="f3b3f-123">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="f3b3f-124">Следеће информације су представљене у табели.</span><span class="sxs-lookup"><span data-stu-id="f3b3f-124">The following information is presented in the table.</span></span>

- <span data-ttu-id="f3b3f-125">**Име**: Представља име атрибута онако како је приказано у ентитету Профил клијента.</span><span class="sxs-lookup"><span data-stu-id="f3b3f-125">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="f3b3f-126">**Тип података**: Одређује да ли је тип података ниска, број или датум.</span><span class="sxs-lookup"><span data-stu-id="f3b3f-126">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="f3b3f-127">**Укључено у претрагу**: Одређује да ли се овај атрибут може користити за претраживање клијената на страници **Клијенти** помоћу поља **Претрага**.</span><span class="sxs-lookup"><span data-stu-id="f3b3f-127">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="f3b3f-128">**Додај филтер**: Контрола за дефинисање како се овај атрибут може користити за филтрирање на страници **Клијенти**.</span><span class="sxs-lookup"><span data-stu-id="f3b3f-128">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="f3b3f-129">Уређивање опција филтрирања за одређени атрибут</span><span class="sxs-lookup"><span data-stu-id="f3b3f-129">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="f3b3f-130">Мени **Филтер** на страници **Клијенти** може да садржи различит број нивоа атрибута (нпр. различите старосне групе по којима се клијенти филтрирају).</span><span class="sxs-lookup"><span data-stu-id="f3b3f-130">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="f3b3f-131">Изаберите **Додај филтер** за дати атрибут на страници **Индекс претраге и филтрирања**.</span><span class="sxs-lookup"><span data-stu-id="f3b3f-131">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="f3b3f-132">Можете дефинисати број резултата и редослед по коме ће они бити организовани.</span><span class="sxs-lookup"><span data-stu-id="f3b3f-132">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="f3b3f-133">У зависности од типа података атрибута, појављује се једно од следећих окана.</span><span class="sxs-lookup"><span data-stu-id="f3b3f-133">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="f3b3f-134">Атрибути типа ниске: Наведите број жељених резултата у окну **Опције филтрирања ниски** и смернице за редослед по ком ће бити организовани.</span><span class="sxs-lookup"><span data-stu-id="f3b3f-134">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="f3b3f-135">Атрибути нумеричког типа: Наведите обухваћене интервале у окну **Опције филтрирања бројева** и смернице за редослед по ком ће бити организовани.</span><span class="sxs-lookup"><span data-stu-id="f3b3f-135">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="f3b3f-136">Атрибути датума типа: Наведите обухваћене интервале у окну **Опције филтрирања датума** и смернице за редослед по ком ће бити организовани.</span><span class="sxs-lookup"><span data-stu-id="f3b3f-136">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="f3b3f-137">Изаберите **Сачувај** да примените промене.</span><span class="sxs-lookup"><span data-stu-id="f3b3f-137">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="f3b3f-138">Изаберите **Покрени** када будете спремни да примените своја подешавања.</span><span class="sxs-lookup"><span data-stu-id="f3b3f-138">Select **Run** once you're ready to apply your settings.</span></span>
