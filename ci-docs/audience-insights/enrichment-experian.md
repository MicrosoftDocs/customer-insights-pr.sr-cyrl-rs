---
title: Обогаћивање помоћу обогаћивања треће стране Experian
description: Опште информације о Experian обогаћивању треће стране.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896391"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="44ba5-103">Обогатите профиле клијената демографским подацима компаније Experian (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="44ba5-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="44ba5-104">Experian је глобални лидер у извештавању о потрошачким и пословним кредитима и маркетиншким услугама.</span><span class="sxs-lookup"><span data-stu-id="44ba5-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="44ba5-105">Помоћу услуга обогаћивања података компаније Experian, можете да изградите дубље разумевање својих клијената обогаћивањем профила клијената демографским подацима као што су величина домаћинства, приход и још много тога.</span><span class="sxs-lookup"><span data-stu-id="44ba5-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="44ba5-106">Предуслови</span><span class="sxs-lookup"><span data-stu-id="44ba5-106">Prerequisites</span></span>

<span data-ttu-id="44ba5-107">Да бисте конфигурисали Experian, морају да се испуне следећи предуслови:</span><span class="sxs-lookup"><span data-stu-id="44ba5-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="44ba5-108">Имате активну претплату на Experian.</span><span class="sxs-lookup"><span data-stu-id="44ba5-108">You have an active Experian subscription.</span></span> <span data-ttu-id="44ba5-109">Да бисте добили претплату, [обратите се компанији Experian](https://www.experian.com/marketing-services/contact) директно.</span><span class="sxs-lookup"><span data-stu-id="44ba5-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="44ba5-110">[Сазнајте више о Experian обогаћивању података](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="44ba5-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="44ba5-111">Администратор је већ конфигурисао Experian везу *или* имате дозволе [администратора](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="44ba5-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="44ba5-112">Такође су вам потребни ID корисника, ID странке и број модела за ваш налог за безбедни транспорт (ST) који омогућава SSH и који је Experian креирао за вас.</span><span class="sxs-lookup"><span data-stu-id="44ba5-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="44ba5-113">Конфигурисање обогаћивања</span><span class="sxs-lookup"><span data-stu-id="44ba5-113">Configure the enrichment</span></span>

1. <span data-ttu-id="44ba5-114">Идите до картице **Подаци** > **Обогаћивање** и изаберите картицу **Откриј**.</span><span class="sxs-lookup"><span data-stu-id="44ba5-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="44ba5-115">Изаберите **Обогати моје податке** на Experian плочици.</span><span class="sxs-lookup"><span data-stu-id="44ba5-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="44ba5-116">![Experian плочица](media/experian-tile.png "Experian плочица")</span><span class="sxs-lookup"><span data-stu-id="44ba5-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="44ba5-117">Изаберите [везу](connections.md) из падајуће листе.</span><span class="sxs-lookup"><span data-stu-id="44ba5-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="44ba5-118">Ако веза није доступна, обратите се администратору.</span><span class="sxs-lookup"><span data-stu-id="44ba5-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="44ba5-119">Ако сте администратор, везу можете да направите ако изаберете **Додај везу** и бирате Experian из падајућег менија.</span><span class="sxs-lookup"><span data-stu-id="44ba5-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="44ba5-120">Изаберите **Повежите се са услугом Experian** да потврдите избор везе.</span><span class="sxs-lookup"><span data-stu-id="44ba5-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="44ba5-121">Изаберите **Следеће** и одаберите **Скуп података клијента** који желите да обогатите демографским подацима услуге Experian.</span><span class="sxs-lookup"><span data-stu-id="44ba5-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="44ba5-122">Можете изабрати ентитет **Клијент** да бисте обогатили све ваше профиле клијената или изаберите ентитет сегмента да бисте обогатили само профиле клијената садржане у том сегменту.</span><span class="sxs-lookup"><span data-stu-id="44ba5-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Снимак екрана приликом одабира скупа података о клијентима.":::

1. <span data-ttu-id="44ba5-124">Изаберите **Следеће** и дефинишите који тип поља из ваших обједињених профила треба користити за тражење одговарајућих демографских података из услуге Experian.</span><span class="sxs-lookup"><span data-stu-id="44ba5-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="44ba5-125">Обавезно је барем једно од поља **Име и адреса**, **Телефон** или **Е-пошта**.</span><span class="sxs-lookup"><span data-stu-id="44ba5-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="44ba5-126">За већу прецизност подударања, могу се додати још два поља.</span><span class="sxs-lookup"><span data-stu-id="44ba5-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="44ba5-127">Овај избор ће утицати на поља за мапирање којима имате приступ у следећем кораку.</span><span class="sxs-lookup"><span data-stu-id="44ba5-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="44ba5-128">Више атрибута кључних идентификатора послатих у Experian вероватно даје већу стопу подударања.</span><span class="sxs-lookup"><span data-stu-id="44ba5-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="44ba5-129">Изаберите **Следеће** да бисте започели мапирање поља.</span><span class="sxs-lookup"><span data-stu-id="44ba5-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="44ba5-130">Дефинишите који тип поља из ваших обједињених профила треба користити за тражење одговарајућих демографских података из услуге Experian.</span><span class="sxs-lookup"><span data-stu-id="44ba5-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="44ba5-131">Обавезна поља су означена.</span><span class="sxs-lookup"><span data-stu-id="44ba5-131">Required fields are marked.</span></span>

1. <span data-ttu-id="44ba5-132">Обезбедите назив за обогаћивање и назив за излазни ентитет.</span><span class="sxs-lookup"><span data-stu-id="44ba5-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="44ba5-133">Изаберите **Сачувај обогаћивање** након прегледа ваших избора.</span><span class="sxs-lookup"><span data-stu-id="44ba5-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="44ba5-134">Конфигуришите везу за Experian</span><span class="sxs-lookup"><span data-stu-id="44ba5-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="44ba5-135">Морате бити администратор да бисте конфигурисали везе.</span><span class="sxs-lookup"><span data-stu-id="44ba5-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="44ba5-136">Изаберите **Додај везу** приликом конфигурисања обогаћивања *или* идите на **Администратор** > **Везе** и изаберите **Подешавање** на плочици Experian.</span><span class="sxs-lookup"><span data-stu-id="44ba5-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="44ba5-137">Изаберите **Први кораци**.</span><span class="sxs-lookup"><span data-stu-id="44ba5-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="44ba5-138">Унесите назив везе у поље **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="44ba5-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="44ba5-139">Унесите важећи ID корисника, ID странке и број модела за свој налог за Experian безбедни транспорт.</span><span class="sxs-lookup"><span data-stu-id="44ba5-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="44ba5-140">Прегледајте и дајте свој пристанак за **Приватност података и усаглашеност** тако што ћете изабрати поље за потврду **Слажем се**</span><span class="sxs-lookup"><span data-stu-id="44ba5-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="44ba5-141">Изаберите **Верификуј** да бисте проверили ваљаност конфигурације.</span><span class="sxs-lookup"><span data-stu-id="44ba5-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="44ba5-142">По завршетку верификације, изаберите **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="44ba5-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Окно за конфигурацију везе за Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="44ba5-144">Резултати обогаћивања</span><span class="sxs-lookup"><span data-stu-id="44ba5-144">Enrichment results</span></span>

<span data-ttu-id="44ba5-145">Да бисте започели процес обогаћивања, изаберите **Покрени** са командне траке.</span><span class="sxs-lookup"><span data-stu-id="44ba5-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="44ba5-146">Такође можете пустити да систем аутоматски покреће обогаћивање као део [планираног освежавања](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="44ba5-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="44ba5-147">Време обраде зависиће од величине ваших података о клијентима и процеса обогаћивања које је за ваш налог подесио Experian.</span><span class="sxs-lookup"><span data-stu-id="44ba5-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="44ba5-148">Након завршетка процеса обогаћивања, податке о новообогаћеним профилима клијената можете прегледати под опцијом **Моја обогаћивања**.</span><span class="sxs-lookup"><span data-stu-id="44ba5-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="44ba5-149">Осим тога, пронаћи ћете време последњег ажурирања и број обогаћених профила.</span><span class="sxs-lookup"><span data-stu-id="44ba5-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="44ba5-150">Детаљном приказу сваког обогаћеног профила можете приступити ако изаберете **Прикажи обогаћене податке**.</span><span class="sxs-lookup"><span data-stu-id="44ba5-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="44ba5-151">Следећи кораци</span><span class="sxs-lookup"><span data-stu-id="44ba5-151">Next steps</span></span>

<span data-ttu-id="44ba5-152">Надоградите на обогаћеним подацима о клијентима.</span><span class="sxs-lookup"><span data-stu-id="44ba5-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="44ba5-153">Креирајте [сегменте](segments.md), [мере](measures.md), па чак и [извезите податке](export-destinations.md) да бисте пружили персонализована искуства својим клијентима.</span><span class="sxs-lookup"><span data-stu-id="44ba5-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="44ba5-154">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="44ba5-154">Data privacy and compliance</span></span>

<span data-ttu-id="44ba5-155">Када омогућите да Dynamics 365 Customer Insights преноси податке у Experian, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="44ba5-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="44ba5-156">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Experian испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="44ba5-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="44ba5-157">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="44ba5-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="44ba5-158">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони ово обогаћивање како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="44ba5-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
