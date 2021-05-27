---
title: Извезите Customer Insights податке у Marketo
description: Сазнајте како да конфигуришете везу и извезете у Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059334"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="1adbd-103">Извоз сегмената у Marketo (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="1adbd-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="1adbd-104">Извезите сегменте обједињених корисничких профила да бисте генерисали кампање, обезбедили маркетинг е-поштом и користили одређене групе клијената са услугом Marketo.</span><span class="sxs-lookup"><span data-stu-id="1adbd-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="1adbd-105">Предуслови за везу</span><span class="sxs-lookup"><span data-stu-id="1adbd-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="1adbd-106">Имате [Marketo налог](https://login.marketo.com/) и одговарајуће акредитиве администратора.</span><span class="sxs-lookup"><span data-stu-id="1adbd-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1adbd-107">Постоје постојеће листе у услузи Marketo и одговарајући ID-ови.</span><span class="sxs-lookup"><span data-stu-id="1adbd-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="1adbd-108">За више информација погледајте [Marketo листе](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="1adbd-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="1adbd-109">Имате [конфигурисане сегменте](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1adbd-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="1adbd-110">Обједињени кориснички профили у извезеним сегментима садрже поље које представља адресу е-поште.</span><span class="sxs-lookup"><span data-stu-id="1adbd-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1adbd-111">Позната ограничења</span><span class="sxs-lookup"><span data-stu-id="1adbd-111">Known limitations</span></span>

- <span data-ttu-id="1adbd-112">До 1 милион профила по извозу у услузи Marketo.</span><span class="sxs-lookup"><span data-stu-id="1adbd-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="1adbd-113">Извоз у Marketo је ограничен на сегменте.</span><span class="sxs-lookup"><span data-stu-id="1adbd-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="1adbd-114">Извоз сегмената са укупно 1 милион профила може трајати до 3 сата.</span><span class="sxs-lookup"><span data-stu-id="1adbd-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="1adbd-115">Број профила које можете да извезете у Marketo зависи од и ограничен је вашим уговором са компанијом Marketo.</span><span class="sxs-lookup"><span data-stu-id="1adbd-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="1adbd-116">Подешавање везе за Marketo</span><span class="sxs-lookup"><span data-stu-id="1adbd-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="1adbd-117">Идите на **Администратор** > **Везе**.</span><span class="sxs-lookup"><span data-stu-id="1adbd-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1adbd-118">Изаберите **Додај везу** и бирајте **Marketo** да бисте конфигурисали везу.</span><span class="sxs-lookup"><span data-stu-id="1adbd-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="1adbd-119">Дајте вези препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="1adbd-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1adbd-120">Име за приказ и врста везе описују ову везу.</span><span class="sxs-lookup"><span data-stu-id="1adbd-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1adbd-121">Препоручујемо да одаберете назив који објашњава сврху и циљ везе.</span><span class="sxs-lookup"><span data-stu-id="1adbd-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1adbd-122">Одаберите ко може да користи ову везу.</span><span class="sxs-lookup"><span data-stu-id="1adbd-122">Choose who can use this connection.</span></span> <span data-ttu-id="1adbd-123">Ако ништа не предузмете, подразумевани ће бити Администратори.</span><span class="sxs-lookup"><span data-stu-id="1adbd-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1adbd-124">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1adbd-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1adbd-125">Унесите **[ID Marketo клијента, тајну клијента и име хоста REST крајње тачке](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="1adbd-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span> <span data-ttu-id="1adbd-126">Име хоста REST крајње тачке је само име хоста, без `https://`.</span><span class="sxs-lookup"><span data-stu-id="1adbd-126">The REST Endpoint Hostname is the hostname only, without `https://`.</span></span> <span data-ttu-id="1adbd-127">Пример: `xyz-abc-123.mktorest.com`.</span><span class="sxs-lookup"><span data-stu-id="1adbd-127">Example: `xyz-abc-123.mktorest.com`.</span></span> 

1. <span data-ttu-id="1adbd-128">Изаберите **Слажем се** да бисте потврдили **Приватност података и усклађеност** и изаберите **Повежи се** ради успостављања везе са услугом Marketo.</span><span class="sxs-lookup"><span data-stu-id="1adbd-128">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="1adbd-129">Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1adbd-129">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="1adbd-130">Изаберите **Сачувај** да бисте креирали везу.</span><span class="sxs-lookup"><span data-stu-id="1adbd-130">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="1adbd-131">Конфигурисање извоза</span><span class="sxs-lookup"><span data-stu-id="1adbd-131">Configure an export</span></span>

<span data-ttu-id="1adbd-132">Овај извоз можете да конфигуришете ако имате приступ вези ове врсте.</span><span class="sxs-lookup"><span data-stu-id="1adbd-132">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1adbd-133">За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1adbd-133">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1adbd-134">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="1adbd-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1adbd-135">Да бисте креирали нови извоз, изаберите **Додај одредиште**.</span><span class="sxs-lookup"><span data-stu-id="1adbd-135">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1adbd-136">У пољу **Веза за извоз**, одаберите везу из одељка Marketo.</span><span class="sxs-lookup"><span data-stu-id="1adbd-136">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="1adbd-137">Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.</span><span class="sxs-lookup"><span data-stu-id="1adbd-137">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1adbd-138">Унесите **[ID Marketo листе](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span><span class="sxs-lookup"><span data-stu-id="1adbd-138">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span></span> <span data-ttu-id="1adbd-139">ID листе је чисто нумеричка вредност.</span><span class="sxs-lookup"><span data-stu-id="1adbd-139">The list ID is a purely numerical value.</span></span> <span data-ttu-id="1adbd-140">На пример, ако је ваш ID Marketo листе ST12345A7, уклоните знак пре и после бројева и унесите `12345`.</span><span class="sxs-lookup"><span data-stu-id="1adbd-140">For example, if your Marketo list ID is ST12345A7, remove the character before and after the numerals and enter `12345`.</span></span> 

1. <span data-ttu-id="1adbd-141">У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном корисничком профилу које представља е-адресу клијента.</span><span class="sxs-lookup"><span data-stu-id="1adbd-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="1adbd-142">По жељи можете да извезете **Име**, **Презиме**, **Град**, **Држава** и **Земља/регион** да бисте креирали персонализованије е-поруке.</span><span class="sxs-lookup"><span data-stu-id="1adbd-142">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="1adbd-143">Изаберите **Додај атрибут** за мапирање ових поља.</span><span class="sxs-lookup"><span data-stu-id="1adbd-143">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="1adbd-144">Изаберите сегменте које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="1adbd-144">Select the segments you want to export.</span></span> <span data-ttu-id="1adbd-145">У услузи Marketo можете укупно извести до 1 милион корисничких профила.</span><span class="sxs-lookup"><span data-stu-id="1adbd-145">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="1adbd-146">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="1adbd-146">Select **Save**.</span></span>

<span data-ttu-id="1adbd-147">Чување извоза не покреће извоз одмах.</span><span class="sxs-lookup"><span data-stu-id="1adbd-147">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1adbd-148">Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1adbd-148">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1adbd-149">Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1adbd-149">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="1adbd-150">У Marketo-у сада можете пронаћи сегменте у одељку [Marketo листе](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="1adbd-150">In Marketo, you can now find your segments under [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1adbd-151">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="1adbd-151">Data privacy and compliance</span></span>

<span data-ttu-id="1adbd-152">Када омогућите да Dynamics 365 Customer Insights преноси податке у Marketo, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="1adbd-152">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1adbd-153">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Marketo испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="1adbd-153">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1adbd-154">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1adbd-154">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1adbd-155">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="1adbd-155">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
