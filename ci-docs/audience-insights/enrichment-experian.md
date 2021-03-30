---
title: Обогаћивање помоћу обогаћивања треће стране Experian
description: Опште информације о Experian обогаћивању треће стране.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4d4723e8f793ee857c4f5204a42be8338c71d4c3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597805"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="6945c-103">Обогатите профиле клијената демографским подацима компаније Experian (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="6945c-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="6945c-104">Experian је глобални лидер у извештавању о потрошачким и пословним кредитима и маркетиншким услугама.</span><span class="sxs-lookup"><span data-stu-id="6945c-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="6945c-105">Помоћу услуга обогаћивања података компаније Experian, можете да изградите дубље разумевање својих клијената обогаћивањем профила клијената демографским подацима као што су величина домаћинства, приход и још много тога.</span><span class="sxs-lookup"><span data-stu-id="6945c-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6945c-106">Предуслови</span><span class="sxs-lookup"><span data-stu-id="6945c-106">Prerequisites</span></span>

<span data-ttu-id="6945c-107">Да бисте конфигурисали Experian, морају да се испуне следећи предуслови:</span><span class="sxs-lookup"><span data-stu-id="6945c-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="6945c-108">Имате активну претплату на Experian.</span><span class="sxs-lookup"><span data-stu-id="6945c-108">You have an active Experian subscription.</span></span> <span data-ttu-id="6945c-109">Да бисте добили претплату, [обратите се компанији Experian](https://www.experian.com/marketing-services/contact) директно.</span><span class="sxs-lookup"><span data-stu-id="6945c-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="6945c-110">[Сазнајте више о Experian обогаћивању података](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="6945c-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="6945c-111">Имате ID корисника, ID странке и број модела за SSH омогућени Secure Transport (ST) налог који је Experian креирао за вас.</span><span class="sxs-lookup"><span data-stu-id="6945c-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="6945c-112">Имате [администраторске](permissions.md#administrator) дозволе у увидима о корисницима.</span><span class="sxs-lookup"><span data-stu-id="6945c-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="6945c-113">Конфигурисање</span><span class="sxs-lookup"><span data-stu-id="6945c-113">Configuration</span></span>

1. <span data-ttu-id="6945c-114">Идите до картице **Подаци** > **Обогаћивање** и изаберите картицу **Откриј**.</span><span class="sxs-lookup"><span data-stu-id="6945c-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="6945c-115">Изаберите **Обогати моје податке** на Experian плочици.</span><span class="sxs-lookup"><span data-stu-id="6945c-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6945c-116">![Experian плочица](media/experian-tile.png "Experian плочица")</span><span class="sxs-lookup"><span data-stu-id="6945c-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="6945c-117">Изаберите **Започните** и унесите ID корисника, ID странке и број модела за ваш Experian Secure Transport налог.</span><span class="sxs-lookup"><span data-stu-id="6945c-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="6945c-118">Прегледајте и дајте свој пристанак за **Приватност података и усаглашеност** тако што ћете изабрати поље за потврду **Слажем се**.</span><span class="sxs-lookup"><span data-stu-id="6945c-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="6945c-119">Потврдите све уносе избором **Примени**.</span><span class="sxs-lookup"><span data-stu-id="6945c-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="6945c-120">Мапирање поља</span><span class="sxs-lookup"><span data-stu-id="6945c-120">Map your fields</span></span>

1.  <span data-ttu-id="6945c-121">Изаберите **Додај податке** и изаберите **Скуп података о клијентима** који желите да обогатите демографским подацима компаније Experian.</span><span class="sxs-lookup"><span data-stu-id="6945c-121">Select **Add data** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="6945c-122">Можете изабрати ентитет **Клијент** да бисте обогатили све ваше профиле клијената или изаберите ентитет сегмента да бисте обогатили само профиле клијената садржане у том сегменту.</span><span class="sxs-lookup"><span data-stu-id="6945c-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="6945c-123">Изаберите своје кључне идентификаторе из поља **Име и адреса**, **Е-адреса** или **Телефон** које ћете послати компанији Experian ради решавања идентитета.</span><span class="sxs-lookup"><span data-stu-id="6945c-123">Select your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="6945c-124">Више атрибута кључних идентификатора послатих у Experian вероватно даје већу стопу подударања.</span><span class="sxs-lookup"><span data-stu-id="6945c-124">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="6945c-125">Изаберите **Следеће** и мапирајте одговарајуће атрибуте из вашег обједињеног ентитета клијента за изабрана поља кључног идентификатора.</span><span class="sxs-lookup"><span data-stu-id="6945c-125">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="6945c-126">Изаберите **Додај атрибут** да бисте мапирали све додатне атрибуте које бисте желели да пошаљете компанији Experian.</span><span class="sxs-lookup"><span data-stu-id="6945c-126">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="6945c-127">Изаберите **Сачувај** да бисте довршили мапирање поља.</span><span class="sxs-lookup"><span data-stu-id="6945c-127">Select **Save** to complete the field mapping.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6945c-128">![Мапирање поља за Experian](media/experian-field-mapping.png "Мапирање поља за Experian")</span><span class="sxs-lookup"><span data-stu-id="6945c-128">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="6945c-129">Резултати обогаћивања</span><span class="sxs-lookup"><span data-stu-id="6945c-129">Enrichment results</span></span>

<span data-ttu-id="6945c-130">Да бисте започели процес обогаћивања, изаберите **Покрени** са командне траке.</span><span class="sxs-lookup"><span data-stu-id="6945c-130">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="6945c-131">Такође можете пустити да систем аутоматски покреће обогаћивање као део [планираног освежавања](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6945c-131">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6945c-132">Време обраде зависиће од величине ваших података о клијентима и процеса обогаћивања које је за ваш налог подесио Experian.</span><span class="sxs-lookup"><span data-stu-id="6945c-132">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="6945c-133">Након завршетка процеса обогаћивања, податке о новообогаћеним профилима клијената можете прегледати под опцијом **Моја обогаћивања**.</span><span class="sxs-lookup"><span data-stu-id="6945c-133">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="6945c-134">Осим тога, пронаћи ћете време последњег ажурирања и број обогаћених профила.</span><span class="sxs-lookup"><span data-stu-id="6945c-134">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="6945c-135">Детаљном приказу сваког обогаћеног профила можете приступити ако изаберете **Прикажи обогаћене податке**.</span><span class="sxs-lookup"><span data-stu-id="6945c-135">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6945c-136">Следећи кораци</span><span class="sxs-lookup"><span data-stu-id="6945c-136">Next steps</span></span>

<span data-ttu-id="6945c-137">Надоградите на обогаћеним подацима о клијентима.</span><span class="sxs-lookup"><span data-stu-id="6945c-137">Build on top of your enriched customer data.</span></span> <span data-ttu-id="6945c-138">Креирајте [сегменте](segments.md), [мере](measures.md), па чак и [извезите податке](export-destinations.md) да бисте пружили персонализована искуства својим клијентима.</span><span class="sxs-lookup"><span data-stu-id="6945c-138">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6945c-139">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="6945c-139">Data privacy and compliance</span></span>

<span data-ttu-id="6945c-140">Када омогућите да Dynamics 365 Customer Insights преноси податке у Experian, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="6945c-140">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6945c-141">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Experian испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="6945c-141">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="6945c-142">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6945c-142">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="6945c-143">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони ово обогаћивање како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="6945c-143">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]