---
title: Обогаћивање профила предузећа независним Leadspace-ом за обогаћивање
description: Опште информације о Leadspace обогаћивању треће стране.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305220"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="fb042-103">Обогаћивање профила предузећа уз Leadspace (преглед)</span><span class="sxs-lookup"><span data-stu-id="fb042-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="fb042-104">Leadspace је компанија за науку о подацима која обезбеђује B2B платформу за податке о клијентима.</span><span class="sxs-lookup"><span data-stu-id="fb042-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="fb042-105">Омогућује клијентима са обједињеним профилима клијената за компаније да обогаћују своје податке.</span><span class="sxs-lookup"><span data-stu-id="fb042-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="fb042-106">Обогаћивања обухватају више атрибута као што су величина предузећа, локација, делатност и још много тога.</span><span class="sxs-lookup"><span data-stu-id="fb042-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fb042-107">Предуслови</span><span class="sxs-lookup"><span data-stu-id="fb042-107">Prerequisites</span></span>

<span data-ttu-id="fb042-108">Да бисте конфигурисали Leadspace, морате да се испуните следеће предуслове:</span><span class="sxs-lookup"><span data-stu-id="fb042-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="fb042-109">Имате активну Leadspace лиценцу.</span><span class="sxs-lookup"><span data-stu-id="fb042-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="fb042-110">Имате [обједињене профиле клијената](customer-profiles.md) за компаније.</span><span class="sxs-lookup"><span data-stu-id="fb042-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="fb042-111">Администратор је већ конфигурисао Leadspace везу или имате дозволе [администратора](permissions.md#administrator) и „вечити кључ“ (који се зове **Leadspace токен**).</span><span class="sxs-lookup"><span data-stu-id="fb042-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="fb042-112">Контактирајте [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) директно да бисте сазнали детаље о њиховом производу.</span><span class="sxs-lookup"><span data-stu-id="fb042-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="fb042-113">Конфигурисање обогаћивања</span><span class="sxs-lookup"><span data-stu-id="fb042-113">Configure the enrichment</span></span>

1. <span data-ttu-id="fb042-114">У увидима о корисницима идите на **Подаци** > **Обогаћивање**.</span><span class="sxs-lookup"><span data-stu-id="fb042-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="fb042-115">Изаберите **Обогати моје податке** на плочици Leadspace и изаберите **Започни**.</span><span class="sxs-lookup"><span data-stu-id="fb042-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Снимак екрана Leadspace плочице.":::

1. <span data-ttu-id="fb042-117">Изаберите [везу](connections.md) са падајуће листе.</span><span class="sxs-lookup"><span data-stu-id="fb042-117">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="fb042-118">Ако веза није доступна, обратите се администратору.</span><span class="sxs-lookup"><span data-stu-id="fb042-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="fb042-119">Ако сте администратор, везу можете креирати избором **Додај везу** и бирањем опције **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="fb042-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="fb042-120">Изаберите **Повежите се са услугом Leadspace** да бисте потврдили избор везе.</span><span class="sxs-lookup"><span data-stu-id="fb042-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="fb042-121">Изаберите **Следеће** и бирајте **Скуп података клијента** који желите да обогатите подацима предузећа из услуге Leadspace.</span><span class="sxs-lookup"><span data-stu-id="fb042-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="fb042-122">Можете изабрати ентитет **Клијент** да бисте обогатили све ваше профиле клијената или изаберите ентитет сегмента да бисте обогатили само профиле клијената садржане у том сегменту.</span><span class="sxs-lookup"><span data-stu-id="fb042-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Снимак екрана приликом одабира скупа података о клијентима.":::

1. <span data-ttu-id="fb042-124">Изаберите **Следеће** и дефинишите која поља из ваших обједињених профила се користе за подударање података о предузећу из услуге Leadspace.</span><span class="sxs-lookup"><span data-stu-id="fb042-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="fb042-125">Поље **Име компаније** је обавезно.</span><span class="sxs-lookup"><span data-stu-id="fb042-125">The **Name of company** field is required.</span></span> <span data-ttu-id="fb042-126">За већу прецизност подударања, до два друга поља, **Веб-локација компаније** и **Локација компаније**, могу се додати.</span><span class="sxs-lookup"><span data-stu-id="fb042-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Окно за мапирање поља Leadspace.":::

1. <span data-ttu-id="fb042-128">Изаберите **Следеће** да бисте довршили мапирање поља.</span><span class="sxs-lookup"><span data-stu-id="fb042-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="fb042-129">Наведите име за обогаћивање и изаберите **Сачувај обогаћивање** након прегледа вашег избора.</span><span class="sxs-lookup"><span data-stu-id="fb042-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="fb042-130">Конфигуришите везу за Leadspace</span><span class="sxs-lookup"><span data-stu-id="fb042-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="fb042-131">Морате бити администратор да бисте конфигурисали везе.</span><span class="sxs-lookup"><span data-stu-id="fb042-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="fb042-132">Изаберите **Додај везу** приликом конфигурисања обогаћивања *или* идите на **Администратор** > **Везе** и изаберите **Подешавање** на плочици Leadspace.</span><span class="sxs-lookup"><span data-stu-id="fb042-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="fb042-133">Изаберите **Први кораци**.</span><span class="sxs-lookup"><span data-stu-id="fb042-133">Select **Get Started**.</span></span> 

1. <span data-ttu-id="fb042-134">Унесите назив везе у поље **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="fb042-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="fb042-135">Наведите важећи токен за Leadspace.</span><span class="sxs-lookup"><span data-stu-id="fb042-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="fb042-136">Прегледајте и дајте сагласност за **Приватност података и усклађеност** избором опције **Слажем се**.</span><span class="sxs-lookup"><span data-stu-id="fb042-136">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="fb042-137">Изаберите **Верификуј** да бисте проверили ваљаност конфигурације.</span><span class="sxs-lookup"><span data-stu-id="fb042-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="fb042-138">По завршетку верификације, изаберите **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="fb042-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Страница за конфигурацију везе за Leadspace.":::

## <a name="enrichment-results"></a><span data-ttu-id="fb042-140">Резултати обогаћивања</span><span class="sxs-lookup"><span data-stu-id="fb042-140">Enrichment results</span></span>

<span data-ttu-id="fb042-141">Након освежавања обогаћивања, можете прегледати ново обогаћене податке компаније у делу [Моја обогаћења](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="fb042-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="fb042-142">Можете пронаћи време последњег ажурирања и број обогаћених профила.</span><span class="sxs-lookup"><span data-stu-id="fb042-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="fb042-143">Детаљном приказу сваког обогаћеног профила можете приступити ако изаберете **Прикажи обогаћене податке**.</span><span class="sxs-lookup"><span data-stu-id="fb042-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="fb042-144">Више информација потражите у чланку [Leadspace API-ји](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="fb042-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="fb042-145">Следећи кораци</span><span class="sxs-lookup"><span data-stu-id="fb042-145">Next steps</span></span>

<span data-ttu-id="fb042-146">Надоградите на обогаћеним подацима о клијентима.</span><span class="sxs-lookup"><span data-stu-id="fb042-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="fb042-147">Креирајте [сегменте](segments.md) и [мере](measures.md), па чак и [извоз података](export-destinations.md) да пружите персонализована искуства својим клијентима.</span><span class="sxs-lookup"><span data-stu-id="fb042-147">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="fb042-148">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="fb042-148">Data privacy and compliance</span></span>

<span data-ttu-id="fb042-149">Када омогућите да Dynamics 365 Customer Insights преноси податке у Leadspace, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="fb042-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="fb042-150">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Leadspace испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="fb042-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="fb042-151">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="fb042-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="fb042-152">Ваш Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони ово обогаћивање како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="fb042-152">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
