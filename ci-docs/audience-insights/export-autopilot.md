---
title: Извезите Customer Insights податке у Autopilot
description: Сазнајте како да конфигуришете везу са услугом Autopilot.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269256"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="6a50f-103">Конектор за Autopilot (преглед)</span><span class="sxs-lookup"><span data-stu-id="6a50f-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="6a50f-104">Извезите сегменте обједињених профила клијената у Autopilot и користите их за маркетинг путем е-поште у услузи Autopilot.</span><span class="sxs-lookup"><span data-stu-id="6a50f-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="6a50f-105">Предуслови</span><span class="sxs-lookup"><span data-stu-id="6a50f-105">Prerequisites</span></span>

-   <span data-ttu-id="6a50f-106">Имате [Autopilot налог](https://www.autopilothq.com/) и одговарајуће акредитиве администратора.</span><span class="sxs-lookup"><span data-stu-id="6a50f-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="6a50f-107">[Конфигурисали сте сегменте](segments.md) у увидима о корисницима.</span><span class="sxs-lookup"><span data-stu-id="6a50f-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="6a50f-108">Обједињени профили клијената у извезеним сегментима садрже поље које представља адресу е-поште.</span><span class="sxs-lookup"><span data-stu-id="6a50f-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="6a50f-109">Повезивање са услугом Autopilot</span><span class="sxs-lookup"><span data-stu-id="6a50f-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="6a50f-110">Идите на **Администратор** > **Одредишта за извоз**.</span><span class="sxs-lookup"><span data-stu-id="6a50f-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="6a50f-111">У делу **Autopilot** изаберите **Подеси**.</span><span class="sxs-lookup"><span data-stu-id="6a50f-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="6a50f-112">Дајте одредишту за извоз препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="6a50f-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Окно за конфигурацију за везу са услугом Autopilot.":::

1. <span data-ttu-id="6a50f-114">Унесите свој **API кључ за Autopilot** [API кључ за Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="6a50f-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="6a50f-115">Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.</span><span class="sxs-lookup"><span data-stu-id="6a50f-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="6a50f-116">Изаберите **Повежи се** за иницијализацију везе са услугом Autopilot.</span><span class="sxs-lookup"><span data-stu-id="6a50f-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="6a50f-117">Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6a50f-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="6a50f-118">Изаберите **Следеће** да бисте конфигурисали извоз.</span><span class="sxs-lookup"><span data-stu-id="6a50f-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="6a50f-119">Конфигурисање конектора</span><span class="sxs-lookup"><span data-stu-id="6a50f-119">Configure the connector</span></span>

1. <span data-ttu-id="6a50f-120">У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном профилу клијента које представља е-адресу клијента.</span><span class="sxs-lookup"><span data-stu-id="6a50f-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="6a50f-121">Поновите исте кораке за друга опционална поља као што су **Име**, **Презиме**.</span><span class="sxs-lookup"><span data-stu-id="6a50f-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="6a50f-122">Изаберите сегменте које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="6a50f-122">Select the segments you want to export.</span></span> <span data-ttu-id="6a50f-123">Изричито **препоручујемо да не извозите укупно више од 100.000 профила клијената** у Autopilot.</span><span class="sxs-lookup"><span data-stu-id="6a50f-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="6a50f-124">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="6a50f-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="6a50f-125">Извоз података</span><span class="sxs-lookup"><span data-stu-id="6a50f-125">Export the data</span></span>

<span data-ttu-id="6a50f-126">Можете да [извезете податке на захтев](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="6a50f-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="6a50f-127">Извоз ће се такође покренути са сваким [планираним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6a50f-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="6a50f-128">Позната ограничења</span><span class="sxs-lookup"><span data-stu-id="6a50f-128">Known limitations</span></span>

- <span data-ttu-id="6a50f-129">У услугу Autopilot можете да извезете укупно до 100.000 профила.</span><span class="sxs-lookup"><span data-stu-id="6a50f-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="6a50f-130">Извоз у Autopilot је ограничен на сегменте.</span><span class="sxs-lookup"><span data-stu-id="6a50f-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="6a50f-131">Извоз до 100.000 профила у Autopilot може да потраје до неколико сати.</span><span class="sxs-lookup"><span data-stu-id="6a50f-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="6a50f-132">Број профила које можете да извезете у Autopilot зависи од вашег уговора са компанијом Autopilot и ограничен је њиме.</span><span class="sxs-lookup"><span data-stu-id="6a50f-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6a50f-133">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="6a50f-133">Data privacy and compliance</span></span>

<span data-ttu-id="6a50f-134">Када омогућите да Dynamics 365 Customer Insights преноси податке у Autopilot, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="6a50f-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6a50f-135">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Autopilot испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="6a50f-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="6a50f-136">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6a50f-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="6a50f-137">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="6a50f-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]