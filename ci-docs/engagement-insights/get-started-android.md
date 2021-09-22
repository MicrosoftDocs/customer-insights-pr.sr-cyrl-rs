---
title: Почетни кораци у раду са Android SDK
description: Сазнајте како да персонализујете и покренете Android SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 77e63929bbcc7ecff34a3839af525b76ec3c7f21173ddc5f8f2d69f11c25c441
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036936"
---
# <a name="get-started-with-the-android-sdk"></a>Почетни кораци у раду са Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ово упутство вас води кроз процес опремања Android апликације са Dynamics 365 Customer Insights SDK за увиде у ангажовање. Догађаје на порталу почећете да видите за пет минута или пре.

## <a name="configuration-options"></a>Опције конфигурације
Следеће опције конфигурације могу се проследити SDK-у:

- **ingestionKey**: Кључ за унос који се користи за слање догађаја у ваш радни простор.

## <a name="prerequisites"></a>Предуслови

- Android Studio

- Минимални ниво за Android API: 16 (Jelly Bean)

- Кључ за унос (погледајте у наставку упутство за добијање)

## <a name="step-1-integrate-the-sdk-into-your-application"></a>Корак 1. Интегришите SDK у своју апликацију
Започните поступак одабиром радног простора у, одабиром Android мобилне платформе и преузимањем Android SDK.

- Користите преклопник радног простора у левом окну за навигацију да бисте изабрали радни простор.

- Ако немате постојећи радни простор, изаберите **Нови радни простор** и следите кораке да креирате [нови радни простор](create-workspace.md).

## <a name="step-2-configure-the-sdk"></a>Корак 2. Конфигурисање SDK

1. Када креирате радни простор, идите на **Администратор** > **Радни простор**, а затим изаберите **Водич за инсталацију**. 

1. Преузмите [Android SDK за увиде у ангажовање](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) и поставите датотеку `eiandroidsdk-debug.aar` у фасциклу `libs`.

1. Отворите датотеку `build.gradle` на нивоу пројекта и додајте следеће исечке:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

1. Подесите конфигурацију SDK за увиде у ангажовање путем ваше датотеке `AndroidManifest.xml` која се налази у фасцикли `manifests`. 
1. Копирајте XML исечак из **водича за инсталацију**. `Your-Ingestion-Key` би требало да се попуни аутоматски.

   > [!NOTE]
   > Не морате да замените одељак `${applicationId}`. Он се попуњава аутоматски.
   

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Омогућите или онемогућите аутоматско налажење догађаја `View` подешавањем вредности `true` или `false` у горенаведеном пољу `autoCapture`.

1. (Опционално) Остале конфигурације укључују подешавање URL адресе сакупљача крајњих тачака. Могу се додати под метаподацима кључа за унос у датотеци `AndroidManifest.xml`:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="step-3-initialize-the-sdk-from-mainactivity"></a>Корак 3. Покретање SDK из MainActivity 

Када покренете SDK, можете радити са догађајима и њиховим својствима у MainActivity окружењу.

    
Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Подесите својство за све догађаје (опционално)
    
Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

Следећи типови су подржани за својства догађаја контекста:
- String
- Датум
- Двострука вредност
- Дугачак
- Булов
- UUID

### <a name="track-an-event"></a>Праћење догађаја

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

### <a name="set-user-details-for-your-event-optional"></a>Подесите корисничке детаље за догађај (опционално)

SDK вам омогућава да дефинишете информације о кориснику које можете послати уз сваки догађај. Информације о кориснику можете одредити позивањем `setUser(user: User)` API-ја на нивоу `Analytics`.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

Класа података `User` садржи следећа својства за ниску:

- **localId**: локални ID корисника.
- **authId**: ID корисника са потврђеним идентитетом.
- **authType**: Тип потврде идентитета који се користи за добијање потврђеног ID-а корисника.
- **name**: име корисника.
- **email**: адреса е-поште корисника.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
