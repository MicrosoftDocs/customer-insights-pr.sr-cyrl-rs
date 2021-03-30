---
title: Активности клијента
description: Дефинишите активности клијената и прегледајте их на временској оси клијената.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: fbfa9d7e00859cc80c24b98bd2dc806f1fda7803
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596747"
---
# <a name="customer-activities"></a><span data-ttu-id="94756-103">Активности клијента</span><span class="sxs-lookup"><span data-stu-id="94756-103">Customer activities</span></span>

<span data-ttu-id="94756-104">Комбинујте активности клијената из [разних извора података](data-sources.md) у услузи Dynamics 365 Customer Insights да бисте креирали временску осу клијената која наводи активности у хронолошком редоследу.</span><span class="sxs-lookup"><span data-stu-id="94756-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="94756-105">Временску осу можете укључити у апликације за ангажовање клијената у систему Dynamics 365 преко [програмског додатка картице клијента](customer-card-add-in.md) или у Power BI контролној табли.</span><span class="sxs-lookup"><span data-stu-id="94756-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="94756-106">Дефинишите активност</span><span class="sxs-lookup"><span data-stu-id="94756-106">Define an activity</span></span>

<span data-ttu-id="94756-107">Ваши извори података укључују ентитете који имају податке о трансакцијама и активностима из више извора података.</span><span class="sxs-lookup"><span data-stu-id="94756-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="94756-108">Идентификујте ове ентитете и изаберите активности које желите да видите на временској оси клијента.</span><span class="sxs-lookup"><span data-stu-id="94756-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="94756-109">Одаберите ентитет који укључује ваше циљне активности или активности.</span><span class="sxs-lookup"><span data-stu-id="94756-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="94756-110">У увидима о корисницима идите на **Подаци** > **Активности**.</span><span class="sxs-lookup"><span data-stu-id="94756-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="94756-111">Изаберите **Додај активност**.</span><span class="sxs-lookup"><span data-stu-id="94756-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="94756-112">Ентитет мора имати најмање један атрибут типа **Датум** да би био укључени у временску осу клијента и додавати ентитете који немају поља типа **Датум**.</span><span class="sxs-lookup"><span data-stu-id="94756-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="94756-113">Контрола **Додајте активност** је онемогућена ако није пронађен такав ентитет.</span><span class="sxs-lookup"><span data-stu-id="94756-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="94756-114">У окну **Додајте активност**, поставите вредности за следећа поља:</span><span class="sxs-lookup"><span data-stu-id="94756-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="94756-115">**Ентитет**: Одаберите ентитет који укључује податке о трансакцијама или активностима.</span><span class="sxs-lookup"><span data-stu-id="94756-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="94756-116">**Примарни кључ**: Изаберите поље које јединствено идентификује запис.</span><span class="sxs-lookup"><span data-stu-id="94756-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="94756-117">Оно не би смело да садржи дупликате, празне вредности или вредности које недостају.</span><span class="sxs-lookup"><span data-stu-id="94756-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="94756-118">**Временска ознака**: Изаберите поље које представља време почетка ваше активности.</span><span class="sxs-lookup"><span data-stu-id="94756-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="94756-119">**Догађај**: Изаберите поље које је догађај за активност.</span><span class="sxs-lookup"><span data-stu-id="94756-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="94756-120">**Веб-адреса**: Изаберите поље које представља URL адресу која пружа додатне информације о овој активности.</span><span class="sxs-lookup"><span data-stu-id="94756-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="94756-121">На пример, трансакциони систем који је извор ове активности.</span><span class="sxs-lookup"><span data-stu-id="94756-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="94756-122">Ова URL адреса може бити било које поље из извора података или се може направити као ново поље помоћу Power Query трансформације.</span><span class="sxs-lookup"><span data-stu-id="94756-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="94756-123">Подаци ове URL адресе ће бити сачувани у ентитету обједињених активности, који може да се користи на нижем току помоћу API-ја.</span><span class="sxs-lookup"><span data-stu-id="94756-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="94756-124">**Детаљи**: По жељи, одаберите поље које ћете додати за додатне детаље.</span><span class="sxs-lookup"><span data-stu-id="94756-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="94756-125">**Икона**: По жељи одаберите икону која представља ову активност.</span><span class="sxs-lookup"><span data-stu-id="94756-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="94756-126">**Тип активности**: Дефинишите референцу типа активности на Common Data Model који најбоље описује семантичку дефиницију активности.</span><span class="sxs-lookup"><span data-stu-id="94756-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="94756-127">У одељку **Успоставите однос**, конфигуришите детаље да бисте повезали податке о активностима са одговарајућим клијентом.</span><span class="sxs-lookup"><span data-stu-id="94756-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

    - <span data-ttu-id="94756-128">**Поље ентитета активности**: Изаберите поље у вашем ентитету активности које ће се користити за успостављање везе са другим ентитетом.</span><span class="sxs-lookup"><span data-stu-id="94756-128">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="94756-129">**ентитет Клијент**: Изаберите одговарајући ентитет корисника са којим ће ваш однос бити у релацији.</span><span class="sxs-lookup"><span data-stu-id="94756-129">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="94756-130">Можете се односити само на оне изворне ентитете клијената који се користе у поступку обједињавања података.</span><span class="sxs-lookup"><span data-stu-id="94756-130">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="94756-131">**Поље ентитета клијента**: Ово поље приказује примарни кључ изворног ентитета клијента како је изабран у процесу мапирања.</span><span class="sxs-lookup"><span data-stu-id="94756-131">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="94756-132">Ово поље примарног кључа у изворном ентитету клијента користи се за успостављање релације са ентитетом активности.</span><span class="sxs-lookup"><span data-stu-id="94756-132">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="94756-133">**Назив**: Ако релација између овог ентитета активности и изабраног изворног ентитета клијента већ постоји, назив релације ће бити у режиму само за читање.</span><span class="sxs-lookup"><span data-stu-id="94756-133">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="94756-134">Ако таква релација не постоји, створиће се нова релација са овде наведеним називом.</span><span class="sxs-lookup"><span data-stu-id="94756-134">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="94756-135">![Дефинисање релације ентитета](media/activities-entities-define.png "Дефинисање релације ентитета")</span><span class="sxs-lookup"><span data-stu-id="94756-135">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

1. <span data-ttu-id="94756-136">Изаберите **Сачувај** да примените промене.</span><span class="sxs-lookup"><span data-stu-id="94756-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="94756-137">На страници **Активности**, изаберите **Покрени**.</span><span class="sxs-lookup"><span data-stu-id="94756-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="94756-138">Постоји [шест врста статуса](system.md#status-types) за задатке/процесе.</span><span class="sxs-lookup"><span data-stu-id="94756-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="94756-139">Уз то, већина процеса [зависи од других процеса на нижем току](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="94756-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="94756-140">Можете изабрати статус процеса да бисте видели детаље о току целог посла.</span><span class="sxs-lookup"><span data-stu-id="94756-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="94756-141">Након избора опције **Види детаље** за један од задатака посла пронаћи ћете додатне информације: време обраде, датум последње обраде и све грешке и упозорења повезана са задатком.</span><span class="sxs-lookup"><span data-stu-id="94756-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="94756-142">Уређивање активности</span><span class="sxs-lookup"><span data-stu-id="94756-142">Edit an activity</span></span>

1. <span data-ttu-id="94756-143">У увидима о корисницима идите на **Подаци** > **Активности**.</span><span class="sxs-lookup"><span data-stu-id="94756-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="94756-144">Изаберите ентитет активности који желите да измените и изаберите **Уређуј**.</span><span class="sxs-lookup"><span data-stu-id="94756-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="94756-145">Или можете да задржите показивач преко реда ентитета и изаберите икону **Уређуј**.</span><span class="sxs-lookup"><span data-stu-id="94756-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="94756-146">Кликните на икону **Уређуј**.</span><span class="sxs-lookup"><span data-stu-id="94756-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="94756-147">У окну **Уређивање активности**, ажурирајте вредности и изаберите **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="94756-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="94756-148">На страници **Активности**, изаберите **Покрени**.</span><span class="sxs-lookup"><span data-stu-id="94756-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="94756-149">Брисање активности</span><span class="sxs-lookup"><span data-stu-id="94756-149">Delete an activity</span></span>

1. <span data-ttu-id="94756-150">У увидима о корисницима идите на **Подаци** > **Активности**.</span><span class="sxs-lookup"><span data-stu-id="94756-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="94756-151">Изаберите ентитет активности који желите да уклоните и изаберите **Избриши**.</span><span class="sxs-lookup"><span data-stu-id="94756-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="94756-152">Или можете да задржите показивач преко реда ентитета и изаберите икону **Избриши**.</span><span class="sxs-lookup"><span data-stu-id="94756-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="94756-153">Поред тога, можете изабрати више ентитета активности које ћете истовремено избрисати.</span><span class="sxs-lookup"><span data-stu-id="94756-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="94756-154">![Уређивање или брисање релација између ентитета](media/activities-entities-edit-delete.png "Уређивање или брисање релација између ентитета")</span><span class="sxs-lookup"><span data-stu-id="94756-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="94756-155">Изаберите икону **Избриши**.</span><span class="sxs-lookup"><span data-stu-id="94756-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="94756-156">Потврдите брисање.</span><span class="sxs-lookup"><span data-stu-id="94756-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]