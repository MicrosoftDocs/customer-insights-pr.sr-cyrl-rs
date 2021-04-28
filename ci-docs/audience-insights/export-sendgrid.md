---
title: Извезите Customer Insights податке у SendGrid
description: Сазнајте како да конфигуришете везу и извезете у SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a4c64cf77c682e07f3d0759c43355336b5806fc8
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759783"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="acca4-103">Извоз сегмената у SendGrid (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="acca4-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="acca4-104">Извезите сегменте обједињених профила клијената у SendGrid листе контаката и користите их за кампање и маркетинг у услузи SendGrid.</span><span class="sxs-lookup"><span data-stu-id="acca4-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="acca4-105">Предуслови за везу</span><span class="sxs-lookup"><span data-stu-id="acca4-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="acca4-106">Имате [SendGrid налог](https://sendgrid.com/) и одговарајуће акредитиве администратора.</span><span class="sxs-lookup"><span data-stu-id="acca4-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="acca4-107">Постоје постојеће листе контаката у услузи SendGrid и одговарајући ID-ови.</span><span class="sxs-lookup"><span data-stu-id="acca4-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="acca4-108">За више информација погледајте [SendGrid – Управљање контактима](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="acca4-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="acca4-109">[Конфигурисали сте сегменте](segments.md) у увидима о корисницима.</span><span class="sxs-lookup"><span data-stu-id="acca4-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="acca4-110">Обједињени профили клијената у извезеним сегментима садрже поље које представља адресу е-поште.</span><span class="sxs-lookup"><span data-stu-id="acca4-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="acca4-111">Позната ограничења</span><span class="sxs-lookup"><span data-stu-id="acca4-111">Known limitations</span></span>

- <span data-ttu-id="acca4-112">Укупно до 100.000 профила у SendGrid.</span><span class="sxs-lookup"><span data-stu-id="acca4-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="acca4-113">Извоз у SendGrid је ограничен на сегменте.</span><span class="sxs-lookup"><span data-stu-id="acca4-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="acca4-114">Извоз до 100.000 профила у SendGrid може да потраје до неколико сати.</span><span class="sxs-lookup"><span data-stu-id="acca4-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="acca4-115">Број профила које можете да извезете у SendGrid зависи од вашег уговора са компанијом SendGrid и ограничен је њиме.</span><span class="sxs-lookup"><span data-stu-id="acca4-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="acca4-116">Подешавање везе у услузи SendGrid</span><span class="sxs-lookup"><span data-stu-id="acca4-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="acca4-117">Идите на **Администратор** > **Везе**.</span><span class="sxs-lookup"><span data-stu-id="acca4-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="acca4-118">Изаберите **Додај везу** и бирајте **SendGrid** да бисте конфигурисали везу.</span><span class="sxs-lookup"><span data-stu-id="acca4-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="acca4-119">Дајте вези препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="acca4-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="acca4-120">Име за приказ и врста везе описују ову везу.</span><span class="sxs-lookup"><span data-stu-id="acca4-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="acca4-121">Препоручујемо да одаберете назив који објашњава сврху и циљ везе.</span><span class="sxs-lookup"><span data-stu-id="acca4-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="acca4-122">Одаберите ко може да користи ову везу.</span><span class="sxs-lookup"><span data-stu-id="acca4-122">Choose who can use this connection.</span></span> <span data-ttu-id="acca4-123">Ако ништа не предузмете, подразумевани ће бити Администратори.</span><span class="sxs-lookup"><span data-stu-id="acca4-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="acca4-124">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="acca4-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="acca4-125">Унесите свој **SendGrid API кључ** [SendGrid API кључ](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="acca4-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="acca4-126">Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.</span><span class="sxs-lookup"><span data-stu-id="acca4-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="acca4-127">Изаберите **Повежи се** за иницијализацију везе са услугом SendGrid.</span><span class="sxs-lookup"><span data-stu-id="acca4-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="acca4-128">Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="acca4-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="acca4-129">Изаберите **Сачувај** да бисте креирали везу.</span><span class="sxs-lookup"><span data-stu-id="acca4-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="acca4-130">Конфигурисање извоза</span><span class="sxs-lookup"><span data-stu-id="acca4-130">Configure an export</span></span>

<span data-ttu-id="acca4-131">Овај извоз можете да конфигуришете ако имате приступ вези ове врсте.</span><span class="sxs-lookup"><span data-stu-id="acca4-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="acca4-132">За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="acca4-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="acca4-133">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="acca4-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="acca4-134">Да бисте креирали нови извоз, изаберите **Додај одредиште**.</span><span class="sxs-lookup"><span data-stu-id="acca4-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="acca4-135">У пољу **Веза за извоз**, одаберите везу из одељка SendGrid.</span><span class="sxs-lookup"><span data-stu-id="acca4-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="acca4-136">Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.</span><span class="sxs-lookup"><span data-stu-id="acca4-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="acca4-137">Унесите **[ID SendGrid листе](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="acca4-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="acca4-138">У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном профилу клијента које представља е-адресу клијента.</span><span class="sxs-lookup"><span data-stu-id="acca4-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="acca4-139">Поновите исте кораке за друга опционална поља као што су **Име**, **Презиме**, **Земља/Регион**, **Држава**, **Град** и **Поштански број**.</span><span class="sxs-lookup"><span data-stu-id="acca4-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="acca4-140">Изаберите сегменте које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="acca4-140">Select the segments you want to export.</span></span> <span data-ttu-id="acca4-141">Изричито **препоручујемо да не извозите укупно више од 100.000 профила клијената** у SendGrid.</span><span class="sxs-lookup"><span data-stu-id="acca4-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="acca4-142">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="acca4-142">Select **Save**.</span></span>

<span data-ttu-id="acca4-143">Чување извоза не покреће извоз одмах.</span><span class="sxs-lookup"><span data-stu-id="acca4-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="acca4-144">Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="acca4-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="acca4-145">Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="acca4-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="acca4-146">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="acca4-146">Data privacy and compliance</span></span>

<span data-ttu-id="acca4-147">Када омогућите да Dynamics 365 Customer Insights преноси податке у SendGrid, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="acca4-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="acca4-148">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да SendGrid испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="acca4-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="acca4-149">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="acca4-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="acca4-150">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="acca4-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]