---
title: Ограничења услуге у Дyнамицс 365 Цустомер Инсигхтс
description: Разумевање ограничења и рестрикција.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eb25e050b8aa768e6e1d8d4c5adce6095cccc346
ms.sourcegitcommit: 31a9b531dacd3a6465b3030c704ff5c085b7e122
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 11/10/2021
ms.locfileid: "7791998"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Ограничења услуга у могућностима услуге Customer Insights

Овај чланак описује уграђена ограничења за услугу Customer Insights, која су дизајнирана да осигурају поузданост и стабилност услуге. Сви захтеви за промене могу се упутити преко [форума идеја](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Увиди у циљну групу

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Ограничења услуге у Дyнамицс 365 Цустомер Инсигхтс корисници увида

| Обласни графикон  | Ограничења  | Белешке |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Сегменти, мере и предвиђања | 300  | Укупан број [сегмената](audience-insights/segments.md), мера и [...](audience-insights/measures.md)[предвиђања](audience-insights/predictions.md) заједно не може да премаши 300.  |
| Релације | 20 нивоа дубине у односима у путањама ентитета. | Приликом креирања [сегмената](audience-insights/segments.md) или [мера](audience-insights/measures.md) користећи интерфејс за израду, путање ентитета могу имати до 20 корака односа између почетног ентитета и циљног ентитета.  |


## <a name="engagement-insights"></a>Увиди у ангажовање

### <a name="workspace-and-event-quotas"></a>Квоте за радни простор и догађаје

Увиди о ангажовање је изузетно скалабилна апликација која може подржати милионе догађаја у секунди. Током верзије за јавни преглед, догађаји имају ограничење обима. Такође постоји ограничење броја радних простора у организацији.

### <a name="engagement-insights-limits"></a>Ограничења увида у ангажовање

- Максимални обим догађаја по радном простору = 100 догађаја у секунди

- Максималан број радних простора по организацији = 100

Када догађаји пређу ограничење, то може довести до губитка података у извештајима заснованим на тим догађајима. Можете да [контактирате подршку](https://go.microsoft.com/fwlink/?linkid=2145734) како бисте затражили повећање обима пре него што прекорачите ограничења. Радићемо са вама како бисмо утврдили вашу потребу за повећањем обима и подржали ваш захтев.


[!INCLUDE[footer-include](includes/footer-banner.md)]
