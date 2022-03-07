---
title: Покретање веб SDK узорка
description: Сазнајте како да персонализујете и покренете веб SDK узорак.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036621"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Покрените веб SKD узорак за Dynamics 365 Customer Insights могућност увида у ангажовање

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Веб SDK библиотека могућности увида у ангажовање је JavaScript библиотека са узорком кода који можете да користите на вашој веб-локацији.

## <a name="prerequisites"></a>Предуслови

- Инсталирајте [Visual Studio Code](https://code.visualstudio.com/).
- [Инсталирајте Live Server проширење](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) у Visual Studio Code уређивачу и упознајте се како да покрећете Live Server.
- Морате имати [кључ за унос](instrument-website.md).

## <a name="run-sample"></a>Покретање узорка

1. [Преузмите веб SDK узорак](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Распакујте компримовану датотеку `ei_websdk_sample.zip`.

1. Отворите распаковану фасциклу у Visual Studio Code.

1. У `ei_websdk_sample.html` датотеци, замените ниску „КЉУЧ ЗА УНОС“ кључем за унос са портала могућности увида у ангажовање, а ниску „НАЗИВ“ глобалним називом за који желите да вежете SDK инстанцу. Обавезно замените на свим местима.

1. Отворите `ei_websdk_sample.html` датотеку користећи Live Server у решењу Visual Studio Code тако што ћете изабрати **Изведи уживо** са статусне траке.

1. По отварању странице, требало би да аутоматски буде послат догађа приказа. Кликом на било које дугме на страници биће послати догађаји радње. Дугме **Прати догађаје** ће такође слати прилагођене догађаје. Избором дугмета **Идите на Bing** послаћете догађај радње пре одласка на Bing веб-локацију.

1. Погледајте догађаје који теку током кретања до вашег радног простора. Овај радни простор повезан је са кључем за унос који сте унели у 4. кораку.


[!INCLUDE[footer-include](../includes/footer-banner.md)]