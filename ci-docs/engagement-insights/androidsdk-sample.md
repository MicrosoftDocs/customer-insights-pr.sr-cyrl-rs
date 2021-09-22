---
title: Android SDK пример
description: Пример пројекта за упознавање платформе Android SDK
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ba51961bc7f9555d7dba5b6a21c8636011438d75cba87bc132b896841c467a33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035844"
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
