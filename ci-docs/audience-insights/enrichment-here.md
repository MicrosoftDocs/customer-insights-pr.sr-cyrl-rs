---
title: Обогаћивање путем независног обогаћивања HERE Technologies
description: Опште информације о HERE Technologies обогаћивању треће стране.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b3c1da0f541efb85b2ca9d87a2e3b97bbfb6ca7f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305312"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="de443-103">Обогаћивање профила клијената уз HERE Technologies (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="de443-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="de443-104">верзија за преглед је компанија за платформу локације која пружа податке и услуге усмерене на локацију.</span><span class="sxs-lookup"><span data-stu-id="de443-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="de443-105">Помоћу услуга обогаћивања података компаније HERE Technologies можете да изградите прецизније разумевање локације својих клијената помоћу нормализације адреса, издвајања географске ширине и дужине и још много тога.</span><span class="sxs-lookup"><span data-stu-id="de443-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="de443-106">Предуслови</span><span class="sxs-lookup"><span data-stu-id="de443-106">Prerequisites</span></span>

<span data-ttu-id="de443-107">Да бисте конфигурисали верзија за преглед обогаћивања, морају бити испуњени следећи предуслови:</span><span class="sxs-lookup"><span data-stu-id="de443-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="de443-108">Морате имати активну претплату за HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="de443-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="de443-109">Да бисте добили претплату, можете [да се региструјете овде](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) или директно [контактирајте HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="de443-109">To get a subscription, you can [sign up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="de443-110">Сазнајте више о HERE Technologies обогаћивању локације.</span><span class="sxs-lookup"><span data-stu-id="de443-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="de443-111">HERE [веза](connections.md) је доступна *или* имате дозволе [администратора](permissions.md#administrator) и HERE Technologies API кључ.</span><span class="sxs-lookup"><span data-stu-id="de443-111">A HERE [connection](connections.md) is available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="de443-112">Конфигурисање обогаћивања</span><span class="sxs-lookup"><span data-stu-id="de443-112">Configure the enrichment</span></span>

1. <span data-ttu-id="de443-113">Идите на **Подаци** > **Обогаћивање**.</span><span class="sxs-lookup"><span data-stu-id="de443-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="de443-114">Изаберите **Обогати моје податке** на плочици HERE Technologies и изаберите **Започни**.</span><span class="sxs-lookup"><span data-stu-id="de443-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="de443-115">![HERE Technologies плочица](media/HERE-tile.png "HERE Technologies плочица")</span><span class="sxs-lookup"><span data-stu-id="de443-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="de443-116">Изаберите [везу](connections.md) са падајуће листе.</span><span class="sxs-lookup"><span data-stu-id="de443-116">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="de443-117">Ако веза није доступна, обратите се администратору.</span><span class="sxs-lookup"><span data-stu-id="de443-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="de443-118">Ако сте администратор, везу можете да направите избором **Додај везу**.</span><span class="sxs-lookup"><span data-stu-id="de443-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="de443-119">Одаберите **HERE Technologies** са падајуће листе.</span><span class="sxs-lookup"><span data-stu-id="de443-119">Choose **HERE Technologies** from the dropdown list.</span></span> 

1. <span data-ttu-id="de443-120">Изаберите **Повежите се са HERE Technologies** да потврдите избор.</span><span class="sxs-lookup"><span data-stu-id="de443-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="de443-121">Изаберите **Следеће** и одаберите **Скуп података клијента** који желите да обогатите са подацима о локацији компаније HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="de443-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="de443-122">Можете изабрати ентитет **Клијент** да бисте обогатили све ваше профиле клијената или изаберите ентитет сегмента да бисте обогатили само профиле клијената садржане у том сегменту.</span><span class="sxs-lookup"><span data-stu-id="de443-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Снимак екрана приликом одабира скупа података о клијентима.":::

1. <span data-ttu-id="de443-124">Одаберите да ли желите да мапирате поља са примарном и/или секундарном адресом.</span><span class="sxs-lookup"><span data-stu-id="de443-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="de443-125">Можете одредити мапирање поља за обе адресе и обогатити профиле за обе адресе засебно.</span><span class="sxs-lookup"><span data-stu-id="de443-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="de443-126">На пример, ако постоје кућна и пословна адреса.</span><span class="sxs-lookup"><span data-stu-id="de443-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="de443-127">Изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="de443-127">Select **Next**.</span></span>

1. <span data-ttu-id="de443-128">Дефинишите која поља из ваших обједињених профила треба користити за подударање података о локацији од компаније HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="de443-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="de443-129">Поља **Улица 1** и **Поштански број** су обавезна за одабрану примарну и/или секундарну адресу.</span><span class="sxs-lookup"><span data-stu-id="de443-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="de443-130">За већу прецизност подударања може се додати више поља.</span><span class="sxs-lookup"><span data-stu-id="de443-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="de443-131">![Страница за конфигурацију HERE Technologies обогаћивања](media/enrichment-HERE-configuration.png "Страница за конфигурацију HERE Technologies обогаћивања")</span><span class="sxs-lookup"><span data-stu-id="de443-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="de443-132">Изаберите **Следеће** да бисте довршили мапирање поља.</span><span class="sxs-lookup"><span data-stu-id="de443-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="de443-133">Наведите назив обогаћивања.</span><span class="sxs-lookup"><span data-stu-id="de443-133">Provide a name for the enrichment.</span></span> 

1. <span data-ttu-id="de443-134">Изаберите **Сачувај обогаћивање** након прегледа ваших избора.</span><span class="sxs-lookup"><span data-stu-id="de443-134">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="de443-135">Конфигуришите везу за HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="de443-135">Configure the connection for HERE Technologies</span></span> 

<span data-ttu-id="de443-136">Морате бити администратор да бисте конфигурисали везе.</span><span class="sxs-lookup"><span data-stu-id="de443-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="de443-137">Изаберите **Додај везу** приликом конфигурисања обогаћивања *или* идите на **Администратор** > **Везе** и изаберите **Подешавање** на плочици HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="de443-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="de443-138">Унесите назив везе у поље **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="de443-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="de443-139">Наведите важећи HERE Technologies API кључ.</span><span class="sxs-lookup"><span data-stu-id="de443-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="de443-140">Прегледајте и дајте сагласност за **Приватност података и усклађеност** избором опције **Слажем се**.</span><span class="sxs-lookup"><span data-stu-id="de443-140">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="de443-141">Изаберите **Верификуј** да бисте проверили ваљаност конфигурације.</span><span class="sxs-lookup"><span data-stu-id="de443-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="de443-142">По завршетку верификације, изаберите **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="de443-142">After completing the verification, select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="de443-143">![Страница за конфигурацију везе за HERE Technologies](media/enrichment-HERE-connection.png "Страница за конфигурацију везе за HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="de443-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="de443-144">Резултати обогаћивања</span><span class="sxs-lookup"><span data-stu-id="de443-144">Enrichment results</span></span>

<span data-ttu-id="de443-145">Да бисте започели процес обогаћивања, изаберите **Покрени** са командне траке.</span><span class="sxs-lookup"><span data-stu-id="de443-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="de443-146">Такође можете пустити да систем аутоматски покреће обогаћивање као део [планираног освежавања](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="de443-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="de443-147">Време обраде зависиће од величине података о клијентима и времена одзива API-ја компаније HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="de443-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="de443-148">Након завршетка процеса обогаћивања, податке о новообогаћеним профилима клијената можете прегледати под опцијом **Моја обогаћивања**.</span><span class="sxs-lookup"><span data-stu-id="de443-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="de443-149">Осим тога, пронаћи ћете време последњег ажурирања и број обогаћених профила.</span><span class="sxs-lookup"><span data-stu-id="de443-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="de443-150">Детаљном приказу сваког обогаћеног профила можете приступити ако изаберете **Прикажи обогаћене податке**.</span><span class="sxs-lookup"><span data-stu-id="de443-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="de443-151">Следећи кораци</span><span class="sxs-lookup"><span data-stu-id="de443-151">Next steps</span></span>

<span data-ttu-id="de443-152">Надоградите на обогаћеним подацима о клијентима.</span><span class="sxs-lookup"><span data-stu-id="de443-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="de443-153">Креирајте [сегменте](segments.md) и [мере](measures.md), па чак и [извоз података](export-destinations.md) да пружите персонализована искуства својим клијентима.</span><span class="sxs-lookup"><span data-stu-id="de443-153">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="de443-154">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="de443-154">Data privacy and compliance</span></span>

<span data-ttu-id="de443-155">Када омогућите да Dynamics 365 Customer Insights преноси податке у HERE Technologies, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="de443-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="de443-156">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да HERE Technologies испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="de443-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="de443-157">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="de443-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="de443-158">Ваш Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони ово обогаћивање како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="de443-158">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
