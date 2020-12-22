---
title: Робот за Microsoft Teams
description: Потражите обједињене профиле клијената у услузи Microsoft Teams уз помоћ робота.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 45ea23fbefe5f1d44c3961183b76d2cc5c45355e
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406866"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="66feb-103">Teams робот за Dynamics 365 Customer Insights (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="66feb-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="66feb-104">Повежите се са услугом Microsoft Teams да бисте дозволили роботу да тражи обједињене профиле клијената на Teams каналима.</span><span class="sxs-lookup"><span data-stu-id="66feb-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="66feb-105">![Teams робот који приказује запис клијента](media/teams-bot.png "Teams робот који приказује запис клијента")</span><span class="sxs-lookup"><span data-stu-id="66feb-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="66feb-106">Предуслови</span><span class="sxs-lookup"><span data-stu-id="66feb-106">Prerequisites</span></span>

<span data-ttu-id="66feb-107">Да бисте поставили и конфигурисали робота, морају се испунити следећи предуслови:</span><span class="sxs-lookup"><span data-stu-id="66feb-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="66feb-108">Постоји бар један [додат извор података](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="66feb-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="66feb-109">[Процес обједињавања](data-unification.md) је довршен.</span><span class="sxs-lookup"><span data-stu-id="66feb-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="66feb-110">Поља су додата у [индекс претраге и филтера](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="66feb-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="66feb-111">Customer Insights и Teams су у истој организацији.</span><span class="sxs-lookup"><span data-stu-id="66feb-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="66feb-112">Конфигурисање робота</span><span class="sxs-lookup"><span data-stu-id="66feb-112">Configure the bot</span></span>

1. <span data-ttu-id="66feb-113">У увидима о корисницима идите на **Администратор** > **Одредишта за извоз**.</span><span class="sxs-lookup"><span data-stu-id="66feb-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="66feb-114">На плочици Microsoft Teams изаберите **Поставити**.</span><span class="sxs-lookup"><span data-stu-id="66feb-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="66feb-115">Преусмерени сте на област **Апликације** у услузи Teams.</span><span class="sxs-lookup"><span data-stu-id="66feb-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="66feb-116">Такође можете отворити Teams и изабрати **Апликације** у доњем левом углу или га директно [преузети са локације AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).</span><span class="sxs-lookup"><span data-stu-id="66feb-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="66feb-117">Потражите **Customer Insights** и изаберите апликацију.</span><span class="sxs-lookup"><span data-stu-id="66feb-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="66feb-118">Изаберите **Додај**.</span><span class="sxs-lookup"><span data-stu-id="66feb-118">Select **Add**.</span></span>
1. <span data-ttu-id="66feb-119">Када се пријавите у Customer Insights у услузи Teams, видећете поруку добродошлице и тада можете почети.</span><span class="sxs-lookup"><span data-stu-id="66feb-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="66feb-120">Ствари које можете да урадите уз робота</span><span class="sxs-lookup"><span data-stu-id="66feb-120">Things you can do with the bot</span></span>

<span data-ttu-id="66feb-121">Робот пружа могућности проналажења за обједињене профиле клијената.</span><span class="sxs-lookup"><span data-stu-id="66feb-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="66feb-122">Унесите **претрага** након чега следи име, адреса е-поште или било које друго поље на обједињеном профилу клијента које се додаје индексу претраге и филтера.</span><span class="sxs-lookup"><span data-stu-id="66feb-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="66feb-123">Добићете картицу са до 15 поља из резултујућег профила клијента.</span><span class="sxs-lookup"><span data-stu-id="66feb-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="66feb-124">Више подударања враћа листу резултата на којима можете одабрати профил.</span><span class="sxs-lookup"><span data-stu-id="66feb-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="66feb-125">Можете додати термин за претрагу у двоструким наводницима да бисте потражили тачно подударање.</span><span class="sxs-lookup"><span data-stu-id="66feb-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="66feb-126">Ако ваша организација одржава више Customer Insights окружења у истој организацији, можете да унесете **switchinstance** да бисте изабрали са којим окружењем желите да повежете робота.</span><span class="sxs-lookup"><span data-stu-id="66feb-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="66feb-127">Унесите **помоћ** да бисте видели листу доступних команди за робота.</span><span class="sxs-lookup"><span data-stu-id="66feb-127">Enter **help** to see a list of available commands for the bot.</span></span>  
