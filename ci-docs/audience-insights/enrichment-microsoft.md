---
title: Обогаћивање корисничких профила подацима компаније Microsoft
description: Користите заштићене податке компаније Microsoft да бисте обогатили податке о клијентима афинитетима према бренду и интересовањима.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 1b11c325649b91ebb47cde924227eacedae64b7a
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305174"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="93377-103">Обогатите корисничке профиле афинитетима бренда и интересовања (преглед)</span><span class="sxs-lookup"><span data-stu-id="93377-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="93377-104">Користите заштићене податке компаније Microsoft да бисте обогатили податке о клијентима афинитетима према бренду и интересовањима.</span><span class="sxs-lookup"><span data-stu-id="93377-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="93377-105">Ови афинитети су засновани на подацима од особа са сличним демографским категоријама као ваши клијенти.</span><span class="sxs-lookup"><span data-stu-id="93377-105">These affinities are based on data from people with demographics similar to your customers.</span></span> <span data-ttu-id="93377-106">Ове информације вам помажу да боље разумете и сегментирате своје клијенте на основу њихових афинитета према одређеним брендовима и интересовањима.</span><span class="sxs-lookup"><span data-stu-id="93377-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="93377-107">У увидима о корисницима, идите на **Подаци** > **Обогаћивање** да бисте [конфигурисали и прегледали обогаћивања](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="93377-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="93377-108">Да бисте конфигурисали обогаћивање афинитета за брендове, идите на картицу **Откријте** и изаберите **Обогати моје податке** на плочици **Брендови**.</span><span class="sxs-lookup"><span data-stu-id="93377-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="93377-109">Да бисте конфигурисали обогаћивање афинитета интересовања, идите на картицу **Откријте** и изаберите **Обогати моје податке** на плочици **Интересовања**.</span><span class="sxs-lookup"><span data-stu-id="93377-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="93377-110">![Плочице Брендови и Интересовања](media/BrandsInterest-tile-Hub.png "Плочице Брендови и Интересовања")</span><span class="sxs-lookup"><span data-stu-id="93377-110">![Brands and Interests tiles](media/BrandsInterest-tile-Hub.png "Brands and Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="93377-111">Како утврђујемо афинитете</span><span class="sxs-lookup"><span data-stu-id="93377-111">How we determine affinities</span></span>

<span data-ttu-id="93377-112">Користимо податке за претрагу на мрежи компаније Microsoft за проналажење афинитета према брендовима и интересовањима у различитим демографским сегментима (дефинисани узрастом, полом или локацијом).</span><span class="sxs-lookup"><span data-stu-id="93377-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="93377-113">Обим претраживања брендова или интересовања на мрежи одређује колики афинитет демографски сегмент има према том бренду или интересовању, у поређењу с другим сегментима.</span><span class="sxs-lookup"><span data-stu-id="93377-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="93377-114">Ниво афинитета и резултат</span><span class="sxs-lookup"><span data-stu-id="93377-114">Affinity level and score</span></span>

<span data-ttu-id="93377-115">На сваком обогаћеном корисничком профилу пружамо две повезане вредности: ниво афинитета и оцену афинитета.</span><span class="sxs-lookup"><span data-stu-id="93377-115">On every enriched customer profile, we provide two related values: affinity level and affinity score.</span></span> <span data-ttu-id="93377-116">Ове вредности вам помажу да утврдите колико је јак афинитет према демографском сегменту тог профила, према бренду или интересовању у поређењу са другим демографским сегментима.</span><span class="sxs-lookup"><span data-stu-id="93377-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="93377-117">*Ниво афинитета* састоји се од четири нивоа, а *оцена афинитета* се израчунава на скали од 100 поена која се пресликава на ниво афинитета.</span><span class="sxs-lookup"><span data-stu-id="93377-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="93377-118">Ниво афинитета</span><span class="sxs-lookup"><span data-stu-id="93377-118">Affinity level</span></span> |<span data-ttu-id="93377-119">Оцена афинитета</span><span class="sxs-lookup"><span data-stu-id="93377-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="93377-120">Веома високо</span><span class="sxs-lookup"><span data-stu-id="93377-120">Very high</span></span>     | <span data-ttu-id="93377-121">85-100</span><span class="sxs-lookup"><span data-stu-id="93377-121">85-100</span></span>       |
|<span data-ttu-id="93377-122">Висок</span><span class="sxs-lookup"><span data-stu-id="93377-122">High</span></span>     | <span data-ttu-id="93377-123">70-84</span><span class="sxs-lookup"><span data-stu-id="93377-123">70-84</span></span>        |
|<span data-ttu-id="93377-124">Средње</span><span class="sxs-lookup"><span data-stu-id="93377-124">Medium</span></span>     | <span data-ttu-id="93377-125">35-69</span><span class="sxs-lookup"><span data-stu-id="93377-125">35-69</span></span>        |
|<span data-ttu-id="93377-126">Низак</span><span class="sxs-lookup"><span data-stu-id="93377-126">Low</span></span>     | <span data-ttu-id="93377-127">1-34</span><span class="sxs-lookup"><span data-stu-id="93377-127">1-34</span></span>        |

<span data-ttu-id="93377-128">У зависности од грануларности којом желите да мерите афинитет, можете да користите ниво афинитета или резултат.</span><span class="sxs-lookup"><span data-stu-id="93377-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="93377-129">Оцена афинитета вам даје прецизнију контролу.</span><span class="sxs-lookup"><span data-stu-id="93377-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="93377-130">Подржане земље/региони</span><span class="sxs-lookup"><span data-stu-id="93377-130">Supported countries/regions</span></span>

<span data-ttu-id="93377-131">Тренутно подржавамо следеће опције земље/региона: Аустралија, Канада (енглески), Француска, Немачка, Уједињено Краљевство или Сједињене Државе (енглески).</span><span class="sxs-lookup"><span data-stu-id="93377-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="93377-132">Да бисте изабрали земљу или регион, отворите **Обогаћивање брендова** или **Обогаћивање интересовања** и изаберите опцију **Промени** поред **Држава / регион**.</span><span class="sxs-lookup"><span data-stu-id="93377-132">To select a country or region, open **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="93377-133">У окну **Подешавања земље/региона** одаберите опцију и изаберите **Примени**.</span><span class="sxs-lookup"><span data-stu-id="93377-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="93377-134">Последице које се односе на избор земље</span><span class="sxs-lookup"><span data-stu-id="93377-134">Implications related to country selection</span></span>

- <span data-ttu-id="93377-135">Када [бирате сопствене брендове](#define-your-brands-or-interests), систем пружа предлоге на основу изабране земље или региона.</span><span class="sxs-lookup"><span data-stu-id="93377-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="93377-136">Када [бирате делатност](#define-your-brands-or-interests), добићете најрелевантније брендове или интересовања на основу изабране земље или региона.</span><span class="sxs-lookup"><span data-stu-id="93377-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="93377-137">Када [обогаћујете профиле](#refresh-enrichment), обогатићемо све профиле клијената за које добијамо податке за изабране брендове и интересовања, укључујући профиле који нису у изабраној земљи или региону.</span><span class="sxs-lookup"><span data-stu-id="93377-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests, including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="93377-138">На пример, ако сте изабрали Немачку, обогатићемо профиле који се налазе у Сједињеним Државама ако имамо податке о изабраним брендовима и интересовањима у САД.</span><span class="sxs-lookup"><span data-stu-id="93377-138">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="93377-139">Конфигурисање обогаћивања</span><span class="sxs-lookup"><span data-stu-id="93377-139">Configure enrichment</span></span>

<span data-ttu-id="93377-140">Вођено искуство вам помаже у конфигурацији обогаћивања.</span><span class="sxs-lookup"><span data-stu-id="93377-140">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="93377-141">Дефинисање брендова или интересовања</span><span class="sxs-lookup"><span data-stu-id="93377-141">Define your brands or interests</span></span>

<span data-ttu-id="93377-142">Изаберите до пет брендова или интересовања помоћу једне или обе ове опције:</span><span class="sxs-lookup"><span data-stu-id="93377-142">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="93377-143">**Делатност**: Изаберите своју делатност са падајуће листе, а затим одаберите најбоље брендове или интересовања за ту делатност.</span><span class="sxs-lookup"><span data-stu-id="93377-143">**Industry**: Select your industry from the dropdown list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="93377-144">**Изаберите своје**: Унесите бренд или интересовање који су релевантни за вашу организацију, а затим одаберите међу предлозима за подударање.</span><span class="sxs-lookup"><span data-stu-id="93377-144">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="93377-145">Ако не наведемо бренд или интересовање које тражите, пошаљите нам повратне информације користећи везу **Предложи**.</span><span class="sxs-lookup"><span data-stu-id="93377-145">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="93377-146">Преглед жељених подешавања за обогаћивање</span><span class="sxs-lookup"><span data-stu-id="93377-146">Review enrichment preferences</span></span>

<span data-ttu-id="93377-147">Прегледајте подразумеване поставке обогаћивања и ажурирајте их по потреби.</span><span class="sxs-lookup"><span data-stu-id="93377-147">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Снимак екрана прозора за жељена подешавања обогаћивања.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="93377-149">Изаберите ентитет који желите да обогатите</span><span class="sxs-lookup"><span data-stu-id="93377-149">Select entity to enrich</span></span>

<span data-ttu-id="93377-150">Изаберите **Обогаћени ентитет** и одаберите скуп података који желите да обогатите подацима предузећа из компаније Microsoft.</span><span class="sxs-lookup"><span data-stu-id="93377-150">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="93377-151">Можете изабрати ентитет Клијент да бисте обогатили све ваше корисничке профиле или изаберите ентитет сегмента да бисте обогатили само корисничке профиле садржане у том сегменту.</span><span class="sxs-lookup"><span data-stu-id="93377-151">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="93377-152">Мапирање поља</span><span class="sxs-lookup"><span data-stu-id="93377-152">Map your fields</span></span>

<span data-ttu-id="93377-153">Мапирајте поља из вашег обједињеног ентитета клијента да бисте дефинисали демографски сегмент који желите да систем користи за обогаћивање података о клијентима.</span><span class="sxs-lookup"><span data-stu-id="93377-153">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="93377-154">Мапирајте земљу/регион и барем атрибуте „Датум рођења“ или „Пол“.</span><span class="sxs-lookup"><span data-stu-id="93377-154">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="93377-155">Поред тога, морате да мапирате најмање један град (и државу/покрајину) или поштански број.</span><span class="sxs-lookup"><span data-stu-id="93377-155">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="93377-156">Изаберите **Уреди** да бисте дефинисали мапирање поља и изаберите **Примени** када завршите.</span><span class="sxs-lookup"><span data-stu-id="93377-156">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="93377-157">Изаберите **Сачувај** да бисте довршили мапирање поља.</span><span class="sxs-lookup"><span data-stu-id="93377-157">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="93377-158">Следећи формати и вредности су подржани (вредности не разликују велика и мала слова):</span><span class="sxs-lookup"><span data-stu-id="93377-158">The following formats and values are supported (values are not case-sensitive):</span></span>

- <span data-ttu-id="93377-159">**Датум рођења**: Препоручујемо да се датум рођења конвертује у тип DateTime током уноса података.</span><span class="sxs-lookup"><span data-stu-id="93377-159">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="93377-160">Алтернативно, то може бити ниска у [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) формату "yyyy-MM-dd" или "yyyy-MM-ddTHH:mm:ss".</span><span class="sxs-lookup"><span data-stu-id="93377-160">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ss".</span></span>
- <span data-ttu-id="93377-161">**Пол**: Мушки, Женски, Непознат.</span><span class="sxs-lookup"><span data-stu-id="93377-161">**Gender**: Male, Female, Unknown.</span></span>
- <span data-ttu-id="93377-162">**Поштански број**: Петоцифрени поштански бројеви за Сједињене Државе, стандардни поштански број свуда другде.</span><span class="sxs-lookup"><span data-stu-id="93377-162">**Postal code**: Five-digit ZIP codes for United States, standard postal code everywhere else.</span></span>
- <span data-ttu-id="93377-163">**Град**: Назив града на енглеском језику.</span><span class="sxs-lookup"><span data-stu-id="93377-163">**City**: City name in English.</span></span>
- <span data-ttu-id="93377-164">**Држава/покрајина**: Скраћеница са два слова за САД и Канаду.</span><span class="sxs-lookup"><span data-stu-id="93377-164">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="93377-165">Скраћеница од два или три слова за Аустралију.</span><span class="sxs-lookup"><span data-stu-id="93377-165">Two- or three-letter abbreviation for Australia.</span></span> <span data-ttu-id="93377-166">Није примењиво за Француску, Немачку или Уједињено Краљевство.</span><span class="sxs-lookup"><span data-stu-id="93377-166">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="93377-167">**Земља/регион**:</span><span class="sxs-lookup"><span data-stu-id="93377-167">**Country/Region**:</span></span>

  - <span data-ttu-id="93377-168">САД: Сједињене Америчке Државе, Сједињене Државе, САД, USA, Америка</span><span class="sxs-lookup"><span data-stu-id="93377-168">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="93377-169">CA: Канада, CA</span><span class="sxs-lookup"><span data-stu-id="93377-169">CA: Canada, CA</span></span>
  - <span data-ttu-id="93377-170">GB: Уједињено Краљевство, UK, Велика Британија, GB, Уједињено Краљевство Велике Британије и Северне Ирске, Уједињено Краљевство Велике Британије</span><span class="sxs-lookup"><span data-stu-id="93377-170">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="93377-171">AU: Аустралија, AU, Комонвелт Аустралије</span><span class="sxs-lookup"><span data-stu-id="93377-171">AU: Australia, AU, Commonwealth of Australia</span></span>
  - <span data-ttu-id="93377-172">FR: Француска, FR, Француска Република</span><span class="sxs-lookup"><span data-stu-id="93377-172">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="93377-173">DE: Немачка, Germany, Deutschland, Allemagne, DE, Савезна Република Немачка, Република Немачка</span><span class="sxs-lookup"><span data-stu-id="93377-173">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="93377-174">Преглед и давање назива обогаћењу</span><span class="sxs-lookup"><span data-stu-id="93377-174">Review and name the enrichment</span></span>

<span data-ttu-id="93377-175">На крају, треба да прегледате информације и наведете име за обогаћивање.</span><span class="sxs-lookup"><span data-stu-id="93377-175">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Страница за преглед и именовање интереса.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="93377-177">Освежите обогаћивање</span><span class="sxs-lookup"><span data-stu-id="93377-177">Refresh enrichment</span></span>

<span data-ttu-id="93377-178">Покрените обогаћивање након конфигурисања брендова, интересовања и мапирања поља за демографске категорије.</span><span class="sxs-lookup"><span data-stu-id="93377-178">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="93377-179">Да бисте покренули поступак, изаберите **Покрени** на страници за конфигурисање брендова или интересовања.</span><span class="sxs-lookup"><span data-stu-id="93377-179">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="93377-180">Поред тога, можете пустити систем да аутоматски покрене обогаћивање као део заказаног освежавања.</span><span class="sxs-lookup"><span data-stu-id="93377-180">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>

<span data-ttu-id="93377-181">У зависности од величине података о клијентима, може проћи неколико минута да се оплемењивање заврши.</span><span class="sxs-lookup"><span data-stu-id="93377-181">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="93377-182">Постоји [шест врста статуса](system.md#status-types) за задатке/процесе.</span><span class="sxs-lookup"><span data-stu-id="93377-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="93377-183">Уз то, већина процеса [зависи од других процеса на нижем току](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="93377-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="93377-184">Можете изабрати статус процеса да бисте видели детаље о току целог посла.</span><span class="sxs-lookup"><span data-stu-id="93377-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="93377-185">Након избора **Види детаље** за један од задатака посла, пронаћи ћете додатне информације: време обраде, датум последње обраде и све грешке и упозорења повезана са задатком.</span><span class="sxs-lookup"><span data-stu-id="93377-185">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="93377-186">Резултати обогаћивања</span><span class="sxs-lookup"><span data-stu-id="93377-186">Enrichment results</span></span>

<span data-ttu-id="93377-187">Након покретања поступка обогаћивања, идите на **Моја обогаћивања** да бисте прегледали укупан број обогаћених клијената и расподелу брендова или интересовања у обогаћеним корисничким профилима.</span><span class="sxs-lookup"><span data-stu-id="93377-187">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Преглед резултата након покретања процеса обогаћивања":::

<span data-ttu-id="93377-189">Прегледајте обогаћене податке избором опције **Приказ обогаћених података** у графикону.</span><span class="sxs-lookup"><span data-stu-id="93377-189">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="93377-190">Обогаћени подаци о брендовима иду у ентитет **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="93377-190">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="93377-191">Подаци за интересовања су у ентитету **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="93377-191">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="93377-192">Наћи ћете и ове ентитете наведене у групи **Обогаћивање** у одељку **Подаци** > **Ентитети**.</span><span class="sxs-lookup"><span data-stu-id="93377-192">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="93377-193">Погледајте податке о обогаћивању на картици клијента</span><span class="sxs-lookup"><span data-stu-id="93377-193">See enrichment data on the customer card</span></span>

<span data-ttu-id="93377-194">Афинитети према бренду и интересовању могу се такође видети на картицама појединачних клијената.</span><span class="sxs-lookup"><span data-stu-id="93377-194">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="93377-195">Идите на **Клијенти** и изаберите кориснички профил.</span><span class="sxs-lookup"><span data-stu-id="93377-195">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="93377-196">На картици клијента ћете пронаћи графиконе за брендове или интересовања за које људи у демографском профилу тог клијента имају афинитет.</span><span class="sxs-lookup"><span data-stu-id="93377-196">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Картица клијента са обогаћеним подацима":::

## <a name="next-steps"></a><span data-ttu-id="93377-198">Следећи кораци</span><span class="sxs-lookup"><span data-stu-id="93377-198">Next steps</span></span>

<span data-ttu-id="93377-199">Надоградите на обогаћеним подацима о клијентима.</span><span class="sxs-lookup"><span data-stu-id="93377-199">Build on top of your enriched customer data.</span></span> <span data-ttu-id="93377-200">Креирајте [сегменте](segments.md) и [мере](measures.md), па чак и [извоз података](export-destinations.md) да пружите персонализована искуства својим клијентима.</span><span class="sxs-lookup"><span data-stu-id="93377-200">Create [Segments](segments.md) and [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
