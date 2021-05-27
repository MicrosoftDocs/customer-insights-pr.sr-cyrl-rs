---
title: Креирање сегмената и управљање њима
description: Направите сегменте клијената да бисте их груписали на основу различитих атрибута.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064955"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="17c1c-103">Креирање сегмената и управљање њима</span><span class="sxs-lookup"><span data-stu-id="17c1c-103">Create and manage segments</span></span>

<span data-ttu-id="17c1c-104">Дефинишите сложене филтере око јединственог ентитета клијента и са њим повезаних ентитета.</span><span class="sxs-lookup"><span data-stu-id="17c1c-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="17c1c-105">Сваки сегмент након обраде креира скуп корисничких записа које можете да извозити и за које можете да предузимате неке кораке.</span><span class="sxs-lookup"><span data-stu-id="17c1c-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="17c1c-106">Сегментима се управља на страници **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="17c1c-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="17c1c-107">Следећи пример илуструје коришћење могућности сегментације.</span><span class="sxs-lookup"><span data-stu-id="17c1c-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="17c1c-108">Дефинисали смо сегмент за клијенте који су наручили робу за најмање 500 USD у последњих 90 дана *и* који су били укључени у позив корисничке службе који је прослеђен.</span><span class="sxs-lookup"><span data-stu-id="17c1c-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Снимак екрана корисничког интерфејса креатора сегмената са две групе које одређују сегмент клијената.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="17c1c-110">Креирајте нови сегмент</span><span class="sxs-lookup"><span data-stu-id="17c1c-110">Create a new segment</span></span>

<span data-ttu-id="17c1c-111">Постоји више начина за креирање новог сегмента.</span><span class="sxs-lookup"><span data-stu-id="17c1c-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="17c1c-112">Овај одељак описује како се креира *празан сегмент* испочетка.</span><span class="sxs-lookup"><span data-stu-id="17c1c-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="17c1c-113">Такође можете да креирате *брзи сегмент* на основу постојећих ентитета или искористите моделе машинског учења да бисте добили *предложене сегменте*.</span><span class="sxs-lookup"><span data-stu-id="17c1c-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="17c1c-114">Још информација: [Преглед сегмената](segments.md).</span><span class="sxs-lookup"><span data-stu-id="17c1c-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="17c1c-115">Док правите сегмент, можете да сачувате радну верзију.</span><span class="sxs-lookup"><span data-stu-id="17c1c-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="17c1c-116">Биће сачувана као неактивни сегмент и не може се активирати као завршена са важећом конфигурацијом.</span><span class="sxs-lookup"><span data-stu-id="17c1c-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="17c1c-117">Идите на страницу **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="17c1c-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="17c1c-118">Изаберите **Ново** > **Празан сегмент**.</span><span class="sxs-lookup"><span data-stu-id="17c1c-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="17c1c-119">У окну **Нови сегмент**, одаберите врсту сегмента:</span><span class="sxs-lookup"><span data-stu-id="17c1c-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="17c1c-120">**Динамички сегменти** се [освежавају](segments.md#refresh-segments) по редовном распореду.</span><span class="sxs-lookup"><span data-stu-id="17c1c-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="17c1c-121">**Статички сегменти** се покрећу једном када их креирате.</span><span class="sxs-lookup"><span data-stu-id="17c1c-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="17c1c-122">Наведите **Излазни назив ентитета** за сегмент.</span><span class="sxs-lookup"><span data-stu-id="17c1c-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="17c1c-123">Опционално, унесите име за приказ и опис који помаже у препознавању сегмента.</span><span class="sxs-lookup"><span data-stu-id="17c1c-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="17c1c-124">Изаберите **Следеће** да дођете на страницу **Градитељ сегмената** на којој дефинишете групу.</span><span class="sxs-lookup"><span data-stu-id="17c1c-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="17c1c-125">Група је скуп клијената.</span><span class="sxs-lookup"><span data-stu-id="17c1c-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="17c1c-126">Одаберите ентитет који обухвата атрибуте по којима желите да сегментирате.</span><span class="sxs-lookup"><span data-stu-id="17c1c-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="17c1c-127">Одаберите атрибут по сегменту.</span><span class="sxs-lookup"><span data-stu-id="17c1c-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="17c1c-128">Овај атрибут може имати један од четири типа вредности: нумерички, ниска, датум или логички.</span><span class="sxs-lookup"><span data-stu-id="17c1c-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="17c1c-129">Одаберите оператор и вредност за изабрани атрибут.</span><span class="sxs-lookup"><span data-stu-id="17c1c-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="17c1c-130">![Прилагођени филтер групе](media/customer-group-numbers.png "Филтер групе клијената")</span><span class="sxs-lookup"><span data-stu-id="17c1c-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="17c1c-131">Број</span><span class="sxs-lookup"><span data-stu-id="17c1c-131">Number</span></span> |<span data-ttu-id="17c1c-132">Дефиниција</span><span class="sxs-lookup"><span data-stu-id="17c1c-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="17c1c-133">1</span><span class="sxs-lookup"><span data-stu-id="17c1c-133">1</span></span>     |<span data-ttu-id="17c1c-134">Entity</span><span class="sxs-lookup"><span data-stu-id="17c1c-134">Entity</span></span>          |
   |<span data-ttu-id="17c1c-135">2</span><span class="sxs-lookup"><span data-stu-id="17c1c-135">2</span></span>     |<span data-ttu-id="17c1c-136">Атрибут</span><span class="sxs-lookup"><span data-stu-id="17c1c-136">Attribute</span></span>          |
   |<span data-ttu-id="17c1c-137">3</span><span class="sxs-lookup"><span data-stu-id="17c1c-137">3</span></span>    |<span data-ttu-id="17c1c-138">Оператор</span><span class="sxs-lookup"><span data-stu-id="17c1c-138">Operator</span></span>         |
   |<span data-ttu-id="17c1c-139">4</span><span class="sxs-lookup"><span data-stu-id="17c1c-139">4</span></span>    |<span data-ttu-id="17c1c-140">Вредност</span><span class="sxs-lookup"><span data-stu-id="17c1c-140">Value</span></span>         |

   1. <span data-ttu-id="17c1c-141">Да бисте групи додали више услова, можете да користите два логичка оператора:</span><span class="sxs-lookup"><span data-stu-id="17c1c-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="17c1c-142">Оператор **И**: Оба услова морају да буду испуњена као део процеса сегментације.</span><span class="sxs-lookup"><span data-stu-id="17c1c-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="17c1c-143">Ова опција је најкориснија када дефинишете услове у различитим ентитетима.</span><span class="sxs-lookup"><span data-stu-id="17c1c-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="17c1c-144">Оператор **ИЛИ**: Било који од услова мора бити испуњен као део процеса сегментације.</span><span class="sxs-lookup"><span data-stu-id="17c1c-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="17c1c-145">Ова опција је најкориснија када дефинишете више услова у истом ентитету.</span><span class="sxs-lookup"><span data-stu-id="17c1c-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="17c1c-146">![Оператор ИЛИ где је потребно испунити било који услов](media/segmentation-either-condition.png "Оператор ИЛИ где је потребно испунити било који услов")</span><span class="sxs-lookup"><span data-stu-id="17c1c-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="17c1c-147">Тренутно је могуће угнездити оператор **ИЛИ** унутар оператора **И**, али не и обрнуто.</span><span class="sxs-lookup"><span data-stu-id="17c1c-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="17c1c-148">Свака група се подудара са скупом клијената.</span><span class="sxs-lookup"><span data-stu-id="17c1c-148">Each group matches set of customers.</span></span> <span data-ttu-id="17c1c-149">Можете комбиновати групе да бисте укључили клијенте потребне за ваш пословни предмет.</span><span class="sxs-lookup"><span data-stu-id="17c1c-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="17c1c-150">Изаберите **Додај групу**.</span><span class="sxs-lookup"><span data-stu-id="17c1c-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="17c1c-151">![Група клијената додај групу](media/customer-group-add-group.png "Група клијената додај групу")</span><span class="sxs-lookup"><span data-stu-id="17c1c-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="17c1c-152">Изаберите један од оператора скупова: **Унија**, **Пресек** или **Разлика**.</span><span class="sxs-lookup"><span data-stu-id="17c1c-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="17c1c-153">![Група клијената додај унију](media/customer-group-union.png "Група клијената додај унију")</span><span class="sxs-lookup"><span data-stu-id="17c1c-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="17c1c-154">**Унија** обједињује две групе.</span><span class="sxs-lookup"><span data-stu-id="17c1c-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="17c1c-155">**Пресек** преклапа две групе.</span><span class="sxs-lookup"><span data-stu-id="17c1c-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="17c1c-156">Само подаци који *су заједнички* за обе групе задржавају се у обједињеној групи.</span><span class="sxs-lookup"><span data-stu-id="17c1c-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="17c1c-157">**Осим** комбинује две групе.</span><span class="sxs-lookup"><span data-stu-id="17c1c-157">**Except** combines the two groups.</span></span> <span data-ttu-id="17c1c-158">Само подаци у групи А који *нису заједнички* са подацима из групе Б задржавају се.</span><span class="sxs-lookup"><span data-stu-id="17c1c-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="17c1c-159">Ако је ентитет повезан путем обједињеног ентитета клијента путем [односа](relationships.md), морате дефинисати путању односа да бисте креирали важећи сегмент.</span><span class="sxs-lookup"><span data-stu-id="17c1c-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="17c1c-160">Додајте ентитете из путање односа док не будете могли да изаберете ентитет **Клијент: CustomerInsights** из падајуће листе.</span><span class="sxs-lookup"><span data-stu-id="17c1c-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="17c1c-161">Затим одаберите **Сви записи** за сваки корак.</span><span class="sxs-lookup"><span data-stu-id="17c1c-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="17c1c-162">![Путања односа током креирања сегмента](media/segments-multiple-relationships.png "Путања односа током креирања сегмента")</span><span class="sxs-lookup"><span data-stu-id="17c1c-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="17c1c-163">Подразумевано, сегменти генеришу излазни ентитет који садржи све атрибуте корисничких профила који се подударају са дефинисаним филтерима.</span><span class="sxs-lookup"><span data-stu-id="17c1c-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="17c1c-164">Ако се сегмент заснива на другим ентитетима осим на ентитету *Клијент*, излазном ентитету можете додати више атрибута из тих ентитета.</span><span class="sxs-lookup"><span data-stu-id="17c1c-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="17c1c-165">Изаберите **Атрибути пројекта** да бисте одабрали атрибуте који ће бити додати излазном ентитету.</span><span class="sxs-lookup"><span data-stu-id="17c1c-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="17c1c-166">Пример: Сегмент се заснива на ентитету који садржи податке о активностима клијената који су повезани са ентитетом *Клијент*.</span><span class="sxs-lookup"><span data-stu-id="17c1c-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="17c1c-167">Сегмент тражи све клијенте који су позвали техничку подршку у последњих 60 дана.</span><span class="sxs-lookup"><span data-stu-id="17c1c-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="17c1c-168">Можете одабрати да додате трајање позива и број позива свим подударним записима клијената у излазном ентитету.</span><span class="sxs-lookup"><span data-stu-id="17c1c-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="17c1c-169">Ове информације могу бити корисне за слање е-поште са корисним везама до чланака помоћи на мрежи и често постављаних питања клијентима који су често звали.</span><span class="sxs-lookup"><span data-stu-id="17c1c-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="17c1c-170">Пројектовани атрибути раде само за ентитете који имају однос „један према више“ са ентитетом клијента.</span><span class="sxs-lookup"><span data-stu-id="17c1c-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="17c1c-171">На пример, један клијент може имати више претплата.</span><span class="sxs-lookup"><span data-stu-id="17c1c-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="17c1c-172">Атрибуте можете пројектовати само из ентитета који се користи у свакој групи упита за сегменте који градите.</span><span class="sxs-lookup"><span data-stu-id="17c1c-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="17c1c-173">Пројектовани атрибути узимају се у обзир када се користе оператори скупова.</span><span class="sxs-lookup"><span data-stu-id="17c1c-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="17c1c-174">Изаберите **Сачувај** да бисте сачували сегмент.</span><span class="sxs-lookup"><span data-stu-id="17c1c-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="17c1c-175">Ваш сегмент ће бити сачуван и обрађен уколико су сви захтеви потврђени.</span><span class="sxs-lookup"><span data-stu-id="17c1c-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="17c1c-176">У супротном, биће сачуван као радна верзија.</span><span class="sxs-lookup"><span data-stu-id="17c1c-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="17c1c-177">Изаберите **Назад на сегменте** да бисте се вратили на страницу **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="17c1c-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="17c1c-178">Брзи сегменти</span><span class="sxs-lookup"><span data-stu-id="17c1c-178">Quick segments</span></span>

<span data-ttu-id="17c1c-179">Брзи сегменти вам омогућавају брзу изградњу једноставних сегмената помоћу једног оператора за брже увиде.</span><span class="sxs-lookup"><span data-stu-id="17c1c-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="17c1c-180">На страници **Сегменти**, изаберите **Ново** > **Креирај из**.</span><span class="sxs-lookup"><span data-stu-id="17c1c-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="17c1c-181">Изаберите опцију **Профили** да изградите сегмент који је заснован на ентитету *обједињеног клијента*.</span><span class="sxs-lookup"><span data-stu-id="17c1c-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="17c1c-182">Изаберите опцију **Мере** за изградњу сегмента око мера које сте претходно креирали.</span><span class="sxs-lookup"><span data-stu-id="17c1c-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="17c1c-183">Изаберите опцију **Обавештавање** да изградите сегмент око једног од излазних ентитета које сте генерисали користећи могућности **Предвиђања** или **Прилагођени модели**.</span><span class="sxs-lookup"><span data-stu-id="17c1c-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="17c1c-184">У дијалогу **Нови брзи сегмент** изаберите атрибут из падајуће листе **Поље**.</span><span class="sxs-lookup"><span data-stu-id="17c1c-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="17c1c-185">Систем ће вам пружити неке додатне увиде који ће вам помоћи да створите боље сегменте својих клијената.</span><span class="sxs-lookup"><span data-stu-id="17c1c-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="17c1c-186">За категоријска поља приказаћемо 10 главних бројева клијента.</span><span class="sxs-lookup"><span data-stu-id="17c1c-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="17c1c-187">Одаберите **Вредност** и изабрали **Преглед**.</span><span class="sxs-lookup"><span data-stu-id="17c1c-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="17c1c-188">За нумерички атрибут, систем ће показати која вредност атрибута спада испод сваког процента клијента.</span><span class="sxs-lookup"><span data-stu-id="17c1c-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="17c1c-189">Одаберите **Оператор** и **Вредност**, а затим изаберите **Преглед**.</span><span class="sxs-lookup"><span data-stu-id="17c1c-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="17c1c-190">Систем ће вам пружити **Процењену величину сегмента**.</span><span class="sxs-lookup"><span data-stu-id="17c1c-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="17c1c-191">Можете одабрати да ли да генеришете сегмент који сте дефинисали или да га прво прегледате како бисте добили другу величину сегмента.</span><span class="sxs-lookup"><span data-stu-id="17c1c-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="17c1c-192">![Назив и процена за брзи сегмент](media/quick-segment-name.png "Назив и процена за брзи сегмент")</span><span class="sxs-lookup"><span data-stu-id="17c1c-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="17c1c-193">Наведите **Назив** за сегмент.</span><span class="sxs-lookup"><span data-stu-id="17c1c-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="17c1c-194">Опционално, наведите **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="17c1c-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="17c1c-195">Изаберите **Сачувај** да бисте креирали сегмент.</span><span class="sxs-lookup"><span data-stu-id="17c1c-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="17c1c-196">Након завршетка обраде сегмента, можете га прегледати као и било који други сегмент који сте креирали.</span><span class="sxs-lookup"><span data-stu-id="17c1c-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="17c1c-197">Следећи кораци</span><span class="sxs-lookup"><span data-stu-id="17c1c-197">Next steps</span></span>

<span data-ttu-id="17c1c-198">[Извезите сегмент](export-destinations.md) и истражите [картицу клијента](customer-card-add-in.md) и [конекторе](export-power-bi.md) да бисте добили увид на нивоу клијента.</span><span class="sxs-lookup"><span data-stu-id="17c1c-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
