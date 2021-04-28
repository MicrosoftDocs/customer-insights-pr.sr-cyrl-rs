---
title: Извезите Customer Insights податке у Marketo
description: Сазнајте како да конфигуришете везу и извезете у Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759839"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="184d8-103">Извоз сегмената у Marketo (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="184d8-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="184d8-104">Извезите сегменте обједињених профила клијената да бисте генерисали кампање, обезбедили маркетинг е-поштом и користили одређене групе клијената са услугом Marketo.</span><span class="sxs-lookup"><span data-stu-id="184d8-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="184d8-105">Предуслови за везу</span><span class="sxs-lookup"><span data-stu-id="184d8-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="184d8-106">Имате [Marketo налог](https://login.marketo.com/) и одговарајуће акредитиве администратора.</span><span class="sxs-lookup"><span data-stu-id="184d8-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="184d8-107">Постоје постојеће листе у услузи Marketo и одговарајући ID-ови.</span><span class="sxs-lookup"><span data-stu-id="184d8-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="184d8-108">За више информација погледајте [Marketo листе](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="184d8-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="184d8-109">Имате [конфигурисане сегменте](segments.md).</span><span class="sxs-lookup"><span data-stu-id="184d8-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="184d8-110">Обједињени профили клијената у извезеним сегментима садрже поље које представља адресу е-поште.</span><span class="sxs-lookup"><span data-stu-id="184d8-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="184d8-111">Позната ограничења</span><span class="sxs-lookup"><span data-stu-id="184d8-111">Known limitations</span></span>

- <span data-ttu-id="184d8-112">До 1 милион профила по извозу у услузи Marketo.</span><span class="sxs-lookup"><span data-stu-id="184d8-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="184d8-113">Извоз у Marketo је ограничен на сегменте.</span><span class="sxs-lookup"><span data-stu-id="184d8-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="184d8-114">Извоз сегмената са укупно 1 милион профила може трајати до 3 сата.</span><span class="sxs-lookup"><span data-stu-id="184d8-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="184d8-115">Број профила које можете да извезете у Marketo зависи од и ограничен је вашим уговором са компанијом Marketo.</span><span class="sxs-lookup"><span data-stu-id="184d8-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="184d8-116">Подешавање везе за Marketo</span><span class="sxs-lookup"><span data-stu-id="184d8-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="184d8-117">Идите на **Администратор** > **Везе**.</span><span class="sxs-lookup"><span data-stu-id="184d8-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="184d8-118">Изаберите **Додај везу** и бирајте **Marketo** да бисте конфигурисали везу.</span><span class="sxs-lookup"><span data-stu-id="184d8-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="184d8-119">Дајте вези препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="184d8-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="184d8-120">Име за приказ и врста везе описују ову везу.</span><span class="sxs-lookup"><span data-stu-id="184d8-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="184d8-121">Препоручујемо да одаберете назив који објашњава сврху и циљ везе.</span><span class="sxs-lookup"><span data-stu-id="184d8-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="184d8-122">Одаберите ко може да користи ову везу.</span><span class="sxs-lookup"><span data-stu-id="184d8-122">Choose who can use this connection.</span></span> <span data-ttu-id="184d8-123">Ако ништа не предузмете, подразумевани ће бити Администратори.</span><span class="sxs-lookup"><span data-stu-id="184d8-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="184d8-124">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="184d8-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="184d8-125">Унесите **[ID Marketo клијента, тајну клијента и име хоста REST крајње тачке](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="184d8-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="184d8-126">Изаберите **Слажем се** да бисте потврдили **Приватност података и усклађеност** и изаберите **Повежи се** ради успостављања везе са услугом Marketo.</span><span class="sxs-lookup"><span data-stu-id="184d8-126">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="184d8-127">Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="184d8-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="184d8-128">Изаберите **Сачувај** да бисте креирали везу.</span><span class="sxs-lookup"><span data-stu-id="184d8-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="184d8-129">Конфигурисање извоза</span><span class="sxs-lookup"><span data-stu-id="184d8-129">Configure an export</span></span>

<span data-ttu-id="184d8-130">Овај извоз можете да конфигуришете ако имате приступ вези ове врсте.</span><span class="sxs-lookup"><span data-stu-id="184d8-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="184d8-131">За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="184d8-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="184d8-132">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="184d8-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="184d8-133">Да бисте креирали нови извоз, изаберите **Додај одредиште**.</span><span class="sxs-lookup"><span data-stu-id="184d8-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="184d8-134">У пољу **Веза за извоз**, одаберите везу из одељка Marketo.</span><span class="sxs-lookup"><span data-stu-id="184d8-134">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="184d8-135">Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.</span><span class="sxs-lookup"><span data-stu-id="184d8-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="184d8-136">Унесите **[ID Marketo листе](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="184d8-136">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="184d8-137">У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном профилу клијента које представља е-адресу клијента.</span><span class="sxs-lookup"><span data-stu-id="184d8-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="184d8-138">По жељи можете да извезете **Име**, **Презиме**, **Град**, **Држава** и **Земља/регион** да бисте креирали персонализованије е-поруке.</span><span class="sxs-lookup"><span data-stu-id="184d8-138">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="184d8-139">Изаберите **Додај атрибут** за мапирање ових поља.</span><span class="sxs-lookup"><span data-stu-id="184d8-139">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="184d8-140">Изаберите сегменте које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="184d8-140">Select the segments you want to export.</span></span> <span data-ttu-id="184d8-141">У услузи Marketo можете укупно извести до 1 милион корисничких профила.</span><span class="sxs-lookup"><span data-stu-id="184d8-141">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="184d8-142">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="184d8-142">Select **Save**.</span></span>

<span data-ttu-id="184d8-143">Чување извоза не покреће извоз одмах.</span><span class="sxs-lookup"><span data-stu-id="184d8-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="184d8-144">Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="184d8-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="184d8-145">Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="184d8-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="184d8-146">У Marketo-у сада можете пронаћи сегменте у одељку [Marketo листе](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="184d8-146">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="184d8-147">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="184d8-147">Data privacy and compliance</span></span>

<span data-ttu-id="184d8-148">Када омогућите да Dynamics 365 Customer Insights преноси податке у Marketo, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="184d8-148">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="184d8-149">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Marketo испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="184d8-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="184d8-150">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="184d8-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="184d8-151">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="184d8-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]