---
title: Робот за Microsoft Teams
description: Потражите обједињене профиле клијената у услузи Microsoft Teams уз помоћ робота.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 03299610fd41a7e142e3c9723fad56ce7f90e083
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267970"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="38a0f-103">Teams робот за Dynamics 365 Customer Insights (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="38a0f-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="38a0f-104">Повежите се са услугом Microsoft Teams да бисте дозволили роботу да тражи обједињене профиле клијената на Teams каналима.</span><span class="sxs-lookup"><span data-stu-id="38a0f-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="38a0f-105">![Teams робот који приказује запис клијента](media/teams-bot.png "Teams робот који приказује запис клијента")</span><span class="sxs-lookup"><span data-stu-id="38a0f-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="38a0f-106">Предуслови</span><span class="sxs-lookup"><span data-stu-id="38a0f-106">Prerequisites</span></span>

<span data-ttu-id="38a0f-107">Да бисте поставили и конфигурисали робота, морају се испунити следећи предуслови:</span><span class="sxs-lookup"><span data-stu-id="38a0f-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="38a0f-108">Постоји бар један [додат извор података](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="38a0f-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="38a0f-109">[Процес обједињавања](data-unification.md) је довршен.</span><span class="sxs-lookup"><span data-stu-id="38a0f-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="38a0f-110">Поља су додата у [индекс претраге и филтера](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="38a0f-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="38a0f-111">Customer Insights и Teams су у истој организацији.</span><span class="sxs-lookup"><span data-stu-id="38a0f-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="38a0f-112">Конфигурисање робота</span><span class="sxs-lookup"><span data-stu-id="38a0f-112">Configure the bot</span></span>

1. <span data-ttu-id="38a0f-113">У увидима о корисницима идите на **Администратор** > **Одредишта за извоз**.</span><span class="sxs-lookup"><span data-stu-id="38a0f-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="38a0f-114">На плочици Microsoft Teams изаберите **Подеси**.</span><span class="sxs-lookup"><span data-stu-id="38a0f-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="38a0f-115">Преусмерени сте на област **Апликације** у услузи Teams.</span><span class="sxs-lookup"><span data-stu-id="38a0f-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="38a0f-116">Такође можете отворити Teams и изабрати **Апликације** у доњем левом углу или га директно [преузети са локације AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).</span><span class="sxs-lookup"><span data-stu-id="38a0f-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="38a0f-117">Потражите **Customer Insights** и изаберите апликацију.</span><span class="sxs-lookup"><span data-stu-id="38a0f-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="38a0f-118">Изаберите **Додај**.</span><span class="sxs-lookup"><span data-stu-id="38a0f-118">Select **Add**.</span></span>
1. <span data-ttu-id="38a0f-119">Када се пријавите у Customer Insights у услузи Teams, видећете поруку добродошлице и тада можете почети.</span><span class="sxs-lookup"><span data-stu-id="38a0f-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="38a0f-120">Ствари које можете да урадите уз робота</span><span class="sxs-lookup"><span data-stu-id="38a0f-120">Things you can do with the bot</span></span>

<span data-ttu-id="38a0f-121">Робот пружа могућности проналажења за обједињене профиле клијената.</span><span class="sxs-lookup"><span data-stu-id="38a0f-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="38a0f-122">Унесите **претрага** након чега следи име, адреса е-поште или било које друго поље на обједињеном профилу клијента које се додаје индексу претраге и филтера.</span><span class="sxs-lookup"><span data-stu-id="38a0f-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="38a0f-123">Добићете картицу са до 15 поља из резултујућег профила клијента.</span><span class="sxs-lookup"><span data-stu-id="38a0f-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="38a0f-124">Више подударања враћа листу резултата на којима можете одабрати профил.</span><span class="sxs-lookup"><span data-stu-id="38a0f-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="38a0f-125">Можете додати термин за претрагу у двоструким наводницима да бисте потражили тачно подударање.</span><span class="sxs-lookup"><span data-stu-id="38a0f-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="38a0f-126">Ако ваша организација одржава више Customer Insights окружења у истој организацији, можете да унесете **switchinstance** да бисте изабрали са којим окружењем желите да повежете робота.</span><span class="sxs-lookup"><span data-stu-id="38a0f-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="38a0f-127">Унесите **помоћ** да бисте видели листу доступних команди за робота.</span><span class="sxs-lookup"><span data-stu-id="38a0f-127">Enter **help** to see a list of available commands for the bot.</span></span>  


[!INCLUDE[footer-include](../includes/footer-banner.md)]