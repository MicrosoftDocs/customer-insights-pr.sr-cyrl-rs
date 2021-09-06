---
title: Ограничења услуге
description: Разумевање ограничења и рестрикција.
ms.date: 07/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2966f2ede1ddbe0245471771365cbf5b593be608764aa10ed28d962c52bb8067
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034882"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Ограничења услуге у Dynamics 365 Customer Insights могућности увида о корисницима

Овај чланак описује уграђена ограничења за услугу Customer Insights, која су дизајнирана да осигурају поузданост и стабилност услуге. Сви захтеви за промене могу се упутити преко [форума идеја](https://go.microsoft.com/fwlink/?linkid=2074172). 
 
| Обласни графикон  | Ограничења  | Напомене |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Сегменти и мере | 100 сегмената или мера. | Укупан број активних[ сегмената](segments.md) и[ мера](measures.md) комбиновано не може прећи 100.  |
| Релације | 20 нивоа дубине у односима у путањама ентитета. | Приликом креирања [сегмената](segments.md) или [мера](measures.md) користећи интерфејс за израду, путање ентитета могу имати до 20 корака односа између почетног ентитета и циљног ентитета.  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]