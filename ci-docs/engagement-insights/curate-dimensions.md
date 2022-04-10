---
title: Користите демографске аспекте за раздвајање података о понашању (одржавани аспекти)
description: Користите одржаване аспекте обједињених профила да бисте омогућили својства профила клијента увида у циљну групу.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 95395e09bc0ba5ba93138957c62105f31c709e91
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/16/2022
ms.locfileid: "8233065"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>Користите демографске аспекте за раздвајање података о понашању

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Коришћењем демографских аспеката обједињених профила, увидима у ангажовање корисници могу да приступају својствима профила увида у циљну групу. Затим можете користити та својства у интерактивним анализама података о понашању, укључујући податке прикупљене увидом у ангажовање на вашој веб-локацији или у апликацији за мобилне уређаје.

>[!NOTE]
> Увид у ангажовање укључује готове аспекте за својства догађаја. Још информација: [Приказ и креирање аспеката](dimensions.md)

## <a name="prerequisite"></a>Предуслов

- Окружење увида у ангажовање у којем имате податке о корисничком профилу повезане са окружењем увида у циљну групу где се креирају профили клијената. Још информација: [Креирање везе између увида у циљне групе и увида у ангажовање](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> Када креирате везу између окружења увида у циљну групу и увида у ангажовање, можда ће вам требати само подаци специфични за својства профила корисника, који могу бити корисни као димензије у увидима у ангажовање. За више информација, идите на [Омогућавање атрибута и сегмената обједињених профила увида у циљну групу](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments).

## <a name="create-a-new-custom-report"></a>Креирање новог прилагођеног извештаја

1. У левом окну изаберите **Прилагођено** > **Нови извештај**, а затим изаберите жељену метрику. (За овај пример смо одабрали **Број прегледа странице по сату**.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="Изаберите метрику.":::

2. У уређивачу визуализације, изаберите **Аспекти**, а затим изаберите **Демографски** у падајућем менију **Тип аспекта**.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="Изаберите демографску категорију.":::

3. Изаберите аспект **Signal.Customer.*xxx***. (Овај пример приказује Signal.Customer.Country.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="Изаберите аспект.":::
  
## <a name="limitations"></a>Ограничења

Тренутно можете да користите само демографске аспекте за раздвајање података о понашању.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
