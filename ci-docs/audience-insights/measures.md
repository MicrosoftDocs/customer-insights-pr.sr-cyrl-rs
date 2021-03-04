---
title: Креирање мера и управљање њима
description: Дефинишите мере за анализу и одраз учинка вашег пословања.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269946"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="c70c3-103">Дефинишите и управљајте мерама</span><span class="sxs-lookup"><span data-stu-id="c70c3-103">Define and manage measures</span></span>

<span data-ttu-id="c70c3-104">Мере вам помажу да боље разумете понашање клијената и пословне перформансе преузимањем релевантних вредности из [обједињених профила](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="c70c3-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="c70c3-105">На пример, предузеће жели да види *укупну потрошњу по клијенту* да би разумело историју куповине појединачног клијента.</span><span class="sxs-lookup"><span data-stu-id="c70c3-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="c70c3-106">Или мери *укупну продају предузећа* да би разумело приход на збирном нивоу у целом предузећу.</span><span class="sxs-lookup"><span data-stu-id="c70c3-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="c70c3-107">Мере се креирају помоћу креатора мера, платформе за упите података са различитим оператерима и једноставним опцијама мапирања.</span><span class="sxs-lookup"><span data-stu-id="c70c3-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="c70c3-108">Омогућава вам да филтрирате податке, групишете резултате, откривате [путање релација између ентитета](relationships.md) и прегледате излаз.</span><span class="sxs-lookup"><span data-stu-id="c70c3-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="c70c3-109">Користите креатор мера за планирање пословних активности тако што ћете потражити податке о клијентима и извући увиде.</span><span class="sxs-lookup"><span data-stu-id="c70c3-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="c70c3-110">На пример, креирање мере *укупна потрошња по клијенту* и *укупан повраћај по клијенту* помаже у идентификовању групе клијената са високом потрошњом, али и високим повраћајем.</span><span class="sxs-lookup"><span data-stu-id="c70c3-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="c70c3-111">Можете да [креирате сегмент](segments.md) да бисте покренули следеће најбоље радње.</span><span class="sxs-lookup"><span data-stu-id="c70c3-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="c70c3-112">Креирање мере</span><span class="sxs-lookup"><span data-stu-id="c70c3-112">Create a measure</span></span>

<span data-ttu-id="c70c3-113">Овај одељак вас води кроз креирање нове мере од почетка.</span><span class="sxs-lookup"><span data-stu-id="c70c3-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="c70c3-114">Можете да израдите меру са атрибутима података од ентитета података који имају успостављену релацију за повезивање са ентитетом Клијент.</span><span class="sxs-lookup"><span data-stu-id="c70c3-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="c70c3-115">У увидима о корисницима идите на **Мере**.</span><span class="sxs-lookup"><span data-stu-id="c70c3-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="c70c3-116">Изаберите **Ново**.</span><span class="sxs-lookup"><span data-stu-id="c70c3-116">Select **New**.</span></span>

1. <span data-ttu-id="c70c3-117">Изаберите **Уређивање назива** и наведите **Назив** за меру.</span><span class="sxs-lookup"><span data-stu-id="c70c3-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="c70c3-118">Ако ваша нова конфигурација мере има само два поља, за пример, CustomerID и један прорачун, излаз ће бити додат као нова колона системски генерисаном ентитету под називом Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="c70c3-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="c70c3-119">И моћи ћете да видите вредност мере у обједињеном профилу клијента.</span><span class="sxs-lookup"><span data-stu-id="c70c3-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="c70c3-120">Друге мере ће генерисати сопствене ентитете.</span><span class="sxs-lookup"><span data-stu-id="c70c3-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="c70c3-121">У области конфигурације, одаберите агрегатну функцију из падајућег менија **Изаберите функцију**.</span><span class="sxs-lookup"><span data-stu-id="c70c3-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="c70c3-122">Агрегатне функције укључују:</span><span class="sxs-lookup"><span data-stu-id="c70c3-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="c70c3-123">**Збир**</span><span class="sxs-lookup"><span data-stu-id="c70c3-123">**Sum**</span></span>
   - <span data-ttu-id="c70c3-124">**Просек**</span><span class="sxs-lookup"><span data-stu-id="c70c3-124">**Average**</span></span>
   - <span data-ttu-id="c70c3-125">**Преборјавање**</span><span class="sxs-lookup"><span data-stu-id="c70c3-125">**Count**</span></span>
   - <span data-ttu-id="c70c3-126">**Број јединствених**</span><span class="sxs-lookup"><span data-stu-id="c70c3-126">**Count Unique**</span></span>
   - <span data-ttu-id="c70c3-127">**Максимум**</span><span class="sxs-lookup"><span data-stu-id="c70c3-127">**Max**</span></span>
   - <span data-ttu-id="c70c3-128">**Минимум**</span><span class="sxs-lookup"><span data-stu-id="c70c3-128">**Min**</span></span>
   - <span data-ttu-id="c70c3-129">**Први**: узима прву вредност записа података</span><span class="sxs-lookup"><span data-stu-id="c70c3-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="c70c3-130">**Последњи**: узима последњу вредност која је додата у запис података</span><span class="sxs-lookup"><span data-stu-id="c70c3-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Оператори за прорачун мера.":::

1. <span data-ttu-id="c70c3-132">Изаберите **Додај атрибут** да бисте изабрали податке који су вам потребни за креирање ове мере.</span><span class="sxs-lookup"><span data-stu-id="c70c3-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="c70c3-133">Изаберите картицу **Атрибути**.</span><span class="sxs-lookup"><span data-stu-id="c70c3-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="c70c3-134">Ентитет података: Изаберите ентитет који укључује атрибут који желите да мерите.</span><span class="sxs-lookup"><span data-stu-id="c70c3-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="c70c3-135">Атрибут података: Изаберите атрибут који желите да користите у агрегатној функцији за израчунавање мере.</span><span class="sxs-lookup"><span data-stu-id="c70c3-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="c70c3-136">Истовремено можете да изаберете само један атрибут.</span><span class="sxs-lookup"><span data-stu-id="c70c3-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="c70c3-137">Такође можете изабрати атрибут података из постојеће мере избором картице **Мере**. Или можете да претражите назив ентитета или назив мере.</span><span class="sxs-lookup"><span data-stu-id="c70c3-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="c70c3-138">Изаберите **Додај** да бисте мери додали изабрани атрибут.</span><span class="sxs-lookup"><span data-stu-id="c70c3-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Изаберите атрибут који ћете користити у прорачунима.":::

1. <span data-ttu-id="c70c3-140">Да бисте изградили сложеније мере, можете додати више атрибута или користити математичке операторе на својој функцији мере.</span><span class="sxs-lookup"><span data-stu-id="c70c3-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Креирајте сложену меру помоћу математичких оператора.":::

1. <span data-ttu-id="c70c3-142">Да бисте додали филтере, изаберите **Филтер** у области конфигурације.</span><span class="sxs-lookup"><span data-stu-id="c70c3-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="c70c3-143">У одељку **Додај атрибут** окна **Филтери**, изаберите атрибут који желите да користите за креирање филтера.</span><span class="sxs-lookup"><span data-stu-id="c70c3-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="c70c3-144">Поставите операторе филтера да дефинишу филтер за сваки изабрани атрибут.</span><span class="sxs-lookup"><span data-stu-id="c70c3-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="c70c3-145">Изаберите **Примени** да бисте мери додали филтере.</span><span class="sxs-lookup"><span data-stu-id="c70c3-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="c70c3-146">Да бисте додали димензије, изаберите **Димензија** у области конфигурације.</span><span class="sxs-lookup"><span data-stu-id="c70c3-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="c70c3-147">Димензије ће се приказати као колоне у излазном ентитету мере.</span><span class="sxs-lookup"><span data-stu-id="c70c3-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="c70c3-148">Изаберите **Уређивање димензија** да бисте додавали атрибуте података по којима желите да групишете вредности мере.</span><span class="sxs-lookup"><span data-stu-id="c70c3-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="c70c3-149">На пример, град или пол.</span><span class="sxs-lookup"><span data-stu-id="c70c3-149">For example, city or gender.</span></span> <span data-ttu-id="c70c3-150">Подразумевано, димензија *CustomerID* се бира за креирање *мера на нивоу клијента*.</span><span class="sxs-lookup"><span data-stu-id="c70c3-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="c70c3-151">Можете да уклоните подразумевану димензију ако желите да креирате *мере на нивоу предузећа*.</span><span class="sxs-lookup"><span data-stu-id="c70c3-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="c70c3-152">Изаберите **Готово** да бисте мери додали димензије.</span><span class="sxs-lookup"><span data-stu-id="c70c3-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="c70c3-153">Ако постоји више путања између ентитета података који сте мапирали и ентитета клијента, морате одабрати једну од идентификованих [путања релација између ентитета](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="c70c3-153">If there are multiple paths between the data entity you mapped and the Customer entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="c70c3-154">Резултати мерења могу се разликовати у зависности од изабране путање.</span><span class="sxs-lookup"><span data-stu-id="c70c3-154">Measure results can vary depending on the selected path.</span></span>
   1. <span data-ttu-id="c70c3-155">Изаберите **Жељене опције података** и одаберите путању ентитета коју треба користити за идентификацију ваше мере.</span><span class="sxs-lookup"><span data-stu-id="c70c3-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span>
   1. <span data-ttu-id="c70c3-156">Изаберите **Готово** да примените свој избор.</span><span class="sxs-lookup"><span data-stu-id="c70c3-156">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Изаберите путању ентитета за меру.":::

1. <span data-ttu-id="c70c3-158">Да бисте додали још прорачуна за меру, изаберите **Нови прорачун**.</span><span class="sxs-lookup"><span data-stu-id="c70c3-158">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="c70c3-159">Ентитете на истој путањи ентитета можете користити само за нове прорачуне.</span><span class="sxs-lookup"><span data-stu-id="c70c3-159">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="c70c3-160">Више прорачуна ће се приказати као нове колоне у излазном ентитету мере.</span><span class="sxs-lookup"><span data-stu-id="c70c3-160">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="c70c3-161">Изаберите **...** на прорачуну да бисте **направили дупликат**, **преименовали** или **уклонили** прорачун из мере.</span><span class="sxs-lookup"><span data-stu-id="c70c3-161">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="c70c3-162">У области **Преглед** видећете шему података излазног ентитета мере, укључујући филтере и димензије.</span><span class="sxs-lookup"><span data-stu-id="c70c3-162">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="c70c3-163">Преглед динамички реагује на промене у конфигурацији.</span><span class="sxs-lookup"><span data-stu-id="c70c3-163">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="c70c3-164">Изаберите **Покрени** да бисте израчунали резултате за конфигурисану меру.</span><span class="sxs-lookup"><span data-stu-id="c70c3-164">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="c70c3-165">Изаберите **Сачувај и затвори** ако желите да задржите тренутну конфигурацију и покренете меру касније.</span><span class="sxs-lookup"><span data-stu-id="c70c3-165">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="c70c3-166">Идите на **Мере** да бисте на листи видели новокреирану меру.</span><span class="sxs-lookup"><span data-stu-id="c70c3-166">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="c70c3-167">Управљање мерама</span><span class="sxs-lookup"><span data-stu-id="c70c3-167">Manage your measures</span></span>

<span data-ttu-id="c70c3-168">Када [креирате меру](#create-a-measure), видећете листу мера на страници **Мере**.</span><span class="sxs-lookup"><span data-stu-id="c70c3-168">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="c70c3-169">Пронаћи ћете информације о типу мере, аутору, датуму настанка, статусу и стању.</span><span class="sxs-lookup"><span data-stu-id="c70c3-169">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="c70c3-170">Када изаберете меру са листе, можете да прегледате излаз и преузмете .CSV датотеку.</span><span class="sxs-lookup"><span data-stu-id="c70c3-170">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="c70c3-171">Да бисте истовремено освежили све мере, изаберите **Освежите све** без избора одређене мере.</span><span class="sxs-lookup"><span data-stu-id="c70c3-171">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c70c3-172">![Радње за управљање јединственим мерама](media/measure-actions.png "Радње за управљање јединственим мерама")</span><span class="sxs-lookup"><span data-stu-id="c70c3-172">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="c70c3-173">Изаберите меру са листе за следеће опције:</span><span class="sxs-lookup"><span data-stu-id="c70c3-173">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="c70c3-174">Изаберите назив мере да бисте видели њене детаље.</span><span class="sxs-lookup"><span data-stu-id="c70c3-174">Select the measure name to see its details.</span></span>
- <span data-ttu-id="c70c3-175">**Уредите** конфигурацију мере.</span><span class="sxs-lookup"><span data-stu-id="c70c3-175">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="c70c3-176">**Освежите** меру на основу најновијих података.</span><span class="sxs-lookup"><span data-stu-id="c70c3-176">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="c70c3-177">**Преименујте** меру.</span><span class="sxs-lookup"><span data-stu-id="c70c3-177">**Rename** the measure.</span></span>
- <span data-ttu-id="c70c3-178">**Избришите** меру.</span><span class="sxs-lookup"><span data-stu-id="c70c3-178">**Delete** the measure.</span></span>
- <span data-ttu-id="c70c3-179">**Активирајте** или **Деактивирајте**.</span><span class="sxs-lookup"><span data-stu-id="c70c3-179">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="c70c3-180">Неактивне мере се неће освежавати током [заказаног освежавања](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c70c3-180">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="c70c3-181">Постоји [шест врста статуса](system.md#status-types) за задатке/процесе.</span><span class="sxs-lookup"><span data-stu-id="c70c3-181">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="c70c3-182">Уз то, већина процеса [зависи од других процеса на нижем току](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="c70c3-182">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="c70c3-183">Можете изабрати статус процеса да бисте видели детаље о току целог посла.</span><span class="sxs-lookup"><span data-stu-id="c70c3-183">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="c70c3-184">Након избора опције **Види детаље** за један од задатака посла пронаћи ћете додатне информације: време обраде, датум последње обраде и све грешке и упозорења повезана са задатком.</span><span class="sxs-lookup"><span data-stu-id="c70c3-184">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="c70c3-185">Следећи корак</span><span class="sxs-lookup"><span data-stu-id="c70c3-185">Next step</span></span>

<span data-ttu-id="c70c3-186">Можете користити постојеће мере за креирање [сегмента клијената](segments.md).</span><span class="sxs-lookup"><span data-stu-id="c70c3-186">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]