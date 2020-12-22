---
title: Обогаћивање профила предузећа независним Leadspace-ом за обогаћивање
description: Опште информације о Leadspace обогаћивању треће стране.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668741"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="0572d-103">Обогаћивање профила предузећа уз Leadspace (преглед)</span><span class="sxs-lookup"><span data-stu-id="0572d-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="0572d-104">Leadspace је компанија за науку о подацима која обезбеђује B2B платформу за податке о клијентима.</span><span class="sxs-lookup"><span data-stu-id="0572d-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="0572d-105">Омогућује клијентима са обједињеним профилима клијената за компаније да обогаћују своје податке.</span><span class="sxs-lookup"><span data-stu-id="0572d-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="0572d-106">Обогаћивања обухватају додатне атрибуте укључујући величину компаније, локацију, делатност и још много тога.</span><span class="sxs-lookup"><span data-stu-id="0572d-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0572d-107">Предуслови</span><span class="sxs-lookup"><span data-stu-id="0572d-107">Prerequisites</span></span>

<span data-ttu-id="0572d-108">Да бисте конфигурисали Leadspace, морате да се испуните следеће предуслове:</span><span class="sxs-lookup"><span data-stu-id="0572d-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="0572d-109">Имате активну Leadspace лиценцу и „трајни кључ“ (назван **Leadspace токен**).</span><span class="sxs-lookup"><span data-stu-id="0572d-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="0572d-110">Контактирајте директно [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) за детаље о њиховом производу.</span><span class="sxs-lookup"><span data-stu-id="0572d-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="0572d-111">Имате [администраторске](permissions.md#administrator) дозволе.</span><span class="sxs-lookup"><span data-stu-id="0572d-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="0572d-112">Имате [обједињене профиле клијената](customer-profiles.md) за компаније.</span><span class="sxs-lookup"><span data-stu-id="0572d-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="0572d-113">Конфигурисање</span><span class="sxs-lookup"><span data-stu-id="0572d-113">Configuration</span></span>

1. <span data-ttu-id="0572d-114">У увидима о корисницима идите на **Подаци** > **Обогаћивање**.</span><span class="sxs-lookup"><span data-stu-id="0572d-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="0572d-115">Изаберите **Обогати моје податке** на плочици Leadspace.</span><span class="sxs-lookup"><span data-stu-id="0572d-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Снимак екрана Leadspace плочице.":::

1. <span data-ttu-id="0572d-117">Изаберите **Започните**, а затим унесите активан **Leadspace токен** (трајни кључ).</span><span class="sxs-lookup"><span data-stu-id="0572d-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="0572d-118">Прегледајте и дајте свој пристанак за **Приватност података и усаглашеност** тако што ћете изабрати поље за потврду **Слажем се**.</span><span class="sxs-lookup"><span data-stu-id="0572d-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="0572d-119">Потврдите оба улаза избором опције **Повежите се на Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="0572d-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="0572d-120">Изаберите **Подаци мапе** и дефинишите која поља из ваших обједињених профила треба користити за тражење одговарајућих података о компанији из Leadspace-а.</span><span class="sxs-lookup"><span data-stu-id="0572d-120">Select **Map data** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="0572d-121">Поље **Име компаније** је обавезно.</span><span class="sxs-lookup"><span data-stu-id="0572d-121">The **Name of company** field is required.</span></span> <span data-ttu-id="0572d-122">За већу прецизност подударања, до два друга поља, **Веб-локација компаније** и **Локација компаније**, могу се додати.</span><span class="sxs-lookup"><span data-stu-id="0572d-122">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Окно за мапирање поља Leadspace.":::
   
1. <span data-ttu-id="0572d-124">Изаберите **Примени** да довршите мапирање поља.</span><span class="sxs-lookup"><span data-stu-id="0572d-124">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="0572d-125">Изаберите **Покрени** како бисте обогатили профиле предузећа.</span><span class="sxs-lookup"><span data-stu-id="0572d-125">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="0572d-126">Колико дуго траје обогаћивање, зависи од броја обједињених профила клијената.</span><span class="sxs-lookup"><span data-stu-id="0572d-126">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="0572d-127">Резултати обогаћивања</span><span class="sxs-lookup"><span data-stu-id="0572d-127">Enrichment results</span></span>

<span data-ttu-id="0572d-128">Након освежавања обогаћивања, можете прегледати ново обогаћене податке компаније у делу [Моја обогаћења](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="0572d-128">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="0572d-129">Можете пронаћи време последњег ажурирања и број обогаћених профила.</span><span class="sxs-lookup"><span data-stu-id="0572d-129">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="0572d-130">Детаљном приказу сваког обогаћеног профила можете приступити ако изаберете **Прикажи обогаћене податке**.</span><span class="sxs-lookup"><span data-stu-id="0572d-130">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="0572d-131">Више информација потражите у чланку [Leadspace API-ји](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="0572d-131">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0572d-132">Следећи кораци</span><span class="sxs-lookup"><span data-stu-id="0572d-132">Next steps</span></span>

<span data-ttu-id="0572d-133">Надоградите на обогаћеним подацима о клијентима.</span><span class="sxs-lookup"><span data-stu-id="0572d-133">Build on top of your enriched customer data.</span></span> <span data-ttu-id="0572d-134">Креирајте [сегменте](segments.md), [мере](measures.md), па чак и [извезите податке](export-destinations.md) да бисте пружили персонализована искуства својим клијентима.</span><span class="sxs-lookup"><span data-stu-id="0572d-134">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0572d-135">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="0572d-135">Data privacy and compliance</span></span>

<span data-ttu-id="0572d-136">Када омогућите да Dynamics 365 Customer Insights преноси податке у Leadspace, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="0572d-136">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0572d-137">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Leadspace испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="0572d-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0572d-138">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0572d-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0572d-139">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони ово обогаћивање како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="0572d-139">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>