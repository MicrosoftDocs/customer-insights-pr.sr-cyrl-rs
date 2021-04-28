---
title: Извезите Customer Insights податке у Autopilot
description: Сазнајте како да конфигуришете везу и извезете у Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760161"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="5de6b-103">Извоз сегмената у Autopilot (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="5de6b-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="5de6b-104">Извезите сегменте обједињених профила клијената у Autopilot и користите их за маркетинг путем е-поште у услузи Autopilot.</span><span class="sxs-lookup"><span data-stu-id="5de6b-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="5de6b-105">Предуслови за везу</span><span class="sxs-lookup"><span data-stu-id="5de6b-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="5de6b-106">Имате [Autopilot налог](https://www.autopilothq.com/) и одговарајуће акредитиве администратора.</span><span class="sxs-lookup"><span data-stu-id="5de6b-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="5de6b-107">[Конфигурисали сте сегменте](segments.md) у увидима о корисницима.</span><span class="sxs-lookup"><span data-stu-id="5de6b-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="5de6b-108">Обједињени профили клијената у извезеним сегментима садрже поље које представља адресу е-поште.</span><span class="sxs-lookup"><span data-stu-id="5de6b-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5de6b-109">Позната ограничења</span><span class="sxs-lookup"><span data-stu-id="5de6b-109">Known limitations</span></span>

- <span data-ttu-id="5de6b-110">У услугу Autopilot можете да извезете укупно до 100.000 профила.</span><span class="sxs-lookup"><span data-stu-id="5de6b-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="5de6b-111">Извоз у Autopilot је ограничен на сегменте.</span><span class="sxs-lookup"><span data-stu-id="5de6b-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="5de6b-112">Извоз до 100.000 профила у Autopilot може да потраје до неколико сати.</span><span class="sxs-lookup"><span data-stu-id="5de6b-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="5de6b-113">Број профила које можете да извезете у Autopilot зависи од вашег уговора са компанијом Autopilot и ограничен је њиме.</span><span class="sxs-lookup"><span data-stu-id="5de6b-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="5de6b-114">Подешавање везе са услугом Autopilot</span><span class="sxs-lookup"><span data-stu-id="5de6b-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="5de6b-115">Идите на **Администратор** > **Везе**.</span><span class="sxs-lookup"><span data-stu-id="5de6b-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="5de6b-116">Изаберите **Додај везу** и бирајте **Autopilot** да бисте конфигурисали везу.</span><span class="sxs-lookup"><span data-stu-id="5de6b-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="5de6b-117">Дајте вези препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="5de6b-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="5de6b-118">Име за приказ и врста везе описују ову везу.</span><span class="sxs-lookup"><span data-stu-id="5de6b-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="5de6b-119">Препоручујемо да одаберете назив који објашњава сврху и циљ везе.</span><span class="sxs-lookup"><span data-stu-id="5de6b-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="5de6b-120">Одаберите ко може да користи ову везу.</span><span class="sxs-lookup"><span data-stu-id="5de6b-120">Choose who can use this connection.</span></span> <span data-ttu-id="5de6b-121">Ако ништа не предузмете, подразумевани ће бити Администратори.</span><span class="sxs-lookup"><span data-stu-id="5de6b-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="5de6b-122">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="5de6b-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="5de6b-123">Унесите свој [API кључ за Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="5de6b-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="5de6b-124">Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.</span><span class="sxs-lookup"><span data-stu-id="5de6b-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="5de6b-125">Изаберите **Повежи се** за иницијализацију везе са услугом Autopilot.</span><span class="sxs-lookup"><span data-stu-id="5de6b-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="5de6b-126">Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5de6b-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="5de6b-127">Изаберите **Сачувај** да бисте креирали везу.</span><span class="sxs-lookup"><span data-stu-id="5de6b-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="5de6b-128">Конфигурисање извоза</span><span class="sxs-lookup"><span data-stu-id="5de6b-128">Configure an export</span></span>

<span data-ttu-id="5de6b-129">Овај извоз можете да конфигуришете ако имате приступ вези ове врсте.</span><span class="sxs-lookup"><span data-stu-id="5de6b-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="5de6b-130">За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="5de6b-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5de6b-131">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="5de6b-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5de6b-132">Да бисте креирали нови извоз, изаберите **Додај одредиште**.</span><span class="sxs-lookup"><span data-stu-id="5de6b-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="5de6b-133">У пољу **Веза за извоз**, одаберите везу из одељка Autopilot.</span><span class="sxs-lookup"><span data-stu-id="5de6b-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="5de6b-134">Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.</span><span class="sxs-lookup"><span data-stu-id="5de6b-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="5de6b-135">У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном профилу клијента које представља е-адресу клијента.</span><span class="sxs-lookup"><span data-stu-id="5de6b-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="5de6b-136">Поновите исте кораке за друга опционална поља као што су **Име**, **Презиме**.</span><span class="sxs-lookup"><span data-stu-id="5de6b-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="5de6b-137">Изаберите сегменте које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="5de6b-137">Select the segments you want to export.</span></span> <span data-ttu-id="5de6b-138">Изричито **препоручујемо да не извозите укупно више од 100.000 профила клијената** у Autopilot.</span><span class="sxs-lookup"><span data-stu-id="5de6b-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="5de6b-139">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="5de6b-139">Select **Save**.</span></span>

<span data-ttu-id="5de6b-140">Чување извоза не покреће извоз одмах.</span><span class="sxs-lookup"><span data-stu-id="5de6b-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="5de6b-141">Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5de6b-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5de6b-142">Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="5de6b-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5de6b-143">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="5de6b-143">Data privacy and compliance</span></span>

<span data-ttu-id="5de6b-144">Када омогућите да Dynamics 365 Customer Insights преноси податке у Autopilot, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="5de6b-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5de6b-145">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Autopilot испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="5de6b-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="5de6b-146">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="5de6b-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="5de6b-147">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="5de6b-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
