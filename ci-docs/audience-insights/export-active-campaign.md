---
title: Извоз Customer Insights података у ActiveCampaign
description: Сазнајте како да конфигуришете везу и извезете је у услугу ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314671"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="a273d-103">Извоз сегмената у ActiveCampaign (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="a273d-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="a273d-104">Извезите сегменте обједињених профила купаца у ActiveCampaign и користите их за маркетиншке активности.</span><span class="sxs-lookup"><span data-stu-id="a273d-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a273d-105">Предуслови</span><span class="sxs-lookup"><span data-stu-id="a273d-105">Prerequisites</span></span>

-   <span data-ttu-id="a273d-106">Имате [ActiveCampaign налог](https://www.activecampaign.com/) и одговарајуће акредитиве администратора.</span><span class="sxs-lookup"><span data-stu-id="a273d-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a273d-107">[Конфигурисали сте сегменте](segments.md) у увидима о корисницима.</span><span class="sxs-lookup"><span data-stu-id="a273d-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="a273d-108">Обједињени кориснички профили у извезеним сегментима садрже поље са адресом е-поште.</span><span class="sxs-lookup"><span data-stu-id="a273d-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a273d-109">Позната ограничења</span><span class="sxs-lookup"><span data-stu-id="a273d-109">Known limitations</span></span>

- <span data-ttu-id="a273d-110">Можете извозити до 1 милион профила по извозу у ActiveCampaign, а то може потрајати и до 90 минута.</span><span class="sxs-lookup"><span data-stu-id="a273d-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="a273d-111">Извоз у ActiveCampaign је ограничен на сегменте.</span><span class="sxs-lookup"><span data-stu-id="a273d-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="a273d-112">Број профила које можете да извезете у ActiveCampaign зависи од вашег уговора са услугом ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="a273d-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="a273d-113">Подесите везу са услугом ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="a273d-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="a273d-114">Идите на **Администратор** > **Везе**.</span><span class="sxs-lookup"><span data-stu-id="a273d-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a273d-115">Изаберите **Додај везу** и изаберите **ActiveCampaign** да бисте конфигурисали везу.</span><span class="sxs-lookup"><span data-stu-id="a273d-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="a273d-116">Дајте вези препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="a273d-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a273d-117">Име за приказ и врста везе описују ову везу.</span><span class="sxs-lookup"><span data-stu-id="a273d-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a273d-118">Препоручујемо да одаберете назив који објашњава сврху и циљ везе.</span><span class="sxs-lookup"><span data-stu-id="a273d-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a273d-119">Одаберите ко може да користи ову везу.</span><span class="sxs-lookup"><span data-stu-id="a273d-119">Choose who can use this connection.</span></span> <span data-ttu-id="a273d-120">Подразумевано су то само администратори.</span><span class="sxs-lookup"><span data-stu-id="a273d-120">By default, it's only administrators.</span></span> <span data-ttu-id="a273d-121">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a273d-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a273d-122">Унесите свој [ActiveCampaign API кључ и име хоста REST крајње тачке](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="a273d-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="a273d-123">Име хоста REST крајње тачке је само име хоста, без https://.</span><span class="sxs-lookup"><span data-stu-id="a273d-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="a273d-124">Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.</span><span class="sxs-lookup"><span data-stu-id="a273d-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a273d-125">Изаберите **Повежи се** за иницијализацију везе са услугом ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="a273d-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="a273d-126">Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a273d-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a273d-127">Изаберите **Сачувај** да бисте креирали везу.</span><span class="sxs-lookup"><span data-stu-id="a273d-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a273d-128">Конфигурисање извоза</span><span class="sxs-lookup"><span data-stu-id="a273d-128">Configure an export</span></span>

<span data-ttu-id="a273d-129">Извоз можете да конфигуришете ако имате приступ вези ове врсте.</span><span class="sxs-lookup"><span data-stu-id="a273d-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="a273d-130">За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a273d-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a273d-131">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="a273d-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a273d-132">Да бисте креирали нови извоз, изаберите **Додај одредиште**.</span><span class="sxs-lookup"><span data-stu-id="a273d-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a273d-133">У пољу **Веза за извоз**, изаберите везу из одељка ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="a273d-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="a273d-134">Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.</span><span class="sxs-lookup"><span data-stu-id="a273d-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a273d-135">Унесите [**ID ActiveCampaign листе**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="a273d-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="a273d-136">У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном корисничком профилу које представља е-адресу клијента.</span><span class="sxs-lookup"><span data-stu-id="a273d-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a273d-137">У ActiveCampaign морате извозити сегменте.</span><span class="sxs-lookup"><span data-stu-id="a273d-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="a273d-138">Опционално, можете да извезете поља Име, Презиме и Телефон да бисте креирали персонализованије адресе е-поште.</span><span class="sxs-lookup"><span data-stu-id="a273d-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="a273d-139">Изаберите Додај атрибут за мапирање ових поља.</span><span class="sxs-lookup"><span data-stu-id="a273d-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="a273d-140">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="a273d-140">Select **Save**.</span></span>

<span data-ttu-id="a273d-141">Чување извоза не покреће извоз одмах.</span><span class="sxs-lookup"><span data-stu-id="a273d-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a273d-142">Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a273d-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a273d-143">Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a273d-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a273d-144">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="a273d-144">Data privacy and compliance</span></span>

<span data-ttu-id="a273d-145">Када омогућите Dynamics 365 Customer Insights за пренос података у ActiveCampaign, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="a273d-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a273d-146">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да ActiveCampaign испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="a273d-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a273d-147">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a273d-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="a273d-148">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="a273d-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
