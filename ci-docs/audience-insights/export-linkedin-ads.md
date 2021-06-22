---
title: Извоз Customer Insights података у LinkedIn Ads
description: Сазнајте како да конфигуришете везу и извозите у LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124548"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="ab29b-103">Извоз сегмената у LinkedIn Ads (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="ab29b-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="ab29b-104">Извезите сегменте обједињених профила клијената у LinkedIn Ads да бисте креирали подударну циљну групу.</span><span class="sxs-lookup"><span data-stu-id="ab29b-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="ab29b-105">Користите подударну циљну групу за циљање предузећа и циљање контаката.</span><span class="sxs-lookup"><span data-stu-id="ab29b-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ab29b-106">Предуслови</span><span class="sxs-lookup"><span data-stu-id="ab29b-106">Prerequisites</span></span>

-   <span data-ttu-id="ab29b-107">Имате [LinkedIn Campaign Manager налог](https://business.linkedin.com/marketing-solutions/ads) и одговарајуће акредитиве администратора.</span><span class="sxs-lookup"><span data-stu-id="ab29b-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ab29b-108">[Конфигурисали сте сегменте](segments.md) у увидима о корисницима.</span><span class="sxs-lookup"><span data-stu-id="ab29b-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ab29b-109">Кориснички профили у извезеним сегментима садрже поље са адресом е-поште.</span><span class="sxs-lookup"><span data-stu-id="ab29b-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ab29b-110">Позната ограничења</span><span class="sxs-lookup"><span data-stu-id="ab29b-110">Known limitations</span></span>

- <span data-ttu-id="ab29b-111">Можете извести до 100.000 профила по извозу у LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="ab29b-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="ab29b-112">Извоз у LinkedIn Ads ограничен је на сегменте.</span><span class="sxs-lookup"><span data-stu-id="ab29b-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="ab29b-113">Извоз до 100.000 профила у LinkedIn Ads може потрајати до 10 минута.</span><span class="sxs-lookup"><span data-stu-id="ab29b-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="ab29b-114">Подесите везу са услугом LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="ab29b-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="ab29b-115">У увидима у циљне групе, идите на **Администратор** > **Везе**.</span><span class="sxs-lookup"><span data-stu-id="ab29b-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ab29b-116">Изаберите **Додај везу** и бирајте **LinkedIn Ads** да бисте конфигурисали везу.</span><span class="sxs-lookup"><span data-stu-id="ab29b-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="ab29b-117">Дајте вези препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="ab29b-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ab29b-118">Име за приказ и врста везе описују ову везу.</span><span class="sxs-lookup"><span data-stu-id="ab29b-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ab29b-119">Препоручујемо да одаберете назив који објашњава сврху и циљ везе.</span><span class="sxs-lookup"><span data-stu-id="ab29b-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ab29b-120">Одаберите ко може да користи ову везу.</span><span class="sxs-lookup"><span data-stu-id="ab29b-120">Choose who can use this connection.</span></span> <span data-ttu-id="ab29b-121">Ако ништа не предузмете, подразумевају се Администратори.</span><span class="sxs-lookup"><span data-stu-id="ab29b-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="ab29b-122">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ab29b-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ab29b-123">Наведите свој [ID LinkedIn Campaign Manager налога](https://www.linkedin.com/help/lms/answer/a424270).</span><span class="sxs-lookup"><span data-stu-id="ab29b-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="ab29b-124">Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.</span><span class="sxs-lookup"><span data-stu-id="ab29b-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ab29b-125">Изаберите **Повежите се** да би се иницијализовала веза са услугом Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="ab29b-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="ab29b-126">Изаберите **Потврдите идентитет помоћу услуге LinkedIn** и обезбедите своје администраторске акредитиве за LinkedIn Campaign Manager.</span><span class="sxs-lookup"><span data-stu-id="ab29b-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="ab29b-127">Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ab29b-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ab29b-128">Изаберите **Сачувај** да бисте креирали везу.</span><span class="sxs-lookup"><span data-stu-id="ab29b-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ab29b-129">Конфигурисање извоза</span><span class="sxs-lookup"><span data-stu-id="ab29b-129">Configure an export</span></span>

<span data-ttu-id="ab29b-130">Извоз можете да конфигуришете ако имате приступ вези ове врсте.</span><span class="sxs-lookup"><span data-stu-id="ab29b-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="ab29b-131">За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ab29b-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ab29b-132">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="ab29b-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ab29b-133">Да бисте креирали нови извоз, изаберите **Додај одредиште**.</span><span class="sxs-lookup"><span data-stu-id="ab29b-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ab29b-134">У пољу **Веза за извоз**, одаберите везу из одељка LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="ab29b-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="ab29b-135">Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.</span><span class="sxs-lookup"><span data-stu-id="ab29b-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ab29b-136">Одаберите да ли желите да извезете податке да обавите [контакт циљање](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) или [циљање компаније](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) у услузи LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="ab29b-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="ab29b-137">У одељку **Подударање података** изаберите поље у вашем обједињеном профилу клијента које представља е-адресу клијента.</span><span class="sxs-lookup"><span data-stu-id="ab29b-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ab29b-138">Потребно је да извезете сегменте у LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="ab29b-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="ab29b-139">Изаберите сегменте које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="ab29b-139">Select the segments you want to export.</span></span> <span data-ttu-id="ab29b-140">Публика која се подудара у услузи LinkedIn Campaign Manager аутоматски ће се креирати са називом сегмената које сте изабрали за извоз.</span><span class="sxs-lookup"><span data-stu-id="ab29b-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="ab29b-141">Сваки сегмент ће резултирати засебном подударном циљном групом.</span><span class="sxs-lookup"><span data-stu-id="ab29b-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="ab29b-142">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="ab29b-142">Select **Save**.</span></span>

<span data-ttu-id="ab29b-143">Чување извоза не покреће извоз одмах.</span><span class="sxs-lookup"><span data-stu-id="ab29b-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ab29b-144">Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ab29b-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ab29b-145">Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ab29b-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ab29b-146">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="ab29b-146">Data privacy and compliance</span></span>

<span data-ttu-id="ab29b-147">Када омогућите Dynamics 365 Customer Insights за пренос података у LinkedIn Ads, дозвољавате пренос података изван граница усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="ab29b-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ab29b-148">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да LinkedIn Ads испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="ab29b-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="ab29b-149">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ab29b-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="ab29b-150">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="ab29b-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
