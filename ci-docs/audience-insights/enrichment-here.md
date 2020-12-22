---
title: Обогаћивање помоћу обогаћивања треће стране HERE Technologies
description: Опште информације о HERE Technologies обогаћивању треће стране.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668696"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="af1be-103">Обогаћивање профила клијената уз HERE Technologies (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="af1be-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="af1be-104">верзија за преглед је компанија за платформу локације која пружа податке и услуге усмерене на локацију.</span><span class="sxs-lookup"><span data-stu-id="af1be-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="af1be-105">Помоћу услуга обогаћивања података компаније HERE Technologies можете да изградите прецизније разумевање локације својих клијената помоћу нормализације адреса, издвајања географске ширине и дужине и још много тога.</span><span class="sxs-lookup"><span data-stu-id="af1be-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="af1be-106">Предуслови</span><span class="sxs-lookup"><span data-stu-id="af1be-106">Prerequisites</span></span>

<span data-ttu-id="af1be-107">Да бисте конфигурисали верзија за преглед обогаћивања, морају бити испуњени следећи предуслови:</span><span class="sxs-lookup"><span data-stu-id="af1be-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="af1be-108">Морате имати активну претплату за HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="af1be-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="af1be-109">Да бисте добили претплату, можете [да се региструјете овде](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) или [контактирајте HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) директно.</span><span class="sxs-lookup"><span data-stu-id="af1be-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="af1be-110">Сазнајте више о HERE Technologies обогаћивању локације.</span><span class="sxs-lookup"><span data-stu-id="af1be-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="af1be-111">Имате HERE Technologies API кључ.</span><span class="sxs-lookup"><span data-stu-id="af1be-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="af1be-112">Имате [администраторске](permissions.md#administrator) дозволе.</span><span class="sxs-lookup"><span data-stu-id="af1be-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="af1be-113">Конфигурисање</span><span class="sxs-lookup"><span data-stu-id="af1be-113">Configuration</span></span>

1. <span data-ttu-id="af1be-114">Идите на **Подаци** > **Обогаћивање**.</span><span class="sxs-lookup"><span data-stu-id="af1be-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="af1be-115">На HERE Technologies плочици изаберите **Обогати моје податке**.</span><span class="sxs-lookup"><span data-stu-id="af1be-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="af1be-116">![HERE Technologies плочица](media/HERE-tile.png "HERE Technologies плочица")</span><span class="sxs-lookup"><span data-stu-id="af1be-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="af1be-117">Унесите активан **HERE Technologies API кључ**.</span><span class="sxs-lookup"><span data-stu-id="af1be-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="af1be-118">Прегледајте и дајте свој пристанак за **Приватност података и усаглашеност** тако што ћете изабрати поље за потврду **Слажем се**.</span><span class="sxs-lookup"><span data-stu-id="af1be-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="af1be-119">Потврдите оба улаза избором опције **Повежите се на HERE**.</span><span class="sxs-lookup"><span data-stu-id="af1be-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1. <span data-ttu-id="af1be-120">Изаберите **Додајте податке** и одаберите да ли желите да мапирате поља са примарном и/или секундарном адресом.</span><span class="sxs-lookup"><span data-stu-id="af1be-120">Select **Add data** and choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="af1be-121">Можете да наведете мапирање поља за обе адресе (на пример, кућну и пословну адресу) и засебно обогатити профиле за обе адресе.</span><span class="sxs-lookup"><span data-stu-id="af1be-121">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="af1be-122">Изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="af1be-122">Select **Next**.</span></span>

1. <span data-ttu-id="af1be-123">Дефинишите која поља из ваших обједињених профила треба користити за подударање података о локацији од компаније HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="af1be-123">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="af1be-124">Поља **Улица 1** и **Поштански број** су обавезна за одабрану примарну и/или секундарну адресу.</span><span class="sxs-lookup"><span data-stu-id="af1be-124">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="af1be-125">За већу прецизност подударања може се додати више поља.</span><span class="sxs-lookup"><span data-stu-id="af1be-125">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="af1be-126">![Страница за конфигурацију HERE Technologies обогаћивања](media/enrichment-HERE-configuration.png "Страница за конфигурацију HERE Technologies обогаћивања")</span><span class="sxs-lookup"><span data-stu-id="af1be-126">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="af1be-127">Изаберите **Примени** да довршите мапирање поља.</span><span class="sxs-lookup"><span data-stu-id="af1be-127">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="af1be-128">Резултати обогаћивања</span><span class="sxs-lookup"><span data-stu-id="af1be-128">Enrichment results</span></span>

<span data-ttu-id="af1be-129">Да бисте започели процес обогаћивања, изаберите **Покрени** са командне траке.</span><span class="sxs-lookup"><span data-stu-id="af1be-129">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="af1be-130">Такође можете пустити да систем аутоматски покреће обогаћивање као део [планираног освежавања](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="af1be-130">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="af1be-131">Време обраде зависиће од величине података о клијентима и времена одзива API-ја компаније HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="af1be-131">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="af1be-132">Након завршетка процеса обогаћивања, податке о новообогаћеним профилима клијената можете прегледати под опцијом **Моја обогаћивања**.</span><span class="sxs-lookup"><span data-stu-id="af1be-132">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="af1be-133">Осим тога, пронаћи ћете време последњег ажурирања и број обогаћених профила.</span><span class="sxs-lookup"><span data-stu-id="af1be-133">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="af1be-134">Детаљном приказу сваког обогаћеног профила можете приступити ако изаберете **Прикажи обогаћене податке**.</span><span class="sxs-lookup"><span data-stu-id="af1be-134">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="af1be-135">Следећи кораци</span><span class="sxs-lookup"><span data-stu-id="af1be-135">Next steps</span></span>

<span data-ttu-id="af1be-136">Надоградите на обогаћеним подацима о клијентима.</span><span class="sxs-lookup"><span data-stu-id="af1be-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="af1be-137">Креирајте [сегменте](segments.md), [мере](measures.md), па чак и [извезите податке](export-destinations.md) да бисте пружили персонализована искуства својим клијентима.</span><span class="sxs-lookup"><span data-stu-id="af1be-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="af1be-138">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="af1be-138">Data privacy and compliance</span></span>

<span data-ttu-id="af1be-139">Када омогућите да Dynamics 365 Customer Insights преноси податке у HERE Technologies, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="af1be-139">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="af1be-140">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да HERE Technologies испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="af1be-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="af1be-141">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="af1be-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="af1be-142">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони ово обогаћивање како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="af1be-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
