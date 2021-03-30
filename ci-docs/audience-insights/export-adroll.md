---
title: Извоз Customer Insights података у AdRoll
description: Сазнајте како да конфигуришете везу са услугом AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697092"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="245cb-103">Конектор за AdRoll (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="245cb-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="245cb-104">Извезите сегменте обједињених профила клијената у AdRoll и користите их за оглашавање.</span><span class="sxs-lookup"><span data-stu-id="245cb-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="245cb-105">Предуслови</span><span class="sxs-lookup"><span data-stu-id="245cb-105">Prerequisites</span></span>

-   <span data-ttu-id="245cb-106">Имате [AdRoll налог](https://www.adroll.com/) и одговарајуће акредитиве администратора.</span><span class="sxs-lookup"><span data-stu-id="245cb-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="245cb-107">[Конфигурисали сте сегменте](segments.md) у увидима о корисницима.</span><span class="sxs-lookup"><span data-stu-id="245cb-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="245cb-108">Обједињени профили клијената у извезеним сегментима садрже поље које представља адресу е-поште.</span><span class="sxs-lookup"><span data-stu-id="245cb-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="245cb-109">Повежите се са услугом AdRoll</span><span class="sxs-lookup"><span data-stu-id="245cb-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="245cb-110">Идите на **Администратор** > **Одредишта за извоз**.</span><span class="sxs-lookup"><span data-stu-id="245cb-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="245cb-111">У одељку **AdRoll** изаберите **Подеси**.</span><span class="sxs-lookup"><span data-stu-id="245cb-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="245cb-112">Дајте одредишту за извоз препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="245cb-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Окно за конфигурацију за везу са услугом AdRoll.":::

1. <span data-ttu-id="245cb-114">Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.</span><span class="sxs-lookup"><span data-stu-id="245cb-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="245cb-115">Изаберите **Повежи се** за иницијализацију везе са услугом AdRoll.</span><span class="sxs-lookup"><span data-stu-id="245cb-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="245cb-116">Изаберите **Потврдите идентитет у услузи AdRoll** и наведите своје акредитиве администратора за AdRoll.</span><span class="sxs-lookup"><span data-stu-id="245cb-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="245cb-117">Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="245cb-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="245cb-118">Унесите свој **ID AdRoll оглашавача** [који може да се оглашава у услузи AdRoll](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="245cb-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="245cb-119">Изаберите **Следеће** да бисте конфигурисали извоз.</span><span class="sxs-lookup"><span data-stu-id="245cb-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="245cb-120">Конфигурисање конектора</span><span class="sxs-lookup"><span data-stu-id="245cb-120">Configure the connector</span></span>

1. <span data-ttu-id="245cb-121">У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном профилу клијента које представља е-адресу клијента.</span><span class="sxs-lookup"><span data-stu-id="245cb-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="245cb-122">То је потребно за извоз сегмената у AdRoll.</span><span class="sxs-lookup"><span data-stu-id="245cb-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="245cb-123">Изаберите сегменте које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="245cb-123">Select the segments you want to export.</span></span> <span data-ttu-id="245cb-124">Изаберите сегмент са најмање 100 чланова.</span><span class="sxs-lookup"><span data-stu-id="245cb-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="245cb-125">Не можете извозити мање сегменте.</span><span class="sxs-lookup"><span data-stu-id="245cb-125">You can't export smaller segments.</span></span> <span data-ttu-id="245cb-126">Поред тога, максимална величина сегмента за извоз је 250.000 чланова по извозу.</span><span class="sxs-lookup"><span data-stu-id="245cb-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="245cb-127">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="245cb-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="245cb-128">Извоз података</span><span class="sxs-lookup"><span data-stu-id="245cb-128">Export the data</span></span>

<span data-ttu-id="245cb-129">Можете да [извезете податке на захтев](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="245cb-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="245cb-130">Извоз ће се такође покренути са сваким [планираним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="245cb-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="245cb-131">Позната ограничења</span><span class="sxs-lookup"><span data-stu-id="245cb-131">Known limitations</span></span>

- <span data-ttu-id="245cb-132">У услугу AdRoll можете да извезете укупно до 250.000 профила по извозу.</span><span class="sxs-lookup"><span data-stu-id="245cb-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="245cb-133">У AdRoll не можете да извезете сегменте са мање од 100 профила.</span><span class="sxs-lookup"><span data-stu-id="245cb-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="245cb-134">Извоз у AdRoll је ограничен на сегменте.</span><span class="sxs-lookup"><span data-stu-id="245cb-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="245cb-135">Извоз до 250.000 профила у AdRoll може да потраје до 10 минута.</span><span class="sxs-lookup"><span data-stu-id="245cb-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="245cb-136">Број профила које можете да извезете у AdRoll зависи од и ограничен је вашим уговором са компанијом AdRoll.</span><span class="sxs-lookup"><span data-stu-id="245cb-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="245cb-137">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="245cb-137">Data privacy and compliance</span></span>

<span data-ttu-id="245cb-138">Када омогућите да Dynamics 365 Customer Insights преноси податке у AdRoll, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="245cb-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="245cb-139">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да AdRoll испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="245cb-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="245cb-140">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="245cb-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="245cb-141">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="245cb-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
