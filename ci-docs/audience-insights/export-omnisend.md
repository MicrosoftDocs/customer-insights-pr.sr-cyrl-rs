---
title: Извоз Customer Insights података у Omnisend
description: Сазнајте како да конфигуришете везу и извозите у Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124547"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="ec12b-103">Извоз сегмената у Omnisend (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="ec12b-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="ec12b-104">Извезите сегменте обједињених профила клијената у Omnisend и користите их за маркетиншке активности.</span><span class="sxs-lookup"><span data-stu-id="ec12b-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ec12b-105">Предуслови</span><span class="sxs-lookup"><span data-stu-id="ec12b-105">Prerequisites</span></span>

-   <span data-ttu-id="ec12b-106">Имате [Omnisend налог](https://www.omnisend.com/) и одговарајуће акредитиве администратора.</span><span class="sxs-lookup"><span data-stu-id="ec12b-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ec12b-107">[Конфигурисали сте сегменте](segments.md) у увидима о корисницима.</span><span class="sxs-lookup"><span data-stu-id="ec12b-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ec12b-108">Обједињени профили клијената у извезеним сегментима садрже поље које представља адресу е-поште.</span><span class="sxs-lookup"><span data-stu-id="ec12b-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ec12b-109">Позната ограничења</span><span class="sxs-lookup"><span data-stu-id="ec12b-109">Known limitations</span></span>

- <span data-ttu-id="ec12b-110">Можете извести до 1 милион профила по извозу у Omnisend, а то може потрајати до 4 сата.</span><span class="sxs-lookup"><span data-stu-id="ec12b-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="ec12b-111">Извоз у Omnisend ограничен је на сегменте.</span><span class="sxs-lookup"><span data-stu-id="ec12b-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="ec12b-112">Број профила које можете да извезете у Omnisend зависи од вашег уговора са услугом Omnisend.</span><span class="sxs-lookup"><span data-stu-id="ec12b-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="ec12b-113">Подешавање везе у услузи Omnisend</span><span class="sxs-lookup"><span data-stu-id="ec12b-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="ec12b-114">Идите на **Администратор** > **Везе**.</span><span class="sxs-lookup"><span data-stu-id="ec12b-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ec12b-115">Изаберите **Додај везу** и бирајте **Omnisend** да бисте конфигурисали везу.</span><span class="sxs-lookup"><span data-stu-id="ec12b-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="ec12b-116">Дајте вези препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="ec12b-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ec12b-117">Име за приказ и врста везе описују ову везу.</span><span class="sxs-lookup"><span data-stu-id="ec12b-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ec12b-118">Препоручујемо да одаберете назив који објашњава сврху и циљ везе.</span><span class="sxs-lookup"><span data-stu-id="ec12b-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ec12b-119">Одаберите ко може да користи ову везу.</span><span class="sxs-lookup"><span data-stu-id="ec12b-119">Choose who can use this connection.</span></span> <span data-ttu-id="ec12b-120">Подразумевано су то само администратори.</span><span class="sxs-lookup"><span data-stu-id="ec12b-120">By default it's only administrators.</span></span> <span data-ttu-id="ec12b-121">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ec12b-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ec12b-122">Унесите свој [API кључ за Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span><span class="sxs-lookup"><span data-stu-id="ec12b-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="ec12b-123">Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.</span><span class="sxs-lookup"><span data-stu-id="ec12b-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ec12b-124">Изаберите **Повежите се** да би се иницијализовала веза са услугом Omnisend.</span><span class="sxs-lookup"><span data-stu-id="ec12b-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="ec12b-125">Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ec12b-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ec12b-126">Изаберите **Сачувај** да бисте креирали везу.</span><span class="sxs-lookup"><span data-stu-id="ec12b-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ec12b-127">Конфигурисање извоза</span><span class="sxs-lookup"><span data-stu-id="ec12b-127">Configure an export</span></span>

<span data-ttu-id="ec12b-128">Овај извоз можете да конфигуришете ако имате приступ вези ове врсте.</span><span class="sxs-lookup"><span data-stu-id="ec12b-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ec12b-129">За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ec12b-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ec12b-130">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="ec12b-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ec12b-131">Да бисте креирали нови извоз, изаберите **Додај одредиште**.</span><span class="sxs-lookup"><span data-stu-id="ec12b-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ec12b-132">У пољу **Веза за извоз**, одаберите везу из одељка Omnisend.</span><span class="sxs-lookup"><span data-stu-id="ec12b-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="ec12b-133">Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.</span><span class="sxs-lookup"><span data-stu-id="ec12b-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ec12b-134">У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном корисничком профилу које представља е-адресу клијента.</span><span class="sxs-lookup"><span data-stu-id="ec12b-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ec12b-135">Потребно је да извезете сегменте у Omnisend.</span><span class="sxs-lookup"><span data-stu-id="ec12b-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="ec12b-136">По жељи можете да извезете поља Име, Презиме, Адреса, Земља/регион, Држава, Град и Поштански број да бисте креирали персонализованије е-поруке.</span><span class="sxs-lookup"><span data-stu-id="ec12b-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="ec12b-137">Изаберите **Додај атрибут** за мапирање ових поља.</span><span class="sxs-lookup"><span data-stu-id="ec12b-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="ec12b-138">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="ec12b-138">Select **Save**.</span></span>

<span data-ttu-id="ec12b-139">Чување извоза не покреће извоз одмах.</span><span class="sxs-lookup"><span data-stu-id="ec12b-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ec12b-140">Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ec12b-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ec12b-141">Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ec12b-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ec12b-142">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="ec12b-142">Data privacy and compliance</span></span>

<span data-ttu-id="ec12b-143">Када омогућите Dynamics 365 Customer Insights за пренос података у Omnisend, дозвољавате пренос података изван граница усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="ec12b-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ec12b-144">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Omnisend испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="ec12b-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ec12b-145">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ec12b-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="ec12b-146">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="ec12b-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
