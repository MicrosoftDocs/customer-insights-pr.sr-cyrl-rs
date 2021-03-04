---
title: Извезите Customer Insights податке у DotDigital
description: Сазнајте како да конфигуришете везу са услугом DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 573a22e24f84c65fc4d21faf823cace801cc7ea3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269118"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="ecb45-103">Конектор за DotDigital (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="ecb45-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="ecb45-104">Извезите сегменте обједињених профила купаца у DotDigital адресаре и користите их за кампање, маркетинг путем е-поште и за изградњу сегмената купаца помоћу услуге DotDigital.</span><span class="sxs-lookup"><span data-stu-id="ecb45-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="ecb45-105">Предуслови</span><span class="sxs-lookup"><span data-stu-id="ecb45-105">Prerequisites</span></span>

-   <span data-ttu-id="ecb45-106">Имате [DotDigital налог](https://dotdigital.com/) и одговарајуће акредитиве администратора.</span><span class="sxs-lookup"><span data-stu-id="ecb45-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ecb45-107">Постоји постојећа публика у адресарима у услузи DotDigital и одговарајући ID-ови.</span><span class="sxs-lookup"><span data-stu-id="ecb45-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="ecb45-108">ID се може наћи у URL-у када одаберете и отворите адресар.</span><span class="sxs-lookup"><span data-stu-id="ecb45-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="ecb45-109">За више информација погледајте [адресаре за DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="ecb45-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="ecb45-110">[Конфигурисали сте сегменте](segments.md) у увидима о корисницима.</span><span class="sxs-lookup"><span data-stu-id="ecb45-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ecb45-111">Обједињени профили клијената у извезеним сегментима садрже поље које представља адресу е-поште.</span><span class="sxs-lookup"><span data-stu-id="ecb45-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="ecb45-112">Повезивање са услугом DotDigital</span><span class="sxs-lookup"><span data-stu-id="ecb45-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="ecb45-113">Идите на **Администратор** > **Одредишта за извоз**.</span><span class="sxs-lookup"><span data-stu-id="ecb45-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ecb45-114">У одељку **DotDigital**, изаберите **Подеси**.</span><span class="sxs-lookup"><span data-stu-id="ecb45-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="ecb45-115">Дајте одредишту за извоз препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="ecb45-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Окно за конфигурацију извоза услуге DotDigital.":::

1. <span data-ttu-id="ecb45-117">Унесите своје **корисничко име и лозинку за DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="ecb45-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="ecb45-118">Унесите **[ID DotDigital адресара](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="ecb45-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="ecb45-119">Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.</span><span class="sxs-lookup"><span data-stu-id="ecb45-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ecb45-120">Изаберите **Повежи се** за иницијализацију везе са услугом DotDigital.</span><span class="sxs-lookup"><span data-stu-id="ecb45-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="ecb45-121">Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ecb45-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ecb45-122">Изаберите **Следеће** да бисте конфигурисали извоз.</span><span class="sxs-lookup"><span data-stu-id="ecb45-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="ecb45-123">Конфигурисање конектора</span><span class="sxs-lookup"><span data-stu-id="ecb45-123">Configure the connector</span></span>

1. <span data-ttu-id="ecb45-124">У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном профилу клијента које представља е-адресу клијента.</span><span class="sxs-lookup"><span data-stu-id="ecb45-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ecb45-125">Поновите исте кораке за друга опционална поља као што су **Име**, **Презиме**, **Пуно име**, **Пол** и **Поштански број**.</span><span class="sxs-lookup"><span data-stu-id="ecb45-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="ecb45-126">Изаберите сегменте које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="ecb45-126">Select the segments you want to export.</span></span> <span data-ttu-id="ecb45-127">У услузи DotDigital можете укупно извести до 1 милион корисничких профила.</span><span class="sxs-lookup"><span data-stu-id="ecb45-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="ecb45-128">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="ecb45-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ecb45-129">Извоз података</span><span class="sxs-lookup"><span data-stu-id="ecb45-129">Export the data</span></span>

<span data-ttu-id="ecb45-130">Можете да [извезете податке на захтев](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="ecb45-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="ecb45-131">Извоз ће се такође покренути са сваким [планираним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ecb45-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ecb45-132">У услузи DotDigital сада можете да пронађете своје сегменте у [DotDigital адресарима](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="ecb45-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ecb45-133">Позната ограничења</span><span class="sxs-lookup"><span data-stu-id="ecb45-133">Known limitations</span></span>

- <span data-ttu-id="ecb45-134">До 1 милион профила по извозу у услузи DotDigital.</span><span class="sxs-lookup"><span data-stu-id="ecb45-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="ecb45-135">Извоз у DotDigital је ограничен на сегменте.</span><span class="sxs-lookup"><span data-stu-id="ecb45-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="ecb45-136">Извоз сегмената са укупно 1 милион профила може трајати до 3 сата због ограничења на страни добављача.</span><span class="sxs-lookup"><span data-stu-id="ecb45-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="ecb45-137">Број профила које можете да извезете у DotDigital зависи од и ограничен је вашим уговором са компанијом DotDigital.</span><span class="sxs-lookup"><span data-stu-id="ecb45-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ecb45-138">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="ecb45-138">Data privacy and compliance</span></span>

<span data-ttu-id="ecb45-139">Када омогућите да Dynamics 365 Customer Insights преноси податке у DotDigital, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="ecb45-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ecb45-140">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да DotDigital испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="ecb45-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="ecb45-141">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ecb45-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ecb45-142">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="ecb45-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]