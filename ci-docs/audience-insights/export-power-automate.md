---
title: Power Automate конектор | Microsoft Docs
description: Креирајте токове у услузи Microsoft Power Automate из услуге Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406833"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="eeabd-103">Power Automate конектор (преглед)</span><span class="sxs-lookup"><span data-stu-id="eeabd-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="eeabd-104">Покрените одређене догађаје који се појављују аутоматски када се промене подаци и управљајте сложенијим токовима директно у услузи [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="eeabd-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="eeabd-105">Power Automate окидачи</span><span class="sxs-lookup"><span data-stu-id="eeabd-105">Power Automate triggers</span></span>

<span data-ttu-id="eeabd-106">Можете користити разне окидаче који вам омогућавају да креирате токове за аутоматизацију задатака који се понављају, попут обавештења или напреднијих радњи.</span><span class="sxs-lookup"><span data-stu-id="eeabd-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="eeabd-107">Покрените када не успе освежавање извора података.</span><span class="sxs-lookup"><span data-stu-id="eeabd-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="eeabd-108">Покрените када успе освежавање извора података.</span><span class="sxs-lookup"><span data-stu-id="eeabd-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="eeabd-109">Покрените када се пређе гранична вредност за сегмент.</span><span class="sxs-lookup"><span data-stu-id="eeabd-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="eeabd-110">Окидач је ограничен на прекорачење граничне вредности.</span><span class="sxs-lookup"><span data-stu-id="eeabd-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="eeabd-111">Покрените када се пређе гранична вредност за пословну меру.</span><span class="sxs-lookup"><span data-stu-id="eeabd-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="eeabd-112">Окидач је ограничен на прекорачење граничне вредности.</span><span class="sxs-lookup"><span data-stu-id="eeabd-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="eeabd-113">Активира се када се заврши потпуно освежавање (извора података, сегмената, мера...).</span><span class="sxs-lookup"><span data-stu-id="eeabd-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="eeabd-114">Покрените када се заврши освежавање процеса обједињавања (мапирање, подударање, спајање).</span><span class="sxs-lookup"><span data-stu-id="eeabd-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="eeabd-115">[Конфигурисање окидача у услузи Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="eeabd-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="eeabd-116">Power Automate радње</span><span class="sxs-lookup"><span data-stu-id="eeabd-116">Power Automate actions</span></span>
<span data-ttu-id="eeabd-117">Power Automate конектор пружа друге радње осим доступних окидача.</span><span class="sxs-lookup"><span data-stu-id="eeabd-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="eeabd-118">За више информација погледајте [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="eeabd-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="eeabd-119">Креирајте Power Automate ток у увидима о корисницима</span><span class="sxs-lookup"><span data-stu-id="eeabd-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="eeabd-120">У увидима о корисницима идите на **Администратор** > **Систем**.</span><span class="sxs-lookup"><span data-stu-id="eeabd-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="eeabd-121">На страници **Систем** изаберите картицу **Статус**.</span><span class="sxs-lookup"><span data-stu-id="eeabd-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="eeabd-122">У одељку **Извори података** изаберите **Токови** и изаберите **Креирање тока** из падајуће листе.</span><span class="sxs-lookup"><span data-stu-id="eeabd-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="eeabd-123">![Power Automate конектор који приказује радњу „Креирај ток“](media/power-automate-connector-create-flow.png "Power Automate конектор који приказује радњу „Креирај ток“")</span><span class="sxs-lookup"><span data-stu-id="eeabd-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="eeabd-124">У услузи Power Automate, изаберите један од доступних окидача да бисте креирали жељени ток.</span><span class="sxs-lookup"><span data-stu-id="eeabd-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="eeabd-125">Ако креирате први ток, прво ћете морати да потврдите идентитет помоћу Power Automate конектора.</span><span class="sxs-lookup"><span data-stu-id="eeabd-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
