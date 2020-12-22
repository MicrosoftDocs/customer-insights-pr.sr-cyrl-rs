---
title: Извезите Customer Insights податке у менаџер Facebook огласа
description: Научите како да конфигуришете везу у оквиру Facebook менаџера огласа.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8260e3b5e529f3d54678d9d6e11aebb2795e27fd
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643701"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="1bd8d-103">Конектор за Facebook менаџер огласа (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="1bd8d-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="1bd8d-104">Извезите сегменте обједињених корисничких профила у Facebook менаџер огласа за креирање кампања на Facebook и Instagram.</span><span class="sxs-lookup"><span data-stu-id="1bd8d-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1bd8d-105">Предуслови</span><span class="sxs-lookup"><span data-stu-id="1bd8d-105">Prerequisites</span></span>

- <span data-ttu-id="1bd8d-106">Морате да имате [**Facebook** налог за оглашавање](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) који укључује [**Facebook пословни налог**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="1bd8d-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="1bd8d-107">Морате да будете администратор на [**Facebook налогу за оглашавање**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="1bd8d-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="1bd8d-108">Повезивање са Facebook менаџером огласа</span><span class="sxs-lookup"><span data-stu-id="1bd8d-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="1bd8d-109">Идите на **Администратор** > **Одредишта за извоз**.</span><span class="sxs-lookup"><span data-stu-id="1bd8d-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="1bd8d-110">Под **Facebook менаџер огласа**, изаберите **Постави**.</span><span class="sxs-lookup"><span data-stu-id="1bd8d-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="1bd8d-111">Дајте одредишту за извоз препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="1bd8d-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="1bd8d-112">Изаберите **Настави са Facebook** да се пријавите на свој Facebook налог за оглашавање.</span><span class="sxs-lookup"><span data-stu-id="1bd8d-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="1bd8d-113">Дајте дозволу **ads_management** након потврде идентитета са услугом Facebook.</span><span class="sxs-lookup"><span data-stu-id="1bd8d-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="1bd8d-114">Изаберите **Facebook налог за оглашавање** са којим желите да радите.</span><span class="sxs-lookup"><span data-stu-id="1bd8d-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="1bd8d-115">Изаберите **Постојећа прилагођена циљна група** са падајуће листе или креирајте **Нову прилагођену циљну групу**.</span><span class="sxs-lookup"><span data-stu-id="1bd8d-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="1bd8d-116">За више информација погледајте [**Публика у Facebook менаџеру огласа**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="1bd8d-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="1bd8d-117">Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.</span><span class="sxs-lookup"><span data-stu-id="1bd8d-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1bd8d-118">Изаберите **Следеће** да бисте конфигурисали извоз.</span><span class="sxs-lookup"><span data-stu-id="1bd8d-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="1bd8d-119">Конфигурисање конектора</span><span class="sxs-lookup"><span data-stu-id="1bd8d-119">Configure the connector</span></span>

1. <span data-ttu-id="1bd8d-120">У **Изаберите поље идентификатора кључа**, изаберите **Е-пошта**, **Име и адреса** или **Телефон** који бисте послали у Facebook менаџер огласа.</span><span class="sxs-lookup"><span data-stu-id="1bd8d-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="1bd8d-121">Мапирајте одговарајуће атрибуте вашег обједињеног ентитета клијента за изабрани идентификатор кључа.</span><span class="sxs-lookup"><span data-stu-id="1bd8d-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="1bd8d-122">[САВЕТ] Најбоље шансе за подударање настају ако одаберете **Е-пошта** као кључни идентификатор.</span><span class="sxs-lookup"><span data-stu-id="1bd8d-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="1bd8d-123">Додавање додатних идентификатора може побољшати подударање.</span><span class="sxs-lookup"><span data-stu-id="1bd8d-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="1bd8d-124">Изаберите **Додај атрибут** да бисте мапирали додатне атрибуте које треба послати у Facebook менаџер огласа.</span><span class="sxs-lookup"><span data-stu-id="1bd8d-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="1bd8d-125">Атрибути из Facebook менаџера огласа се пресликавају на следећа имена прилагођена кориснику: **ИМЕ** = **Име**, **ПР** = **Презиме**, **ПС** = **Прво слово имена**, **ТЕЛ** = **Телефон**, **ПОЛ** = **Пол**, **ДРЂ** = **Датум рођења**, **ДРЖ** = **Држава**, **ГР** = **Град**, **П. БР.** = **Поштански број**, **ЗМ** = **Земља**</span><span class="sxs-lookup"><span data-stu-id="1bd8d-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="1bd8d-126">Изаберите сегменте које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="1bd8d-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="1bd8d-127">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="1bd8d-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="1bd8d-128">Извоз података</span><span class="sxs-lookup"><span data-stu-id="1bd8d-128">Export the data</span></span>

<span data-ttu-id="1bd8d-129">Можете да [извезете податке на захтев](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="1bd8d-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="1bd8d-130">Извоз ће се такође покренути са сваким [планираним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1bd8d-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1bd8d-131">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="1bd8d-131">Data privacy and compliance</span></span>

<span data-ttu-id="1bd8d-132">Када омогућите да Dynamics 365 Customer Insights преноси податке у менаџер Facebook огласа, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="1bd8d-132">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1bd8d-133">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Facebook огласи испуњавају све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="1bd8d-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="1bd8d-134">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1bd8d-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1bd8d-135">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="1bd8d-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
