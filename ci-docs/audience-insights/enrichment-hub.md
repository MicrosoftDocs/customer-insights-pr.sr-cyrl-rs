---
title: Обогатите обједињене профиле клијената
description: Користите могућности за обогаћивање података о клијентима.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896023"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="5e533-103">Обогаћивање за профиле корисника (преглед)</span><span class="sxs-lookup"><span data-stu-id="5e533-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="5e533-104">Користите податке из извора као што су Microsoft и други партнери да бисте обогатили податке о клијентима.</span><span class="sxs-lookup"><span data-stu-id="5e533-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Страница чворишта за обогаћивање":::

<span data-ttu-id="5e533-106">У увидима о корисницима идите на **Подаци** > **Обогаћивање** да бисте користили опције обогаћивања.</span><span class="sxs-lookup"><span data-stu-id="5e533-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="5e533-107">Да бисте креирали или мењали обогаћивања, морате да имате дозволе сарадника или администратора.</span><span class="sxs-lookup"><span data-stu-id="5e533-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="5e533-108">Више информација потражите у [дозволама](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="5e533-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="5e533-109">На картици **Откривање** ћете пронаћи следећа обогаћивања:</span><span class="sxs-lookup"><span data-stu-id="5e533-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="5e533-110">[Брендове](enrichment-microsoft.md) обезбеђује Microsoft</span><span class="sxs-lookup"><span data-stu-id="5e533-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="5e533-111">[Интересовања](enrichment-microsoft.md) обезбеђује Microsoft</span><span class="sxs-lookup"><span data-stu-id="5e533-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="5e533-112">[Подаци о компанији](enrichment-leadspace.md) које пружа Leadspace</span><span class="sxs-lookup"><span data-stu-id="5e533-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="5e533-113">[Демографски подаци](enrichment-experian.md) које пружа Experian</span><span class="sxs-lookup"><span data-stu-id="5e533-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="5e533-114">[Податке о локацији](enrichment-here.md) пружа HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="5e533-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="5e533-115">[Прилагођени подаци](enrichment-SFTP-custom-import.md) помоћу протокола Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="5e533-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="5e533-116">На картици **Моја обогаћивања** можете да видите обогаћивања која сте конфигурисали и да мењате њихова својства.</span><span class="sxs-lookup"><span data-stu-id="5e533-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="5e533-117">Управљање постојећим обогаћивањима</span><span class="sxs-lookup"><span data-stu-id="5e533-117">Manage existing enrichments</span></span>

<span data-ttu-id="5e533-118">Идите на **Моја обогаћивања** да видите сва конфигурисана обогаћивања.</span><span class="sxs-lookup"><span data-stu-id="5e533-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="5e533-119">Свако обогаћивање представљено је као ред који укључује додатне информације о обогаћивању.</span><span class="sxs-lookup"><span data-stu-id="5e533-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="5e533-120">Изаберите обогаћивање да бисте видели доступне опције.</span><span class="sxs-lookup"><span data-stu-id="5e533-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="5e533-121">Такође можете одабрати три тачке (...) на ставци листе да бисте видели опције.</span><span class="sxs-lookup"><span data-stu-id="5e533-121">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Опције за управљање обогаћивањима на листи обогаћивања":::

- <span data-ttu-id="5e533-123">**Прикажите** детаље обогаћивања са бројем обогаћених профила клијената.</span><span class="sxs-lookup"><span data-stu-id="5e533-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="5e533-124">**Уређујте** конфигурацију обогаћивања.</span><span class="sxs-lookup"><span data-stu-id="5e533-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="5e533-125">**Покрените** обогаћивање ради ажурирања профила клијената најновијим подацима.</span><span class="sxs-lookup"><span data-stu-id="5e533-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="5e533-126">**Деактивирајте** постојеће обогаћивање како би се зауставили аутоматско освежавање са сваким заказаним освежавањем.</span><span class="sxs-lookup"><span data-stu-id="5e533-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="5e533-127">Подаци из последњег успешног освежавања и даље ће бити доступни.</span><span class="sxs-lookup"><span data-stu-id="5e533-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="5e533-128">**Активирајте** неактивно обогаћивање да бисте поново покренули аутоматско освежавање са сваким заказаним освежавањем.</span><span class="sxs-lookup"><span data-stu-id="5e533-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="5e533-129">**Избришите** обогаћивање.</span><span class="sxs-lookup"><span data-stu-id="5e533-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="5e533-130">Можете да покренете или деактивирате више обогаћивања одједном тако што ћете их изабрати на листи.</span><span class="sxs-lookup"><span data-stu-id="5e533-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="5e533-131">Опције прегледа и уређивања нису доступне као масовна радња и раде само за једно обогаћивање.</span><span class="sxs-lookup"><span data-stu-id="5e533-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="5e533-132">Обогаћивања и везе</span><span class="sxs-lookup"><span data-stu-id="5e533-132">Enrichments and connections</span></span>

<span data-ttu-id="5e533-133">Обогаћења трећих лица се конфигуришу помоћу [веза](connections.md) које администратор поставља са акредитивима и даје сагласност за пренос података.</span><span class="sxs-lookup"><span data-stu-id="5e533-133">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="5e533-134">Везу могу да користе администратори и сарадници да би конфигурисали обогаћивања.</span><span class="sxs-lookup"><span data-stu-id="5e533-134">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="5e533-135">Вишеструка обогаћивања истог типа</span><span class="sxs-lookup"><span data-stu-id="5e533-135">Multiple enrichments of the same type</span></span>

<span data-ttu-id="5e533-136">Ентитет који треба обогатити наводи се током конфигурације обогаћивања, што вам омогућава да обогатите само подскуп својих профила.</span><span class="sxs-lookup"><span data-stu-id="5e533-136">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="5e533-137">На пример, обогатите податке само за одређени сегмент.</span><span class="sxs-lookup"><span data-stu-id="5e533-137">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="5e533-138">Можете да конфигуришете неколико обогаћивања истог типа и да поново користите исту везу.</span><span class="sxs-lookup"><span data-stu-id="5e533-138">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="5e533-139">Нека обогаћивања ће имати ограничења у броју обогаћивања истог типа која се могу креирати.</span><span class="sxs-lookup"><span data-stu-id="5e533-139">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="5e533-140">Ограничења и тренутна употреба могу се видети на страници **Обогаћивање**.</span><span class="sxs-lookup"><span data-stu-id="5e533-140">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
