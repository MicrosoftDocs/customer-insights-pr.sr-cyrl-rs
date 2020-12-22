---
title: Обогаћивање помоћу обогаћивања треће стране Experian
description: Опште информације о Experian обогаћивању треће стране.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668831"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="7890b-103">Обогатите профиле клијената демографским подацима компаније Experian (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="7890b-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="7890b-104">Experian је глобални лидер у извештавању о потрошачким и пословним кредитима и маркетиншким услугама.</span><span class="sxs-lookup"><span data-stu-id="7890b-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="7890b-105">Помоћу услуга обогаћивања података компаније Experian, можете да изградите дубље разумевање својих клијената обогаћивањем профила клијената демографским подацима као што су величина домаћинства, приход и још много тога.</span><span class="sxs-lookup"><span data-stu-id="7890b-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7890b-106">Предуслови</span><span class="sxs-lookup"><span data-stu-id="7890b-106">Prerequisites</span></span>

<span data-ttu-id="7890b-107">Да бисте конфигурисали Experian, морају да се испуне следећи предуслови:</span><span class="sxs-lookup"><span data-stu-id="7890b-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="7890b-108">Имате активну претплату на Experian.</span><span class="sxs-lookup"><span data-stu-id="7890b-108">You have an active Experian subscription.</span></span> <span data-ttu-id="7890b-109">Да бисте добили претплату, [обратите се компанији Experian](https://www.experian.com/marketing-services/contact) директно.</span><span class="sxs-lookup"><span data-stu-id="7890b-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="7890b-110">[Сазнајте више о Experian обогаћивању података](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="7890b-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="7890b-111">Имате ID корисника, ID странке и број модела за SSH омогућени Secure Transport (ST) налог који је Experian креирао за вас.</span><span class="sxs-lookup"><span data-stu-id="7890b-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="7890b-112">Имате [администраторске](permissions.md#administrator) дозволе у увидима о корисницима.</span><span class="sxs-lookup"><span data-stu-id="7890b-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="7890b-113">Конфигурисање</span><span class="sxs-lookup"><span data-stu-id="7890b-113">Configuration</span></span>

1. <span data-ttu-id="7890b-114">Идите до картице **Подаци** > **Обогаћивање** и изаберите картицу **Откриј**.</span><span class="sxs-lookup"><span data-stu-id="7890b-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="7890b-115">Изаберите **Обогати моје податке** на Experian плочици.</span><span class="sxs-lookup"><span data-stu-id="7890b-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7890b-116">![Experian плочица](media/experian-tile.png "Experian плочица")</span><span class="sxs-lookup"><span data-stu-id="7890b-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="7890b-117">Изаберите **Започните** и унесите ID корисника, ID странке и број модела за ваш Experian Secure Transport налог.</span><span class="sxs-lookup"><span data-stu-id="7890b-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="7890b-118">Прегледајте и дајте свој пристанак за **Приватност података и усаглашеност** тако што ћете изабрати поље за потврду **Слажем се**.</span><span class="sxs-lookup"><span data-stu-id="7890b-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="7890b-119">Потврдите све уносе избором **Примени**.</span><span class="sxs-lookup"><span data-stu-id="7890b-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="7890b-120">Мапирање поља</span><span class="sxs-lookup"><span data-stu-id="7890b-120">Map your fields</span></span>

1. <span data-ttu-id="7890b-121">Изаберите **Додај податке** и изаберите кључне идентификаторе из опција **Име и адреса**, **Е-пошта** или **Телефон** које ћете послати компанији Experian ради решавања идентитета.</span><span class="sxs-lookup"><span data-stu-id="7890b-121">Select **Add data** and choose your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="7890b-122">Више атрибута кључних идентификатора послатих у Experian вероватно даје већу стопу подударања.</span><span class="sxs-lookup"><span data-stu-id="7890b-122">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="7890b-123">Изаберите **Следеће** и мапирајте одговарајуће атрибуте из вашег обједињеног ентитета клијента за изабрана поља кључног идентификатора.</span><span class="sxs-lookup"><span data-stu-id="7890b-123">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="7890b-124">Изаберите **Додај атрибут** да бисте мапирали све додатне атрибуте које бисте желели да пошаљете компанији Experian.</span><span class="sxs-lookup"><span data-stu-id="7890b-124">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="7890b-125">Изаберите **Сачувај** да бисте довршили мапирање поља.</span><span class="sxs-lookup"><span data-stu-id="7890b-125">Select **Save** to complete the field mapping.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7890b-126">![Мапирање поља за Experian](media/experian-field-mapping.png "Мапирање поља за Experian")</span><span class="sxs-lookup"><span data-stu-id="7890b-126">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="7890b-127">Резултати обогаћивања</span><span class="sxs-lookup"><span data-stu-id="7890b-127">Enrichment results</span></span>

<span data-ttu-id="7890b-128">Да бисте започели процес обогаћивања, изаберите **Покрени** са командне траке.</span><span class="sxs-lookup"><span data-stu-id="7890b-128">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="7890b-129">Такође можете пустити да систем аутоматски покреће обогаћивање као део [планираног освежавања](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7890b-129">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7890b-130">Време обраде зависиће од величине ваших података о клијентима и процеса обогаћивања које је за ваш налог подесио Experian.</span><span class="sxs-lookup"><span data-stu-id="7890b-130">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="7890b-131">Након завршетка процеса обогаћивања, податке о новообогаћеним профилима клијената можете прегледати под опцијом **Моја обогаћивања**.</span><span class="sxs-lookup"><span data-stu-id="7890b-131">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="7890b-132">Осим тога, пронаћи ћете време последњег ажурирања и број обогаћених профила.</span><span class="sxs-lookup"><span data-stu-id="7890b-132">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="7890b-133">Детаљном приказу сваког обогаћеног профила можете приступити ако изаберете **Прикажи обогаћене податке**.</span><span class="sxs-lookup"><span data-stu-id="7890b-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7890b-134">Следећи кораци</span><span class="sxs-lookup"><span data-stu-id="7890b-134">Next steps</span></span>

<span data-ttu-id="7890b-135">Надоградите на обогаћеним подацима о клијентима.</span><span class="sxs-lookup"><span data-stu-id="7890b-135">Build on top of your enriched customer data.</span></span> <span data-ttu-id="7890b-136">Креирајте [сегменте](segments.md), [мере](measures.md), па чак и [извезите податке](export-destinations.md) да бисте пружили персонализована искуства својим клијентима.</span><span class="sxs-lookup"><span data-stu-id="7890b-136">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7890b-137">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="7890b-137">Data privacy and compliance</span></span>

<span data-ttu-id="7890b-138">Када омогућите да Dynamics 365 Customer Insights преноси податке у Experian, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="7890b-138">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7890b-139">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Experian испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="7890b-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="7890b-140">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="7890b-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="7890b-141">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони ово обогаћивање како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="7890b-141">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
