---
title: Извоз Customer Insights података у Constant Contact
description: Сазнајте како да конфигуришете везу и извезете садржај у Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29f4320c798db62609283e3c48f0b47a4f0b982f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124291"
---
# <a name="export-segments-to-constant-contact-preview"></a><span data-ttu-id="e396d-103">Извоз сегмената у Constant Contact (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="e396d-103">Export segments to Constant Contact (preview)</span></span>

<span data-ttu-id="e396d-104">Извезите сегменте обједињених профила клијената у Constant Contact и користите их за маркетиншке активности.</span><span class="sxs-lookup"><span data-stu-id="e396d-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="e396d-105">Предуслови за везу</span><span class="sxs-lookup"><span data-stu-id="e396d-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="e396d-106">Имате [Constant Contact налог](https://www.constantcontact.com/account-home) и одговарајуће акредитиве администратора.</span><span class="sxs-lookup"><span data-stu-id="e396d-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e396d-107">[Конфигурисали сте сегменте](segments.md) у увидима о корисницима.</span><span class="sxs-lookup"><span data-stu-id="e396d-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="e396d-108">Обједињени профили клијената у извезеним сегментима садрже поље које представља адресу е-поште.</span><span class="sxs-lookup"><span data-stu-id="e396d-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e396d-109">Позната ограничења</span><span class="sxs-lookup"><span data-stu-id="e396d-109">Known limitations</span></span>

- <span data-ttu-id="e396d-110">Можете извести до 1 милион профила по извозу у Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="e396d-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="e396d-111">Извоз у Constant Contact ограничен је на сегменте.</span><span class="sxs-lookup"><span data-stu-id="e396d-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="e396d-112">Извоз до 1 милион профила у Constant Contact може потрајати до 1 сата.</span><span class="sxs-lookup"><span data-stu-id="e396d-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="e396d-113">Број профила које можете да извезете у Constant Contact зависи и ограничен је вашим уговором са услугом Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="e396d-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="e396d-114">Подешавање везе са услугом Constant Contact</span><span class="sxs-lookup"><span data-stu-id="e396d-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="e396d-115">Идите на **Администратор** > **Везе**.</span><span class="sxs-lookup"><span data-stu-id="e396d-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e396d-116">Изаберите **Додај везу** и бирајте **Constant Contact** да бисте конфигурисали везу.</span><span class="sxs-lookup"><span data-stu-id="e396d-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="e396d-117">Дајте вези препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="e396d-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e396d-118">Име за приказ и врста везе описују ову везу.</span><span class="sxs-lookup"><span data-stu-id="e396d-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e396d-119">Препоручујемо да одаберете назив који објашњава сврху и циљ везе.</span><span class="sxs-lookup"><span data-stu-id="e396d-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e396d-120">Одаберите ко може да користи ову везу.</span><span class="sxs-lookup"><span data-stu-id="e396d-120">Choose who can use this connection.</span></span> <span data-ttu-id="e396d-121">Ако ништа не предузмете, подразумевани ће бити Администратори.</span><span class="sxs-lookup"><span data-stu-id="e396d-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e396d-122">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e396d-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e396d-123">Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.</span><span class="sxs-lookup"><span data-stu-id="e396d-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e396d-124">Изаберите **Повежите се** да би се иницијализовала веза са услугом Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="e396d-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="e396d-125">Изаберите **Потврдите идентитет помоћу услуге AdRoll** и обезбедите своје администраторске акредитиве за Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="e396d-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="e396d-126">Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e396d-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e396d-127">Изаберите **Сачувај** да бисте креирали везу.</span><span class="sxs-lookup"><span data-stu-id="e396d-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e396d-128">Конфигурисање извоза</span><span class="sxs-lookup"><span data-stu-id="e396d-128">Configure an export</span></span>

<span data-ttu-id="e396d-129">Овај извоз можете да конфигуришете ако имате приступ вези ове врсте.</span><span class="sxs-lookup"><span data-stu-id="e396d-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e396d-130">За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e396d-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e396d-131">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="e396d-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e396d-132">Да бисте креирали нови извоз, изаберите **Додај одредиште**.</span><span class="sxs-lookup"><span data-stu-id="e396d-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e396d-133">У пољу **Веза за извоз**, одаберите везу из одељка Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="e396d-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="e396d-134">Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.</span><span class="sxs-lookup"><span data-stu-id="e396d-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e396d-135">Унесите [**ID Constant Contact листе**](https://app.constantcontact.com/pages/contacts/ui#lists).</span><span class="sxs-lookup"><span data-stu-id="e396d-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="e396d-136">Отворите листу у услузи Constant Contact да бисте пронашли ID листе у URL адреси.</span><span class="sxs-lookup"><span data-stu-id="e396d-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="e396d-137">У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном профилу клијента које представља е-адресу клијента.</span><span class="sxs-lookup"><span data-stu-id="e396d-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="e396d-138">То је потребно да извезете сегменте у Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="e396d-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="e396d-139">По жељи можете да извезете Име и Презиме као додатна поља за стварање персонализованих е-порука.</span><span class="sxs-lookup"><span data-stu-id="e396d-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="e396d-140">Изаберите **Додај атрибут** за мапирање ових поља.</span><span class="sxs-lookup"><span data-stu-id="e396d-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="e396d-141">Изаберите сегменте које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="e396d-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="e396d-142">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="e396d-142">Select **Save**.</span></span>

<span data-ttu-id="e396d-143">Чување извоза не покреће извоз одмах.</span><span class="sxs-lookup"><span data-stu-id="e396d-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e396d-144">Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e396d-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e396d-145">Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e396d-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e396d-146">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="e396d-146">Data privacy and compliance</span></span>

<span data-ttu-id="e396d-147">Када омогућите Dynamics 365 Customer Insights за пренос података у Constant Contact, дозвољавате пренос података изван граница усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="e396d-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e396d-148">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Constant Contact испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="e396d-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e396d-149">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e396d-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="e396d-150">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="e396d-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
