---
title: Обогаћивање путем независног обогаћивања Experian
description: Опште информације о Experian независном обогаћивању.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309838"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="b8594-103">Обогатите профиле клијената демографским подацима из услуге Experian (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="b8594-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="b8594-104">Experian је глобални лидер у извештавању о потрошачким и пословним кредитима и маркетиншким услугама.</span><span class="sxs-lookup"><span data-stu-id="b8594-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="b8594-105">Користећи Experian услуге обогаћивања података, можете да развијете дубље разумевање својих клијената обогаћујући своје профиле клијената демографским подацима као што су величина домаћинства, приход и још много тога.</span><span class="sxs-lookup"><span data-stu-id="b8594-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b8594-106">Предуслови</span><span class="sxs-lookup"><span data-stu-id="b8594-106">Prerequisites</span></span>

<span data-ttu-id="b8594-107">Да бисте конфигурисали Experian, морате испунити следеће предуслове:</span><span class="sxs-lookup"><span data-stu-id="b8594-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="b8594-108">Имате активну претплату на Experian.</span><span class="sxs-lookup"><span data-stu-id="b8594-108">You have an active Experian subscription.</span></span> <span data-ttu-id="b8594-109">Да бисте набавили претплату, [контактирајте Experian](https://www.experian.com/marketing-services/contact) директно.</span><span class="sxs-lookup"><span data-stu-id="b8594-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="b8594-110">[Сазнајте више о Experian обогаћивању података](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="b8594-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="b8594-111">Администратор је већ конфигурисао везу са услугом Experian *или* имате дозволе [администратора](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="b8594-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="b8594-112">Такође су вам потребни ИД корисника, ИД странке и број модела за ваш SSH омогућени налог за безбедни транспорт (ST)који је услуга Experian креирала за вас.</span><span class="sxs-lookup"><span data-stu-id="b8594-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="b8594-113">Подржане земље/региони</span><span class="sxs-lookup"><span data-stu-id="b8594-113">Supported countries/regions</span></span>

<span data-ttu-id="b8594-114">Тренутно подржавамо обогаћивање профила купаца само у Сједињеним Државама.</span><span class="sxs-lookup"><span data-stu-id="b8594-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="b8594-115">Конфигурисање обогаћивања</span><span class="sxs-lookup"><span data-stu-id="b8594-115">Configure the enrichment</span></span>

1. <span data-ttu-id="b8594-116">Идите до картице **Подаци** > **Обогаћивање** и изаберите картицу **Откриј**.</span><span class="sxs-lookup"><span data-stu-id="b8594-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="b8594-117">Изаберите **Обогати моје податке** на плочици Experian.</span><span class="sxs-lookup"><span data-stu-id="b8594-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b8594-118">![Experian плочиц](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="b8594-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="b8594-119">Изаберите [везу](connections.md) са падајуће листе.</span><span class="sxs-lookup"><span data-stu-id="b8594-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="b8594-120">Ако веза није доступна, обратите се администратору.</span><span class="sxs-lookup"><span data-stu-id="b8594-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="b8594-121">Ако сте администратор, везу можете да направите ако изаберете **Додај везу** и бирате Experian са падајуће листе.</span><span class="sxs-lookup"><span data-stu-id="b8594-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="b8594-122">Изаберите **Повежи се за услугом Experian** да бисте потврдили избор везе.</span><span class="sxs-lookup"><span data-stu-id="b8594-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="b8594-123">Изаберите **Следеће** и бирајте **Скуп података о клијенту** који желите да обогатите демографским подацима из услуге Experian.</span><span class="sxs-lookup"><span data-stu-id="b8594-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="b8594-124">Можете изабрати ентитет **Клијент** да бисте обогатили све ваше профиле клијената или изаберите ентитет сегмента да бисте обогатили само профиле клијената садржане у том сегменту.</span><span class="sxs-lookup"><span data-stu-id="b8594-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Снимак екрана приликом одабира скупа података о клијентима.":::

1. <span data-ttu-id="b8594-126">Изаберите **Следеће** и дефинишите који тип поља из ваших обједињених профила треба да користите за тражење одговарајућих демографских података из услуге Experian.</span><span class="sxs-lookup"><span data-stu-id="b8594-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="b8594-127">Обавезно је барем једно од поља **Име и адреса**, **Телефон** или **Е-пошта**.</span><span class="sxs-lookup"><span data-stu-id="b8594-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="b8594-128">За већу прецизност подударања, могу се додати још два поља.</span><span class="sxs-lookup"><span data-stu-id="b8594-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="b8594-129">Овај избор ће утицати на поља за мапирање којима имате приступ у следећем кораку.</span><span class="sxs-lookup"><span data-stu-id="b8594-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="b8594-130">Више атрибута идентификатора кључа послатих услузи Experian повећавају вероватноћу постизања више стопе подударања.</span><span class="sxs-lookup"><span data-stu-id="b8594-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="b8594-131">Изаберите **Следеће** да бисте започели мапирање поља.</span><span class="sxs-lookup"><span data-stu-id="b8594-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="b8594-132">Дефинишите која поља из ваших обједињених профила треба да користите за тражење одговарајућих демографских података из услуге Experian.</span><span class="sxs-lookup"><span data-stu-id="b8594-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="b8594-133">Обавезна поља су означена.</span><span class="sxs-lookup"><span data-stu-id="b8594-133">Required fields are marked.</span></span>

1. <span data-ttu-id="b8594-134">Обезбедите назив за обогаћивање и назив за излазни ентитет.</span><span class="sxs-lookup"><span data-stu-id="b8594-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="b8594-135">Изаберите **Сачувај обогаћивање** након прегледа ваших избора.</span><span class="sxs-lookup"><span data-stu-id="b8594-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="b8594-136">Конфигурисање везе за Experian</span><span class="sxs-lookup"><span data-stu-id="b8594-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="b8594-137">Морате бити администратор да бисте конфигурисали везе.</span><span class="sxs-lookup"><span data-stu-id="b8594-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="b8594-138">Изаберите **Додај везу** када конфигуришете обогаћивање *или* идите на **Администратор** > **Везе** и изаберите **Подесити** на плочици Experian.</span><span class="sxs-lookup"><span data-stu-id="b8594-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="b8594-139">Изаберите **Први кораци**.</span><span class="sxs-lookup"><span data-stu-id="b8594-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="b8594-140">Унесите назив везе у поље **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="b8594-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="b8594-141">Унесите важећи ИД корисника, ИД странке и број модела за свој налог за Experian безбедан транспорт.</span><span class="sxs-lookup"><span data-stu-id="b8594-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="b8594-142">Прегледајте и дајте сагласност за **Приватност података и усклађеност** избором опције **Слажем се**.</span><span class="sxs-lookup"><span data-stu-id="b8594-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="b8594-143">Изаберите **Верификуј** да бисте проверили ваљаност конфигурације.</span><span class="sxs-lookup"><span data-stu-id="b8594-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="b8594-144">По завршетку верификације, изаберите **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="b8594-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Окно за конфигурацију Experian везе.":::

## <a name="enrichment-results"></a><span data-ttu-id="b8594-146">Резултати обогаћивања</span><span class="sxs-lookup"><span data-stu-id="b8594-146">Enrichment results</span></span>

<span data-ttu-id="b8594-147">Да бисте започели процес обогаћивања, изаберите **Покрени** са командне траке.</span><span class="sxs-lookup"><span data-stu-id="b8594-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="b8594-148">Такође можете пустити да систем аутоматски покреће обогаћивање као део [планираног освежавања](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b8594-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b8594-149">Време обраде зависиће од величине ваших података о клијенту и процеса обогаћивања које је за ваш налог подесио Experian.</span><span class="sxs-lookup"><span data-stu-id="b8594-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="b8594-150">Након завршетка процеса обогаћивања, податке о новообогаћеним корисничким профилима можете прегледати под опцијом **Моја обогаћивања**.</span><span class="sxs-lookup"><span data-stu-id="b8594-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="b8594-151">Осим тога, пронаћи ћете време последњег ажурирања и број обогаћених профила.</span><span class="sxs-lookup"><span data-stu-id="b8594-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="b8594-152">Детаљном приказу сваког обогаћеног профила можете приступити ако изаберете **Прикажи обогаћене податке**.</span><span class="sxs-lookup"><span data-stu-id="b8594-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b8594-153">Следећи кораци</span><span class="sxs-lookup"><span data-stu-id="b8594-153">Next steps</span></span>

<span data-ttu-id="b8594-154">Надоградите на обогаћеним подацима о клијентима.</span><span class="sxs-lookup"><span data-stu-id="b8594-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="b8594-155">Креирајте [сегменте](segments.md) и [мере](measures.md), па чак и [извоз података](export-destinations.md) да пружите персонализована искуства својим клијентима.</span><span class="sxs-lookup"><span data-stu-id="b8594-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b8594-156">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="b8594-156">Data privacy and compliance</span></span>

<span data-ttu-id="b8594-157">Када омогућите Dynamics 365 Customer Insights за пренос података у Experian, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="b8594-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b8594-158">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Experian испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="b8594-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b8594-159">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b8594-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b8594-160">Ваш Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони ово обогаћивање како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="b8594-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
