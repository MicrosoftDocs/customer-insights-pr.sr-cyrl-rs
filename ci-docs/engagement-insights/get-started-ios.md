---
title: Почетни кораци у раду са iOS SDK
description: Сазнајте како да персонализујете и покренете iOS SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: de8291fc429ae6433301a47bfdf9a3271b1b77294fd58448c7aa6bd0783edc97
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036891"
---
# <a name="get-started-with-the-ios-sdk"></a>Почетни кораци у раду са iOS SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ово упутство вас води кроз процес опремања iOS апликације са Dynamics 365 Customer Insights SDK за увиде у ангажовање. Догађаје на порталу почећете да видите за пет минута или пре.

## <a name="configuration-options"></a>Опције конфигурације

Следеће опције конфигурације могу се проследити SDK-у путем обезбеђене `EIConfig.plist` датотеке:

- **ingestionKey**: Кључ за унос који се користи за слање догађаја у ваш пројекат.
- **autocollectAction**: Логичка вредност за омогућавање или онемогућавање аутоматског опремања догађаја радње.
- **autocollectView**: Логичка вредност за омогућавање или онемогућавање аутоматског опремања догађаја приказа.
- **endpointUrl**: URL адреса крајње тачке на коју ће догађаји бити усмерени.

## <a name="prerequisites"></a>Предуслови

- Xcode верзије 9+
- iOS верзије 8.2+
- Кључ за унос (погледајте упутства у наставку за добијање)

## <a name="integrate-the-sdk-into-your-application"></a>Интегришите SDK у своју апликацију

Започните поступак одабиром радног простора у којем ћете радити, одабиром iOS мобилне платформе и преузимањем SDK.

- Користите преклопник радног простора у левом окну за навигацију да бисте изабрали радни простор.

- Ако немате постојећи радни простор, изаберите **Нови радни простор** и следите кораке да креирате [нови радни простор](create-workspace.md).

## <a name="configure-the-sdk"></a>Конфигурисање SDK

Када преузмете SDK, можете радити с њим на платформи Xcode да бисте омогућили и дефинисали догађаје.

1. Када креирате радни простор, идите на **Администратор** > **Радни простор** а затим изаберите **Водич за инсталацију**.

1. Преузмите [iOS SDK увиде у ангажовање](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip) и поставите датотеку `EIObjC.xcframework` у фасциклу `Frameworks`.

1. Ако фасцикла `Frameworks` не постоји, направите је у фасцикли пројекта.

## <a name="enable-auto-instrumentation"></a>Омогућавање аутоматског опремања
 
Можете лако омогућити аутоматско опремање без кодирања. Када се пројекат покрене, аутоматски ће пратити догађаје `view` и `action` помоћу конфигурисаног кључа за унос. 

1. Ажурирајте и укључите обезбеђену датотеку `EIConfig.plist` у фасцикли директоријума пројекта за следећа поља:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = ДА
    - autocollectAction = ДА

2. Затим додајте датотеку `EIConfig.plist` у свој пројекат на платформи Xcode. 



Да бисте онемогућили аутоматско опремање, у обухваћеној датотеци `EIConfig.plist` у фасцикли директоријума пројекта ажурирајте следећа поља: 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Примена прилагођених догађаја

1. Отворите пројекат у платформи Xcode и идите на подешавања **Општи подаци**. 
1. Додајте `EIObjC.xcframework` пројекту у одељку „Радни оквири, библиотеке и уграђени садржај“.

1. Увезите датотеку заглавља оквира у AppDelegate.m са следећим исечком:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Покрените SDK за увиде у ангажовање из апликације: didFinishLaunchingWithOptions.
1. Копирајте XML исечак из **водича за инсталацију**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Праћење догађаја:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Подесите корисничке детаље за догађај

SDK вам омогућава да дефинишете информације о кориснику које можете послати уз сваки догађај. Информације о кориснику можете одредити позивањем `setUser:(nonnull EIUser *)user` API-ја на SDK-у.

Навођење корисничких детаља на нивоу `Analytics` значи да ће све телеметрије имати ове информације. Међутим, ако наведете на нивоу догађаја позивањем `setUser:(nonnull EIUser *)user` API-ја на објекту EIEvent, само ће тај одређени догађај садржати информације.

Класа података `EIUser` садржи следећа својства за NSString:

- **localId**: локални ID корисника.
- **authId**: ID корисника са потврђеним идентитетом.
- **authType**: тип потврде идентитета који се користи за добијање ID-а корисника са потврђеним идентитетом.
- **name**: име корисника.
- **email**: адреса е-поште корисника.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
