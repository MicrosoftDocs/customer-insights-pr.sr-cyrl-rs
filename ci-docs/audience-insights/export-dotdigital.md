---
title: Извезите Customer Insights податке у DotDigital
description: Сазнајте како да конфигуришете везу и извезете у DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d08504856e1c673ef32433b83bf491d7f4e8cee4
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976864"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a><span data-ttu-id="bfadf-103">Извоз листи сегмената у DotDigital (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="bfadf-103">Export segment lists to DotDigital (preview)</span></span>

<span data-ttu-id="bfadf-104">Извезите сегменте обједињених корисничких профила у DotDigital адресаре и користите их за кампање, маркетинг путем е-поште и за изградњу сегмената купаца помоћу услуге DotDigital.</span><span class="sxs-lookup"><span data-stu-id="bfadf-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="bfadf-105">Предуслови за везу</span><span class="sxs-lookup"><span data-stu-id="bfadf-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="bfadf-106">Имате [DotDigital налог](https://dotdigital.com/) и одговарајуће акредитиве администратора.</span><span class="sxs-lookup"><span data-stu-id="bfadf-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="bfadf-107">Постоји постојећа публика у адресарима у услузи DotDigital и одговарајући ID-ови.</span><span class="sxs-lookup"><span data-stu-id="bfadf-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="bfadf-108">ID се може наћи у URL-у када одаберете и отворите адресар.</span><span class="sxs-lookup"><span data-stu-id="bfadf-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="bfadf-109">За више информација погледајте [адресаре за DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="bfadf-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="bfadf-110">[Конфигурисали сте сегменте](segments.md) у увидима о корисницима.</span><span class="sxs-lookup"><span data-stu-id="bfadf-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="bfadf-111">Обједињени кориснички профили у извезеним сегментима садрже поље које представља адресу е-поште.</span><span class="sxs-lookup"><span data-stu-id="bfadf-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="bfadf-112">Позната ограничења</span><span class="sxs-lookup"><span data-stu-id="bfadf-112">Known limitations</span></span>

- <span data-ttu-id="bfadf-113">До 1 милион профила по извозу у услузи DotDigital.</span><span class="sxs-lookup"><span data-stu-id="bfadf-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="bfadf-114">Извоз у DotDigital је ограничен на сегменте.</span><span class="sxs-lookup"><span data-stu-id="bfadf-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="bfadf-115">Извоз сегмената са укупно 1 милион профила може трајати до 3 сата због ограничења на страни добављача.</span><span class="sxs-lookup"><span data-stu-id="bfadf-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="bfadf-116">Број профила које можете да извезете у DotDigital зависи од и ограничен је вашим уговором са компанијом DotDigital.</span><span class="sxs-lookup"><span data-stu-id="bfadf-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="bfadf-117">Подешавање везе у услузи DotDigital</span><span class="sxs-lookup"><span data-stu-id="bfadf-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="bfadf-118">Идите на **Администратор** > **Везе**.</span><span class="sxs-lookup"><span data-stu-id="bfadf-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="bfadf-119">Изаберите **Додај везу** и бирајте **DotDigital** да бисте конфигурисали везу.</span><span class="sxs-lookup"><span data-stu-id="bfadf-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="bfadf-120">Дајте вези препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="bfadf-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="bfadf-121">Име за приказ и врста везе описују ову везу.</span><span class="sxs-lookup"><span data-stu-id="bfadf-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="bfadf-122">Препоручујемо да одаберете назив који објашњава сврху и циљ везе.</span><span class="sxs-lookup"><span data-stu-id="bfadf-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="bfadf-123">Одаберите ко може да користи ову везу.</span><span class="sxs-lookup"><span data-stu-id="bfadf-123">Choose who can use this connection.</span></span> <span data-ttu-id="bfadf-124">Ако ништа не предузмете, подразумевани ће бити Администратори.</span><span class="sxs-lookup"><span data-stu-id="bfadf-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="bfadf-125">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="bfadf-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="bfadf-126">Унесите своје **корисничко име и лозинку за DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="bfadf-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="bfadf-127">Унесите **[ID DotDigital адресара](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="bfadf-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="bfadf-128">Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.</span><span class="sxs-lookup"><span data-stu-id="bfadf-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="bfadf-129">Изаберите **Повежи се** за иницијализацију везе са услугом DotDigital.</span><span class="sxs-lookup"><span data-stu-id="bfadf-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="bfadf-130">Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="bfadf-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="bfadf-131">Изаберите **Сачувај** да бисте креирали везу.</span><span class="sxs-lookup"><span data-stu-id="bfadf-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="bfadf-132">Конфигурисање извоза</span><span class="sxs-lookup"><span data-stu-id="bfadf-132">Configure an export</span></span>

<span data-ttu-id="bfadf-133">Овај извоз можете да конфигуришете ако имате приступ вези ове врсте.</span><span class="sxs-lookup"><span data-stu-id="bfadf-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="bfadf-134">За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="bfadf-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="bfadf-135">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="bfadf-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bfadf-136">Да бисте креирали нови извоз, изаберите **Додај одредиште**.</span><span class="sxs-lookup"><span data-stu-id="bfadf-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="bfadf-137">У пољу **Веза за извоз**, одаберите везу из одељка DotDigital.</span><span class="sxs-lookup"><span data-stu-id="bfadf-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="bfadf-138">Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.</span><span class="sxs-lookup"><span data-stu-id="bfadf-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="bfadf-139">У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном корисничком профилу које представља е-адресу клијента.</span><span class="sxs-lookup"><span data-stu-id="bfadf-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="bfadf-140">Поновите исте кораке за друга опционална поља као што су **Име**, **Презиме**, **Пуно име**, **Пол** и **Поштански број**.</span><span class="sxs-lookup"><span data-stu-id="bfadf-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="bfadf-141">Изаберите сегменте које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="bfadf-141">Select the segments you want to export.</span></span> <span data-ttu-id="bfadf-142">У услузи DotDigital можете укупно извести до 1 милион корисничких профила.</span><span class="sxs-lookup"><span data-stu-id="bfadf-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="bfadf-143">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="bfadf-143">Select **Save**.</span></span>

<span data-ttu-id="bfadf-144">Чување извоза не покреће извоз одмах.</span><span class="sxs-lookup"><span data-stu-id="bfadf-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="bfadf-145">Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bfadf-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bfadf-146">Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="bfadf-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="bfadf-147">У услузи DotDigital сада можете да пронађете своје сегменте у [DotDigital адресарима](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="bfadf-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bfadf-148">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="bfadf-148">Data privacy and compliance</span></span>

<span data-ttu-id="bfadf-149">Када омогућите да Dynamics 365 Customer Insights преноси податке у DotDigital, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="bfadf-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bfadf-150">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да DotDigital испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="bfadf-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="bfadf-151">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="bfadf-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="bfadf-152">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="bfadf-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
