---
title: Напредни веб SDK сценарији
description: Напредни сценарији које треба узети у обзир приликом опремања веб-локације помоћу SDK-а.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 11/12/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7455d276035bfaf1f8a93d0e3b0b0884353a4010715c05d1d696309f7eb4b233
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036346"
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
    
Следећи пример приказује исечак кода који шаље информације о кориснику. Тамо где видите Функције означене са *, замените их вашом применом позивања тих вредности:  

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

Податке о кориснику можете одредити и позивањем `setUser(user: IUser)` API-ја у SDK-у. Телеметрија послата након позивања `setUser API`-ја садржаће информације о кориснику.

## <a name="adding-custom-properties-for-each-event"></a>Додавање прилагођених својстава за сваки догађај

SDK вам омогућава да наведете прилагођена својства која можете послати уз сваки догађај. Можете одредити прилагођена својства као објекат који садржи парове кључ/вредност (вредност може бити типа `string | number | boolean`). Објекат може бити додат у својство под називом `props`, слично као `src`, `name` и `cfg` у конфигурацији исечка кода. 

Следећи пример приказује исечак кода који шаље прилагођена својства:

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
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

Такође можете појединачно навести прилагођена својства позивањем `setProperty(name: string, value: string | number | boolean)` API-ја у SDK-у.

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