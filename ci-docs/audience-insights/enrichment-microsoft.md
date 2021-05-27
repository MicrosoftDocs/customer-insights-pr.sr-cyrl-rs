---
title: Обогаћивање корисничких профила подацима компаније Microsoft
description: Користите заштићене податке компаније Microsoft да бисте обогатили податке о клијентима афинитетима према бренду и интересовањима.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: be042dd139607849b795c903fa58da2edb9ff589
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064909"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="8e31b-103">Обогатите корисничке профиле афинитетима бренда и интересовања (преглед)</span><span class="sxs-lookup"><span data-stu-id="8e31b-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="8e31b-104">Користите заштићене податке компаније Microsoft да бисте обогатили податке о клијентима афинитетима према бренду и интересовањима.</span><span class="sxs-lookup"><span data-stu-id="8e31b-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="8e31b-105">Ови афинитети се одређују на основу података људи са сличном демографијом као и ваши клијенти.</span><span class="sxs-lookup"><span data-stu-id="8e31b-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="8e31b-106">Ове информације вам помажу да боље разумете и сегментирате своје клијенте на основу њихових афинитета према одређеним брендовима и интересовањима.</span><span class="sxs-lookup"><span data-stu-id="8e31b-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="8e31b-107">У увидима о корисницима, идите на **Подаци** > **Обогаћивање** да бисте [конфигурисали и прегледали обогаћивања](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="8e31b-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="8e31b-108">Да бисте конфигурисали обогаћивање афинитета за брендове, идите на картицу **Откријте** и изаберите **Обогати моје податке** на плочици **Брендови**.</span><span class="sxs-lookup"><span data-stu-id="8e31b-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="8e31b-109">Да бисте конфигурисали обогаћивање афинитета интересовања, идите на картицу **Откријте** и изаберите **Обогати моје податке** на плочици **Интересовања**.</span><span class="sxs-lookup"><span data-stu-id="8e31b-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8e31b-110">![Плочице Брендови и интересовања](media/BrandsInterest-tile-Hub.png "Плочице Брендови и интересовања")</span><span class="sxs-lookup"><span data-stu-id="8e31b-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="8e31b-111">Како утврђујемо афинитете</span><span class="sxs-lookup"><span data-stu-id="8e31b-111">How we determine affinities</span></span>

<span data-ttu-id="8e31b-112">Користимо податке за претрагу на мрежи компаније Microsoft за проналажење афинитета према брендовима и интересовањима у различитим демографским сегментима (дефинисани узрастом, полом или локацијом).</span><span class="sxs-lookup"><span data-stu-id="8e31b-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="8e31b-113">Обим претраживања брендова или интересовања на мрежи одређује колики афинитет демографски сегмент има према том бренду или интересовању, у поређењу с другим сегментима.</span><span class="sxs-lookup"><span data-stu-id="8e31b-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="8e31b-114">Ниво афинитета и резултат</span><span class="sxs-lookup"><span data-stu-id="8e31b-114">Affinity level and score</span></span>

<span data-ttu-id="8e31b-115">На сваком обогаћеном корисничком профилу пружамо две повезане вредности – ниво афинитета и оцену афинитета.</span><span class="sxs-lookup"><span data-stu-id="8e31b-115">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="8e31b-116">Ове вредности вам помажу да утврдите колико је јак афинитет према демографском сегменту тог профила, према бренду или интересовању у поређењу са другим демографским сегментима.</span><span class="sxs-lookup"><span data-stu-id="8e31b-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="8e31b-117">*Ниво афинитета* састоји се од четири нивоа, а *оцена афинитета* се израчунава на скали од 100 поена која се пресликава на ниво афинитета.</span><span class="sxs-lookup"><span data-stu-id="8e31b-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="8e31b-118">Ниво афинитета</span><span class="sxs-lookup"><span data-stu-id="8e31b-118">Affinity level</span></span> |<span data-ttu-id="8e31b-119">Оцена афинитета</span><span class="sxs-lookup"><span data-stu-id="8e31b-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="8e31b-120">Веома високо</span><span class="sxs-lookup"><span data-stu-id="8e31b-120">Very high</span></span>     | <span data-ttu-id="8e31b-121">85-100</span><span class="sxs-lookup"><span data-stu-id="8e31b-121">85-100</span></span>       |
|<span data-ttu-id="8e31b-122">Висок</span><span class="sxs-lookup"><span data-stu-id="8e31b-122">High</span></span>     | <span data-ttu-id="8e31b-123">70-84</span><span class="sxs-lookup"><span data-stu-id="8e31b-123">70-84</span></span>        |
|<span data-ttu-id="8e31b-124">Средње</span><span class="sxs-lookup"><span data-stu-id="8e31b-124">Medium</span></span>     | <span data-ttu-id="8e31b-125">35-69</span><span class="sxs-lookup"><span data-stu-id="8e31b-125">35-69</span></span>        |
|<span data-ttu-id="8e31b-126">Низак</span><span class="sxs-lookup"><span data-stu-id="8e31b-126">Low</span></span>     | <span data-ttu-id="8e31b-127">1-34</span><span class="sxs-lookup"><span data-stu-id="8e31b-127">1-34</span></span>        |

<span data-ttu-id="8e31b-128">У зависности од грануларности којом желите да мерите афинитет, можете да користите ниво афинитета или резултат.</span><span class="sxs-lookup"><span data-stu-id="8e31b-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="8e31b-129">Оцена афинитета вам даје прецизнију контролу.</span><span class="sxs-lookup"><span data-stu-id="8e31b-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="8e31b-130">Подржане земље/региони</span><span class="sxs-lookup"><span data-stu-id="8e31b-130">Supported countries/regions</span></span>

<span data-ttu-id="8e31b-131">Тренутно подржавамо следеће опције земље/региона: Аустралија, Канада (енглески), Француска, Немачка, Уједињено Краљевство или Сједињене Државе (енглески).</span><span class="sxs-lookup"><span data-stu-id="8e31b-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="8e31b-132">Да бисте изабрали земљу, отворите **Обогаћивање брендова** или **Обогаћивање камата** и изаберите **Промени** поред ставке **Држава/регион**.</span><span class="sxs-lookup"><span data-stu-id="8e31b-132">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="8e31b-133">У окну **Подешавања земље/региона** одаберите опцију и изаберите **Примени**.</span><span class="sxs-lookup"><span data-stu-id="8e31b-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="8e31b-134">Последице које се односе на избор земље</span><span class="sxs-lookup"><span data-stu-id="8e31b-134">Implications related to country selection</span></span>

- <span data-ttu-id="8e31b-135">Када [бирате сопствене брендове](#define-your-brands-or-interests), систем пружа предлоге на основу изабране земље или региона.</span><span class="sxs-lookup"><span data-stu-id="8e31b-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="8e31b-136">Када [бирате делатност](#define-your-brands-or-interests), добићете најрелевантније брендове или интересовања на основу изабране земље или региона.</span><span class="sxs-lookup"><span data-stu-id="8e31b-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="8e31b-137">Када [обогаћујемо профиле](#refresh-enrichment), обогатићемо све корисничке профиле за које добијамо податке за изабране брендове и интересовања.</span><span class="sxs-lookup"><span data-stu-id="8e31b-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="8e31b-138">То укључује профиле који нису у изабраној земљи или региону.</span><span class="sxs-lookup"><span data-stu-id="8e31b-138">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="8e31b-139">На пример, ако сте изабрали Немачку, обогатићемо профиле који се налазе у Сједињеним Државама ако имамо податке о изабраним брендовима и интересовањима у САД.</span><span class="sxs-lookup"><span data-stu-id="8e31b-139">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="8e31b-140">Конфигурисање обогаћивања</span><span class="sxs-lookup"><span data-stu-id="8e31b-140">Configure Enrichment</span></span>

<span data-ttu-id="8e31b-141">Вођено искуство вам помаже у конфигурацији обогаћивања.</span><span class="sxs-lookup"><span data-stu-id="8e31b-141">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="8e31b-142">Дефинисање брендова или интересовања</span><span class="sxs-lookup"><span data-stu-id="8e31b-142">Define your brands or interests</span></span>

<span data-ttu-id="8e31b-143">Изаберите једну од следећих опција:</span><span class="sxs-lookup"><span data-stu-id="8e31b-143">Select one of the following options:</span></span>

- <span data-ttu-id="8e31b-144">**Делатност**: Систем идентификује најбоље брендове или интересовања која су релевантна за вашу делатност и обогаћује ваше податке о клијентима.</span><span class="sxs-lookup"><span data-stu-id="8e31b-144">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="8e31b-145">**Одаберите сопствено**: Изаберите до пет ставки са листе брендова или интересовања која су најрелевантнија за вашу организацију.</span><span class="sxs-lookup"><span data-stu-id="8e31b-145">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="8e31b-146">Да бисте додали бренд или интересовање, унесите га у поље за унос да бисте добили предлоге на основу термина који се подударају.</span><span class="sxs-lookup"><span data-stu-id="8e31b-146">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="8e31b-147">Ако не наведемо бренд или интересовање које тражите, пошаљите нам повратне информације користећи везу **Предложи**.</span><span class="sxs-lookup"><span data-stu-id="8e31b-147">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="8e31b-148">Преглед жељених подешавања за обогаћивање</span><span class="sxs-lookup"><span data-stu-id="8e31b-148">Review enrichment preferences</span></span>

<span data-ttu-id="8e31b-149">Прегледајте подразумеване поставке обогаћивања и ажурирајте их по потреби.</span><span class="sxs-lookup"><span data-stu-id="8e31b-149">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Снимак екрана прозора за жељена подешавања обогаћивања.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="8e31b-151">Изаберите ентитет који желите да обогатите</span><span class="sxs-lookup"><span data-stu-id="8e31b-151">Select entity to enrich</span></span>

<span data-ttu-id="8e31b-152">Изаберите **Обогаћени ентитет** и одаберите скуп података који желите да обогатите подацима предузећа из компаније Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8e31b-152">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="8e31b-153">Можете изабрати ентитет Клијент да бисте обогатили све ваше корисничке профиле или изаберите ентитет сегмента да бисте обогатили само корисничке профиле садржане у том сегменту.</span><span class="sxs-lookup"><span data-stu-id="8e31b-153">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="8e31b-154">Мапирање поља</span><span class="sxs-lookup"><span data-stu-id="8e31b-154">Map your fields</span></span>

<span data-ttu-id="8e31b-155">Мапирајте поља из вашег обједињеног ентитета клијента да бисте дефинисали демографски сегмент који желите да систем користи за обогаћивање података о клијентима.</span><span class="sxs-lookup"><span data-stu-id="8e31b-155">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="8e31b-156">Мапирајте земљу/регион и барем атрибуте „Датум рођења“ или „Пол“.</span><span class="sxs-lookup"><span data-stu-id="8e31b-156">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="8e31b-157">Поред тога, морате да мапирате најмање један град (и државу/покрајину) или поштански број.</span><span class="sxs-lookup"><span data-stu-id="8e31b-157">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="8e31b-158">Изаберите **Уреди** да бисте дефинисали мапирање поља и изаберите **Примени** када завршите.</span><span class="sxs-lookup"><span data-stu-id="8e31b-158">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="8e31b-159">Изаберите **Сачувај** да бисте довршили мапирање поља.</span><span class="sxs-lookup"><span data-stu-id="8e31b-159">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="8e31b-160">Следећи формати и вредности су подржани, вредности не разликују велика и мала слова:</span><span class="sxs-lookup"><span data-stu-id="8e31b-160">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="8e31b-161">**Датум рођења**: Препоручујемо да се датум рођења конвертује у тип DateTime током уноса података.</span><span class="sxs-lookup"><span data-stu-id="8e31b-161">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="8e31b-162">Алтернативно, то може бити низ у [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) формату „yyyy-MM-dd“ или „yyyy-MM-ddTHH:mm:ssZ“.</span><span class="sxs-lookup"><span data-stu-id="8e31b-162">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="8e31b-163">**Пол**: Мушко, Женско, Непознато</span><span class="sxs-lookup"><span data-stu-id="8e31b-163">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="8e31b-164">**Поштански број**: Петоцифрени поштански бројеви за САД, стандардни поштански број на свим другим местима</span><span class="sxs-lookup"><span data-stu-id="8e31b-164">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="8e31b-165">**Град**: Назив града на енглеском језику</span><span class="sxs-lookup"><span data-stu-id="8e31b-165">**City**: City name in English</span></span>
- <span data-ttu-id="8e31b-166">**Држава/покрајина**: Скраћеница са два слова за САД и Канаду.</span><span class="sxs-lookup"><span data-stu-id="8e31b-166">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="8e31b-167">Скраћеница од два или три слова за Аустралију.</span><span class="sxs-lookup"><span data-stu-id="8e31b-167">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="8e31b-168">Није примењиво за Француску, Немачку или Уједињено Краљевство.</span><span class="sxs-lookup"><span data-stu-id="8e31b-168">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="8e31b-169">**Земља/регион**:</span><span class="sxs-lookup"><span data-stu-id="8e31b-169">**Country/Region**:</span></span>

  - <span data-ttu-id="8e31b-170">САД: Сједињене Америчке Државе, Сједињене Државе, САД, USA, Америка</span><span class="sxs-lookup"><span data-stu-id="8e31b-170">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="8e31b-171">CA: Канада, CA</span><span class="sxs-lookup"><span data-stu-id="8e31b-171">CA: Canada, CA</span></span>
  - <span data-ttu-id="8e31b-172">GB: Уједињено Краљевство, UK, Велика Британија, GB, Уједињено Краљевство Велике Британије и Северне Ирске, Уједињено Краљевство Велике Британије</span><span class="sxs-lookup"><span data-stu-id="8e31b-172">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="8e31b-173">AU: Аустралија, AU, Комонвелт Аустралије</span><span class="sxs-lookup"><span data-stu-id="8e31b-173">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="8e31b-174">FR: Француска, FR, Француска Република</span><span class="sxs-lookup"><span data-stu-id="8e31b-174">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="8e31b-175">DE: Немачка, Germany, Deutschland, Allemagne, DE, Савезна Република Немачка, Република Немачка</span><span class="sxs-lookup"><span data-stu-id="8e31b-175">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="8e31b-176">Преглед и давање назива обогаћењу</span><span class="sxs-lookup"><span data-stu-id="8e31b-176">Review and name the enrichment</span></span>

<span data-ttu-id="8e31b-177">На крају, треба да прегледате информације и наведете име за обогаћивање.</span><span class="sxs-lookup"><span data-stu-id="8e31b-177">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Страница за преглед и именовање интереса.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="8e31b-179">Освежите обогаћивање</span><span class="sxs-lookup"><span data-stu-id="8e31b-179">Refresh enrichment</span></span>

<span data-ttu-id="8e31b-180">Покрените обогаћивање након конфигурисања брендова, интересовања и мапирања поља за демографске категорије.</span><span class="sxs-lookup"><span data-stu-id="8e31b-180">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="8e31b-181">Да бисте покренули поступак, изаберите **Покрени** на страници за конфигурисање брендова или интересовања.</span><span class="sxs-lookup"><span data-stu-id="8e31b-181">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="8e31b-182">Поред тога, можете пустити систем да аутоматски покрене обогаћивање као део заказаног освежавања.</span><span class="sxs-lookup"><span data-stu-id="8e31b-182">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="8e31b-183">У зависности од величине података о клијентима, може проћи неколико минута да се оплемењивање заврши.</span><span class="sxs-lookup"><span data-stu-id="8e31b-183">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="8e31b-184">Постоји [шест врста статуса](system.md#status-types) за задатке/процесе.</span><span class="sxs-lookup"><span data-stu-id="8e31b-184">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="8e31b-185">Уз то, већина процеса [зависи од других процеса на нижем току](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="8e31b-185">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="8e31b-186">Можете изабрати статус процеса да бисте видели детаље о току целог посла.</span><span class="sxs-lookup"><span data-stu-id="8e31b-186">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="8e31b-187">Након избора опције **Види детаље** за један од задатака посла пронаћи ћете додатне информације: време обраде, датум последње обраде и све грешке и упозорења повезана са задатком.</span><span class="sxs-lookup"><span data-stu-id="8e31b-187">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="8e31b-188">Резултати обогаћивања</span><span class="sxs-lookup"><span data-stu-id="8e31b-188">Enrichment results</span></span>

<span data-ttu-id="8e31b-189">Након покретања поступка обогаћивања, идите на **Моја обогаћивања** да бисте прегледали укупан број обогаћених клијената и расподелу брендова или интересовања у обогаћеним корисничким профилима.</span><span class="sxs-lookup"><span data-stu-id="8e31b-189">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Преглед резултата након покретања процеса обогаћивања":::

<span data-ttu-id="8e31b-191">Прегледајте обогаћене податке избором опције **Приказ обогаћених података** у графикону.</span><span class="sxs-lookup"><span data-stu-id="8e31b-191">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="8e31b-192">Обогаћени подаци о брендовима иду у ентитет **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="8e31b-192">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="8e31b-193">Подаци за интересовања су у ентитету **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="8e31b-193">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="8e31b-194">Наћи ћете и ове ентитете наведене у групи **Обогаћивање** у одељку **Подаци** > **Ентитети**.</span><span class="sxs-lookup"><span data-stu-id="8e31b-194">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="8e31b-195">Погледајте податке о обогаћивању на картици клијента</span><span class="sxs-lookup"><span data-stu-id="8e31b-195">See enrichment data on the customer card</span></span>

<span data-ttu-id="8e31b-196">Афинитети према бренду и интересовању могу се такође видети на картицама појединачних клијената.</span><span class="sxs-lookup"><span data-stu-id="8e31b-196">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="8e31b-197">Идите на **Клијенти** и изаберите кориснички профил.</span><span class="sxs-lookup"><span data-stu-id="8e31b-197">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="8e31b-198">На картици клијента ћете пронаћи графиконе за брендове или интересовања за које људи у демографском профилу тог клијента имају афинитет.</span><span class="sxs-lookup"><span data-stu-id="8e31b-198">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Картица клијента са обогаћеним подацима":::

## <a name="next-steps"></a><span data-ttu-id="8e31b-200">Следећи кораци</span><span class="sxs-lookup"><span data-stu-id="8e31b-200">Next steps</span></span>

<span data-ttu-id="8e31b-201">Надоградите на обогаћеним подацима о клијентима.</span><span class="sxs-lookup"><span data-stu-id="8e31b-201">Build on top of your enriched customer data.</span></span> <span data-ttu-id="8e31b-202">Креирајте [сегменте](segments.md), [мере](measures.md), па чак и [извоз података](export-destinations.md) да бисте пружили персонализована искуства својим клијентима.</span><span class="sxs-lookup"><span data-stu-id="8e31b-202">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
