---
title: Обогатите обједињене профиле клијената
description: Користите могућности за обогаћивање података о клијентима.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667112"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="2c04a-103">Обогаћивање за профиле корисника (преглед)</span><span class="sxs-lookup"><span data-stu-id="2c04a-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="2c04a-104">Користите податке из извора као што су Microsoft и други партнери да бисте обогатили податке о клијентима.</span><span class="sxs-lookup"><span data-stu-id="2c04a-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Страница чворишта за обогаћивање":::

<span data-ttu-id="2c04a-106">У увидима о корисницима идите на **Подаци** > **Обогаћивање** да бисте користили опције обогаћивања.</span><span class="sxs-lookup"><span data-stu-id="2c04a-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="2c04a-107">Да бисте креирали или мењали обогаћивања, морате да имате дозволе сарадника или администратора.</span><span class="sxs-lookup"><span data-stu-id="2c04a-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="2c04a-108">Више информација потражите у [дозволама](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="2c04a-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="2c04a-109">На картици **Откривање** ћете пронаћи следећа обогаћивања:</span><span class="sxs-lookup"><span data-stu-id="2c04a-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="2c04a-110">[Брендови](enrichment-microsoft-graph.md) које пружа Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="2c04a-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="2c04a-111">[Интересовања](enrichment-microsoft-graph.md) које пружа Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="2c04a-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="2c04a-112">[Подаци о компанији](enrichment-leadspace.md) које пружа Leadspace</span><span class="sxs-lookup"><span data-stu-id="2c04a-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="2c04a-113">[Демографски подаци](enrichment-experian.md) које пружа Experian</span><span class="sxs-lookup"><span data-stu-id="2c04a-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="2c04a-114">[Податке о локацији](enrichment-here.md) пружа HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="2c04a-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="2c04a-115">[Прилагођени подаци](enrichment-SFTP-custom-import.md) помоћу протокола Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="2c04a-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="2c04a-116">На картици **Моја обогаћивања** можете да видите обогаћивања која сте конфигурисали и да мењате њихова својства.</span><span class="sxs-lookup"><span data-stu-id="2c04a-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="2c04a-117">Управљање постојећим обогаћивањима</span><span class="sxs-lookup"><span data-stu-id="2c04a-117">Manage existing enrichments</span></span>

<span data-ttu-id="2c04a-118">Идите на **Моја обогаћивања** да видите сва конфигурисана обогаћивања.</span><span class="sxs-lookup"><span data-stu-id="2c04a-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="2c04a-119">Свако обогаћивање представљено је као ред који укључује додатне информације о обогаћивању.</span><span class="sxs-lookup"><span data-stu-id="2c04a-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="2c04a-120">Изаберите обогаћивање да бисте видели доступне опције.</span><span class="sxs-lookup"><span data-stu-id="2c04a-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="2c04a-121">Алтернативно, можете одабрати три тачке (...) на ставки листе да бисте видели опције.</span><span class="sxs-lookup"><span data-stu-id="2c04a-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Опције за управљање обогаћивањима на листи обогаћивања":::

- <span data-ttu-id="2c04a-123">**Прикажите** детаље обогаћивања са бројем обогаћених профила клијената.</span><span class="sxs-lookup"><span data-stu-id="2c04a-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="2c04a-124">**Уређујте** конфигурацију обогаћивања.</span><span class="sxs-lookup"><span data-stu-id="2c04a-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="2c04a-125">**Покрените** обогаћивање ради ажурирања профила клијената најновијим подацима.</span><span class="sxs-lookup"><span data-stu-id="2c04a-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="2c04a-126">**Деактивирајте** постојеће обогаћивање како би се зауставили аутоматско освежавање са сваким заказаним освежавањем.</span><span class="sxs-lookup"><span data-stu-id="2c04a-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="2c04a-127">Подаци из последњег успешног освежавања и даље ће бити доступни.</span><span class="sxs-lookup"><span data-stu-id="2c04a-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="2c04a-128">**Активирајте** неактивно обогаћивање да бисте поново покренули аутоматско освежавање са сваким заказаним освежавањем.</span><span class="sxs-lookup"><span data-stu-id="2c04a-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="2c04a-129">**Избришите** обогаћивање.</span><span class="sxs-lookup"><span data-stu-id="2c04a-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="2c04a-130">Можете да покренете или деактивирате више обогаћивања одједном тако што ћете их изабрати на листи.</span><span class="sxs-lookup"><span data-stu-id="2c04a-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="2c04a-131">Опције прегледа и уређивања нису доступне као масовна радња и раде само за једно обогаћивање.</span><span class="sxs-lookup"><span data-stu-id="2c04a-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>
