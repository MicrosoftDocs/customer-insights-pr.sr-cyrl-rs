---
title: Извоз Customer Insights података у Snapchat
description: Сазнајте како да конфигуришете везу и извезете у Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d3dae7f0fef1fc3792c90c8ac0d3b037f5c0923d
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760625"
---
# <a name="export-segment-lists-to-snapchat-preview"></a><span data-ttu-id="d70fa-103">Извоз листи сегмената у Snapchat (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="d70fa-103">Export segment lists to Snapchat (preview)</span></span>

<span data-ttu-id="d70fa-104">Извезите сегменте обједињених профила клијената у Snapchat и користите их за оглашавање.</span><span class="sxs-lookup"><span data-stu-id="d70fa-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="d70fa-105">Предуслови за везу</span><span class="sxs-lookup"><span data-stu-id="d70fa-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="d70fa-106">Имате [Snapchat Business налог](https://business.snapchat.com/), [Snapchat Ads налог](https://ads.snapchat.com/) и одговарајуће акредитиве администратора.</span><span class="sxs-lookup"><span data-stu-id="d70fa-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d70fa-107">[Конфигурисали сте сегменте](segments.md) у увидима о корисницима.</span><span class="sxs-lookup"><span data-stu-id="d70fa-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d70fa-108">Обједињени профили клијената у извезеним сегментима садрже поље које представља адресу е-поште.</span><span class="sxs-lookup"><span data-stu-id="d70fa-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d70fa-109">Позната ограничења</span><span class="sxs-lookup"><span data-stu-id="d70fa-109">Known limitations</span></span>

- <span data-ttu-id="d70fa-110">Извоз у Snapchat ограничен је на сегменте.</span><span class="sxs-lookup"><span data-stu-id="d70fa-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="d70fa-111">Извоз до 1 милион профила у Snapchat може потрајати до 15 минута.</span><span class="sxs-lookup"><span data-stu-id="d70fa-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="d70fa-112">Подешавање везе у услузи Snapchat</span><span class="sxs-lookup"><span data-stu-id="d70fa-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="d70fa-113">Идите на **Администратор** > **Везе**.</span><span class="sxs-lookup"><span data-stu-id="d70fa-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d70fa-114">Изаберите **Додај везу** и бирајте **Snapchat** да бисте конфигурисали везу.</span><span class="sxs-lookup"><span data-stu-id="d70fa-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="d70fa-115">Дајте вези препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="d70fa-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d70fa-116">Име за приказ и врста везе описују ову везу.</span><span class="sxs-lookup"><span data-stu-id="d70fa-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d70fa-117">Препоручујемо да одаберете назив који објашњава сврху и циљ везе.</span><span class="sxs-lookup"><span data-stu-id="d70fa-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d70fa-118">Одаберите ко може да користи ову везу.</span><span class="sxs-lookup"><span data-stu-id="d70fa-118">Choose who can use this connection.</span></span> <span data-ttu-id="d70fa-119">Ако ништа не предузмете, подразумевани ће бити Администратори.</span><span class="sxs-lookup"><span data-stu-id="d70fa-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d70fa-120">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d70fa-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d70fa-121">Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.</span><span class="sxs-lookup"><span data-stu-id="d70fa-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d70fa-122">Изаберите **Повежите се** да би се иницијализовала веза са услугом Snapchat.</span><span class="sxs-lookup"><span data-stu-id="d70fa-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="d70fa-123">Изаберите **Потврдите идентитет помоћу услуге Snapchat** и обезбедите своје администраторске акредитиве за Snapchat.</span><span class="sxs-lookup"><span data-stu-id="d70fa-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="d70fa-124">Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d70fa-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d70fa-125">Изаберите **Сачувај** да бисте креирали везу.</span><span class="sxs-lookup"><span data-stu-id="d70fa-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d70fa-126">Конфигурисање извоза</span><span class="sxs-lookup"><span data-stu-id="d70fa-126">Configure an export</span></span>

<span data-ttu-id="d70fa-127">Овај извоз можете да конфигуришете ако имате приступ вези ове врсте.</span><span class="sxs-lookup"><span data-stu-id="d70fa-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d70fa-128">За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d70fa-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d70fa-129">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="d70fa-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d70fa-130">Да бисте креирали нови извоз, изаберите **Додај одредиште**.</span><span class="sxs-lookup"><span data-stu-id="d70fa-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d70fa-131">У пољу **Веза за извоз**, одаберите везу из одељка Snapchat.</span><span class="sxs-lookup"><span data-stu-id="d70fa-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="d70fa-132">Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.</span><span class="sxs-lookup"><span data-stu-id="d70fa-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d70fa-133">Унесите [**ID циљне групе за Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="d70fa-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="d70fa-134">У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном профилу клијента које представља е-адресу клијента.</span><span class="sxs-lookup"><span data-stu-id="d70fa-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="d70fa-135">То је потребно да извезете сегменте у Snapchat.</span><span class="sxs-lookup"><span data-stu-id="d70fa-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="d70fa-136">Изаберите сегменте које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="d70fa-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="d70fa-137">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="d70fa-137">Select **Save**.</span></span>

<span data-ttu-id="d70fa-138">Чување извоза не покреће извоз одмах.</span><span class="sxs-lookup"><span data-stu-id="d70fa-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d70fa-139">Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d70fa-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d70fa-140">Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d70fa-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d70fa-141">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="d70fa-141">Data privacy and compliance</span></span>

<span data-ttu-id="d70fa-142">Када омогућите Dynamics 365 Customer Insights за пренос података у Snapchat, дозвољавате пренос података изван граница усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="d70fa-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d70fa-143">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Snapchat испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="d70fa-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d70fa-144">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d70fa-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="d70fa-145">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="d70fa-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
