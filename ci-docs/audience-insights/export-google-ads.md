---
title: Извезите Customer Insights податке у Google огласима
description: Сазнајте како да конфигуришете везу са Google огласима.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568496"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="12190-103">Конектор за Google огласе (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="12190-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="12190-104">Извезите сегменте обједињених профила клијената у листу корисника Google огласа и користите их за оглашавање у Google претрази, на Gmail-у, YouTube-у и Google мрежи мултимедијалног оглашавања.</span><span class="sxs-lookup"><span data-stu-id="12190-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="12190-105">Предуслови</span><span class="sxs-lookup"><span data-stu-id="12190-105">Prerequisites</span></span>

-   <span data-ttu-id="12190-106">Имате [налог Google огласа](https://ads.google.com/) и одговарајуће акредитиве администратора.</span><span class="sxs-lookup"><span data-stu-id="12190-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="12190-107">Постоји постојећа публика у Google огласима и одговарајући ID-ови.</span><span class="sxs-lookup"><span data-stu-id="12190-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="12190-108">За више информација погледајте [Корисници Google огласа](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="12190-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="12190-109">Имате [конфигурисане сегменте](segments.md)</span><span class="sxs-lookup"><span data-stu-id="12190-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="12190-110">Обједињени профили клијената у извезеним сегментима садрже поља која представљају адресу е-поште, име и презиме</span><span class="sxs-lookup"><span data-stu-id="12190-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="12190-111">Повежите се са Google огласима</span><span class="sxs-lookup"><span data-stu-id="12190-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="12190-112">Идите на **Администратор** > **Одредишта за извоз**.</span><span class="sxs-lookup"><span data-stu-id="12190-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="12190-113">У одељку **Google огласи**, изаберите **Подеси**.</span><span class="sxs-lookup"><span data-stu-id="12190-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="12190-114">Дајте одредишту за извоз препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="12190-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="12190-115">Унесите **[ID клијента за Google огласе](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="12190-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="12190-116">Унесите **[токен одобреног програмера за Google огласе](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="12190-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="12190-117">Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.</span><span class="sxs-lookup"><span data-stu-id="12190-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="12190-118">Унесите **[ID корисника за Google огласе](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** и изаберите **Повежите се** да бисте започели повезивање са Google огласима.</span><span class="sxs-lookup"><span data-stu-id="12190-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="12190-119">Изаберите **Потврдите идентитет у Google огласима** и наведите акредитиве за Google огласе.</span><span class="sxs-lookup"><span data-stu-id="12190-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="12190-120">Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="12190-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Извезите снимак екрана за везу са Google огласима":::

1. <span data-ttu-id="12190-122">Изаберите **Следеће** да бисте конфигурисали извоз.</span><span class="sxs-lookup"><span data-stu-id="12190-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="12190-123">Конфигурисање конектора</span><span class="sxs-lookup"><span data-stu-id="12190-123">Configure the connector</span></span>

1. <span data-ttu-id="12190-124">У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном профилу клијента које представља е-адресу клијента.</span><span class="sxs-lookup"><span data-stu-id="12190-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="12190-125">Поновите исте кораке за поља **Име** и **Презиме**.</span><span class="sxs-lookup"><span data-stu-id="12190-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="12190-126">Изаберите сегменте које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="12190-126">Select the segments you want to export.</span></span> <span data-ttu-id="12190-127">У Google огласима можете укупно извести до 1 милион корисничких профила.</span><span class="sxs-lookup"><span data-stu-id="12190-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="12190-128">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="12190-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="12190-129">Извоз података</span><span class="sxs-lookup"><span data-stu-id="12190-129">Export the data</span></span>

<span data-ttu-id="12190-130">Можете да [извезете податке на захтев](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="12190-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="12190-131">Извоз ће се такође покренути са сваким [планираним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="12190-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="12190-132">У Google огласима сада можете пронаћи сегменте у одељку [Корисници Google огласа](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="12190-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="12190-133">Позната ограничења</span><span class="sxs-lookup"><span data-stu-id="12190-133">Known limitations</span></span>

- <span data-ttu-id="12190-134">До 1 милион профила по извозу у Google огласима.</span><span class="sxs-lookup"><span data-stu-id="12190-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="12190-135">Извоз у Google огласе је ограничен на сегменте.</span><span class="sxs-lookup"><span data-stu-id="12190-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="12190-136">Извоз сегмената са укупно 1 милион профила може трајати до 5 минута због ограничења на страни добављача.</span><span class="sxs-lookup"><span data-stu-id="12190-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="12190-137">Подударање у Google огласима може да потраје до 48 сати.</span><span class="sxs-lookup"><span data-stu-id="12190-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="12190-138">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="12190-138">Data privacy and compliance</span></span>

<span data-ttu-id="12190-139">Када омогућите да Dynamics 365 Customer Insights преноси податке у Google огласе, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="12190-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="12190-140">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Google огласи испуњавају све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="12190-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="12190-141">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="12190-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="12190-142">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="12190-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
