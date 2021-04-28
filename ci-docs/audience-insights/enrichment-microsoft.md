---
title: Обогаћивање профила клијената подацима компаније Microsoft
description: Користите заштићене податке компаније Microsoft да бисте обогатили податке о клијентима афинитетима према бренду и интересовањима.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6f19033236190547f68d2b91ec6b32074bf7912a
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896620"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="ae31b-103">Обогатите профиле клијената афинитетима бренда и интересовања (преглед)</span><span class="sxs-lookup"><span data-stu-id="ae31b-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="ae31b-104">Користите заштићене податке компаније Microsoft да бисте обогатили податке о клијентима афинитетима према бренду и интересовањима.</span><span class="sxs-lookup"><span data-stu-id="ae31b-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="ae31b-105">Ови афинитети се одређују на основу података људи са сличном демографијом као и ваши клијенти.</span><span class="sxs-lookup"><span data-stu-id="ae31b-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="ae31b-106">Ове информације вам помажу да боље разумете и сегментирате своје клијенте на основу њихових афинитета према одређеним брендовима и интересовањима.</span><span class="sxs-lookup"><span data-stu-id="ae31b-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="ae31b-107">У увидима о корисницима, идите на **Подаци** > **Обогаћивање** да бисте [конфигурисали и прегледали обогаћивања](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="ae31b-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="ae31b-108">Да бисте конфигурисали обогаћивање афинитета за брендове, идите на картицу **Откријте** и изаберите **Обогати моје податке** на плочици **Брендови**.</span><span class="sxs-lookup"><span data-stu-id="ae31b-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="ae31b-109">Да бисте конфигурисали обогаћивање афинитета интересовања, идите на картицу **Откријте** и изаберите **Обогати моје податке** на плочици **Интересовања**.</span><span class="sxs-lookup"><span data-stu-id="ae31b-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ae31b-110">![Плочице Брендови и интересовања](media/BrandsInterest-tile-Hub.png "Плочице Брендови и интересовања")</span><span class="sxs-lookup"><span data-stu-id="ae31b-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="ae31b-111">Како утврђујемо афинитете</span><span class="sxs-lookup"><span data-stu-id="ae31b-111">How we determine affinities</span></span>

<span data-ttu-id="ae31b-112">Користимо податке за претрагу на мрежи компаније Microsoft за проналажење афинитета према брендовима и интересовањима у различитим демографским сегментима (дефинисани узрастом, полом или локацијом).</span><span class="sxs-lookup"><span data-stu-id="ae31b-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="ae31b-113">Обим претраживања брендова или интересовања на мрежи одређује колики афинитет демографски сегмент има према том бренду или интересовању, у поређењу с другим сегментима.</span><span class="sxs-lookup"><span data-stu-id="ae31b-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span> <span data-ttu-id="ae31b-114">бренд или интересовање.</span><span class="sxs-lookup"><span data-stu-id="ae31b-114">brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="ae31b-115">Ниво афинитета и резултат</span><span class="sxs-lookup"><span data-stu-id="ae31b-115">Affinity level and score</span></span>

<span data-ttu-id="ae31b-116">На сваком обогаћеном профилу клијента пружамо две повезане вредности – ниво афинитета и оцену афинитета.</span><span class="sxs-lookup"><span data-stu-id="ae31b-116">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="ae31b-117">Ове вредности вам помажу да утврдите колико је јак афинитет према демографском сегменту тог профила, према бренду или интересовању у поређењу са другим демографским сегментима.</span><span class="sxs-lookup"><span data-stu-id="ae31b-117">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="ae31b-118">*Ниво афинитета* састоји се од четири нивоа, а *оцена афинитета* се израчунава на скали од 100 поена која се пресликава на ниво афинитета.</span><span class="sxs-lookup"><span data-stu-id="ae31b-118">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="ae31b-119">Ниво афинитета</span><span class="sxs-lookup"><span data-stu-id="ae31b-119">Affinity level</span></span> |<span data-ttu-id="ae31b-120">Оцена афинитета</span><span class="sxs-lookup"><span data-stu-id="ae31b-120">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="ae31b-121">Веома високо</span><span class="sxs-lookup"><span data-stu-id="ae31b-121">Very high</span></span>     | <span data-ttu-id="ae31b-122">85-100</span><span class="sxs-lookup"><span data-stu-id="ae31b-122">85-100</span></span>       |
|<span data-ttu-id="ae31b-123">Висок</span><span class="sxs-lookup"><span data-stu-id="ae31b-123">High</span></span>     | <span data-ttu-id="ae31b-124">70-84</span><span class="sxs-lookup"><span data-stu-id="ae31b-124">70-84</span></span>        |
|<span data-ttu-id="ae31b-125">Средње</span><span class="sxs-lookup"><span data-stu-id="ae31b-125">Medium</span></span>     | <span data-ttu-id="ae31b-126">35-69</span><span class="sxs-lookup"><span data-stu-id="ae31b-126">35-69</span></span>        |
|<span data-ttu-id="ae31b-127">Низак</span><span class="sxs-lookup"><span data-stu-id="ae31b-127">Low</span></span>     | <span data-ttu-id="ae31b-128">1-34</span><span class="sxs-lookup"><span data-stu-id="ae31b-128">1-34</span></span>        |

<span data-ttu-id="ae31b-129">У зависности од грануларности којом желите да мерите афинитет, можете да користите ниво афинитета или резултат.</span><span class="sxs-lookup"><span data-stu-id="ae31b-129">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="ae31b-130">Оцена афинитета вам даје прецизнију контролу.</span><span class="sxs-lookup"><span data-stu-id="ae31b-130">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="ae31b-131">Подржане земље/региони</span><span class="sxs-lookup"><span data-stu-id="ae31b-131">Supported countries/regions</span></span>

<span data-ttu-id="ae31b-132">Тренутно подржавамо следеће опције земље/региона: Аустралија, Канада (енглески), Француска, Немачка, Уједињено Краљевство или Сједињене Државе (енглески).</span><span class="sxs-lookup"><span data-stu-id="ae31b-132">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="ae31b-133">Да бисте изабрали земљу, отворите **Обогаћивање брендова** или **Обогаћивање камата** и изаберите **Промени** поред ставке **Држава/регион**.</span><span class="sxs-lookup"><span data-stu-id="ae31b-133">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="ae31b-134">У окну **Подешавања земље/региона** одаберите опцију и изаберите **Примени**.</span><span class="sxs-lookup"><span data-stu-id="ae31b-134">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="ae31b-135">Последице које се односе на избор земље</span><span class="sxs-lookup"><span data-stu-id="ae31b-135">Implications related to country selection</span></span>

- <span data-ttu-id="ae31b-136">Када [бирате сопствене брендове](#define-your-brands-or-interests), систем пружа предлоге на основу изабране земље или региона.</span><span class="sxs-lookup"><span data-stu-id="ae31b-136">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="ae31b-137">Када [бирате делатност](#define-your-brands-or-interests), добићете најрелевантније брендове или интересовања на основу изабране земље или региона.</span><span class="sxs-lookup"><span data-stu-id="ae31b-137">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="ae31b-138">Када [обогаћујемо профиле](#refresh-enrichment), обогатићемо све профиле клијенте за које добијамо податке за изабране брендове и интересовања.</span><span class="sxs-lookup"><span data-stu-id="ae31b-138">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="ae31b-139">То укључује профиле који нису у изабраној земљи или региону.</span><span class="sxs-lookup"><span data-stu-id="ae31b-139">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="ae31b-140">На пример, ако сте изабрали Немачку, обогатићемо профиле који се налазе у Сједињеним Државама ако имамо податке о изабраним брендовима и интересовањима у САД.</span><span class="sxs-lookup"><span data-stu-id="ae31b-140">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="ae31b-141">Конфигурисање обогаћивања</span><span class="sxs-lookup"><span data-stu-id="ae31b-141">Configure Enrichment</span></span>

<span data-ttu-id="ae31b-142">Вођено искуство вам помаже у конфигурацији обогаћивања.</span><span class="sxs-lookup"><span data-stu-id="ae31b-142">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="ae31b-143">Дефинисање брендова или интересовања</span><span class="sxs-lookup"><span data-stu-id="ae31b-143">Define your brands or interests</span></span>

<span data-ttu-id="ae31b-144">Изаберите једну од следећих опција:</span><span class="sxs-lookup"><span data-stu-id="ae31b-144">Select one of the following options:</span></span>

- <span data-ttu-id="ae31b-145">**Делатност**: Систем идентификује најбоље брендове или интересовања која су релевантна за вашу делатност и обогаћује ваше податке о клијентима.</span><span class="sxs-lookup"><span data-stu-id="ae31b-145">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="ae31b-146">**Одаберите сопствено**: Изаберите до пет ставки са листе брендова или интересовања која су најрелевантнија за вашу организацију.</span><span class="sxs-lookup"><span data-stu-id="ae31b-146">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="ae31b-147">Да бисте додали бренд или интересовање, унесите га у поље за унос да бисте добили предлоге на основу термина који се подударају.</span><span class="sxs-lookup"><span data-stu-id="ae31b-147">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="ae31b-148">Ако не наведемо бренд или интересовање које тражите, пошаљите нам повратне информације користећи везу **Предложи**.</span><span class="sxs-lookup"><span data-stu-id="ae31b-148">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="ae31b-149">Преглед жељених подешавања за обогаћивање</span><span class="sxs-lookup"><span data-stu-id="ae31b-149">Review enrichment preferences</span></span>

<span data-ttu-id="ae31b-150">Прегледајте подразумеване поставке обогаћивања и ажурирајте их по потреби.</span><span class="sxs-lookup"><span data-stu-id="ae31b-150">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Снимак екрана прозора за жељена подешавања обогаћивања.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="ae31b-152">Изаберите ентитет који желите да обогатите</span><span class="sxs-lookup"><span data-stu-id="ae31b-152">Select entity to enrich</span></span>

<span data-ttu-id="ae31b-153">Изаберите **Обогаћени ентитет** и одаберите скуп података који желите да обогатите подацима предузећа из компаније Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ae31b-153">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="ae31b-154">Можете изабрати ентитет Клијент да бисте обогатили све ваше профиле клијената или изаберите ентитет сегмента да бисте обогатили само профиле клијената садржане у том сегменту.</span><span class="sxs-lookup"><span data-stu-id="ae31b-154">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="ae31b-155">Мапирање поља</span><span class="sxs-lookup"><span data-stu-id="ae31b-155">Map your fields</span></span>

<span data-ttu-id="ae31b-156">Мапирајте поља из вашег обједињеног ентитета клијента да бисте дефинисали демографски сегмент који желите да систем користи за обогаћивање података о клијентима.</span><span class="sxs-lookup"><span data-stu-id="ae31b-156">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="ae31b-157">Мапирајте земљу/регион и барем атрибуте „Датум рођења“ или „Пол“.</span><span class="sxs-lookup"><span data-stu-id="ae31b-157">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="ae31b-158">Поред тога, морате да мапирате најмање један град (и државу/покрајину) или поштански број.</span><span class="sxs-lookup"><span data-stu-id="ae31b-158">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="ae31b-159">Изаберите **Уреди** да бисте дефинисали мапирање поља и изаберите **Примени** када завршите.</span><span class="sxs-lookup"><span data-stu-id="ae31b-159">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="ae31b-160">Изаберите **Сачувај** да бисте довршили мапирање поља.</span><span class="sxs-lookup"><span data-stu-id="ae31b-160">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="ae31b-161">Следећи формати и вредности су подржани, вредности не разликују велика и мала слова:</span><span class="sxs-lookup"><span data-stu-id="ae31b-161">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="ae31b-162">**Датум рођења**: Препоручујемо да се датум рођења конвертује у тип DateTime током уноса података.</span><span class="sxs-lookup"><span data-stu-id="ae31b-162">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="ae31b-163">Алтернативно, то може бити низ у [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) формату „yyyy-MM-dd“ или „yyyy-MM-ddTHH:mm:ssZ“.</span><span class="sxs-lookup"><span data-stu-id="ae31b-163">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="ae31b-164">**Пол**: Мушко, Женско, Непознато</span><span class="sxs-lookup"><span data-stu-id="ae31b-164">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="ae31b-165">**Поштански број**: Петоцифрени поштански бројеви за САД, стандардни поштански број на свим другим местима</span><span class="sxs-lookup"><span data-stu-id="ae31b-165">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="ae31b-166">**Град**: Назив града на енглеском језику</span><span class="sxs-lookup"><span data-stu-id="ae31b-166">**City**: City name in English</span></span>
- <span data-ttu-id="ae31b-167">**Држава/покрајина**: Скраћеница са два слова за САД и Канаду.</span><span class="sxs-lookup"><span data-stu-id="ae31b-167">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="ae31b-168">Скраћеница од два или три слова за Аустралију.</span><span class="sxs-lookup"><span data-stu-id="ae31b-168">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="ae31b-169">Није примењиво за Француску, Немачку или Уједињено Краљевство.</span><span class="sxs-lookup"><span data-stu-id="ae31b-169">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="ae31b-170">**Земља/регион**:</span><span class="sxs-lookup"><span data-stu-id="ae31b-170">**Country/Region**:</span></span>

  - <span data-ttu-id="ae31b-171">САД: Сједињене Америчке Државе, Сједињене Државе, САД, USA, Америка</span><span class="sxs-lookup"><span data-stu-id="ae31b-171">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="ae31b-172">CA: Канада, CA</span><span class="sxs-lookup"><span data-stu-id="ae31b-172">CA: Canada, CA</span></span>
  - <span data-ttu-id="ae31b-173">GB: Уједињено Краљевство, UK, Велика Британија, GB, Уједињено Краљевство Велике Британије и Северне Ирске, Уједињено Краљевство Велике Британије</span><span class="sxs-lookup"><span data-stu-id="ae31b-173">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="ae31b-174">AU: Аустралија, AU, Комонвелт Аустралије</span><span class="sxs-lookup"><span data-stu-id="ae31b-174">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="ae31b-175">FR: Француска, FR, Француска Република</span><span class="sxs-lookup"><span data-stu-id="ae31b-175">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="ae31b-176">DE: Немачка, Germany, Deutschland, Allemagne, DE, Савезна Република Немачка, Република Немачка</span><span class="sxs-lookup"><span data-stu-id="ae31b-176">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="ae31b-177">Преглед и давање назива обогаћењу</span><span class="sxs-lookup"><span data-stu-id="ae31b-177">Review and name the enrichment</span></span>

<span data-ttu-id="ae31b-178">На крају, треба да прегледате информације и наведете име за обогаћивање.</span><span class="sxs-lookup"><span data-stu-id="ae31b-178">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Страница за преглед и именовање интереса.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="ae31b-180">Освежите обогаћивање</span><span class="sxs-lookup"><span data-stu-id="ae31b-180">Refresh enrichment</span></span>

<span data-ttu-id="ae31b-181">Покрените обогаћивање након конфигурисања брендова, интересовања и мапирања поља за демографске категорије.</span><span class="sxs-lookup"><span data-stu-id="ae31b-181">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="ae31b-182">Да бисте покренули поступак, изаберите **Покрени** на страници за конфигурисање брендова или интересовања.</span><span class="sxs-lookup"><span data-stu-id="ae31b-182">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="ae31b-183">Поред тога, можете пустити систем да аутоматски покрене обогаћивање као део заказаног освежавања.</span><span class="sxs-lookup"><span data-stu-id="ae31b-183">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="ae31b-184">У зависности од величине података о клијентима, може проћи неколико минута да се оплемењивање заврши.</span><span class="sxs-lookup"><span data-stu-id="ae31b-184">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="ae31b-185">Постоји [шест врста статуса](system.md#status-types) за задатке/процесе.</span><span class="sxs-lookup"><span data-stu-id="ae31b-185">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="ae31b-186">Уз то, већина процеса [зависи од других процеса на нижем току](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="ae31b-186">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="ae31b-187">Можете изабрати статус процеса да бисте видели детаље о току целог посла.</span><span class="sxs-lookup"><span data-stu-id="ae31b-187">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="ae31b-188">Након избора опције **Види детаље** за један од задатака посла пронаћи ћете додатне информације: време обраде, датум последње обраде и све грешке и упозорења повезана са задатком.</span><span class="sxs-lookup"><span data-stu-id="ae31b-188">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="ae31b-189">Резултати обогаћивања</span><span class="sxs-lookup"><span data-stu-id="ae31b-189">Enrichment results</span></span>

<span data-ttu-id="ae31b-190">Након покретања поступка обогаћивања, идите на **Моја обогаћивања** да бисте прегледали укупан број обогаћених клијената и расподелу брендова или интересовања у обогаћеним профилима клијената.</span><span class="sxs-lookup"><span data-stu-id="ae31b-190">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Преглед резултата након покретања процеса обогаћивања":::

<span data-ttu-id="ae31b-192">Прегледајте обогаћене податке избором опције **Приказ обогаћених података** у графикону.</span><span class="sxs-lookup"><span data-stu-id="ae31b-192">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="ae31b-193">Обогаћени подаци о брендовима иду у ентитет **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="ae31b-193">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="ae31b-194">Подаци за интересовања су у ентитету **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="ae31b-194">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="ae31b-195">Наћи ћете и ове ентитете наведене у групи **Обогаћивање** у одељку **Подаци** > **Ентитети**.</span><span class="sxs-lookup"><span data-stu-id="ae31b-195">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="ae31b-196">Погледајте податке о обогаћивању на картици клијента</span><span class="sxs-lookup"><span data-stu-id="ae31b-196">See enrichment data on the customer card</span></span>

<span data-ttu-id="ae31b-197">Афинитети према бренду и интересовању могу се такође видети на картицама појединачних клијената.</span><span class="sxs-lookup"><span data-stu-id="ae31b-197">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="ae31b-198">Идите на **Клијенти** и изаберите профил клијента.</span><span class="sxs-lookup"><span data-stu-id="ae31b-198">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="ae31b-199">На картици клијента ћете пронаћи графиконе за брендове или интересовања за које људи у демографском профилу тог клијента имају афинитет.</span><span class="sxs-lookup"><span data-stu-id="ae31b-199">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Картица клијента са обогаћеним подацима":::

## <a name="next-steps"></a><span data-ttu-id="ae31b-201">Следећи кораци</span><span class="sxs-lookup"><span data-stu-id="ae31b-201">Next steps</span></span>

<span data-ttu-id="ae31b-202">Надоградите на обогаћеним подацима о клијентима.</span><span class="sxs-lookup"><span data-stu-id="ae31b-202">Build on top of your enriched customer data.</span></span> <span data-ttu-id="ae31b-203">Креирајте [сегменте](segments.md), [мере](measures.md), па чак и [извоз података](export-destinations.md) да бисте пружили персонализована искуства својим клијентима.</span><span class="sxs-lookup"><span data-stu-id="ae31b-203">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
