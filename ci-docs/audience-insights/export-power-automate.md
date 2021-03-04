---
title: Power Automate конектор | Microsoft Docs
description: Креирајте токове у услузи Microsoft Power Automate из услуге Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268842"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="a0f73-103">Power Automate конектор (преглед)</span><span class="sxs-lookup"><span data-stu-id="a0f73-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="a0f73-104">Покрените одређене догађаје који се појављују аутоматски када се промене подаци и управљајте сложенијим токовима директно у услузи [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="a0f73-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="a0f73-105">Power Automate окидачи</span><span class="sxs-lookup"><span data-stu-id="a0f73-105">Power Automate triggers</span></span>

<span data-ttu-id="a0f73-106">Користите окидаче да креирате токове у облаку и аутоматизујете понављајуће задатке, као што су обавештења или напредније радње.</span><span class="sxs-lookup"><span data-stu-id="a0f73-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="a0f73-107">Покрените када не успе освежавање извора података.</span><span class="sxs-lookup"><span data-stu-id="a0f73-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="a0f73-108">Покрените када успе освежавање извора података.</span><span class="sxs-lookup"><span data-stu-id="a0f73-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="a0f73-109">Покрените када се пређе гранична вредност за сегмент.</span><span class="sxs-lookup"><span data-stu-id="a0f73-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="a0f73-110">Окидач је ограничен на прекорачење граничне вредности.</span><span class="sxs-lookup"><span data-stu-id="a0f73-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="a0f73-111">Покрените када се пређе гранична вредност за пословну меру.</span><span class="sxs-lookup"><span data-stu-id="a0f73-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="a0f73-112">Окидач је ограничен на прекорачење граничне вредности.</span><span class="sxs-lookup"><span data-stu-id="a0f73-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="a0f73-113">Активира се када се заврши потпуно освежавање (извора података, сегмената, мера...).</span><span class="sxs-lookup"><span data-stu-id="a0f73-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="a0f73-114">Покрените када се заврши освежавање процеса обједињавања (мапирање, подударање, спајање).</span><span class="sxs-lookup"><span data-stu-id="a0f73-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="a0f73-115">[Конфигурисање окидача у услузи Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="a0f73-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="a0f73-116">Power Automate радње</span><span class="sxs-lookup"><span data-stu-id="a0f73-116">Power Automate actions</span></span>
<span data-ttu-id="a0f73-117">Power Automate конектор пружа друге радње осим доступних окидача.</span><span class="sxs-lookup"><span data-stu-id="a0f73-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="a0f73-118">За више информација погледајте [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="a0f73-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="a0f73-119">Креирање Power Automate тока</span><span class="sxs-lookup"><span data-stu-id="a0f73-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="a0f73-120">У увидима о корисницима идите на **Администратор** > **Одредишта за извоз**.</span><span class="sxs-lookup"><span data-stu-id="a0f73-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a0f73-121">На плочици **Power Automate** изаберите **Подеси**.</span><span class="sxs-lookup"><span data-stu-id="a0f73-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="a0f73-122">Отвара се Customer Insights конектор (преглед) у услузи Power Automate.</span><span class="sxs-lookup"><span data-stu-id="a0f73-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="a0f73-123">**Пријавите се** у Power Automate.</span><span class="sxs-lookup"><span data-stu-id="a0f73-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="a0f73-124">Изаберите један од доступних окидача и додајте још корака свом новом току.</span><span class="sxs-lookup"><span data-stu-id="a0f73-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="a0f73-125">За више информација погледајте [Креирање тока у облаку у услузи Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="a0f73-125">For more information, see [Create a cloud flow in Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="a0f73-126">Примери коришћења токова:</span><span class="sxs-lookup"><span data-stu-id="a0f73-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="a0f73-127">Пошаљите поруку на Microsoft Teams канал ако освежавање извора података не успе.</span><span class="sxs-lookup"><span data-stu-id="a0f73-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="a0f73-128">Пошаљите е-поруку власницима података када се пређе праг на сегменту.</span><span class="sxs-lookup"><span data-stu-id="a0f73-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]