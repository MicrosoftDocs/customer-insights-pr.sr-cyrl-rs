---
title: Ограничења услуге у услузи Dynamics 365 Customer Insights
description: Разумевање ограничења и рестрикција.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641780"
---
# <a name="service-limits-in-customer-insights"></a>Ограничења услуге у увидима клијената

Овај чланак описује уграђена ограничења за услугу Customer Insights, која су дизајнирана да осигурају поузданост и стабилност услуге. Сви захтеви за промене могу се упутити преко [форума идеја](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="customer-insights"></a>Customer Insights

| Обласни графикон  | Ограничења  | Белешке |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Сегменти, мере и предвиђања | 300  | Укупан број [сегмената](segments.md), [мера и](measures.md) предвиђања [заједно](predictions.md) не може да премаши 300.  |
| Релације | 20 нивоа дубине у односима у путањама ентитета. | Приликом креирања [сегмената](segments.md) или [мера](measures.md) користећи интерфејс за израду, путање ентитета могу имати до 20 корака односа између почетног ентитета и циљног ентитета.  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
