---
title: Покретање веб SDK узорка
description: Сазнајте како да персонализујете и покренете веб SDK узорак.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a50a10db784ec7c1943c94e74000713309787e5c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225349"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Покрените веб SKD узорак за Dynamics 365 Customer Insights могућност увида у ангажовање

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Веб SDK библиотека могућности увида у ангажовање је JavaScript библиотека са узорком кода који можете да користите на вашој веб-локацији.

## <a name="prerequisites"></a>Предуслови

- Инсталирајте [Visual Studio Code](https://code.visualstudio.com/).
- [Инсталирајте Live Server проширење](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) у Visual Studio Code уређивачу и упознајте се како да покрећете Live Server.
- Морате имати [радни простор увиди у ангажовање](create-workspace.md).

## <a name="run-sample"></a>Покретање узорка

1. [Преузмите веб SDK узорак](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Распакујте компримовану датотеку `ei_websdk_sample.zip`.

1. Отворите распаковану фасциклу у Visual Studio Code.

1. Идите на портал увида у ангажовање за свој радни простор. Изаберите **Администратор** > **Радни простор** и онда **Упутство за инсталацију**. Пратите прву опцију и изаберите **Копирај код** да бисте копирали JavaScript исечак кода.

1. У датотеци `ei_websdk_sample.html`, испод ове линије налепите исечак кода који сте управо копирали:

   - <-- НАЛЕПИТЕ JAVASCRIPT ИСЕЧАК КОДА СА ПОРТАЛА УВИДА У АНГАЖОВАЊЕ ОВДЕ ИСПОД ОВЕ ЛИНИЈЕ -->

1. Отворите `ei_websdk_sample.html` датотеку користећи Live Server у решењу Visual Studio Code тако што ћете изабрати **Изведи уживо** са статусне траке.

1. По отварању странице, требало би да аутоматски буде послат догађа приказа. Кликом на било које дугме на страници биће послати догађаји радње. Дугме **Прати догађаје** ће такође слати прилагођене догађаје. Избором дугмета **Идите на Bing** послаћете догађај радње пре одласка на Bing веб-локацију.

1. Погледајте догађаје који теку током кретања до вашег радног простора. Овај радни простор повезан је са кључем за унос који сте унели у 4. кораку.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
