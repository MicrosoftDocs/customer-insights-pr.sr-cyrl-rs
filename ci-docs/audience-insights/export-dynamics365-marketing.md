---
title: Извезите Customer Insights податке у Dynamics 365 Marketing
description: Сазнајте како да конфигуришете везу и извезете у Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a13f6f81f5e2570d3302d88c02755f1d86321a01
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759655"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="41623-103">Коришћење сегмената у услузи Dynamics 365 Marketing (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="41623-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="41623-104">Користите [сегменте](segments.md) да бисте генерисали кампање и контактирали одређене групе клијената помоћу услуге Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="41623-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="41623-105">Више информација потражите у чланку [Коришћење сегмената из услуга Dynamics 365 Customer Insights уз Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="41623-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="41623-106">Предуслов за везу</span><span class="sxs-lookup"><span data-stu-id="41623-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="41623-107">Записи контаката морају бити присутни у услузи Dynamics 365 Marketing да бисте могли да извезете сегмент из услуге Customer Insights у Marketing.</span><span class="sxs-lookup"><span data-stu-id="41623-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="41623-108">Прочитајте више о томе како се уносе контакти у [Dynamics 365 Marketing помоћу услуге Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="41623-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="41623-109">Извоз сегмената из увида о корисницима у Marketing неће креирати нове записе контаката у инстанцама услуге Marketing.</span><span class="sxs-lookup"><span data-stu-id="41623-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="41623-110">Евиденција контаката из услуге Marketing мора се унети у увид о корисницима и користити као извор података.</span><span class="sxs-lookup"><span data-stu-id="41623-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="41623-111">Такође их треба укључити у јединствени ентитет клијента да би се ID-ови клијената мапирали у ID-ове контаката да би сегменти могли да се извезу.</span><span class="sxs-lookup"><span data-stu-id="41623-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="41623-112">Подешавање везе за Marketing</span><span class="sxs-lookup"><span data-stu-id="41623-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="41623-113">Идите на **Администратор** > **Везе**.</span><span class="sxs-lookup"><span data-stu-id="41623-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="41623-114">Изаберите **Додај везу** и бирајте **Dynamics 365 Marketing** да бисте конфигурисали везу.</span><span class="sxs-lookup"><span data-stu-id="41623-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="41623-115">Дајте вези препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="41623-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="41623-116">Име за приказ и врста везе описују ову везу.</span><span class="sxs-lookup"><span data-stu-id="41623-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="41623-117">Препоручујемо да одаберете назив који објашњава сврху и циљ везе.</span><span class="sxs-lookup"><span data-stu-id="41623-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="41623-118">Одаберите ко може да користи ову везу.</span><span class="sxs-lookup"><span data-stu-id="41623-118">Choose who can use this connection.</span></span> <span data-ttu-id="41623-119">Ако ништа не предузмете, подразумевани ће бити Администратори.</span><span class="sxs-lookup"><span data-stu-id="41623-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="41623-120">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="41623-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="41623-121">Унесите URL организације за Marketing у поље **Адреса сервера**.</span><span class="sxs-lookup"><span data-stu-id="41623-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="41623-122">У одељку **Администраторски налог на серверу**, изаберите **Пријавите се** и изаберите Dynamics 365 Marketing налог.</span><span class="sxs-lookup"><span data-stu-id="41623-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="41623-123">Мапирајте поље корисничког ID-а са Dynamics 365 ID-ом контакта.</span><span class="sxs-lookup"><span data-stu-id="41623-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="41623-124">Изаберите **Сачувај** да бисте креирали везу.</span><span class="sxs-lookup"><span data-stu-id="41623-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="41623-125">Конфигурисање извоза</span><span class="sxs-lookup"><span data-stu-id="41623-125">Configure an export</span></span>

<span data-ttu-id="41623-126">Овај извоз можете да конфигуришете ако имате приступ вези ове врсте.</span><span class="sxs-lookup"><span data-stu-id="41623-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="41623-127">За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="41623-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="41623-128">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="41623-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="41623-129">Да бисте креирали нови извоз, изаберите **Додај одредиште**.</span><span class="sxs-lookup"><span data-stu-id="41623-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="41623-130">У пољу **Веза за извоз**, одаберите везу из одељка Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="41623-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="41623-131">Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.</span><span class="sxs-lookup"><span data-stu-id="41623-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="41623-132">Изаберите један или више сегмената.</span><span class="sxs-lookup"><span data-stu-id="41623-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="41623-133">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="41623-133">Select **Save**.</span></span>

<span data-ttu-id="41623-134">Чување извоза не покреће извоз одмах.</span><span class="sxs-lookup"><span data-stu-id="41623-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="41623-135">Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="41623-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="41623-136">Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="41623-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
