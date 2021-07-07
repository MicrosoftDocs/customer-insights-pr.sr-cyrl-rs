---
title: Активности клијента
description: Дефинишите активности клијената и прегледајте их на временској оси клијената.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 342aeb33f652d5d60cd25e13969766954bf56370
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304944"
---
# <a name="customer-activities"></a><span data-ttu-id="322fd-103">Активности клијента</span><span class="sxs-lookup"><span data-stu-id="322fd-103">Customer activities</span></span>

<span data-ttu-id="322fd-104">Комбинујте активности клијената из [разних извора података](data-sources.md) у услузи Dynamics 365 Customer Insights како бисте креирали временску осу која хронолошки наводи активности.</span><span class="sxs-lookup"><span data-stu-id="322fd-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="322fd-105">Укључите хронологију у Dynamics 365 апликације са решењем [Програмски додатак за корисничку картицу](customer-card-add-in.md) или у Power BI контролној табли.</span><span class="sxs-lookup"><span data-stu-id="322fd-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="322fd-106">Дефинишите активност</span><span class="sxs-lookup"><span data-stu-id="322fd-106">Define an activity</span></span>

<span data-ttu-id="322fd-107">Ваши извори података могу да укључе ентитете који имају податке о трансакцијама и активностима из више извора података.</span><span class="sxs-lookup"><span data-stu-id="322fd-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="322fd-108">Идентификујте ове ентитете и изаберите активности које желите да видите на временској оси клијента.</span><span class="sxs-lookup"><span data-stu-id="322fd-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="322fd-109">Одаберите ентитет који укључује ваше циљне активности или активности.</span><span class="sxs-lookup"><span data-stu-id="322fd-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="322fd-110">Ентитет мора имати најмање један атрибут типа **Датум** да би био укључени у временску осу клијента и додавати ентитете који немају поља типа **Датум**.</span><span class="sxs-lookup"><span data-stu-id="322fd-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="322fd-111">Контрола **Додајте активност** је онемогућена ако није пронађен такав ентитет.</span><span class="sxs-lookup"><span data-stu-id="322fd-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="322fd-112">У увидима о корисницима идите на **Подаци** > **Активности**.</span><span class="sxs-lookup"><span data-stu-id="322fd-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="322fd-113">Изаберите **Додај активност** да бисте започели вођено искуство за поступак подешавања активности.</span><span class="sxs-lookup"><span data-stu-id="322fd-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="322fd-114">У кораку **Подаци о активностима**, подесите вредности за следећа поља:</span><span class="sxs-lookup"><span data-stu-id="322fd-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="322fd-115">**Назив активности**: Изаберите име за своју активност.</span><span class="sxs-lookup"><span data-stu-id="322fd-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="322fd-116">**Ентитет**: Одаберите ентитет који укључује податке о трансакцијама или активностима.</span><span class="sxs-lookup"><span data-stu-id="322fd-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="322fd-117">**Примарни кључ**: Изаберите поље које јединствено идентификује запис.</span><span class="sxs-lookup"><span data-stu-id="322fd-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="322fd-118">Оно не би смело да садржи дупликате, празне вредности или вредности које недостају.</span><span class="sxs-lookup"><span data-stu-id="322fd-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Подесите податке о активности са именом, ентитетом и примарним кључем.":::

1. <span data-ttu-id="322fd-120">Изаберите **Следеће** да пређете на следећи корак.</span><span class="sxs-lookup"><span data-stu-id="322fd-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="322fd-121">У кораку **Релација** конфигуришите детаље за повезивање података о активностима са одговарајућим клијентом.</span><span class="sxs-lookup"><span data-stu-id="322fd-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="322fd-122">Овај корак визуализује везу између ентитета.</span><span class="sxs-lookup"><span data-stu-id="322fd-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="322fd-123">**Први**: Страно поље у ентитету активности које ће се користити за успостављање релације са другим ентитетом.</span><span class="sxs-lookup"><span data-stu-id="322fd-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="322fd-124">**Други**: Одговарајући изворни ентитет клијента са којим ће ваш ентитет активности бити у релацији.</span><span class="sxs-lookup"><span data-stu-id="322fd-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="322fd-125">Можете се повезати само са изворним ентитетима клијената који се користе у процесу обједињавања података.</span><span class="sxs-lookup"><span data-stu-id="322fd-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="322fd-126">**Трећи**: Ако релација између овог ентитета активности и изабраног изворног ентитета клијента већ постоји, назив релације ће бити у режиму само за читање.</span><span class="sxs-lookup"><span data-stu-id="322fd-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="322fd-127">Ако таква релација не постоји, створиће се нова релација са именом које наведете у овом пољу.</span><span class="sxs-lookup"><span data-stu-id="322fd-127">If no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Дефинисање релације између ентитета.":::

1. <span data-ttu-id="322fd-129">Изаберите **Следеће** да пређете на следећи корак.</span><span class="sxs-lookup"><span data-stu-id="322fd-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="322fd-130">У кораку **Обједињавање активности**, одаберите догађај активности и време почетка активности.</span><span class="sxs-lookup"><span data-stu-id="322fd-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="322fd-131">**Обавезна поља**</span><span class="sxs-lookup"><span data-stu-id="322fd-131">**Required fields**</span></span>
      - <span data-ttu-id="322fd-132">**Активност догађаја**: Поље које је догађај за ову активност.</span><span class="sxs-lookup"><span data-stu-id="322fd-132">**Event activity**: Field that is the event for this activity.</span></span>
      - <span data-ttu-id="322fd-133">**Временска ознака**: Поље које представља време почетка ваше активности.</span><span class="sxs-lookup"><span data-stu-id="322fd-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="322fd-134">**Опционална поља**</span><span class="sxs-lookup"><span data-stu-id="322fd-134">**Optional fields**</span></span>
      - <span data-ttu-id="322fd-135">**Додатни детаљ**: Поље са релевантним информацијама за ову активност.</span><span class="sxs-lookup"><span data-stu-id="322fd-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      - <span data-ttu-id="322fd-136">**Икона**: Икона која најбоље представља ову врсту активности.</span><span class="sxs-lookup"><span data-stu-id="322fd-136">**Icon**: Icon that best represents this activity type.</span></span>
      - <span data-ttu-id="322fd-137">**Веб-адреса**: Поље које садржи URL адресу са информацијама о овој активности.</span><span class="sxs-lookup"><span data-stu-id="322fd-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="322fd-138">На пример, трансакциони систем који је извор ове активности.</span><span class="sxs-lookup"><span data-stu-id="322fd-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="322fd-139">Ова URL адреса може бити било које поље из извора података или се може направити као ново поље помоћу Power Query трансформације.</span><span class="sxs-lookup"><span data-stu-id="322fd-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="322fd-140">Подаци о URL адреси биће сачувани у ентитету *Обједињена активност*, који се може последично користити помоћу [API-ја](apis.md).</span><span class="sxs-lookup"><span data-stu-id="322fd-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Наведите податке о активностима клијената у ентитету Уједињене активности.":::

1. <span data-ttu-id="322fd-142">Изаберите **Следеће** да бисте прешли на следећи корак.</span><span class="sxs-lookup"><span data-stu-id="322fd-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="322fd-143">Можете изабрати **Завршите и прегледај** да бисте сада сачували активност са типом активности подешеним на **Остало**.</span><span class="sxs-lookup"><span data-stu-id="322fd-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="322fd-144">У кораку **Тип активности**, одаберите тип активности и опционално одаберите ако желите да семантички мапирате неке од врста активности за употребу у другим областима услуге Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="322fd-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="322fd-145">Тренутно, типови активности *Претплата* и *SalesOrderLine* се могу семантички мапирати након договора о мапирању поља.</span><span class="sxs-lookup"><span data-stu-id="322fd-145">Currently, *Subscription* and *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="322fd-146">Ако врста активности није релевантна за нову активност, можете одабрати *Остало* или *Креирај нову* за прилагођени тип активности.</span><span class="sxs-lookup"><span data-stu-id="322fd-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="322fd-147">Изаберите **Следеће** да бисте прешли на следећи корак.</span><span class="sxs-lookup"><span data-stu-id="322fd-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="322fd-148">У кораку **Преглед**, потврдите своје изборе.</span><span class="sxs-lookup"><span data-stu-id="322fd-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="322fd-149">Вратите се на било који од претходних корака и ажурирајте информације ако је потребно.</span><span class="sxs-lookup"><span data-stu-id="322fd-149">Go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Прегледајте наведена поља за активност.":::
   
1. <span data-ttu-id="322fd-151">Изаберите **Сачувај активност** да бисте применили промене и изабрали **Готово** да бисте се вратили у **Подаци** > **Активности**.</span><span class="sxs-lookup"><span data-stu-id="322fd-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="322fd-152">Овде видите које су активности постављене да се приказују на временској оси.</span><span class="sxs-lookup"><span data-stu-id="322fd-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="322fd-153">На страници **Активности**, изаберите **Покрени** да бисте обрадили активност.</span><span class="sxs-lookup"><span data-stu-id="322fd-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="322fd-154">Постоји [шест врста статуса](system.md#status-types) за задатке/процесе.</span><span class="sxs-lookup"><span data-stu-id="322fd-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="322fd-155">Уз то, већина процеса [зависи од других процеса на нижем току](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="322fd-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="322fd-156">Можете изабрати статус процеса да бисте видели детаље о току целог посла.</span><span class="sxs-lookup"><span data-stu-id="322fd-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="322fd-157">Након избора опције **Види детаље** за један од задатака посла пронаћи ћете додатне информације: време обраде, датум последње обраде и све грешке и упозорења повезана са задатком.</span><span class="sxs-lookup"><span data-stu-id="322fd-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="322fd-158">Управљање постојећим активностима</span><span class="sxs-lookup"><span data-stu-id="322fd-158">Manage existing activities</span></span>

<span data-ttu-id="322fd-159">На страници **Подаци** > **Активности** можете да видите све сачуване активности и управљате њима.</span><span class="sxs-lookup"><span data-stu-id="322fd-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="322fd-160">Свака активност се представља у реду који такође укључује детаље о извору, ентитету и типу активности.</span><span class="sxs-lookup"><span data-stu-id="322fd-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="322fd-161">Следеће радње су доступне када изаберете активност.</span><span class="sxs-lookup"><span data-stu-id="322fd-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="322fd-162">**Уреди**: Отвара подешавање активности у кораку прегледа.</span><span class="sxs-lookup"><span data-stu-id="322fd-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="322fd-163">У овом кораку можете променити било коју тренутну конфигурацију.</span><span class="sxs-lookup"><span data-stu-id="322fd-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="322fd-164">Када промените конфигурацију, изаберите **Сачувај активност**, а затим изаберите **Покрени** да бисте обрадили промене.</span><span class="sxs-lookup"><span data-stu-id="322fd-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="322fd-165">**Преименуј**: Отвара дијалог у који можете унети друго име за изабрану активност.</span><span class="sxs-lookup"><span data-stu-id="322fd-165">**Rename**: Opens a dialog where you can enter a different name for the selected activity.</span></span> <span data-ttu-id="322fd-166">Изаберите **Сачувај** да примените промене.</span><span class="sxs-lookup"><span data-stu-id="322fd-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="322fd-167">**Избриши**: Отвара дијалог за потврду брисања изабране активности.</span><span class="sxs-lookup"><span data-stu-id="322fd-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="322fd-168">Такође можете избрисати више активности одједном тако што ћете изабрати активности, а затим изабрати икону за брисање.</span><span class="sxs-lookup"><span data-stu-id="322fd-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="322fd-169">Изаберите **Избриши** да бисте потврдили брисање.</span><span class="sxs-lookup"><span data-stu-id="322fd-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
