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
ms.openlocfilehash: 67bfa23d56b26ae592efa4d7197713664bb02623
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304852"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="64fbb-103">Извоз сегмената у AdRoll (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="64fbb-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="64fbb-104">Извезите сегменте обједињених профила клијената у AdRoll и користите их за оглашавање.</span><span class="sxs-lookup"><span data-stu-id="64fbb-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="64fbb-105">Предуслови за везу</span><span class="sxs-lookup"><span data-stu-id="64fbb-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="64fbb-106">Имате [AdRoll налог](https://www.adroll.com/) и одговарајуће акредитиве администратора.</span><span class="sxs-lookup"><span data-stu-id="64fbb-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="64fbb-107">[Конфигурисали сте сегменте](segments.md) у увидима о корисницима.</span><span class="sxs-lookup"><span data-stu-id="64fbb-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="64fbb-108">Обједињени кориснички профили у извезеним сегментима садрже поље које представља адресу е-поште.</span><span class="sxs-lookup"><span data-stu-id="64fbb-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="64fbb-109">Позната ограничења</span><span class="sxs-lookup"><span data-stu-id="64fbb-109">Known limitations</span></span>

- <span data-ttu-id="64fbb-110">Одједном можете да извезете највише 250.000 профила у AdRoll.</span><span class="sxs-lookup"><span data-stu-id="64fbb-110">You can export up to 250,000 profiles at a time to AdRoll.</span></span>
- <span data-ttu-id="64fbb-111">У AdRoll не можете да извезете сегменте са мање од 100 профила.</span><span class="sxs-lookup"><span data-stu-id="64fbb-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="64fbb-112">Извоз у AdRoll је ограничен на сегменте.</span><span class="sxs-lookup"><span data-stu-id="64fbb-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="64fbb-113">Извоз до 250.000 профила у AdRoll може да потраје до 10 минута.</span><span class="sxs-lookup"><span data-stu-id="64fbb-113">Exporting up to 250,000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="64fbb-114">Број профила које можете да извезете у AdRoll зависи од вашег уговора са услугом AdRoll.</span><span class="sxs-lookup"><span data-stu-id="64fbb-114">The number of profiles that you can export to AdRoll is dependent on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="64fbb-115">Подешавање везе у услузи AdRoll</span><span class="sxs-lookup"><span data-stu-id="64fbb-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="64fbb-116">Идите на **Администратор** > **Везе**.</span><span class="sxs-lookup"><span data-stu-id="64fbb-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="64fbb-117">Изаберите **Додај везу** и бирајте **AdRoll** да бисте конфигурисали везу.</span><span class="sxs-lookup"><span data-stu-id="64fbb-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="64fbb-118">Дајте вези препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="64fbb-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="64fbb-119">Име за приказ и врста везе описују ову везу.</span><span class="sxs-lookup"><span data-stu-id="64fbb-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="64fbb-120">Препоручујемо да одаберете назив који објашњава сврху и циљ везе.</span><span class="sxs-lookup"><span data-stu-id="64fbb-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="64fbb-121">Одаберите ко може да користи ову везу.</span><span class="sxs-lookup"><span data-stu-id="64fbb-121">Choose who can use this connection.</span></span> <span data-ttu-id="64fbb-122">Ако ништа не предузмете, подразумевани ће бити Администратори.</span><span class="sxs-lookup"><span data-stu-id="64fbb-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="64fbb-123">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="64fbb-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="64fbb-124">Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.</span><span class="sxs-lookup"><span data-stu-id="64fbb-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="64fbb-125">Изаберите **Повежи се** за иницијализацију везе са услугом AdRoll.</span><span class="sxs-lookup"><span data-stu-id="64fbb-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="64fbb-126">Изаберите **Потврдите идентитет у услузи AdRoll** и наведите своје акредитиве администратора за AdRoll.</span><span class="sxs-lookup"><span data-stu-id="64fbb-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="64fbb-127">Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="64fbb-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="64fbb-128">Изаберите **Сачувај** да бисте креирали везу.</span><span class="sxs-lookup"><span data-stu-id="64fbb-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="64fbb-129">Конфигурисање извоза</span><span class="sxs-lookup"><span data-stu-id="64fbb-129">Configure an export</span></span>

<span data-ttu-id="64fbb-130">Овај извоз можете да конфигуришете ако имате приступ вези ове врсте.</span><span class="sxs-lookup"><span data-stu-id="64fbb-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="64fbb-131">За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="64fbb-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="64fbb-132">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="64fbb-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="64fbb-133">Да бисте креирали нови извоз, изаберите **Додај одредиште**.</span><span class="sxs-lookup"><span data-stu-id="64fbb-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="64fbb-134">У пољу **Веза за извоз**, одаберите везу из одељка AdRoll.</span><span class="sxs-lookup"><span data-stu-id="64fbb-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="64fbb-135">Ако не видите назив овог одељка, тада вам нису доступне везе овог типа.</span><span class="sxs-lookup"><span data-stu-id="64fbb-135">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="64fbb-136">Унесите свој **ID AdRoll оглашавача**.</span><span class="sxs-lookup"><span data-stu-id="64fbb-136">Enter your **AdRoll Advertiser ID**.</span></span> <span data-ttu-id="64fbb-137">За више информација, погледајте чланак [Профили AdRoll оглашавача](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="64fbb-137">For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="64fbb-138">У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном корисничком профилу које представља е-адресу клијента.</span><span class="sxs-lookup"><span data-stu-id="64fbb-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="64fbb-139">То је потребно за извоз сегмената у AdRoll.</span><span class="sxs-lookup"><span data-stu-id="64fbb-139">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="64fbb-140">Изаберите сегменте које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="64fbb-140">Select the segments you want to export.</span></span> <span data-ttu-id="64fbb-141">Изаберите сегмент са најмање 100 чланова.</span><span class="sxs-lookup"><span data-stu-id="64fbb-141">Select a segment with a least 100 members.</span></span> <span data-ttu-id="64fbb-142">Не можете извозити мање сегменте.</span><span class="sxs-lookup"><span data-stu-id="64fbb-142">You can't export smaller segments.</span></span> <span data-ttu-id="64fbb-143">Поред тога, максимална величина сегмента за извоз је 250.000 чланова по извозу.</span><span class="sxs-lookup"><span data-stu-id="64fbb-143">Additionally the maximum size of a segment to export is 250,000 members per export.</span></span> 

1. <span data-ttu-id="64fbb-144">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="64fbb-144">Select **Save**.</span></span>

<span data-ttu-id="64fbb-145">Чување извоза не покреће извоз одмах.</span><span class="sxs-lookup"><span data-stu-id="64fbb-145">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="64fbb-146">Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="64fbb-146">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="64fbb-147">Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="64fbb-147">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="64fbb-148">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="64fbb-148">Data privacy and compliance</span></span>

<span data-ttu-id="64fbb-149">Када омогућите да Dynamics 365 Customer Insights преноси податке у AdRoll, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="64fbb-149">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="64fbb-150">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да AdRoll испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="64fbb-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="64fbb-151">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="64fbb-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="64fbb-152">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="64fbb-152">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
