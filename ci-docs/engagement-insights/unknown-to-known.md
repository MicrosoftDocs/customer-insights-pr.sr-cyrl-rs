---
title: Препознајте веб-догађаје од посетилаца којима је претходно потврђен идентитет из непознатих у познате
description: Функција Непознато у познато вам омогућава да повежете догађаје на веб-локацији са посетиоцима који су претходно извршили потврду идентитета.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: d1bbc3315b55e2ee233dc672456e0c27e4ad0fbd5937af09cc790c96ee274000
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036801"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Препознајте веб-догађаје од посетилаца којима је претходно потврђен идентитет

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Функција **непознато у познато** у могућности увида у ангажовање омогућава повезивање догађаја на веб-локацији са посетиоцима који су претходно извршили потврду идентитета. Ако је функција онемогућена, посетиоци који су потврдили идентитет током раније посете, а затим отишли, неће бити идентификовани ако при повратку опет не изврше потврду идентитета. 

На пример, особа је прошле недеље посетила веб-локацију, пријавила се на свој кориснички налог на њој и прегледала каталог производа. Особа се следеће недеље враћа да прегледа још производа без пријављивања на свој налог. Власник веб-локације који користи функцију **Непознато у познато** би знао да се иста особа вратила и шта је радила на веб-локацији. Ово омогућава прецизније извештавање и анализу активности веб-странице.

## <a name="enable-unknown-to-known"></a>Омогућавање функције „непознато у познато“

За омогућавање ове функције морате да будете [администратор радног простора](user-roles.md). 

1. У увидима у ангажовање, идите на **Администратор** > **Радни простор**. 
2. Изаберите картицу **Подешавања**.
3. У одељку **Непознато у познато**, подесите прекидач на **Омогућено**.

![Омогућавање функције „непознато у познато“](media/U2Ktoggle.png "Омогућавање функције „непознато у познато“")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>Додавање JavaScript кода у фрагмент за праћење ваше локације

Веб-локација може забележити **authId корисника** са следећим JavaScript узорком користећи [веб SDK увида у ангажовање](advanced-SDK-implementation.md). Како би функција **непознато у познато** радила, морате да забележите authId *и* омогућите userMapping:True у вашем JavaScript фрагменту као у доњем примеру.

```
[…]
window, document
{
src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js",
name:"myproject",
cfg:{
ingestionKey:<paste your ingestion key>",
autoCapture:{
view:true,
click:true
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
