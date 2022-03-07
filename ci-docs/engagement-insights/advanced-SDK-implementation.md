---
title: Напредни веб SDK сценарији
description: Напредни сценарији које треба узети у обзир приликом опремања веб-локације помоћу SDK-а.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a083d8215f295af0884257a016b62b8c7e4ab2c7
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227216"
---
# <a name="advanced-web-sdk-instrumentation"></a>Напредно веб SDK опремање

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Овај чланак вас води кроз напредне сценарије које треба размотрити када [опремате вашу веб-локацију](instrument-website.md) са SDK-ом Dynamics 365 Customer Insights могућности увида у ангажовање.

## <a name="setting-user-details-for-your-event"></a>Подешавање детаља о кориснику за ваш догађај

SDK вам омогућава да дефинишете информације о кориснику које можете послати уз сваки догађај. Можете навести детаље о кориснику у својству које под називом `user` (очекивани подаци за ово својство су објекат `IUser`), слично као `src`,`name` и `cfg` у конфигурацији исечка кода.

Објекат `IUser` садржи следећа својства низа:

- **localId**: локални ID корисника.
- **authId**: ID корисника са потврђеним идентитетом.
- **authType**: тип потврде идентитета који се користи за добијање ID-а корисника са потврђеним идентитетом.
- **name**: име корисника.
- **email**: адреса е-поште корисника.

Следећи пример приказује исечак кода који шаље информације о кориснику. Тамо где видите функције којима претходи симбол звездице *, замените функцију прилагођеном применом:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

Корисничке податке можете навести и позивањем `setUser(user: IUser)` API-ја. Телеметрија послата након позивања `setUser` API-ја садржаће информације о кориснику.

## <a name="adding-custom-properties-for-each-event"></a>Додавање прилагођених својстава за сваки догађај

SDK вам омогућава да наведете прилагођена својства која можете послати уз сваки догађај. Можете одредити прилагођена својства као објекат који садржи парове кључ/вредност (вредност може бити типа `string | number | boolean`). Објекат можете додати у својство које се зове `props`, слично као и `src`, `name` и `cfg` у конфигурацији фрагмента кода.

Следећи пример приказује исечак кода који шаље прилагођена својства:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

Прилагођена својства можете навести појединачно и позивањем `setProperty(name: string, value: string | number | boolean)` API-ја.

## <a name="sending-custom-events"></a>Слање прилагођених догађаја

SDK можете да користите за слање прилагођених догађаја. Морате навести назив догађаја и својства која ће бити послата уз догађај.

Следећи пример приказује исечак кода који прати прилагођени догађај. „НАЗИВ“ је вредност у `name` кључу у конфигурацији исечка кода. То је такође назив променљиве у објекту прозора у који се учитава SDK.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]
