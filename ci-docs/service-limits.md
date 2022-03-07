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
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350425"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Ограничења услуга у могућностима услуге Customer Insights

Овај чланак описује уграђена ограничења за услугу Customer Insights, која су дизајнирана да осигурају поузданост и стабилност услуге. Сви захтеви за промене могу се упутити преко [форума идеја](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Увиди у циљну групу

| Обласни графикон  | Ограничења  | Белешке |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Сегменти, мере и предвиђања | 300  | Укупан број [сегмената](audience-insights/segments.md), [мера и](audience-insights/measures.md) предвиђања [заједно](audience-insights/predictions.md) не може да премаши 300.  |
| Релације | 20 нивоа дубине у односима у путањама ентитета. | Приликом креирања [сегмената](audience-insights/segments.md) или [мера](audience-insights/measures.md) користећи интерфејс за израду, путање ентитета могу имати до 20 корака односа између почетног ентитета и циљног ентитета.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
