---
title: Мапирање ентитета за обједињавање података
description: Мапирајте податке да бисте креирали обједињене профиле клијената.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: e98c7717f7707d43a9fd1fc6f6b0e9c49e4e7ee0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406870"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="6a6d7-103">Ентитети и атрибути мапе</span><span class="sxs-lookup"><span data-stu-id="6a6d7-103">Map entities and attributes</span></span>

<span data-ttu-id="6a6d7-104">**Мапирање** је прва фаза у процесу обједињавања података у увидима о корисницима.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="6a6d7-105">Мапирање се састоји од три фазе:</span><span class="sxs-lookup"><span data-stu-id="6a6d7-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="6a6d7-106">*Избор ентитета*: Идентификујте комбиноване ентитете који воде до скупа података са потпунијим информацијама о вашим клијентима.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="6a6d7-107">*Избор атрибута*: За сваки ентитет одредите колоне које желите да комбинујете и усагласите у фазама *подударање* и *спајање*.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="6a6d7-108">Ове колоне се зову *Атрибути*.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="6a6d7-109">*Избор примарног кључа и семантичког типа*: За сваки ентитет идентификујте атрибут који желите да дефинишете као примарни кључ за тај ентитет, а за сваки атрибут идентификујте семантички тип који најбоље описује тај атрибут.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="6a6d7-110">За више информација о општем току обједињавања података, погледајте [Уједначавање](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="6a6d7-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="6a6d7-111">Изаберите прве ентитете</span><span class="sxs-lookup"><span data-stu-id="6a6d7-111">Select the first entities</span></span>

1. <span data-ttu-id="6a6d7-112">У увидима о корисницима идите на **Подаци** > **Обједини** > **Мапирај**.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="6a6d7-113">Започните фазу мапирања одабиром **Изабери ентитете**.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="6a6d7-114">Изаберите ентитете и атрибуте које желите да користите у фазама *подударање* и *спајање*.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="6a6d7-115">Можете да изаберете тражене атрибуте појединачно из ентитета или да укључите све атрибуте из ентитета избором поља за потврду **Укључи сва поља** на нивоу ентитета.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="6a6d7-116">Препоручујемо да изаберете најмање два ентитета који ће имати користи од процеса обједињавања података.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6a6d7-117">![Пример додавања ентитета](media/data-manager-configure-map-add-entities-example.png "Пример додавања ентитета")</span><span class="sxs-lookup"><span data-stu-id="6a6d7-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="6a6d7-118">У овом примеру додајемо ентитете **eCommerceContacts** и **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="6a6d7-119">Одабиром ових ентитета можете стећи увид у то који од пословних корисника на мрежи су чланови програма лојалности.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="6a6d7-120">Можете претраживати кључне речи по свим атрибутима и ентитетима да бисте изабрали потребне атрибуте које желите да мапирате.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6a6d7-121">![Пример поља за претрагу](media/data-manager-configure-map-search-fields-example.png "Пример поља за претрагу")</span><span class="sxs-lookup"><span data-stu-id="6a6d7-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="6a6d7-122">Изаберите **Примени** да бисте потврдили своје изборе.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="6a6d7-123">Изаберите примарни кључ и семантички тип за атрибуте</span><span class="sxs-lookup"><span data-stu-id="6a6d7-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="6a6d7-124">Након избора ентитета, на страници **Мапа** се наводе изабрани ентитети за преглед.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="6a6d7-125">Дефинишите примарни кључ за ентитет и идентификујте семантички тип за атрибут у ентитету.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="6a6d7-126">**Примарни кључ**: Изаберите један атрибут као примарни кључ за сваки ваш ентитет.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="6a6d7-127">Да би атрибут био важећи примарни кључ, не би требало да садржи дуплиране вредности, недостајуће вредности или празне вредности.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="6a6d7-128">Атрибути типа података ниска, цео број и GUID подржани су као примарни кључеви и биће приказани у пољу за одабир.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="6a6d7-129">**Семантички тип атрибута**: Категорије ваших атрибута, као што су адреса е-поште или име.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="6a6d7-130">Да бисте користили моделе вештачке интелигенције за паметно предвиђање семантике, уштедите време и побољшајте тачност, подесите **Интелигентно мапирање** на **Да**.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="6a6d7-131">Интелигентно мапирање истиче препоруке о семантици засноване на вештачкој интелигенцији у пољу **Тип**.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="6a6d7-132">Ако га подесите на **ИСКЉУЧЕНО**, видећете наше редовне препоруке за мапирање.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="6a6d7-133">Можете одабрати било који семантички тип са доступне листе опција и заменити предложени избор.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6a6d7-134">![Тип атрибута и семантичко предвиђање](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Тип атрибута и семантичко предвиђање")</span><span class="sxs-lookup"><span data-stu-id="6a6d7-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="6a6d7-135">Такође је могуће додати прилагођени семантички тип.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="6a6d7-136">Изаберите поље типа за тај атрибут и унесите своје прилагођено семантичко име типа.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="6a6d7-137">Тако такође можете да промените врсте атрибута које је систем идентификовао.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="6a6d7-138">Сви атрибути за које је семантички тип аутоматски идентификован груписани су у одељку **Преглед мапираних поља**.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="6a6d7-139">Прегледајте ове атрибуте и њихове семантичке типове, јер ће се користити за комбиновање ваших ентитета у кораку обједињавања током уједначавања података.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="6a6d7-140">Атрибути који нису аутоматски мапирани у семантички тип груписани су у одељку **Дефинисање података у немапираним пољима**.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="6a6d7-141">Изаберите поље семантичког типа за немапиране атрибуте или унесите назив прилагођеног типа атрибута.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6a6d7-142">![Примарни кључ и врста атрибута](media/data-manager-configure-map-add-attributes.png "Примарни кључ и врста атрибута")</span><span class="sxs-lookup"><span data-stu-id="6a6d7-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="6a6d7-143">Једно поље би требало да се мапира у семантички тип Person.FullName да би се име клијента попунило у корисничкој картици.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="6a6d7-144">У супротном, картице клијената ће се приказивати без имена.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="6a6d7-145">Додавање и уклањање атрибута и ентитета</span><span class="sxs-lookup"><span data-stu-id="6a6d7-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="6a6d7-146">У дијалогу **Уједначавање** > **Мапа**, изаберите **Уреди поља**.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="6a6d7-147">У окну **Уреди поља**, додајте или уклоните атрибуте и ентитете.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="6a6d7-148">Користите претрагу или листајте да бисте пронашли и изабрали своје атрибуте и ентитете од интереса.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="6a6d7-149">Не можете уклонити атрибут или ентитет ако се већ подударају.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6a6d7-150">![Додајте или уклоните атрибуте](media/configure-data-map-edit.png "Додајте или уклоните атрибуте")</span><span class="sxs-lookup"><span data-stu-id="6a6d7-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="6a6d7-151">Изаберите **Примени**.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="6a6d7-152">Додавање слика профилима</span><span class="sxs-lookup"><span data-stu-id="6a6d7-152">Add images to profiles</span></span>

<span data-ttu-id="6a6d7-153">Ако ентитет садржи URL адресе јавно доступних слика или логотипа профила, можете их додати у обједињени профил клијента.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="6a6d7-154">Изаберите ентитет и пронађите поље које садржи URL до слике профила.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="6a6d7-155">У поље за унос **Тип** ручно унесите следећу вредност:</span><span class="sxs-lookup"><span data-stu-id="6a6d7-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="6a6d7-156">За особу: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="6a6d7-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="6a6d7-157">За организацију: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="6a6d7-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="6a6d7-158">Наставите са корацима обједињавања и уверите се да је атрибут који садржи URL адресу слике такође додат у корак [Спајање](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="6a6d7-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="6a6d7-159">Подешавање атрибута за организације</span><span class="sxs-lookup"><span data-stu-id="6a6d7-159">Set attributes for organizations</span></span>

<span data-ttu-id="6a6d7-160">За организације (преглед), тип атрибута треба да буде мапиран на „Organization.Name“</span><span class="sxs-lookup"><span data-stu-id="6a6d7-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="6a6d7-161">![Примарни кључ и врста атрибута B2B](media/configure-data-map-edit-b2b.png "Примарни кључ и врста атрибута B2B")</span><span class="sxs-lookup"><span data-stu-id="6a6d7-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="6a6d7-162">Следећи корак</span><span class="sxs-lookup"><span data-stu-id="6a6d7-162">Next step</span></span>

<span data-ttu-id="6a6d7-163">Као део процеса обједињавања података, идите на страницу **Подударање**.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="6a6d7-164">Посетите чланак [**Подударање**](match-entities.md) да бисте више сазнали о овој фази.</span><span class="sxs-lookup"><span data-stu-id="6a6d7-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="6a6d7-165">Погледајте следећи видео: [Први кораци: Креирање јединственог профила клијента](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="6a6d7-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>
