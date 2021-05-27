---
title: Извезите Customer Insights податке у Google огласима
description: Сазнајте како да конфигуришете везу и извезете у Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 73f3257a3ae6e8423f45410546535df5e3b400ce
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976336"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="7ee1a-103">Извоз сегмената у Google Ads (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="7ee1a-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="7ee1a-104">Извезите сегменте обједињених корисничких профила у листу корисника Google огласа и користите их за оглашавање у Google претрази, на Gmail-у, YouTube-у и Google мрежи мултимедијалног оглашавања.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="7ee1a-105">Предуслови за везу</span><span class="sxs-lookup"><span data-stu-id="7ee1a-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="7ee1a-106">Имате [налог Google огласа](https://ads.google.com/) и одговарајуће акредитиве администратора.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="7ee1a-107">Ви имате [одобрени токен за Google Ads програмера](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="7ee1a-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="7ee1a-108">Испуњавате захтеве [политике подударања клијената](https://support.google.com/adspolicy/answer/6299717)</span><span class="sxs-lookup"><span data-stu-id="7ee1a-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="7ee1a-109">Испуњавате захтеве [величине листа за поновно оглашавање](https://support.google.com/google-ads/answer/7558048)</span><span class="sxs-lookup"><span data-stu-id="7ee1a-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="7ee1a-110">Постоји постојећа публика у Google огласима и одговарајући ID-ови.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="7ee1a-111">За више информација погледајте [Корисници Google огласа](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="7ee1a-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="7ee1a-112">Имате [конфигурисане сегменте](segments.md)</span><span class="sxs-lookup"><span data-stu-id="7ee1a-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="7ee1a-113">Обједињени кориснички профили у извезеним сегментима садрже поља која представљају адресу е-поште, име и презиме</span><span class="sxs-lookup"><span data-stu-id="7ee1a-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="7ee1a-114">Позната ограничења</span><span class="sxs-lookup"><span data-stu-id="7ee1a-114">Known limitations</span></span>

- <span data-ttu-id="7ee1a-115">До 1 милион профила по извозу у Google огласима.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="7ee1a-116">Извоз у Google огласе је ограничен на сегменте.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="7ee1a-117">Извоз сегмената са укупно 1 милион профила може трајати до 5 минута због ограничења на страни добављача.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="7ee1a-118">Подударање у Google огласима може да потраје до 48 сати.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="7ee1a-119">Подешавање везе са услугом Google Ads</span><span class="sxs-lookup"><span data-stu-id="7ee1a-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="7ee1a-120">Идите на **Администратор** > **Везе**.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="7ee1a-121">Изаберите **Додај везу** и бирајте **Google Ads** да бисте конфигурисали везу.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="7ee1a-122">Дајте вези препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="7ee1a-123">Име за приказ и врста везе описују ову везу.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="7ee1a-124">Препоручујемо да одаберете назив који објашњава сврху и циљ везе.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="7ee1a-125">Одаберите ко може да користи ову везу.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-125">Choose who can use this connection.</span></span> <span data-ttu-id="7ee1a-126">Ако ништа не предузмете, подразумевани ће бити Администратори.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="7ee1a-127">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="7ee1a-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="7ee1a-128">Унесите **[ID клијента за Google огласе](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="7ee1a-129">Унесите **[токен одобреног програмера за Google огласе](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="7ee1a-130">Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="7ee1a-131">Изаберите **Потврдите идентитет у Google огласима** и наведите акредитиве за Google огласе.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="7ee1a-132">Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="7ee1a-133">Изаберите **Сачувај** да бисте креирали везу.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="7ee1a-134">Конфигурисање извоза</span><span class="sxs-lookup"><span data-stu-id="7ee1a-134">Configure an export</span></span>

<span data-ttu-id="7ee1a-135">Овај извоз можете да конфигуришете ако имате приступ вези ове врсте.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="7ee1a-136">За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="7ee1a-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="7ee1a-137">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7ee1a-138">Да бисте креирали нови извоз, изаберите **Додај одредиште**.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="7ee1a-139">У пољу **Веза за извоз**, одаберите везу из одељка Google Ads.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="7ee1a-140">Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="7ee1a-141">Унесите **[ID корисника за Google огласе](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** и изаберите **Повежите се** да бисте започели повезивање са Google огласима.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="7ee1a-142">У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном корисничком профилу које представља е-адресу клијента.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="7ee1a-143">Поновите исте кораке за поља **Име** и **Презиме**.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="7ee1a-144">Изаберите сегменте које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-144">Select the segments you want to export.</span></span> <span data-ttu-id="7ee1a-145">У Google огласима можете укупно извести до 1 милион корисничких профила.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="7ee1a-146">Чување извоза не покреће извоз одмах.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="7ee1a-147">Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7ee1a-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7ee1a-148">Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="7ee1a-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7ee1a-149">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="7ee1a-149">Data privacy and compliance</span></span>

<span data-ttu-id="7ee1a-150">Када омогућите да Dynamics 365 Customer Insights преноси податке у Google огласе, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7ee1a-151">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Google огласи испуњавају све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="7ee1a-152">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="7ee1a-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="7ee1a-153">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="7ee1a-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
