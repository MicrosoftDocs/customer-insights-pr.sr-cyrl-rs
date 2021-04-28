---
title: Извезите Customer Insights податке у Dynamics 365 Sales
description: Сазнајте како да конфигуришете везу и извезете у Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc1a05ba4d21d96aa1a9724d158687bbb86949b6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759622"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="13741-103">Коришћење сегмената у услузи Dynamics 365 Sales (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="13741-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="13741-104">Користите податке о клијентима да бисте креирали маркетиншке спискове, пратили токове посла и слали промоције са услугом Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="13741-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="13741-105">Предуслов за везу</span><span class="sxs-lookup"><span data-stu-id="13741-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="13741-106">Записи контаката морају бити присутни у услузи Dynamics 365 Sales да бисте могли да извезете сегмент из услуге Customer Insights у Sales.</span><span class="sxs-lookup"><span data-stu-id="13741-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="13741-107">Прочитајте више о томе како се уносе контакти у [Dynamics 365 Sales помоћу услуге Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="13741-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="13741-108">Извоз сегмената из увида о корисницима у Sales неће креирати нове записе контаката у инстанцама услуге Sales.</span><span class="sxs-lookup"><span data-stu-id="13741-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="13741-109">Евиденција контаката из услуге Sales мора се унети у увид о корисницима и користити као извор података.</span><span class="sxs-lookup"><span data-stu-id="13741-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="13741-110">Такође их треба укључити у јединствени ентитет клијента да би се ID-ови клијената мапирали у ID-ове контаката да би сегменти могли да се извезу.</span><span class="sxs-lookup"><span data-stu-id="13741-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="13741-111">Подешавање везе са услугом Sales</span><span class="sxs-lookup"><span data-stu-id="13741-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="13741-112">Идите на **Администратор** > **Везе**.</span><span class="sxs-lookup"><span data-stu-id="13741-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="13741-113">Изаберите **Додај везу** и бирајте **Dynamics 365 Sales** да бисте конфигурисали везу.</span><span class="sxs-lookup"><span data-stu-id="13741-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="13741-114">Дајте вези препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="13741-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="13741-115">Име за приказ и врста везе описују ову везу.</span><span class="sxs-lookup"><span data-stu-id="13741-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="13741-116">Препоручујемо да одаберете назив који објашњава сврху и циљ везе.</span><span class="sxs-lookup"><span data-stu-id="13741-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="13741-117">Одаберите ко може да користи ову везу.</span><span class="sxs-lookup"><span data-stu-id="13741-117">Choose who can use this connection.</span></span> <span data-ttu-id="13741-118">Ако ништа не предузмете, подразумевани ће бити Администратори.</span><span class="sxs-lookup"><span data-stu-id="13741-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="13741-119">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="13741-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="13741-120">Унесите URL организације за Sales у поље **Адреса сервера**.</span><span class="sxs-lookup"><span data-stu-id="13741-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="13741-121">У одељку **Администраторски налог на серверу**, изаберите **Пријавите се** и изаберите Dynamics 365 Sales налог.</span><span class="sxs-lookup"><span data-stu-id="13741-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="13741-122">Мапирајте поље корисничког ID-а са Dynamics 365 ID-ом контакта.</span><span class="sxs-lookup"><span data-stu-id="13741-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="13741-123">Изаберите **Сачувај** да бисте креирали везу.</span><span class="sxs-lookup"><span data-stu-id="13741-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="13741-124">Конфигурисање извоза</span><span class="sxs-lookup"><span data-stu-id="13741-124">Configure an export</span></span>

<span data-ttu-id="13741-125">Овај извоз можете да конфигуришете ако имате приступ вези ове врсте.</span><span class="sxs-lookup"><span data-stu-id="13741-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="13741-126">За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="13741-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="13741-127">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="13741-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="13741-128">Да бисте креирали нови извоз, изаберите **Додај одредиште**.</span><span class="sxs-lookup"><span data-stu-id="13741-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="13741-129">У пољу **Веза за извоз**, одаберите везу из одељка Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="13741-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="13741-130">Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.</span><span class="sxs-lookup"><span data-stu-id="13741-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="13741-131">Изаберите један или више сегмената.</span><span class="sxs-lookup"><span data-stu-id="13741-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="13741-132">Изаберите ставку **Сачувај**</span><span class="sxs-lookup"><span data-stu-id="13741-132">Select **Save**</span></span>

<span data-ttu-id="13741-133">Чување извоза не покреће извоз одмах.</span><span class="sxs-lookup"><span data-stu-id="13741-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="13741-134">Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="13741-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="13741-135">Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="13741-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
