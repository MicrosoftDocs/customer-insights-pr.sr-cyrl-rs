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
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Teams робот за Dynamics 365 Customer Insights (верзија за преглед)

Повежите се са услугом Microsoft Teams да бисте дозволили роботу да тражи обједињене профиле клијената на Teams каналима.

> [!div class="mx-imgBorder"]
> ![Teams робот који приказује запис клијента](media/teams-bot.png "Teams робот који приказује запис клијента")

## <a name="prerequisites"></a>Предуслови

Да бисте поставили и конфигурисали робота, морају се испунити следећи предуслови:

- Постоји бар један [додат извор података](data-sources.md).
- [Процес обједињавања](data-unification.md) је довршен.
- Поља су додата у [индекс претраге и филтера](search-filter-index.md).
- Customer Insights и Teams су у истој организацији.

## <a name="configure-the-bot"></a>Конфигурисање робота

1. У увидима о корисницима идите на **Администратор** > **Одредишта за извоз**.
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


[!INCLUDE[footer-include](../includes/footer-banner.md)]