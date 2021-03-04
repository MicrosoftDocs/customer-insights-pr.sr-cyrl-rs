---
title: Извезите Customer Insights податке у Marketo
description: Сазнајте како да конфигуришете везу са услугом Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267099"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="93634-103">Конектор за Marketo (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="93634-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="93634-104">Извезите сегменте обједињених профила клијената да бисте генерисали кампање, обезбедили маркетинг е-поштом и користили одређене групе клијената са услугом Marketo.</span><span class="sxs-lookup"><span data-stu-id="93634-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="93634-105">Предуслови</span><span class="sxs-lookup"><span data-stu-id="93634-105">Prerequisites</span></span>

-   <span data-ttu-id="93634-106">Имате [Marketo налог](https://login.marketo.com/) и одговарајуће акредитиве администратора.</span><span class="sxs-lookup"><span data-stu-id="93634-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="93634-107">Постоје постојеће листе у услузи Marketo и одговарајући ID-ови.</span><span class="sxs-lookup"><span data-stu-id="93634-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="93634-108">За више информација погледајте [Marketo листе](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="93634-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="93634-109">Имате [конфигурисане сегменте](segments.md).</span><span class="sxs-lookup"><span data-stu-id="93634-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="93634-110">Обједињени профили клијената у извезеним сегментима садрже поље које представља адресу е-поште.</span><span class="sxs-lookup"><span data-stu-id="93634-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="93634-111">Повезивање са услугом Marketo</span><span class="sxs-lookup"><span data-stu-id="93634-111">Connect to Marketo</span></span>

1. <span data-ttu-id="93634-112">Идите на **Администратор** > **Одредишта за извоз**.</span><span class="sxs-lookup"><span data-stu-id="93634-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="93634-113">Под **Marketo**, изаберите **Подеси**.</span><span class="sxs-lookup"><span data-stu-id="93634-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="93634-114">Дајте одредишту за извоз препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="93634-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="93634-115">Унесите **[ Marketo ID клијента, тајну клијента и име хоста REST крајње тачке](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="93634-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="93634-116">Унесите **[ID Marketo листе](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="93634-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="93634-117">Изаберите **Слажем се** да бисте потврдили **Приватност података и усклађеност** и изаберите **Повежи се** ради успостављања везе са услугом Marketo.</span><span class="sxs-lookup"><span data-stu-id="93634-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="93634-118">Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="93634-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Извезите снимак екрана за везу са услугом Marketo":::

1. <span data-ttu-id="93634-120">Изаберите **Следеће** да бисте конфигурисали извоз.</span><span class="sxs-lookup"><span data-stu-id="93634-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="93634-121">Конфигурисање конектора</span><span class="sxs-lookup"><span data-stu-id="93634-121">Configure the connector</span></span>

1. <span data-ttu-id="93634-122">У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном профилу клијента које представља е-адресу клијента.</span><span class="sxs-lookup"><span data-stu-id="93634-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="93634-123">По жељи можете да извезете **Име**, **Презиме**, **Град**, **Државу** и **Земљу/регион** као додатна поља за стварање персонализованих е-порука.</span><span class="sxs-lookup"><span data-stu-id="93634-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="93634-124">Изаберите **Додај атрибут** за мапирање ових поља.</span><span class="sxs-lookup"><span data-stu-id="93634-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="93634-125">Изаберите сегменте које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="93634-125">Select the segments you want to export.</span></span> <span data-ttu-id="93634-126">У услузи Marketo можете укупно извести до 1 милион корисничких профила.</span><span class="sxs-lookup"><span data-stu-id="93634-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Изаберите поља и сегменте за извоз у Marketo":::

1. <span data-ttu-id="93634-128">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="93634-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="93634-129">Извоз података</span><span class="sxs-lookup"><span data-stu-id="93634-129">Export the data</span></span>

<span data-ttu-id="93634-130">Можете да [извезете податке на захтев](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="93634-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="93634-131">Извоз ће се такође покренути са сваким [планираним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="93634-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="93634-132">У Marketo-у сада можете пронаћи сегменте у одељку [Marketo листе](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="93634-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="93634-133">Позната ограничења</span><span class="sxs-lookup"><span data-stu-id="93634-133">Known limitations</span></span>

- <span data-ttu-id="93634-134">До 1 милион профила по извозу у услузи Marketo.</span><span class="sxs-lookup"><span data-stu-id="93634-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="93634-135">Извоз у Marketo је ограничен на сегменте.</span><span class="sxs-lookup"><span data-stu-id="93634-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="93634-136">Извоз сегмената са укупно 1 милион профила може трајати до 3 сата.</span><span class="sxs-lookup"><span data-stu-id="93634-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="93634-137">Број профила које можете да извезете у Marketo зависи од и ограничен је вашим уговором са компанијом Marketo.</span><span class="sxs-lookup"><span data-stu-id="93634-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="93634-138">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="93634-138">Data privacy and compliance</span></span>

<span data-ttu-id="93634-139">Када омогућите да Dynamics 365 Customer Insights преноси податке у Marketo, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="93634-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="93634-140">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Marketo испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="93634-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="93634-141">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="93634-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="93634-142">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="93634-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]