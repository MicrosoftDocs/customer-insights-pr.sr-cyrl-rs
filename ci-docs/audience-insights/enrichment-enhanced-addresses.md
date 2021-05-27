---
title: Обогаћивање побољшавања адресе
description: Обогатите и нормализујте информације о адресама корисничких профила помоћу Microsoft модела.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965596"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="2182c-103">Обогаћивање корисничких профила са побољшаним адресама</span><span class="sxs-lookup"><span data-stu-id="2182c-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="2182c-104">Адресе у вашим подацима могу бити неструктуриране, непотпуне или нетачне.</span><span class="sxs-lookup"><span data-stu-id="2182c-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="2182c-105">Користите Microsoft моделе за нормализацију и обогаћивање адреса у [формату Common Data Model](/common-data-model/schema/core/applicationcommon/address) ради веће тачности и увида.</span><span class="sxs-lookup"><span data-stu-id="2182c-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="2182c-106">Како побољшавамо адресе</span><span class="sxs-lookup"><span data-stu-id="2182c-106">How we enhance addresses</span></span>

<span data-ttu-id="2182c-107">Наш модел пролази кроз поступак у два корака за побољшање адресе.</span><span class="sxs-lookup"><span data-stu-id="2182c-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="2182c-108">Прво рашчлањује адресу да би идентификовао њене компоненте и ставља их у структурирани формат.</span><span class="sxs-lookup"><span data-stu-id="2182c-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="2182c-109">Затим користимо вештачку интелигенцију да бисмо исправили, употпунили и стандардизовали вредности у адреси.</span><span class="sxs-lookup"><span data-stu-id="2182c-109">Then, we use artificial intelligence to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="2182c-110">Пример</span><span class="sxs-lookup"><span data-stu-id="2182c-110">Example</span></span>

<span data-ttu-id="2182c-111">Информације о адреси могу да буду у нестандардном формату и да садрже правописне грешке.</span><span class="sxs-lookup"><span data-stu-id="2182c-111">Address information might be in a non-standard format and contain spelling errors.</span></span> <span data-ttu-id="2182c-112">Модел може решити ове проблеме и креирати доследне адресе у обједињеним корисничким профилима.</span><span class="sxs-lookup"><span data-stu-id="2182c-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="2182c-113">Ограничења</span><span class="sxs-lookup"><span data-stu-id="2182c-113">Limitations</span></span>

<span data-ttu-id="2182c-114">Побољшане адресе функционишу само са вредностима које већ постоје у подацима унетих адреса.</span><span class="sxs-lookup"><span data-stu-id="2182c-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="2182c-115">Модел не ради следеће:</span><span class="sxs-lookup"><span data-stu-id="2182c-115">The model doesn't:</span></span> 

1. <span data-ttu-id="2182c-116">Не проверава да ли је адреса важећа.</span><span class="sxs-lookup"><span data-stu-id="2182c-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="2182c-117">Не проверава да ли је нека од вредности, попут поштанских бројева или назива улица, важећа.</span><span class="sxs-lookup"><span data-stu-id="2182c-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="2182c-118">Не мења вредности које не препознаје.</span><span class="sxs-lookup"><span data-stu-id="2182c-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="2182c-119">Модел за побољшање адреса користи технике засноване на машинском учењу.</span><span class="sxs-lookup"><span data-stu-id="2182c-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="2182c-120">Иако примењујемо висок праг поузданости када модел мења улазну вредност, као и код било ког модела заснованог на машинском учењу, 100% тачност није загарантована.</span><span class="sxs-lookup"><span data-stu-id="2182c-120">While we apply a high confidence threshold for when the model changes an input value, as with any ML-based model, 100% accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="2182c-121">Подржане земље или региони</span><span class="sxs-lookup"><span data-stu-id="2182c-121">Supported countries or regions</span></span>

<span data-ttu-id="2182c-122">Тренутно подржавамо обогаћивање адреса у овим земљама или регионима:</span><span class="sxs-lookup"><span data-stu-id="2182c-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="2182c-123">Аустралија</span><span class="sxs-lookup"><span data-stu-id="2182c-123">Australia</span></span>
- <span data-ttu-id="2182c-124">Канада</span><span class="sxs-lookup"><span data-stu-id="2182c-124">Canada</span></span>
- <span data-ttu-id="2182c-125">Уједињено Краљевство</span><span class="sxs-lookup"><span data-stu-id="2182c-125">United Kingdom</span></span>
- <span data-ttu-id="2182c-126">Сједињене Државе</span><span class="sxs-lookup"><span data-stu-id="2182c-126">United States</span></span>

<span data-ttu-id="2182c-127">Адресе морају да садрже вредност земље/региона.</span><span class="sxs-lookup"><span data-stu-id="2182c-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="2182c-128">Не обрађујемо адресе за земље или регионе који нису подржани и адресе за које није наведена земља или регион.</span><span class="sxs-lookup"><span data-stu-id="2182c-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="2182c-129">Конфигурисање обогаћивања</span><span class="sxs-lookup"><span data-stu-id="2182c-129">Configure the enrichment</span></span>

1. <span data-ttu-id="2182c-130">Идите на **Подаци** > **Обогаћивање**.</span><span class="sxs-lookup"><span data-stu-id="2182c-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="2182c-131">Изаберите **Обогати моје податке** на плочици **Побољшане адресе**.</span><span class="sxs-lookup"><span data-stu-id="2182c-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Снимак екрана плочице Побољшане адресе.":::

1. <span data-ttu-id="2182c-133">Изаберите **Скуп података клијента** и одаберите ентитет који садржи адресе које желите да обогатите.</span><span class="sxs-lookup"><span data-stu-id="2182c-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="2182c-134">Можете изабрати ентитет *Клијент* да обогатите адресе у свим вашим корисничким профилима или изаберите ентитет сегмента за обогаћивање адреса само у корисничким профилима садржаним у том сегменту.</span><span class="sxs-lookup"><span data-stu-id="2182c-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="2182c-135">Изаберите начин обликовања адреса у скупу података.</span><span class="sxs-lookup"><span data-stu-id="2182c-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="2182c-136">Одаберите **Адреса са једним атрибутом** ако адресе у вашим подацима користе једно поље.</span><span class="sxs-lookup"><span data-stu-id="2182c-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="2182c-137">Одаберите **Адреса са више атрибута** ако адресе у вашим подацима користе више од једног поља података.</span><span class="sxs-lookup"><span data-stu-id="2182c-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2182c-138">Држава/регион је обавезна и за адресу са једним атрибутом и за ону са више атрибута.</span><span class="sxs-lookup"><span data-stu-id="2182c-138">Country/Region is mandatory in both single-attribute and multiple-attribute address.</span></span> <span data-ttu-id="2182c-139">Адресе које не садрже важеће или подржане вредности земље/региона неће бити обогаћене</span><span class="sxs-lookup"><span data-stu-id="2182c-139">Addresses that don't contain valid or supported country/region values won't be enriched</span></span>

1.  <span data-ttu-id="2182c-140">Мапирајте поља адресе из вашег обједињеног ентитета клијента.</span><span class="sxs-lookup"><span data-stu-id="2182c-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Побољшана страница за мапирање поља адресе.":::

1. <span data-ttu-id="2182c-142">Изаберите **Следеће** да бисте довршили мапирање поља.</span><span class="sxs-lookup"><span data-stu-id="2182c-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="2182c-143">Обезбедите назив за обогаћивање и излазни ентитет.</span><span class="sxs-lookup"><span data-stu-id="2182c-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="2182c-144">Изаберите **Сачувај обогаћивање** након прегледа ваших избора.</span><span class="sxs-lookup"><span data-stu-id="2182c-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="2182c-145">Резултати обогаћивања</span><span class="sxs-lookup"><span data-stu-id="2182c-145">Enrichment results</span></span>

<span data-ttu-id="2182c-146">Да бисте започели процес обогаћивања, изаберите **Покрени** са командне траке.</span><span class="sxs-lookup"><span data-stu-id="2182c-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="2182c-147">Такође можете пустити да систем аутоматски покреће обогаћивање као део [планираног освежавања](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2182c-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2182c-148">Време обраде зависи од величине података ваших клијената.</span><span class="sxs-lookup"><span data-stu-id="2182c-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="2182c-149">Након завршетка процеса обогаћивања, податке о новообогаћеним корисничким профилима можете прегледати под опцијом **Моја обогаћивања**.</span><span class="sxs-lookup"><span data-stu-id="2182c-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="2182c-150">Осим тога, пронаћи ћете време последњег ажурирања и број обогаћених профила.</span><span class="sxs-lookup"><span data-stu-id="2182c-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="2182c-151">Детаљном приказу сваког обогаћеног профила можете приступити ако изаберете **Прикажи обогаћене податке**.</span><span class="sxs-lookup"><span data-stu-id="2182c-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2182c-152">Следећи кораци</span><span class="sxs-lookup"><span data-stu-id="2182c-152">Next steps</span></span>

<span data-ttu-id="2182c-153">Надоградите на обогаћеним подацима о клијентима.</span><span class="sxs-lookup"><span data-stu-id="2182c-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="2182c-154">Креирајте [сегменте](segments.md), [мере](measures.md), па чак и [извезите податке](export-destinations.md) да бисте пружили персонализована искуства својим клијентима.</span><span class="sxs-lookup"><span data-stu-id="2182c-154">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
