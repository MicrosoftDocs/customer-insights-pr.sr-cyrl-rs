---
title: Извоз Customer Insights података у Microsoft Advertising
description: Сазнајте како да конфигуришете везу и извезете садржај у Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124546"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="f7e09-103">Извоз сегмената у Microsoft Advertising (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="f7e09-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="f7e09-104">Извезите Customer Insights сегменте у Microsoft Advertising да бисте креирали циљне групе за подударање клијената.</span><span class="sxs-lookup"><span data-stu-id="f7e09-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="f7e09-105">Користите ове циљне групе за своје огласне кампање.</span><span class="sxs-lookup"><span data-stu-id="f7e09-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f7e09-106">Предуслови</span><span class="sxs-lookup"><span data-stu-id="f7e09-106">Prerequisites</span></span>

-   <span data-ttu-id="f7e09-107">Имате [Microsoft Advertising налог](https://ads.microsoft.com/) и одговарајуће акредитиве администратора.</span><span class="sxs-lookup"><span data-stu-id="f7e09-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f7e09-108">Прихватили сте услове коришћења за подударање клијената.</span><span class="sxs-lookup"><span data-stu-id="f7e09-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="f7e09-109">[Конфигурисани сегменти](segments.md) у увидима у циљну групу.</span><span class="sxs-lookup"><span data-stu-id="f7e09-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="f7e09-110">Обједињени кориснички профили у извезеним сегментима садрже поље са адресом е-поште.</span><span class="sxs-lookup"><span data-stu-id="f7e09-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f7e09-111">Позната ограничења</span><span class="sxs-lookup"><span data-stu-id="f7e09-111">Known limitations</span></span>

- <span data-ttu-id="f7e09-112">Можете извести до 500.000 профила по извозу у Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="f7e09-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="f7e09-113">Извоз у Microsoft Advertising ограничен је на сегменте.</span><span class="sxs-lookup"><span data-stu-id="f7e09-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="f7e09-114">Извоз до 500.000 профила у Microsoft Advertising може потрајати до 10 минута.</span><span class="sxs-lookup"><span data-stu-id="f7e09-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="f7e09-115">Подешавање везе са услугом Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="f7e09-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="f7e09-116">Идите на **Администратор** > **Везе**.</span><span class="sxs-lookup"><span data-stu-id="f7e09-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f7e09-117">Изаберите **Додај везу** и бирајте **Microsoft Advertising** да бисте конфигурисали везу.</span><span class="sxs-lookup"><span data-stu-id="f7e09-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="f7e09-118">Дајте вези препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="f7e09-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f7e09-119">Име за приказ и врста везе описују ову везу.</span><span class="sxs-lookup"><span data-stu-id="f7e09-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f7e09-120">Препоручујемо да одаберете назив који објашњава сврху и циљ везе.</span><span class="sxs-lookup"><span data-stu-id="f7e09-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f7e09-121">Одаберите ко може да користи ову везу.</span><span class="sxs-lookup"><span data-stu-id="f7e09-121">Choose who can use this connection.</span></span> <span data-ttu-id="f7e09-122">Подразумевано су администратори.</span><span class="sxs-lookup"><span data-stu-id="f7e09-122">The default is administrators.</span></span> <span data-ttu-id="f7e09-123">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f7e09-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f7e09-124">Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.</span><span class="sxs-lookup"><span data-stu-id="f7e09-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f7e09-125">Изаберите **Повежите се** да бисте покренули везу са услугом Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="f7e09-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="f7e09-126">Изаберите **Потврди идентитет помоћу услуге Microsoft Advertising** и обезбедите своје администраторске акредитиве за Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="f7e09-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="f7e09-127">Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f7e09-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f7e09-128">Изаберите **Сачувај** да бисте креирали везу.</span><span class="sxs-lookup"><span data-stu-id="f7e09-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="f7e09-129">Конфигурисање извоза</span><span class="sxs-lookup"><span data-stu-id="f7e09-129">Configure an export</span></span>

<span data-ttu-id="f7e09-130">Овај извоз можете да конфигуришете ако имате приступ вези ове врсте.</span><span class="sxs-lookup"><span data-stu-id="f7e09-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f7e09-131">За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f7e09-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f7e09-132">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="f7e09-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f7e09-133">Да бисте креирали нови извоз, изаберите **Додај одредиште**.</span><span class="sxs-lookup"><span data-stu-id="f7e09-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f7e09-134">У пољу **Веза за извоз**, одаберите везу из одељка Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="f7e09-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="f7e09-135">Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.</span><span class="sxs-lookup"><span data-stu-id="f7e09-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f7e09-136">Изаберите сегменте за извоз.</span><span class="sxs-lookup"><span data-stu-id="f7e09-136">Select the segments to export.</span></span> <span data-ttu-id="f7e09-137">Циљне групе за подударање клијената у услузи Microsoft Advertising аутоматски се креира са називом сегмената изабраних за извоз.</span><span class="sxs-lookup"><span data-stu-id="f7e09-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="f7e09-138">Сваки сегмент ће резултирати засебном циљном групом за подударање клијената.</span><span class="sxs-lookup"><span data-stu-id="f7e09-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="f7e09-139">Унесите свој **ID Microsoft Advertising клијента и ID налога**.</span><span class="sxs-lookup"><span data-stu-id="f7e09-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="f7e09-140">Можете пронаћи ID клијента (`cid`) и ID пословног контакта (`aid`) у параметрима URL адресе када се пријавите у Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="f7e09-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="f7e09-141">У одељку **Подударање података**, у пољу **Е-пошта**, изаберите поље у вашем обједињеном профилу клијента са е-адресом клијента.</span><span class="sxs-lookup"><span data-stu-id="f7e09-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="f7e09-142">Потребно је да извезете сегменте у Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="f7e09-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="f7e09-143">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="f7e09-143">Select **Save**.</span></span>

<span data-ttu-id="f7e09-144">Чување извоза не покреће извоз одмах.</span><span class="sxs-lookup"><span data-stu-id="f7e09-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f7e09-145">Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f7e09-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f7e09-146">Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f7e09-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f7e09-147">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="f7e09-147">Data privacy and compliance</span></span>

<span data-ttu-id="f7e09-148">Када омогућите Dynamics 365 Customer Insights за пренос података у Microsoft Advertising, дозвољавате пренос података изван граница усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="f7e09-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f7e09-149">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Microsoft Advertising испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="f7e09-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f7e09-150">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f7e09-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="f7e09-151">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="f7e09-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
