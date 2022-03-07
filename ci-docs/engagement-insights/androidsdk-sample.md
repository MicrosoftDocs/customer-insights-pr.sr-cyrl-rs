---
title: Android SDK пример
description: Пример пројекта за упознавање платформе Android SDK
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 2ee29a98192bb53bd92241d71c1a76ec2b7bf846
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229936"
---
# <a name="run-the-android-sdk-sample"></a>Покретање Android SDK примера

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Овај пример Android пројекта помаже вам да разумете како SDK ради у апликацији. Нећете морати да пишете кôд. Само додајте кључ за унос и одмах ћете видети догађаје у свом радном простору.

## <a name="prerequisites"></a>Предуслови

- [Android Studio](https://developer.android.com/studio)
- [Кључ за унос](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Преузмите Android SDK пример

1. [Преузмите Android SDK пример увида у ангажовање](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Распакујте компримовану датотеку `ei-android-sample.zip`.
1. Отворите распаковану фасциклу у услузи Android Studio.
1. У датотеци `AndroidManifest.xml`, замените ниску `"Your-Ingestion-Key"` са кључем за унос радног простора из увида у ангажовање у одељку **Администратор** > **Радни простор** > **Водич за инсталацију**. 

   > [!NOTE]
   > Не морате да замените одељак `${applicationId}`. Он се попуњава аутоматски.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Да бисте започели пробни пројекат, изаберите **Покрени**.
1. Прегледајте догађаје у свом радном простору.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
