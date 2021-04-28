---
title: Извоз Customer Insights података у RollWorks
description: Сазнајте како да конфигуришете везу и извезете у RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4979f0147dea2270f11342c1bb6b0693f3c24aea
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760628"
---
# <a name="export-segment-lists-to-rollworks-preview"></a><span data-ttu-id="2b291-103">Извоз листи сегмената у RollWorks (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="2b291-103">Export segment lists to RollWorks (preview)</span></span>

<span data-ttu-id="2b291-104">Извезите сегменте обједињених профила клијената у RollWorks и користите их за оглашавање.</span><span class="sxs-lookup"><span data-stu-id="2b291-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="2b291-105">Предуслови за везу</span><span class="sxs-lookup"><span data-stu-id="2b291-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="2b291-106">Имате [RollWorks налог](https://www.rollworks.com/) и одговарајуће акредитиве администратора.</span><span class="sxs-lookup"><span data-stu-id="2b291-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="2b291-107">[Конфигурисали сте сегменте](segments.md) у увидима о корисницима.</span><span class="sxs-lookup"><span data-stu-id="2b291-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="2b291-108">Обједињени профили клијената у извезеним сегментима садрже поље које представља адресу е-поште.</span><span class="sxs-lookup"><span data-stu-id="2b291-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="2b291-109">Позната ограничења</span><span class="sxs-lookup"><span data-stu-id="2b291-109">Known limitations</span></span>

- <span data-ttu-id="2b291-110">Можете извести до 250.000 профила по извозу у RollWorks.</span><span class="sxs-lookup"><span data-stu-id="2b291-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="2b291-111">Не можете да извезете сегменте са мање од 100 профила у RollWorks.</span><span class="sxs-lookup"><span data-stu-id="2b291-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="2b291-112">Извоз у RollWorks ограничен је на сегменте.</span><span class="sxs-lookup"><span data-stu-id="2b291-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="2b291-113">Извоз до 250.000 профила у RollWorks може потрајати до 10 минута.</span><span class="sxs-lookup"><span data-stu-id="2b291-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="2b291-114">Број профила које можете да извезете у RollWorks зависи и ограничен је вашим уговором са услугом RollWorks.</span><span class="sxs-lookup"><span data-stu-id="2b291-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="2b291-115">Подешавање везе са услугом RollWorks</span><span class="sxs-lookup"><span data-stu-id="2b291-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="2b291-116">Идите на **Администратор** > **Везе**.</span><span class="sxs-lookup"><span data-stu-id="2b291-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="2b291-117">Изаберите **Додај везу** и бирајте **RollWorks** да бисте конфигурисали везу.</span><span class="sxs-lookup"><span data-stu-id="2b291-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="2b291-118">Дајте вези препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="2b291-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="2b291-119">Име за приказ и врста везе описују ову везу.</span><span class="sxs-lookup"><span data-stu-id="2b291-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="2b291-120">Препоручујемо да одаберете назив који објашњава сврху и циљ везе.</span><span class="sxs-lookup"><span data-stu-id="2b291-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="2b291-121">Одаберите ко може да користи ову везу.</span><span class="sxs-lookup"><span data-stu-id="2b291-121">Choose who can use this connection.</span></span> <span data-ttu-id="2b291-122">Ако ништа не предузмете, подразумевани ће бити Администратори.</span><span class="sxs-lookup"><span data-stu-id="2b291-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="2b291-123">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="2b291-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="2b291-124">Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.</span><span class="sxs-lookup"><span data-stu-id="2b291-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="2b291-125">Изаберите **Повежите се** да би се иницијализовала веза са услугом RollWorks.</span><span class="sxs-lookup"><span data-stu-id="2b291-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="2b291-126">Изаберите **Потврдите идентитет помоћу услуге RollWorks** и обезбедите своје администраторске акредитиве за RollWorks.</span><span class="sxs-lookup"><span data-stu-id="2b291-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="2b291-127">Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2b291-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="2b291-128">Изаберите **Сачувај** да бисте креирали везу.</span><span class="sxs-lookup"><span data-stu-id="2b291-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="2b291-129">Конфигурисање извоза</span><span class="sxs-lookup"><span data-stu-id="2b291-129">Configure an export</span></span>

<span data-ttu-id="2b291-130">Овај извоз можете да конфигуришете ако имате приступ вези ове врсте.</span><span class="sxs-lookup"><span data-stu-id="2b291-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="2b291-131">За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="2b291-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2b291-132">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="2b291-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2b291-133">Да бисте креирали нови извоз, изаберите **Додај одредиште**.</span><span class="sxs-lookup"><span data-stu-id="2b291-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="2b291-134">У пољу **Веза за извоз**, одаберите везу из одељка RollWorks.</span><span class="sxs-lookup"><span data-stu-id="2b291-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="2b291-135">Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.</span><span class="sxs-lookup"><span data-stu-id="2b291-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="2b291-136">Унесите свој **ID RollWorks оглашавача** [RollWorks оглас](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="2b291-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="2b291-137">У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном профилу клијента које представља е-адресу клијента.</span><span class="sxs-lookup"><span data-stu-id="2b291-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="2b291-138">То је потребно да извезете сегменте у RollWorks.</span><span class="sxs-lookup"><span data-stu-id="2b291-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="2b291-139">Изаберите сегменте које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="2b291-139">Select the segments you want to export.</span></span> <span data-ttu-id="2b291-140">Изаберите сегмент са најмање 100 чланова.</span><span class="sxs-lookup"><span data-stu-id="2b291-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="2b291-141">Не можете извозити мање сегменте.</span><span class="sxs-lookup"><span data-stu-id="2b291-141">You can't export smaller segments.</span></span> <span data-ttu-id="2b291-142">Поред тога, максимална величина сегмента за извоз је 250.000 чланова по извозу.</span><span class="sxs-lookup"><span data-stu-id="2b291-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="2b291-143">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="2b291-143">Select **Save**.</span></span>

<span data-ttu-id="2b291-144">Чување извоза не покреће извоз одмах.</span><span class="sxs-lookup"><span data-stu-id="2b291-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="2b291-145">Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2b291-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2b291-146">Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="2b291-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2b291-147">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="2b291-147">Data privacy and compliance</span></span>

<span data-ttu-id="2b291-148">Када омогућите Dynamics 365 Customer Insights за пренос података у RollWorks, дозвољавате пренос података изван граница усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="2b291-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2b291-149">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да RollWorks испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="2b291-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2b291-150">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2b291-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="2b291-151">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="2b291-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
