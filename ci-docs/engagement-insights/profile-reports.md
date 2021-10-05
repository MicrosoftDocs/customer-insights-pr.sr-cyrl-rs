---
title: Омогућавање унапред дефинисаних извештаја о профилима
description: Како да креирате унапред дефинисане извештаје о профилима груписане према полу, старости и округу или региону порекла.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bf2ec67c9fb99918b87841d3c0b131934e31b58b
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486138"
---
# <a name="out-of-box-profile-reports"></a>Унапред дефинисани извештаји о профилима

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Извештај је збирка визуелизације података која вам помаже да разумете како се корисници понашају. Повезивањем са Customer Insights увидима у циљну групу, увиди у ангажовање могу да прикажу извештај са информацијама о обједињеним профилима клијената. Овај извештај обухвата број профила које имате, груписане према полу, старости и географској локацији.

## <a name="prerequisites"></a>Предуслови

Окружење увида у циљну групу мора да складишти податке у Azure Data Lake Storage налогу који је кориснички управљан.

Ако користите пробну верзију могућности увида у циљну групу или окружење у језеру података којем управља Customer Insights, [обратите нам се](https://go.microsoft.com/fwlink/?linkid=2145734) за помоћ.  


## <a name="enable-the-customer-profile-report"></a>Омогућавање извештаја о профилу клијента

Администратор окружења мора да [повеже увиде у ангажовање и увиде у циљну групу](integrate-audience-insights-engagement-insights.md).

Након навођења детаља о вези, администратор може одобрити приступ другим људима у организацији да виде извештај. Администратор окружења који подешава везу аутоматски има приступ извештају. 

По завршетку везе, функција **Профили** ће бити доступна у левом окну за навигацију. 

- Иди на **Откривање** > **Профили** да бисте видели извештај.

Извештај **Профили** садржи визуализације о полу, старости и географској локацији повезаних профила клијената.

:::image type="content" source="media/customer-profiles.png" alt-text="Извештај о профилу клијента.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]