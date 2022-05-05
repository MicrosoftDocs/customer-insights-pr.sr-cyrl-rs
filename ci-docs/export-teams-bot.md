---
title: Робот за Microsoft Teams
description: Потражите обједињене профиле клијената у услузи Microsoft Teams уз помоћ робота.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 89a293d5b6f9f5452b2ccba495d2475002806019
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643904"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Teams робот за Dynamics 365 Customer Insights (верзија за преглед)

Повежите се са услугом Microsoft Teams да бисте дозволили роботу да тражи обједињене профиле клијената на Teams каналима.

> [!div class="mx-imgBorder"]
> ![Teams робот који приказује запис клијента.](media/teams-bot.png "Teams робот који приказује запис клијента")

## <a name="prerequisites"></a>Предуслови

Да бисте поставили и конфигурисали робота, морају се испунити следећи предуслови:

- Постоји бар један [додат извор података](data-sources.md).
- [Процес обједињавања](data-unification.md) је довршен.
- Поља су додата у [индекс претраге и филтера](search-filter-index.md).
- Customer Insights и Teams су у истој организацији.
- Ваше окружење има примарну циљну групу постављену за појединачне клијенте. Пословни налози нису подржани.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Конфигурисање робота

1. Идите на **одредишта за АдминЕxпорт** > **·**.
1. На плочици Microsoft Teams изаберите **Подеси**.
1. Преусмерени сте на област **Апликације** у услузи Teams. Такође можете отворити Teams и изабрати **Апликације** у доњем левом углу или га директно [преузети са локације AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).
1. Потражите **Customer Insights** и изаберите апликацију.
1. Изаберите **Додај**.
1. Када се пријавите у Customer Insights у услузи Teams, видећете поруку добродошлице и тада можете почети.

## <a name="things-you-can-do-with-the-bot"></a>Ствари које можете да урадите уз робота

Робот пружа могућности проналажења за обједињене профиле клијената.

- Унесите **претрага** након чега следи име, адреса е-поште или било које друго поље на обједињеном профилу клијента које се додаје индексу претраге и филтера.

  Добићете картицу са до 15 поља из резултујућег профила клијента. Више подударања враћа листу резултата на којима можете одабрати профил. Можете додати термин за претрагу у двоструким наводницима да бисте потражили тачно подударање.

- Ако ваша организација одржава више Customer Insights окружења у истој организацији, можете да унесете **switchinstance** да бисте изабрали са којим окружењем желите да повежете робота.

- Унесите **помоћ** да бисте видели листу доступних команди за робота.  


[!INCLUDE [footer-include](includes/footer-banner.md)]