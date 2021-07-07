---
title: Извезите Customer Insights податке у менаџер Facebook огласа
description: Сазнајте како да конфигуришете везу и извезете у Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e20c7b7fd3989d7621cb7765f38b85c8ab4adfcb
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305128"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="a1de2-103">Извоз сегмената у Facebook Ads Manager (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="a1de2-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="a1de2-104">Извезите сегменте обједињених корисничких профила у Facebook менаџер огласа за креирање кампања на Facebook и Instagram.</span><span class="sxs-lookup"><span data-stu-id="a1de2-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="a1de2-105">Предуслови за везу</span><span class="sxs-lookup"><span data-stu-id="a1de2-105">Prerequisites for connection</span></span>

- <span data-ttu-id="a1de2-106">Потребно је да имате [**Facebook Ads налог**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) који укључује [**Facebook пословни налог**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="a1de2-106">You need to have a [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="a1de2-107">Морате бити администратор [**Facebook Ads налога**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="a1de2-107">You need to be an administrator on the [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a1de2-108">Позната ограничења</span><span class="sxs-lookup"><span data-stu-id="a1de2-108">Known limitations</span></span>

- <span data-ttu-id="a1de2-109">До 10 милиона профила клијената по извозу у Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="a1de2-109">Up to 10 million customer profiles per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="a1de2-110">Извоз у Facebook Ads Manager је ограничен на сегменте.</span><span class="sxs-lookup"><span data-stu-id="a1de2-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="a1de2-111">Направите или ажурирајте прилагођену циљну групу у Facebook само типа *листа клијената*.</span><span class="sxs-lookup"><span data-stu-id="a1de2-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="a1de2-112">Извоз сегмената са укупно 10 милиона профила може потрајати до 90 минута.</span><span class="sxs-lookup"><span data-stu-id="a1de2-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="a1de2-113">Подешавање везе са услугом Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="a1de2-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="a1de2-114">Да би корисници могли да направе извоз, администратор мора да конфигурише везу са услугом и дозволи сарадницима да користе везу.</span><span class="sxs-lookup"><span data-stu-id="a1de2-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="a1de2-115">Идите на **Администратор** > **Везе**.</span><span class="sxs-lookup"><span data-stu-id="a1de2-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a1de2-116">Изаберите **Додај везу** и бирајте **Facebook Ads Manager** да бисте конфигурисали везу.</span><span class="sxs-lookup"><span data-stu-id="a1de2-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="a1de2-117">Дајте вези препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="a1de2-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a1de2-118">Име за приказ и врста везе описују ову везу.</span><span class="sxs-lookup"><span data-stu-id="a1de2-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a1de2-119">Препоручујемо да одаберете назив који објашњава сврху и циљ везе.</span><span class="sxs-lookup"><span data-stu-id="a1de2-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a1de2-120">Одаберите ко може да користи ову везу.</span><span class="sxs-lookup"><span data-stu-id="a1de2-120">Choose who can use this connection.</span></span> <span data-ttu-id="a1de2-121">Ако ништа не предузмете, подразумевани ће бити Администратори.</span><span class="sxs-lookup"><span data-stu-id="a1de2-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a1de2-122">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a1de2-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a1de2-123">Потврдите веродостојност помоћу услуге Facebook Ads:</span><span class="sxs-lookup"><span data-stu-id="a1de2-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="a1de2-124">Изаберите **Настави са Facebook-ом** да бисте се пријавили на свој Facebook Ads налог.</span><span class="sxs-lookup"><span data-stu-id="a1de2-124">Select **Continue with Facebook** to sign in to your Facebook Ads account.</span></span>

   1. <span data-ttu-id="a1de2-125">Дајте дозволу **ads_management** након потврде идентитета са услугом Facebook.</span><span class="sxs-lookup"><span data-stu-id="a1de2-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="a1de2-126">Изаберите **Facebook налог за оглашавање** са којим желите да радите.</span><span class="sxs-lookup"><span data-stu-id="a1de2-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="a1de2-127">Изаберите **Постојећа прилагођена циљна група** са падајуће листе или креирајте **нову прилагођену циљну групу**.</span><span class="sxs-lookup"><span data-stu-id="a1de2-127">Select an **Existing custom audience** from the dropdown list or create a **New custom audience**.</span></span> <span data-ttu-id="a1de2-128">За више информација погледајте [**Публика у Facebook менаџеру огласа**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="a1de2-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="a1de2-129">Овим извозом у услузи Facebook можете само да креирате или ажурирате прилагођену циљну групу типа *листа клијената*.</span><span class="sxs-lookup"><span data-stu-id="a1de2-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="a1de2-130">У неким случајевима, на падајућој листи видите прилагођену циљну групу различитих врста.</span><span class="sxs-lookup"><span data-stu-id="a1de2-130">In some cases, you see custom audiences of different types in the dropdown list.</span></span> <span data-ttu-id="a1de2-131">Избор неког другог типа уместо *листе клијената* довешће до неуспелог извоза.</span><span class="sxs-lookup"><span data-stu-id="a1de2-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="a1de2-132">Прегледајте **Приватност података и усклађеност** и изаберите **Слажем се**.</span><span class="sxs-lookup"><span data-stu-id="a1de2-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="a1de2-133">Изаберите **Сачувај** да бисте креирали везу.</span><span class="sxs-lookup"><span data-stu-id="a1de2-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a1de2-134">Конфигурисање извоза</span><span class="sxs-lookup"><span data-stu-id="a1de2-134">Configure an export</span></span>

<span data-ttu-id="a1de2-135">Овај извоз можете да конфигуришете ако имате приступ вези ове врсте.</span><span class="sxs-lookup"><span data-stu-id="a1de2-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a1de2-136">За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a1de2-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a1de2-137">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="a1de2-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a1de2-138">Да бисте креирали нови извоз, изаберите **Додај одредиште**.</span><span class="sxs-lookup"><span data-stu-id="a1de2-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="a1de2-139">У пољу **Веза за извоз** одаберите везу из одељка **Facebook Ads Manager**.</span><span class="sxs-lookup"><span data-stu-id="a1de2-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="a1de2-140">Ако не видите назив овог одељка, тада вам нису доступне везе овог типа.</span><span class="sxs-lookup"><span data-stu-id="a1de2-140">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="a1de2-141">У **Изаберите поље идентификатора кључа**, изаберите **Е-пошта**, **Име и адреса** или **Телефон** који бисте послали у Facebook менаџер огласа.</span><span class="sxs-lookup"><span data-stu-id="a1de2-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="a1de2-142">Дајте вези препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="a1de2-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="a1de2-143">Мапирајте одговарајуће атрибуте вашег обједињеног ентитета клијента за изабрани идентификатор кључа.</span><span class="sxs-lookup"><span data-stu-id="a1de2-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > [!TIP]
   > <span data-ttu-id="a1de2-144">Најбоље шансе за подударање настају ако одаберете опцију **Е-пошта** као кључни идентификатор.</span><span class="sxs-lookup"><span data-stu-id="a1de2-144">The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="a1de2-145">Додавање додатних идентификатора може побољшати подударање.</span><span class="sxs-lookup"><span data-stu-id="a1de2-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="a1de2-146">Изаберите **Додај атрибут** да бисте мапирали више атрибута за слање у Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="a1de2-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="a1de2-147">Атрибути из услуге Facebook Ads Manager се пресликавају на следећа имена прилагођена кориснику: **FN** = **Име**, **LN** = **Презиме**, **FI** = **Прво слово имена**, **PHONE** = **Телефон**, **GEN** = **Пол**, **DOB** = **Датум рођења**, **ST** = **Држава**, **CT** = **Град**, **ZIP** = **Поштански број**, **COUNTRY** = **Земља**</span><span class="sxs-lookup"><span data-stu-id="a1de2-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / ZIP Code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="a1de2-148">Изаберите сегменте које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="a1de2-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="a1de2-149">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="a1de2-149">Select **Save**.</span></span>

<span data-ttu-id="a1de2-150">Чување извоза не покреће извоз одмах.</span><span class="sxs-lookup"><span data-stu-id="a1de2-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a1de2-151">Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a1de2-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="a1de2-152">Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a1de2-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a1de2-153">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="a1de2-153">Data privacy and compliance</span></span>

<span data-ttu-id="a1de2-154">Када омогућите да Dynamics 365 Customer Insights преноси податке у менаџер Facebook огласа, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="a1de2-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a1de2-155">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Facebook огласи испуњавају све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="a1de2-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="a1de2-156">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a1de2-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a1de2-157">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="a1de2-157">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
