---
title: Извезите Customer Insights податке у SendGrid
description: Сазнајте како да конфигуришете везу са услугом SendGrid.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268750"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="244ae-103">Конектор за SendGrid (преглед)</span><span class="sxs-lookup"><span data-stu-id="244ae-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="244ae-104">Извезите сегменте обједињених профила клијената у SendGrid листе контаката и користите их за кампање и маркетинг у услузи SendGrid.</span><span class="sxs-lookup"><span data-stu-id="244ae-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="244ae-105">Предуслови</span><span class="sxs-lookup"><span data-stu-id="244ae-105">Prerequisites</span></span>

-   <span data-ttu-id="244ae-106">Имате [SendGrid налог](https://sendgrid.com/) и одговарајуће акредитиве администратора.</span><span class="sxs-lookup"><span data-stu-id="244ae-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="244ae-107">Постоје постојеће листе контаката у услузи SendGrid и одговарајући ID-ови.</span><span class="sxs-lookup"><span data-stu-id="244ae-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="244ae-108">За више информација погледајте [SendGrid – Управљање контактима](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="244ae-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="244ae-109">[Конфигурисали сте сегменте](segments.md) у увидима о корисницима.</span><span class="sxs-lookup"><span data-stu-id="244ae-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="244ae-110">Обједињени профили клијената у извезеним сегментима садрже поље које представља адресу е-поште.</span><span class="sxs-lookup"><span data-stu-id="244ae-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="244ae-111">Повежите се са услугом SendGrid</span><span class="sxs-lookup"><span data-stu-id="244ae-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="244ae-112">Идите на **Администратор** > **Одредишта за извоз**.</span><span class="sxs-lookup"><span data-stu-id="244ae-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="244ae-113">У делу **SendGrid** изаберите **Подеси**.</span><span class="sxs-lookup"><span data-stu-id="244ae-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="244ae-114">Дајте одредишту за извоз препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="244ae-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Окно за конфигурацију извоза у услузи SendGrid.":::

1. <span data-ttu-id="244ae-116">Унесите свој **SendGrid API кључ** [SendGrid API кључ](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="244ae-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="244ae-117">Унесите **[ID SendGrid листе](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="244ae-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="244ae-118">Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.</span><span class="sxs-lookup"><span data-stu-id="244ae-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="244ae-119">Изаберите **Повежи се** за иницијализацију везе са услугом SendGrid.</span><span class="sxs-lookup"><span data-stu-id="244ae-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="244ae-120">Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="244ae-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="244ae-121">Изаберите **Следеће** да бисте конфигурисали извоз.</span><span class="sxs-lookup"><span data-stu-id="244ae-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="244ae-122">Конфигурисање конектора</span><span class="sxs-lookup"><span data-stu-id="244ae-122">Configure the connector</span></span>

1. <span data-ttu-id="244ae-123">У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном профилу клијента које представља е-адресу клијента.</span><span class="sxs-lookup"><span data-stu-id="244ae-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="244ae-124">Поновите исте кораке за друга опционална поља као што су **Име**, **Презиме**, **Земља/Регион**, **Држава**, **Град** и **Поштански број**.</span><span class="sxs-lookup"><span data-stu-id="244ae-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="244ae-125">Изаберите сегменте које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="244ae-125">Select the segments you want to export.</span></span> <span data-ttu-id="244ae-126">Изричито **препоручујемо да не извозите укупно више од 100.000 профила клијената** у SendGrid.</span><span class="sxs-lookup"><span data-stu-id="244ae-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="244ae-127">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="244ae-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="244ae-128">Извоз података</span><span class="sxs-lookup"><span data-stu-id="244ae-128">Export the data</span></span>

<span data-ttu-id="244ae-129">Можете да [извезете податке на захтев](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="244ae-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="244ae-130">Извоз ће се такође покренути са сваким [планираним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="244ae-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="244ae-131">Позната ограничења</span><span class="sxs-lookup"><span data-stu-id="244ae-131">Known limitations</span></span>

- <span data-ttu-id="244ae-132">Укупно до 100.000 профила у SendGrid.</span><span class="sxs-lookup"><span data-stu-id="244ae-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="244ae-133">Извоз у SendGrid је ограничен на сегменте.</span><span class="sxs-lookup"><span data-stu-id="244ae-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="244ae-134">Извоз до 100.000 профила у SendGrid може да потраје до неколико сати.</span><span class="sxs-lookup"><span data-stu-id="244ae-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="244ae-135">Број профила које можете да извезете у SendGrid зависи од вашег уговора са компанијом SendGrid и ограничен је њиме.</span><span class="sxs-lookup"><span data-stu-id="244ae-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="244ae-136">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="244ae-136">Data privacy and compliance</span></span>

<span data-ttu-id="244ae-137">Када омогућите да Dynamics 365 Customer Insights преноси податке у SendGrid, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="244ae-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="244ae-138">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да SendGrid испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="244ae-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="244ae-139">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="244ae-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="244ae-140">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="244ae-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]