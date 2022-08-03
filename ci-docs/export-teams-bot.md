---
title: Teams робот за Dynamics 365 Customer Insights (верзија за преглед)
description: Потражите обједињене профиле клијената у услузи Microsoft Teams уз помоћ робота.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195860"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Teams робот за Dynamics 365 Customer Insights (верзија за преглед)

Повежите се са услугом Microsoft Teams да бисте дозволили роботу да тражи обједињене профиле клијената на Teams каналима.

:::image type="content" source="media/teams-bot.png" alt-text="Teams робот који приказује запис клијента":::

## <a name="prerequisites"></a>Предуслови

- Додата је [извор података једна особа](data-sources.md).
- [Процес обједињавања](data-unification.md) је довршен.
- Поља се додају индексу сеарцх [&амп; филтер](search-filter-index.md).
- Customer Insights и Teams су у истој организацији.
- Ваше окружење има примарну циљну групу постављену за појединачне клијенте. Пословни налози нису подржани.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Конфигурисање робота

1. Идите на **Администратор** > **Везе**.
1. На плочици Microsoft Teams изаберите **Подеси**.
1. Преусмерени сте на област **Апликације** у услузи Teams. Такође можете отворити Teams и изабрати **Апликације** у доњем левом углу или га директно [преузети са локације AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).
1. Потражите **Customer Insights** и изаберите апликацију.
1. Изаберите **Додај**.
1. пријавите се на Увид купца у тимовима. Приказује се порука добродошлице.

## <a name="things-you-can-do-with-the-bot"></a>Ствари које можете да урадите уз робота

Робот пружа могућности проналажења за обједињене профиле клијената.

- Унесите **претрагу** праћену именом, е-адресом или било којим другим пољем у обједињеном профилу купца које се додаје индексу сеарцх &амп; филтер.

  Добићете картицу са до 15 поља из резултујућег профила клијента. Више подударања враћа листу резултата на којима можете одабрати профил. Да бисте потражили тачно подударање, додајте термин за претрагу у двоструке наводнике.

- Ако ваша организација одржава више окружења за увиде клијената у истој организацији, **унесите сwитцхинстанце да** бисте одабрали са којим окружењем желите да повежете бота.

- Унесите **помоћ** да бисте видели листу доступних команди за робота.  

[!INCLUDE [footer-include](includes/footer-banner.md)]