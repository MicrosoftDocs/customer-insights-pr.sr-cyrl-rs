---
title: Извоз Customer Insights података у Campaign Monitor
description: Сазнајте како да конфигуришете везу и извезете садржај у Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 091a3197dc0c19ff78f0419fb4e88868e0f78359
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124199"
---
# <a name="export-segments-to-campaign-monitor-preview"></a><span data-ttu-id="0bdb3-103">Извоз сегмената у Campaign Monitor (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="0bdb3-103">Export segments to Campaign Monitor (preview)</span></span>

<span data-ttu-id="0bdb3-104">Извезите сегменте обједињених профила клијената у Campaign Monitor и користите их за маркетиншке активности.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0bdb3-105">Предуслови</span><span class="sxs-lookup"><span data-stu-id="0bdb3-105">Prerequisites</span></span>

-   <span data-ttu-id="0bdb3-106">Имате [Campaign Monitor налог](https://www.campaignmonitor.com/) и одговарајуће акредитиве администратора.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0bdb3-107">[Конфигурисали сте сегменте](segments.md) у увидима о корисницима.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="0bdb3-108">Обједињени профили клијената у извезеним сегментима садрже поље које представља адресу е-поште.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0bdb3-109">Позната ограничења</span><span class="sxs-lookup"><span data-stu-id="0bdb3-109">Known limitations</span></span>

- <span data-ttu-id="0bdb3-110">Можете извести до 1 милион профила по извозу у Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="0bdb3-111">Извоз у Campaign Monitor ограничен је на сегменте.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="0bdb3-112">Извоз до 1 милион профила у Campaign Monitor може потрајати до 20 минута.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="0bdb3-113">Број профила које можете да извезете у Campaign Monitor зависи и ограничен је вашим уговором са услугом Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="0bdb3-114">Подешавање везе са услугом Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="0bdb3-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="0bdb3-115">Идите на **Администратор** > **Везе**.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0bdb3-116">Изаберите **Додај везу** и бирајте **Campaign Monitor** да бисте конфигурисали везу.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="0bdb3-117">Дајте вези препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0bdb3-118">Име за приказ и врста везе описују ову везу.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0bdb3-119">Препоручујемо да одаберете назив који објашњава сврху и циљ везе.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0bdb3-120">Одаберите ко може да користи ову везу.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-120">Choose who can use this connection.</span></span> <span data-ttu-id="0bdb3-121">Ако ништа не предузмете, подразумевани ће бити Администратори.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="0bdb3-122">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0bdb3-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0bdb3-123">Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0bdb3-124">Изаберите **Повежите се** да би се иницијализовала веза са услугом Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="0bdb3-125">Изаберите **Потврдите идентитет помоћу услуге Campaign Monitor** и обезбедите своје администраторске акредитиве за Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="0bdb3-126">Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="0bdb3-127">Изаберите **Сачувај** да бисте креирали везу.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="0bdb3-128">Конфигурисање извоза</span><span class="sxs-lookup"><span data-stu-id="0bdb3-128">Configure an export</span></span>

<span data-ttu-id="0bdb3-129">Овај извоз можете да конфигуришете ако имате приступ вези ове врсте.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0bdb3-130">За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0bdb3-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0bdb3-131">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0bdb3-132">Да бисте креирали нови извоз, изаберите **Додај одредиште**.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0bdb3-133">У пољу **Веза за извоз**, одаберите везу из одељка Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="0bdb3-134">Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="0bdb3-135">Унесите [**ID Campaign Monitor листе**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="0bdb3-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="0bdb3-136">Прво [генеришите API кључ](https://www.campaignmonitor.com/api/getting-started/) у одељку **Подешавања налога** у услузи Campaign Monitor да бисте видели ID API листе.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="0bdb3-137">У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном профилу клијента које представља е-адресу клијента.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="0bdb3-138">То је потребно да извезете сегменте у Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="0bdb3-139">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-139">Select **Save**.</span></span>

<span data-ttu-id="0bdb3-140">Чување извоза не покреће извоз одмах.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0bdb3-141">Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0bdb3-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0bdb3-142">Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0bdb3-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0bdb3-143">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="0bdb3-143">Data privacy and compliance</span></span>

<span data-ttu-id="0bdb3-144">Када омогућите Dynamics 365 Customer Insights за пренос података у Campaign Monitor, дозвољавате пренос података изван граница усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0bdb3-145">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Campaign Monitor испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0bdb3-146">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0bdb3-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="0bdb3-147">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="0bdb3-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
