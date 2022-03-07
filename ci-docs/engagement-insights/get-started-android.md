---
title: Почетни кораци у раду са Android SDK
description: Сазнајте како да персонализујете и покренете Android SDK
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 10/19/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: b06822b2c2d6a859bdf808f7800baef43c4ab874
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226187"
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

## <a name="integrate-the-sdk-into-your-application"></a>Интегришите SDK у своју апликацију
Започните поступак одабиром радног простора у, одабиром Android мобилне платформе и преузимањем Android SDK.

- Користите преклопник радног простора у левом окну за навигацију да бисте изабрали радни простор.

- Ако немате постојећи радни простор, изаберите **Нови радни простор** и следите кораке да креирате [нови радни простор](create-workspace.md).

- Када креирате радни простор, идите на **Администратор** > **Радни простор**, а затим изаберите **Водич за инсталацију**.

## <a name="configure-the-sdk"></a>Конфигурисање SDK

Када преузмете SDK, можете радити с њим на платформи Android Studio да бисте омогућили и дефинисали догађаје. Постоје два начина да то урадите:
### <a name="option-1-use-jitpack-recommended"></a>Опција 1: Користите ЈитПацк (препоручује се)
1. Додајте JitPack спремиште свом корену `build.gradle`:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. Додајте зависност:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:v1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-use-download-link"></a>Опција 2: Коришћење везе за преузимање
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

## <a name="enable-auto-instrumentation"></a>Омогућавање аутоматског опремања

1. Додајте дозволу за мрежу и интернет у своју `AndroidManifest.xml` датотеку која се налази у фасцикли `manifests`.
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```

1. Подесите конфигурацију SDK за увиде у ангажовање путем ваше датотеке `AndroidManifest.xml`.

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

   >[!NOTE]
   >`Action` догађаје треба додати ручно.

1. (Опционално) Остале конфигурације укључују подешавање URL адресе сакупљача крајњих тачака. Они се могу додати испод метаподатака кључа за ингестион у програму `AndroidManifest.xml`.

   ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
   ```

## <a name="implement-custom-events"></a>Примена прилагођених догађаја

Када покренете SDK, можете радити са догађајима и њиховим својствима у `MainActivity` окружењу.


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

## <a name="set-user-details-for-your-event-optional"></a>Подесите корисничке детаље за догађај (опционално)

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
