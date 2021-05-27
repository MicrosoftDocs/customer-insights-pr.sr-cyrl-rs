---
title: Креирање мера и управљање њима
description: Дефинишите мере за анализу и одраз учинка вашег пословања.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 402e5ef3515bce0e6f56788781b7bd909738aaa6
ms.sourcegitcommit: b833e333745d321edeaf96d3ed14458cbce02ff1
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049268"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="372e0-103">Дефинишите и управљајте мерама</span><span class="sxs-lookup"><span data-stu-id="372e0-103">Define and manage measures</span></span>

<span data-ttu-id="372e0-104">Мере вам помажу да боље разумете понашање клијената и пословне резултате.</span><span class="sxs-lookup"><span data-stu-id="372e0-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="372e0-105">Они гледају на релевантне вредности из [обједињених профила](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="372e0-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="372e0-106">На пример, предузеће жели да види *укупну потрошњу по клијенту* да бисте разумели историју куповине појединачног клијента или меру *укупне продаје предузећа* да бисте разумели укупни приход у целом послу.</span><span class="sxs-lookup"><span data-stu-id="372e0-106">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="372e0-107">Мере се креирају помоћу креатора мера, платформе за упите података са различитим оператерима и једноставним опцијама мапирања.</span><span class="sxs-lookup"><span data-stu-id="372e0-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="372e0-108">Омогућава вам да филтрирате податке, групишете резултате, откривате [путање релација између ентитета](relationships.md) и прегледате излаз.</span><span class="sxs-lookup"><span data-stu-id="372e0-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="372e0-109">Користите креатор мера за планирање пословних активности тако што ћете потражити податке о клијентима и извући увиде.</span><span class="sxs-lookup"><span data-stu-id="372e0-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="372e0-110">На пример, креирање мере *укупна потрошња по клијенту* и *укупан повраћај по клијенту* помаже у идентификовању групе клијената са високом потрошњом, али и високим повраћајем.</span><span class="sxs-lookup"><span data-stu-id="372e0-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="372e0-111">Можете да [креирате сегмент](segments.md) да бисте покренули следеће најбоље радње.</span><span class="sxs-lookup"><span data-stu-id="372e0-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="372e0-112">Направите сопствену меру испочетка</span><span class="sxs-lookup"><span data-stu-id="372e0-112">Build your own measure from scratch</span></span>

<span data-ttu-id="372e0-113">Овај одељак вас води кроз креирање нове мере од почетка.</span><span class="sxs-lookup"><span data-stu-id="372e0-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="372e0-114">Можете да израдите меру са атрибутима података од ентитета података који имају успостављену релацију за повезивање са ентитетом Клијент.</span><span class="sxs-lookup"><span data-stu-id="372e0-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="372e0-115">У увидима о корисницима идите на **Мере**.</span><span class="sxs-lookup"><span data-stu-id="372e0-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="372e0-116">Изаберите **Нова** и бирајте **Направите сопствену**.</span><span class="sxs-lookup"><span data-stu-id="372e0-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="372e0-117">Изаберите **Уређивање назива** и наведите **Назив** за меру.</span><span class="sxs-lookup"><span data-stu-id="372e0-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="372e0-118">Ако ваша нова конфигурација мере има само два поља, нпр. CustomerID и један прорачун, излаз ће бити додат као нова колона системски генерисаном ентитету под називом Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="372e0-118">If your new measure configuration has only two fields, for example, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="372e0-119">И моћи ћете да видите вредност мере у обједињеном корисничком профилу.</span><span class="sxs-lookup"><span data-stu-id="372e0-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="372e0-120">Друге мере ће генерисати сопствене ентитете.</span><span class="sxs-lookup"><span data-stu-id="372e0-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="372e0-121">У области конфигурације, одаберите агрегатну функцију из падајућег менија **Изаберите функцију**.</span><span class="sxs-lookup"><span data-stu-id="372e0-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="372e0-122">Агрегатне функције укључују:</span><span class="sxs-lookup"><span data-stu-id="372e0-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="372e0-123">**Збир**</span><span class="sxs-lookup"><span data-stu-id="372e0-123">**Sum**</span></span>
   - <span data-ttu-id="372e0-124">**Просек**</span><span class="sxs-lookup"><span data-stu-id="372e0-124">**Average**</span></span>
   - <span data-ttu-id="372e0-125">**Преборјавање**</span><span class="sxs-lookup"><span data-stu-id="372e0-125">**Count**</span></span>
   - <span data-ttu-id="372e0-126">**Број јединствених**</span><span class="sxs-lookup"><span data-stu-id="372e0-126">**Count Unique**</span></span>
   - <span data-ttu-id="372e0-127">**Максимум**</span><span class="sxs-lookup"><span data-stu-id="372e0-127">**Max**</span></span>
   - <span data-ttu-id="372e0-128">**Минимум**</span><span class="sxs-lookup"><span data-stu-id="372e0-128">**Min**</span></span>
   - <span data-ttu-id="372e0-129">**Први**: узима прву вредност записа података</span><span class="sxs-lookup"><span data-stu-id="372e0-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="372e0-130">**Последњи**: узима последњу вредност која је додата у запис података</span><span class="sxs-lookup"><span data-stu-id="372e0-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Оператори за прорачун мера.":::

1. <span data-ttu-id="372e0-132">Изаберите **Додај атрибут** да бисте изабрали податке који су вам потребни за креирање ове мере.</span><span class="sxs-lookup"><span data-stu-id="372e0-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="372e0-133">Изаберите картицу **Атрибути**.</span><span class="sxs-lookup"><span data-stu-id="372e0-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="372e0-134">Ентитет података: Изаберите ентитет који укључује атрибут који желите да мерите.</span><span class="sxs-lookup"><span data-stu-id="372e0-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="372e0-135">Атрибут података: Изаберите атрибут који желите да користите у агрегатној функцији за израчунавање мере.</span><span class="sxs-lookup"><span data-stu-id="372e0-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="372e0-136">Истовремено можете да изаберете само један атрибут.</span><span class="sxs-lookup"><span data-stu-id="372e0-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="372e0-137">Такође можете изабрати атрибут података из постојеће мере избором картице **Мере**. Или можете да претражите назив ентитета или назив мере.</span><span class="sxs-lookup"><span data-stu-id="372e0-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="372e0-138">Изаберите **Додај** да бисте мери додали изабрани атрибут.</span><span class="sxs-lookup"><span data-stu-id="372e0-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Изаберите атрибут који ћете користити у прорачунима.":::

1. <span data-ttu-id="372e0-140">Да бисте изградили сложеније мере, можете додати више атрибута или користити математичке операторе на својој функцији мере.</span><span class="sxs-lookup"><span data-stu-id="372e0-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Креирајте сложену меру помоћу математичких оператора.":::

1. <span data-ttu-id="372e0-142">Да бисте додали филтере, изаберите **Филтер** у области конфигурације.</span><span class="sxs-lookup"><span data-stu-id="372e0-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="372e0-143">У одељку **Додај атрибут** окна **Филтери**, изаберите атрибут који желите да користите за креирање филтера.</span><span class="sxs-lookup"><span data-stu-id="372e0-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="372e0-144">Поставите операторе филтера да дефинишу филтер за сваки изабрани атрибут.</span><span class="sxs-lookup"><span data-stu-id="372e0-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="372e0-145">Изаберите **Примени** да бисте мери додали филтере.</span><span class="sxs-lookup"><span data-stu-id="372e0-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="372e0-146">Да бисте додали димензије, изаберите **Димензија** у области конфигурације.</span><span class="sxs-lookup"><span data-stu-id="372e0-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="372e0-147">Димензије ће се приказати као колоне у излазном ентитету мере.</span><span class="sxs-lookup"><span data-stu-id="372e0-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="372e0-148">Изаберите **Уређивање димензија** да бисте додавали атрибуте података по којима желите да групишете вредности мере.</span><span class="sxs-lookup"><span data-stu-id="372e0-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="372e0-149">На пример, град или пол.</span><span class="sxs-lookup"><span data-stu-id="372e0-149">For example, city or gender.</span></span> <span data-ttu-id="372e0-150">Подразумевано, димензија *CustomerID* се бира за креирање *мера на нивоу клијента*.</span><span class="sxs-lookup"><span data-stu-id="372e0-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="372e0-151">Можете да уклоните подразумевану димензију ако желите да креирате *мере на нивоу предузећа*.</span><span class="sxs-lookup"><span data-stu-id="372e0-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="372e0-152">Изаберите **Готово** да бисте мери додали димензије.</span><span class="sxs-lookup"><span data-stu-id="372e0-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="372e0-153">Ако у вашим подацима постоје вредности које треба да замените целим бројем, на пример, замените *null* са *0*, изаберите **Правила**.</span><span class="sxs-lookup"><span data-stu-id="372e0-153">If there are values in your data that you need to replace with an integer, for example, replace *null* with *0*, select **Rules**.</span></span> <span data-ttu-id="372e0-154">Конфигуришите правило и обавезно одаберите само целе бројеве као замену.</span><span class="sxs-lookup"><span data-stu-id="372e0-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="372e0-155">Ако постоји више путања између ентитета података који сте мапирали и ентитета *Клијент*, морате одабрати једну од идентификованих [путања релација између ентитета](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="372e0-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="372e0-156">Резултати мерења могу се разликовати у зависности од изабране путање.</span><span class="sxs-lookup"><span data-stu-id="372e0-156">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="372e0-157">Изаберите **Жељене опције података** и одаберите путању ентитета коју треба користити за идентификацију ваше мере.</span><span class="sxs-lookup"><span data-stu-id="372e0-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="372e0-158">Ако постоји само један пут до ентитета *Клијент*, ова контрола се неће приказати.</span><span class="sxs-lookup"><span data-stu-id="372e0-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="372e0-159">Изаберите **Готово** да примените свој избор.</span><span class="sxs-lookup"><span data-stu-id="372e0-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Изаберите путању ентитета за меру.":::

1. <span data-ttu-id="372e0-161">Да бисте додали још прорачуна за меру, изаберите **Нови прорачун**.</span><span class="sxs-lookup"><span data-stu-id="372e0-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="372e0-162">Ентитете на истој путањи ентитета можете користити само за нове прорачуне.</span><span class="sxs-lookup"><span data-stu-id="372e0-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="372e0-163">Више прорачуна ће се приказати као нове колоне у излазном ентитету мере.</span><span class="sxs-lookup"><span data-stu-id="372e0-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="372e0-164">Изаберите **...** на прорачуну да бисте **направили дупликат**, **преименовали** или **уклонили** прорачун из мере.</span><span class="sxs-lookup"><span data-stu-id="372e0-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="372e0-165">У области **Преглед** видећете шему података излазног ентитета мере, укључујући филтере и димензије.</span><span class="sxs-lookup"><span data-stu-id="372e0-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="372e0-166">Преглед динамички реагује на промене у конфигурацији.</span><span class="sxs-lookup"><span data-stu-id="372e0-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="372e0-167">Изаберите **Покрени** да бисте израчунали резултате за конфигурисану меру.</span><span class="sxs-lookup"><span data-stu-id="372e0-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="372e0-168">Изаберите **Сачувај и затвори** ако желите да задржите тренутну конфигурацију и покренете меру касније.</span><span class="sxs-lookup"><span data-stu-id="372e0-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="372e0-169">Идите на **Мере** да бисте на листи видели новокреирану меру.</span><span class="sxs-lookup"><span data-stu-id="372e0-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="372e0-170">Коришћење предлошка за изградњу мере</span><span class="sxs-lookup"><span data-stu-id="372e0-170">Use a template to build a measure</span></span>

<span data-ttu-id="372e0-171">Да бисте их креирали, можете користити унапред дефинисане предлошке најчешће коришћених мера.</span><span class="sxs-lookup"><span data-stu-id="372e0-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="372e0-172">Детаљни описи предложака и вођено искуство помажу вам у ефикасном креирању мера.</span><span class="sxs-lookup"><span data-stu-id="372e0-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="372e0-173">Предлошци се надовезују на мапиране податке из ентитета *Обједињена активност*.</span><span class="sxs-lookup"><span data-stu-id="372e0-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="372e0-174">Уверите се да сте конфигурисали [активности клијената](activities.md) пре него што креирате меру из предлошка.</span><span class="sxs-lookup"><span data-stu-id="372e0-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="372e0-175">Доступни предлошци мера:</span><span class="sxs-lookup"><span data-stu-id="372e0-175">Available measure templates:</span></span> 
- <span data-ttu-id="372e0-176">Просечна вредност трансакције (ATV)</span><span class="sxs-lookup"><span data-stu-id="372e0-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="372e0-177">Укупна вредност трансакције</span><span class="sxs-lookup"><span data-stu-id="372e0-177">Total transaction value</span></span>
- <span data-ttu-id="372e0-178">Просечан дневни приход</span><span class="sxs-lookup"><span data-stu-id="372e0-178">Average daily revenue</span></span>
- <span data-ttu-id="372e0-179">Просечан годишњи приход</span><span class="sxs-lookup"><span data-stu-id="372e0-179">Average yearly revenue</span></span>
- <span data-ttu-id="372e0-180">Број трансакција</span><span class="sxs-lookup"><span data-stu-id="372e0-180">Transaction count</span></span>
- <span data-ttu-id="372e0-181">Освојени поени лојалности</span><span class="sxs-lookup"><span data-stu-id="372e0-181">Loyalty points earned</span></span>
- <span data-ttu-id="372e0-182">Искоришћени поени лојалности</span><span class="sxs-lookup"><span data-stu-id="372e0-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="372e0-183">Биланс поена лојалности</span><span class="sxs-lookup"><span data-stu-id="372e0-183">Loyalty points balance</span></span>
- <span data-ttu-id="372e0-184">Временски опсег активности клијента</span><span class="sxs-lookup"><span data-stu-id="372e0-184">Active customer lifespan</span></span>
- <span data-ttu-id="372e0-185">Трајање чланства у програму лојалности</span><span class="sxs-lookup"><span data-stu-id="372e0-185">Loyalty membership duration</span></span>
- <span data-ttu-id="372e0-186">Време од последње куповине</span><span class="sxs-lookup"><span data-stu-id="372e0-186">Time since last purchase</span></span>

<span data-ttu-id="372e0-187">Следећи поступак описује кораке за изградњу нове мере помоћу предлошка.</span><span class="sxs-lookup"><span data-stu-id="372e0-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="372e0-188">У увидима о корисницима идите на **Мере**.</span><span class="sxs-lookup"><span data-stu-id="372e0-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="372e0-189">Изаберите **Нова** и бирајте **Одабери предложак**.</span><span class="sxs-lookup"><span data-stu-id="372e0-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Снимак екрана падајућег менија приликом креирања нове мере са истицањем на предлошку.":::

1. <span data-ttu-id="372e0-191">Пронађите предложак који одговара вашим потребама и изаберите **Одабери предложак**.</span><span class="sxs-lookup"><span data-stu-id="372e0-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="372e0-192">Прегледајте потребне податке и изаберите **Започните** ако су сви подаци на свом месту.</span><span class="sxs-lookup"><span data-stu-id="372e0-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="372e0-193">У окну **Уређивање назива** поставите назив мере и излазни ентитет.</span><span class="sxs-lookup"><span data-stu-id="372e0-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="372e0-194">Изаберите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="372e0-194">Select **Done**.</span></span>

1. <span data-ttu-id="372e0-195">У одељку **Подешавање временског периода** дефинишите временски оквир података који ће се користити.</span><span class="sxs-lookup"><span data-stu-id="372e0-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="372e0-196">Одаберите да ли желите да нова мера покрије читав скуп података избором **Све време**.</span><span class="sxs-lookup"><span data-stu-id="372e0-196">Choose if you want the new measure to cover the entire data set by selecting **All time**.</span></span> <span data-ttu-id="372e0-197">Или ако желите да се мера усредсреди на **Одређени временски период**.</span><span class="sxs-lookup"><span data-stu-id="372e0-197">Or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Снимак екрана који приказује одељак временског периода приликом конфигурисања мере из предлошка.":::

1. <span data-ttu-id="372e0-199">У следећем одељку, изаберите **Додај податке** да бисте изабрали активности и мапирали одговарајуће податке из свог ентитета *Обједињена активност*.</span><span class="sxs-lookup"><span data-stu-id="372e0-199">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="372e0-200">Корак 1 од 2: Испод **Типа активности** одаберите тип ентитета који желите да користите.</span><span class="sxs-lookup"><span data-stu-id="372e0-200">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="372e0-201">За **Активности**, изаберите ентитете које желите да мапирате.</span><span class="sxs-lookup"><span data-stu-id="372e0-201">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="372e0-202">Корак 2 од 2: Изаберите атрибут из ентитета *Обједињена активност* за компоненту која је обавезна за формулу.</span><span class="sxs-lookup"><span data-stu-id="372e0-202">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="372e0-203">На пример, за „Просечна вредност трансакције“, то је атрибут који представља вредност трансакције.</span><span class="sxs-lookup"><span data-stu-id="372e0-203">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="372e0-204">За **Временску ознаку активности**, одаберите атрибут из ентитета обједињене активности који представља датум и време активности.</span><span class="sxs-lookup"><span data-stu-id="372e0-204">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="372e0-205">Када мапирање података буде успешно, можете видети да статус има вредност **Комплетно** и назив мапираних активности и атрибута.</span><span class="sxs-lookup"><span data-stu-id="372e0-205">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Снимак екрана довршене конфигурације предлошка мере.":::

1. <span data-ttu-id="372e0-207">Сада можете одабрати **Покрени** да бисте израчунали резултате мере.</span><span class="sxs-lookup"><span data-stu-id="372e0-207">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="372e0-208">Да бисте је касније прецизирали, изаберите **Сачувај радну верзију**.</span><span class="sxs-lookup"><span data-stu-id="372e0-208">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="372e0-209">Управљање мерама</span><span class="sxs-lookup"><span data-stu-id="372e0-209">Manage your measures</span></span>

<span data-ttu-id="372e0-210">Списак мера можете пронаћи на страници **Мере**.</span><span class="sxs-lookup"><span data-stu-id="372e0-210">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="372e0-211">Пронаћи ћете информације о типу мере, аутору, датуму настанка, статусу и стању.</span><span class="sxs-lookup"><span data-stu-id="372e0-211">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="372e0-212">Када изаберете меру са листе, можете да прегледате излаз и преузмете .CSV датотеку.</span><span class="sxs-lookup"><span data-stu-id="372e0-212">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="372e0-213">Да бисте истовремено освежили све мере, изаберите **Освежите све** без избора одређене мере.</span><span class="sxs-lookup"><span data-stu-id="372e0-213">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="372e0-214">![Радње за управљање јединственим мерама](media/measure-actions.png "Радње за управљање јединственим мерама")</span><span class="sxs-lookup"><span data-stu-id="372e0-214">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="372e0-215">Изаберите меру са листе за следеће опције:</span><span class="sxs-lookup"><span data-stu-id="372e0-215">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="372e0-216">Изаберите назив мере да бисте видели њене детаље.</span><span class="sxs-lookup"><span data-stu-id="372e0-216">Select the measure name to see its details.</span></span>
- <span data-ttu-id="372e0-217">**Уредите** конфигурацију мере.</span><span class="sxs-lookup"><span data-stu-id="372e0-217">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="372e0-218">**Освежите** меру на основу најновијих података.</span><span class="sxs-lookup"><span data-stu-id="372e0-218">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="372e0-219">**Преименујте** меру.</span><span class="sxs-lookup"><span data-stu-id="372e0-219">**Rename** the measure.</span></span>
- <span data-ttu-id="372e0-220">**Избришите** меру.</span><span class="sxs-lookup"><span data-stu-id="372e0-220">**Delete** the measure.</span></span>
- <span data-ttu-id="372e0-221">**Активирајте** или **Деактивирајте**.</span><span class="sxs-lookup"><span data-stu-id="372e0-221">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="372e0-222">Неактивне мере се неће освежавати током [заказаног освежавања](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="372e0-222">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="372e0-223">Постоји [шест врста статуса](system.md#status-types) за задатке/процесе.</span><span class="sxs-lookup"><span data-stu-id="372e0-223">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="372e0-224">Уз то, већина процеса [зависи од других процеса на нижем току](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="372e0-224">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="372e0-225">Можете изабрати статус процеса да бисте видели детаље о току целог посла.</span><span class="sxs-lookup"><span data-stu-id="372e0-225">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="372e0-226">Након избора опције **Види детаље** за један од задатака посла пронаћи ћете додатне информације: време обраде, датум последње обраде и све грешке и упозорења повезана са задатком.</span><span class="sxs-lookup"><span data-stu-id="372e0-226">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="372e0-227">Следећи корак</span><span class="sxs-lookup"><span data-stu-id="372e0-227">Next step</span></span>

<span data-ttu-id="372e0-228">Можете користити постојеће мере за креирање [сегмента клијената](segments.md).</span><span class="sxs-lookup"><span data-stu-id="372e0-228">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
