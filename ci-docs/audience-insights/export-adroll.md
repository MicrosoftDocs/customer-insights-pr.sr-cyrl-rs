---
title: Извоз Customer Insights података у AdRoll
description: Сазнајте како да конфигуришете везу и извезете у AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dbebc3ee3978ca6ee9d1ad1c15c226479876709f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124383"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="e3bee-103">Извоз сегмената у AdRoll (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="e3bee-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="e3bee-104">Извезите сегменте обједињених профила клијената у AdRoll и користите их за оглашавање.</span><span class="sxs-lookup"><span data-stu-id="e3bee-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="e3bee-105">Предуслови за везу</span><span class="sxs-lookup"><span data-stu-id="e3bee-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="e3bee-106">Имате [AdRoll налог](https://www.adroll.com/) и одговарајуће акредитиве администратора.</span><span class="sxs-lookup"><span data-stu-id="e3bee-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e3bee-107">[Конфигурисали сте сегменте](segments.md) у увидима о корисницима.</span><span class="sxs-lookup"><span data-stu-id="e3bee-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="e3bee-108">Обједињени профили клијената у извезеним сегментима садрже поље које представља адресу е-поште.</span><span class="sxs-lookup"><span data-stu-id="e3bee-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e3bee-109">Позната ограничења</span><span class="sxs-lookup"><span data-stu-id="e3bee-109">Known limitations</span></span>

- <span data-ttu-id="e3bee-110">У услугу AdRoll можете да извезете укупно до 250.000 профила по извозу.</span><span class="sxs-lookup"><span data-stu-id="e3bee-110">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="e3bee-111">У AdRoll не можете да извезете сегменте са мање од 100 профила.</span><span class="sxs-lookup"><span data-stu-id="e3bee-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="e3bee-112">Извоз у AdRoll је ограничен на сегменте.</span><span class="sxs-lookup"><span data-stu-id="e3bee-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="e3bee-113">Извоз до 250.000 профила у AdRoll може да потраје до 10 минута.</span><span class="sxs-lookup"><span data-stu-id="e3bee-113">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="e3bee-114">Број профила које можете да извезете у AdRoll зависи од и ограничен је вашим уговором са компанијом AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e3bee-114">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="e3bee-115">Подешавање везе у услузи AdRoll</span><span class="sxs-lookup"><span data-stu-id="e3bee-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="e3bee-116">Идите на **Администратор** > **Везе**.</span><span class="sxs-lookup"><span data-stu-id="e3bee-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e3bee-117">Изаберите **Додај везу** и бирајте **AdRoll** да бисте конфигурисали везу.</span><span class="sxs-lookup"><span data-stu-id="e3bee-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="e3bee-118">Дајте вези препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="e3bee-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e3bee-119">Име за приказ и врста везе описују ову везу.</span><span class="sxs-lookup"><span data-stu-id="e3bee-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e3bee-120">Препоручујемо да одаберете назив који објашњава сврху и циљ везе.</span><span class="sxs-lookup"><span data-stu-id="e3bee-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e3bee-121">Одаберите ко може да користи ову везу.</span><span class="sxs-lookup"><span data-stu-id="e3bee-121">Choose who can use this connection.</span></span> <span data-ttu-id="e3bee-122">Ако ништа не предузмете, подразумевани ће бити Администратори.</span><span class="sxs-lookup"><span data-stu-id="e3bee-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e3bee-123">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e3bee-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e3bee-124">Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.</span><span class="sxs-lookup"><span data-stu-id="e3bee-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e3bee-125">Изаберите **Повежи се** за иницијализацију везе са услугом AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e3bee-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="e3bee-126">Изаберите **Потврдите идентитет у услузи AdRoll** и наведите своје акредитиве администратора за AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e3bee-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="e3bee-127">Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e3bee-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e3bee-128">Изаберите **Сачувај** да бисте креирали везу.</span><span class="sxs-lookup"><span data-stu-id="e3bee-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e3bee-129">Конфигурисање извоза</span><span class="sxs-lookup"><span data-stu-id="e3bee-129">Configure an export</span></span>

<span data-ttu-id="e3bee-130">Овај извоз можете да конфигуришете ако имате приступ вези ове врсте.</span><span class="sxs-lookup"><span data-stu-id="e3bee-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e3bee-131">За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e3bee-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e3bee-132">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="e3bee-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e3bee-133">Да бисте креирали нови извоз, изаберите **Додај одредиште**.</span><span class="sxs-lookup"><span data-stu-id="e3bee-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e3bee-134">У пољу **Веза за извоз**, одаберите везу из одељка AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e3bee-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="e3bee-135">Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.</span><span class="sxs-lookup"><span data-stu-id="e3bee-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e3bee-136">Унесите свој **ID AdRoll оглашавача** За више информација, погледајте чланак [Профили AdRoll оглашавача](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="e3bee-136">Enter your **AdRoll Advertiser ID** For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="e3bee-137">У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном профилу клијента које представља е-адресу клијента.</span><span class="sxs-lookup"><span data-stu-id="e3bee-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="e3bee-138">То је потребно за извоз сегмената у AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e3bee-138">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="e3bee-139">Изаберите сегменте које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="e3bee-139">Select the segments you want to export.</span></span> <span data-ttu-id="e3bee-140">Изаберите сегмент са најмање 100 чланова.</span><span class="sxs-lookup"><span data-stu-id="e3bee-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="e3bee-141">Не можете извозити мање сегменте.</span><span class="sxs-lookup"><span data-stu-id="e3bee-141">You can't export smaller segments.</span></span> <span data-ttu-id="e3bee-142">Поред тога, максимална величина сегмента за извоз је 250.000 чланова по извозу.</span><span class="sxs-lookup"><span data-stu-id="e3bee-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="e3bee-143">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="e3bee-143">Select **Save**.</span></span>

<span data-ttu-id="e3bee-144">Чување извоза не покреће извоз одмах.</span><span class="sxs-lookup"><span data-stu-id="e3bee-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e3bee-145">Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e3bee-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e3bee-146">Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e3bee-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e3bee-147">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="e3bee-147">Data privacy and compliance</span></span>

<span data-ttu-id="e3bee-148">Када омогућите да Dynamics 365 Customer Insights преноси податке у AdRoll, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="e3bee-148">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e3bee-149">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да AdRoll испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="e3bee-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e3bee-150">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e3bee-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="e3bee-151">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="e3bee-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
