---
title: Извезите Customer Insights податке у Mailchimp
description: Сазнајте како да конфигуришете везу са услугом Mailchimp.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: edff494f6edf26a8b641cb1d788a715389ddb346
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406839"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="3fe84-103">Конектор за Mailchimp (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="3fe84-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="3fe84-104">Извезите сегменте обједињених профила клијената у Mailchimp да бисте креирали билтене и кампање е-поште.</span><span class="sxs-lookup"><span data-stu-id="3fe84-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3fe84-105">Предуслови</span><span class="sxs-lookup"><span data-stu-id="3fe84-105">Prerequisites</span></span>

-   <span data-ttu-id="3fe84-106">Имате [Mailchimp налог](https://mailchimp.com/) и одговарајуће акредитиве администратора.</span><span class="sxs-lookup"><span data-stu-id="3fe84-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="3fe84-107">Постоји постојећа публика у Mailchimp-у и одговарајући ID-ови.</span><span class="sxs-lookup"><span data-stu-id="3fe84-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="3fe84-108">За више информација погледајте [Mailchimp корисници](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="3fe84-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="3fe84-109">Имате [конфигурисане сегменте](segments.md)</span><span class="sxs-lookup"><span data-stu-id="3fe84-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="3fe84-110">Обједињени профили клијената у извезеним сегментима садрже поље које представља адресу е-поште.</span><span class="sxs-lookup"><span data-stu-id="3fe84-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="3fe84-111">Повежите се са услугом Mailchimp</span><span class="sxs-lookup"><span data-stu-id="3fe84-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="3fe84-112">Идите на **Администратор** > **Одредишта за извоз**.</span><span class="sxs-lookup"><span data-stu-id="3fe84-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="3fe84-113">Под **Mailchimp**, изаберите **Подеси**.</span><span class="sxs-lookup"><span data-stu-id="3fe84-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="3fe84-114">Дајте одредишту за извоз препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="3fe84-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="3fe84-115">Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.</span><span class="sxs-lookup"><span data-stu-id="3fe84-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="3fe84-116">Унесите **[Mailchimp ID корисника](https://mailchimp.com/help/find-audience-id/)** и изаберите **Повежите се** да бисте започели повезивање са Mailchimp-ом.</span><span class="sxs-lookup"><span data-stu-id="3fe84-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="3fe84-117">Изаберите **Потврдите идентитет у Mailchimp-у** и наведите акредитиве за Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="3fe84-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="3fe84-118">Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3fe84-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Извезите снимак екрана за везу са услугом Mailchimp":::

1. <span data-ttu-id="3fe84-120">Изаберите **Следеће** да бисте конфигурисали извоз.</span><span class="sxs-lookup"><span data-stu-id="3fe84-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="3fe84-121">Конфигурисање конектора</span><span class="sxs-lookup"><span data-stu-id="3fe84-121">Configure the connector</span></span>

1. <span data-ttu-id="3fe84-122">У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном профилу клијента које представља е-адресу клијента.</span><span class="sxs-lookup"><span data-stu-id="3fe84-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="3fe84-123">По жељи можете да извезете **Име** и **Презиме** као додатна поља за стварање персонализованих е-порука.</span><span class="sxs-lookup"><span data-stu-id="3fe84-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="3fe84-124">Изаберите **Додај атрибут** за мапирање ових поља.</span><span class="sxs-lookup"><span data-stu-id="3fe84-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="3fe84-125">Изаберите сегменте које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="3fe84-125">Select the segments you want to export.</span></span> <span data-ttu-id="3fe84-126">У услузи Mailchimp можете укупно извести до 1 милион корисничких профила.</span><span class="sxs-lookup"><span data-stu-id="3fe84-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Изаберите поља и сегменте за извоз у Mailchimp":::

1. <span data-ttu-id="3fe84-128">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="3fe84-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="3fe84-129">Извоз података</span><span class="sxs-lookup"><span data-stu-id="3fe84-129">Export the data</span></span>

<span data-ttu-id="3fe84-130">Можете да [извезете податке на захтев](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="3fe84-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="3fe84-131">Извоз ће се такође покренути са сваким [планираним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3fe84-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3fe84-132">У Mailchimp-у сада можете пронаћи сегменте у одељку [Mailchimp корисници](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="3fe84-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="3fe84-133">Позната ограничења</span><span class="sxs-lookup"><span data-stu-id="3fe84-133">Known limitations</span></span>

- <span data-ttu-id="3fe84-134">До 1 милион профила по извозу у услузи Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="3fe84-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="3fe84-135">Извоз у Mailchimp је ограничен на сегменте.</span><span class="sxs-lookup"><span data-stu-id="3fe84-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="3fe84-136">Извоз сегмената са укупно 1 милион профила може трајати до три сата због ограничења на страни добављача.</span><span class="sxs-lookup"><span data-stu-id="3fe84-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="3fe84-137">Број профила које можете да извезете у Mailchimp зависи од и ограничен је вашим уговором са компанијом Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="3fe84-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3fe84-138">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="3fe84-138">Data privacy and compliance</span></span>

<span data-ttu-id="3fe84-139">Када омогућите да Dynamics 365 Customer Insights преноси податке у Mailchimp, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="3fe84-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3fe84-140">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Mailchimp испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="3fe84-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3fe84-141">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3fe84-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3fe84-142">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="3fe84-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
