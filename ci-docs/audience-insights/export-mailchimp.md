---
title: Извезите Customer Insights податке у Mailchimp
description: Сазнајте како да конфигуришете везу и извезете у Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b94a8e8b6bb867ca04a64007d592b22fbd700618
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759896"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a><span data-ttu-id="dae85-103">Извоз листи сегмената у Mailchimp (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="dae85-103">Export segment lists to Mailchimp (preview)</span></span>

<span data-ttu-id="dae85-104">Извезите сегменте обједињених профила клијената у Mailchimp да бисте креирали билтене и кампање е-поште.</span><span class="sxs-lookup"><span data-stu-id="dae85-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="dae85-105">Предуслови за везу</span><span class="sxs-lookup"><span data-stu-id="dae85-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="dae85-106">Имате [Mailchimp налог](https://mailchimp.com/) и одговарајуће акредитиве администратора.</span><span class="sxs-lookup"><span data-stu-id="dae85-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="dae85-107">Постоји постојећа публика у Mailchimp-у и одговарајући ID-ови.</span><span class="sxs-lookup"><span data-stu-id="dae85-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="dae85-108">За више информација погледајте [Mailchimp корисници](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="dae85-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="dae85-109">Имате [конфигурисане сегменте](segments.md)</span><span class="sxs-lookup"><span data-stu-id="dae85-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="dae85-110">Обједињени профили клијената у извезеним сегментима садрже поље које представља адресу е-поште.</span><span class="sxs-lookup"><span data-stu-id="dae85-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="dae85-111">Позната ограничења</span><span class="sxs-lookup"><span data-stu-id="dae85-111">Known limitations</span></span>

- <span data-ttu-id="dae85-112">До 1 милион профила по извозу у услузи Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="dae85-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="dae85-113">Извоз у Mailchimp је ограничен на сегменте.</span><span class="sxs-lookup"><span data-stu-id="dae85-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="dae85-114">Извоз сегмената са 1 милион профила може трајати до три сата.</span><span class="sxs-lookup"><span data-stu-id="dae85-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="dae85-115">Број профила које можете да извезете у Mailchimp зависи од и ограничен је вашим уговором са компанијом Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="dae85-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="dae85-116">Подешавање везе са услугом Mailchimp</span><span class="sxs-lookup"><span data-stu-id="dae85-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="dae85-117">Идите на **Администратор** > **Везе**.</span><span class="sxs-lookup"><span data-stu-id="dae85-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="dae85-118">Изаберите **Додај везу** и бирајте **Autopilot** да бисте конфигурисали везу.</span><span class="sxs-lookup"><span data-stu-id="dae85-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="dae85-119">Дајте вези препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="dae85-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="dae85-120">Име за приказ и врста везе описују ову везу.</span><span class="sxs-lookup"><span data-stu-id="dae85-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="dae85-121">Препоручујемо да одаберете назив који објашњава сврху и циљ везе.</span><span class="sxs-lookup"><span data-stu-id="dae85-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="dae85-122">Одаберите ко може да користи ову везу.</span><span class="sxs-lookup"><span data-stu-id="dae85-122">Choose who can use this connection.</span></span> <span data-ttu-id="dae85-123">Ако ништа не предузмете, подразумевани ће бити Администратори.</span><span class="sxs-lookup"><span data-stu-id="dae85-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="dae85-124">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="dae85-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="dae85-125">Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.</span><span class="sxs-lookup"><span data-stu-id="dae85-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="dae85-126">Изаберите **Повежите се** да би се иницијализовала веза са услугом Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="dae85-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="dae85-127">Изаберите **Потврдите идентитет у Mailchimp-у** и наведите акредитиве за Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="dae85-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="dae85-128">Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="dae85-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="dae85-129">Изаберите **Сачувај** да бисте креирали везу.</span><span class="sxs-lookup"><span data-stu-id="dae85-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="dae85-130">Конфигурисање конектора</span><span class="sxs-lookup"><span data-stu-id="dae85-130">Configure the connector</span></span>

<span data-ttu-id="dae85-131">Овај извоз можете да конфигуришете ако имате приступ вези ове врсте.</span><span class="sxs-lookup"><span data-stu-id="dae85-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="dae85-132">За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="dae85-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="dae85-133">Идите на **Подаци**> **Извози**.</span><span class="sxs-lookup"><span data-stu-id="dae85-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="dae85-134">Да бисте креирали нови извоз, изаберите **Додај одредиште**.</span><span class="sxs-lookup"><span data-stu-id="dae85-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="dae85-135">У пољу **Веза за извоз**, одаберите везу из одељка Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="dae85-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="dae85-136">Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.</span><span class="sxs-lookup"><span data-stu-id="dae85-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="dae85-137">Унесите **[ID циљне групе за Mailchimp](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="dae85-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="dae85-138">У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном профилу клијента које представља е-адресу клијента.</span><span class="sxs-lookup"><span data-stu-id="dae85-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="dae85-139">Опционално, можете да извезете **Име** и **Презиме** да бисте креирали персонализованије е-поруке.</span><span class="sxs-lookup"><span data-stu-id="dae85-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="dae85-140">Изаберите **Додај атрибут** за мапирање ових поља.</span><span class="sxs-lookup"><span data-stu-id="dae85-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="dae85-141">Изаберите сегменте које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="dae85-141">Select the segments you want to export.</span></span> <span data-ttu-id="dae85-142">У услузи Mailchimp можете укупно извести до 1 милион корисничких профила.</span><span class="sxs-lookup"><span data-stu-id="dae85-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="dae85-143">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="dae85-143">Select **Save**.</span></span>

<span data-ttu-id="dae85-144">Чување извоза не покреће извоз одмах.</span><span class="sxs-lookup"><span data-stu-id="dae85-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="dae85-145">Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dae85-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="dae85-146">Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="dae85-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="dae85-147">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="dae85-147">Data privacy and compliance</span></span>

<span data-ttu-id="dae85-148">Када омогућите да Dynamics 365 Customer Insights преноси податке у Mailchimp, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="dae85-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="dae85-149">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Mailchimp испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="dae85-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="dae85-150">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="dae85-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="dae85-151">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="dae85-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
