---
title: Power Automate конектор | Microsoft Docs
description: Креирајте токове у услузи Microsoft Power Automate из услуге Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 57be0a204ef920b7a4bb31cf9a5b3a77f96eca0d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305082"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="ee087-103">Power Automate конектор (преглед)</span><span class="sxs-lookup"><span data-stu-id="ee087-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="ee087-104">Покрените одређене догађаје који се појављују аутоматски када се промене подаци и управљајте сложенијим токовима директно у услузи [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="ee087-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="ee087-105">Power Automate окидачи</span><span class="sxs-lookup"><span data-stu-id="ee087-105">Power Automate triggers</span></span>

<span data-ttu-id="ee087-106">Користите окидаче да креирате токове у облаку и аутоматизујете понављајуће задатке, као што су обавештења или напредније радње.</span><span class="sxs-lookup"><span data-stu-id="ee087-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="ee087-107">Покрените када не успе освежавање извора података.</span><span class="sxs-lookup"><span data-stu-id="ee087-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="ee087-108">Покрените када успе освежавање извора података.</span><span class="sxs-lookup"><span data-stu-id="ee087-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="ee087-109">Покрените када се пређе гранична вредност за сегмент.</span><span class="sxs-lookup"><span data-stu-id="ee087-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="ee087-110">Окидач је ограничен на прекорачење граничне вредности.</span><span class="sxs-lookup"><span data-stu-id="ee087-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="ee087-111">Покрените када се пређе гранична вредност за пословну меру.</span><span class="sxs-lookup"><span data-stu-id="ee087-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="ee087-112">Подржане су само пословне мере без димензије.</span><span class="sxs-lookup"><span data-stu-id="ee087-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="ee087-113">Окидач је ограничен на прекорачење граничне вредности.</span><span class="sxs-lookup"><span data-stu-id="ee087-113">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="ee087-114">Активира се када се заврши потпуно освежавање (извора података, сегмената, мера, ...).</span><span class="sxs-lookup"><span data-stu-id="ee087-114">Trigger when a full refresh of (data sources, segments, measures, ...) is completed.</span></span>
- <span data-ttu-id="ee087-115">Покрените када се заврши освежавање процеса обједињавања (мапирање, подударање, спајање).</span><span class="sxs-lookup"><span data-stu-id="ee087-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

[<span data-ttu-id="ee087-116">Конфигуришите окидаче у услузи Power Automate.</span><span class="sxs-lookup"><span data-stu-id="ee087-116">Configure your triggers in Power Automate.</span></span>](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a><span data-ttu-id="ee087-117">Power Automate радње</span><span class="sxs-lookup"><span data-stu-id="ee087-117">Power Automate actions</span></span>

<span data-ttu-id="ee087-118">Power Automate конектор пружа друге радње осим доступних окидача.</span><span class="sxs-lookup"><span data-stu-id="ee087-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="ee087-119">За више информација погледајте [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="ee087-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="ee087-120">Креирање Power Automate тока</span><span class="sxs-lookup"><span data-stu-id="ee087-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="ee087-121">У увидима о корисницима идите на **Администратор** > **Одредишта за извоз**.</span><span class="sxs-lookup"><span data-stu-id="ee087-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ee087-122">На плочици **Power Automate** изаберите **Подеси**.</span><span class="sxs-lookup"><span data-stu-id="ee087-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="ee087-123">Отвара се Customer Insights конектор (преглед) у услузи Power Automate.</span><span class="sxs-lookup"><span data-stu-id="ee087-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="ee087-124">**Пријавите се** у Power Automate.</span><span class="sxs-lookup"><span data-stu-id="ee087-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="ee087-125">Изаберите један од доступних окидача и додајте још корака свом новом току.</span><span class="sxs-lookup"><span data-stu-id="ee087-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="ee087-126">За више информација погледајте [Креирање тока у облаку у услузи Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="ee087-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="ee087-127">Примери како се користе токови:</span><span class="sxs-lookup"><span data-stu-id="ee087-127">Examples of how to use flows:</span></span> 
- <span data-ttu-id="ee087-128">Пошаљите поруку на Microsoft Teams канал ако освежавање извора података не успе.</span><span class="sxs-lookup"><span data-stu-id="ee087-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="ee087-129">Пошаљите е-поруку власницима података када се пређе праг на сегменту.</span><span class="sxs-lookup"><span data-stu-id="ee087-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
