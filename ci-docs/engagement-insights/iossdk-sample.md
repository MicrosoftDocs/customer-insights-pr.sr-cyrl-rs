---
title: Покретање iOS SDK примера
description: Пример пројекта за учење о платформи iOS SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 053e626d06d3e17b39b448987410058e45e8ae0385f3ecdef40314cb46ae4bf4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036846"
---
# <a name="run-the-ios-sdk-sample"></a>Покретање iOS SDK примера

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Овај пример iOS пројекта помаже вам да разумете како SDK ради у апликацији. Нећете морати да пишете кôд. Само додајте кључ за унос и одмах ћете видети догађаје у свом радном простору.

## <a name="prerequisites"></a>Предуслови

- [Xcode верзије 9+](https://developer.apple.com/xcode/downloads/)
- [Кључ за унос](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>Преузмите iOS SDK пример

1. [Преузмите iOS SDK пример увида у ангажман](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. Распакујте компримовану датотеку `ei-ios-sample.zip`.
1. Отворите пример пројекта апликације у услузи Xcode.
1. У датотеци `EIConfig.plist`, замените ниску `“YOUR-INGESTION-KEY”` у пољу `ingestionKey` са кључем за унос радног простора из увида у ангажовање у одељку **Администратор** > **Радни простор** > **Водич за инсталацију**.
1. Да бисте започели пробни пројекат, изаберите **Покрени**.
1. Прегледајте догађаје у свом радном простору.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
