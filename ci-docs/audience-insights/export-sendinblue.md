---
title: Извоз Customer Insights података у Sendinblue
description: Сазнајте како да конфигуришете везу и извезете је у услугу Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314670"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="1cae8-103">Извоз сегмената у Sendinblue (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="1cae8-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="1cae8-104">Извезите сегменте уједначених профила клијената да бисте генерисали кампање, обезбедили маркетинг е-поштом и користили одређене групе клијената са услугом Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="1cae8-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="1cae8-105">Предуслови за везу</span><span class="sxs-lookup"><span data-stu-id="1cae8-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="1cae8-106">Имате [Sendinblue налог](https://www.sendinblue.com/) и одговарајуће акредитиве администратора.</span><span class="sxs-lookup"><span data-stu-id="1cae8-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1cae8-107">Постоје постојеће листе у услузи Sendinblue и одговарајући ИД-ови.</span><span class="sxs-lookup"><span data-stu-id="1cae8-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="1cae8-108">Имате [конфигурисане сегменте](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1cae8-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="1cae8-109">Обједињени кориснички профили у извезеним сегментима садрже поље које представља адресу е-поште.</span><span class="sxs-lookup"><span data-stu-id="1cae8-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1cae8-110">Позната ограничења</span><span class="sxs-lookup"><span data-stu-id="1cae8-110">Known limitations</span></span>

- <span data-ttu-id="1cae8-111">До 1 милион профила по извозу у Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="1cae8-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="1cae8-112">Извоз у Sendinblue је ограничен на сегменте.</span><span class="sxs-lookup"><span data-stu-id="1cae8-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="1cae8-113">Извоз сегмената са укупно милион профила може трајати до 90 минута.</span><span class="sxs-lookup"><span data-stu-id="1cae8-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="1cae8-114">Број профила које можете да извезете у Sendinblue зависи од вашег уговора са услугом Sendinblue и ограничен је њиме.</span><span class="sxs-lookup"><span data-stu-id="1cae8-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="1cae8-115">Подешавање везе са услугом Sendinblue</span><span class="sxs-lookup"><span data-stu-id="1cae8-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="1cae8-116">Идите на **Администратор** > **Везе**.</span><span class="sxs-lookup"><span data-stu-id="1cae8-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1cae8-117">Изаберите **Додај везу** и бирајте **Sendinblue** да бисте конфигурисали везу.</span><span class="sxs-lookup"><span data-stu-id="1cae8-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="1cae8-118">Дајте вези препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="1cae8-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1cae8-119">Име за приказ и врста везе описују ову везу.</span><span class="sxs-lookup"><span data-stu-id="1cae8-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1cae8-120">Препоручујемо да одаберете назив који објашњава сврху и циљ везе.</span><span class="sxs-lookup"><span data-stu-id="1cae8-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1cae8-121">Одаберите ко може да користи ову везу.</span><span class="sxs-lookup"><span data-stu-id="1cae8-121">Choose who can use this connection.</span></span> <span data-ttu-id="1cae8-122">Подразумевано су то само администратори.</span><span class="sxs-lookup"><span data-stu-id="1cae8-122">By default it's only administrators.</span></span> <span data-ttu-id="1cae8-123">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1cae8-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1cae8-124">Унесите свој **[Sendinblue API кључ](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="1cae8-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="1cae8-125">Изаберите **Слажем се** да бисте потврдили **Приватност и усклађеност података** и изаберите **Повежи се** за иницијализацију везе са услугом Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="1cae8-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="1cae8-126">Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1cae8-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="1cae8-127">Изаберите **Сачувај** да бисте креирали везу.</span><span class="sxs-lookup"><span data-stu-id="1cae8-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="1cae8-128">Конфигурисање извоза</span><span class="sxs-lookup"><span data-stu-id="1cae8-128">Configure an export</span></span>

<span data-ttu-id="1cae8-129">Овај извоз можете да конфигуришете ако имате приступ вези ове врсте.</span><span class="sxs-lookup"><span data-stu-id="1cae8-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1cae8-130">За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1cae8-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1cae8-131">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="1cae8-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1cae8-132">Да бисте креирали нови извоз, изаберите **Додај одредиште**.</span><span class="sxs-lookup"><span data-stu-id="1cae8-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1cae8-133">У пољу **Веза за извоз**, изаберите везу из одељка Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="1cae8-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="1cae8-134">Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.</span><span class="sxs-lookup"><span data-stu-id="1cae8-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1cae8-135">Унесите **ID Sendinblue листе**</span><span class="sxs-lookup"><span data-stu-id="1cae8-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="1cae8-136">У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном корисничком профилу које представља е-адресу клијента.</span><span class="sxs-lookup"><span data-stu-id="1cae8-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="1cae8-137">Опционално, можете да извезете поља **Име**, **Презиме** и **Телефон** да бисте креирали персонализованије адресе е-поште.</span><span class="sxs-lookup"><span data-stu-id="1cae8-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="1cae8-138">Изаберите **Додај атрибут** за мапирање ових поља.</span><span class="sxs-lookup"><span data-stu-id="1cae8-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="1cae8-139">Изаберите сегменте које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="1cae8-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="1cae8-140">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="1cae8-140">Select **Save**.</span></span>

<span data-ttu-id="1cae8-141">Чување извоза не покреће извоз одмах.</span><span class="sxs-lookup"><span data-stu-id="1cae8-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1cae8-142">Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1cae8-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1cae8-143">Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1cae8-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1cae8-144">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="1cae8-144">Data privacy and compliance</span></span>

<span data-ttu-id="1cae8-145">Када омогућите Dynamics 365 Customer Insights за пренос података у Sendinblue, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="1cae8-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1cae8-146">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Sendinblue испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="1cae8-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1cae8-147">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1cae8-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1cae8-148">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="1cae8-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
