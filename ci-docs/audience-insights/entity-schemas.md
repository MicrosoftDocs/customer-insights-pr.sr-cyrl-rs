---
title: Шеме Customer Insights ентитета у услузи Common Data Model
description: Радите са ентитетима у услузи Common Data Model.
ms.date: 04/17/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 6667e411a1b56e13105a6b59b7b5d249bc8141ea
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596379"
---
# <a name="entity-schemas-in-common-data-model"></a>Шеме ентитета у платформи Common Data Model

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Common Data Model](/common-data-model/) је декларативна спецификација и дефиниција стандардних ентитета који представљају уобичајене концепте и активности у пословним и продуктивним апликацијама. Овај модел се проширује и на посматрачке и аналитичке податке. Common Data Model пружа добро дефинисане, модуларне и прошириве пословне ентитете – попут пословног контакта, пословне јединице, предмета, контакта, потенцијалног клијента, могућности за пословање и производа – као и интеракције са добављачима, радницима и клијентима – као што су активности и уговори о нивоу услуга. Свако може да изгради и прошири Common Data Model дефиниције да би пронашао додатне идеје специфичне за пословање.

Овај заједнички модел података омогућава апликацијама и интеграторима података да лакше сарађују пружајући обједињену дефиницију података. Common Data Model укључује богат систем метаподатака са стандардним ентитетима, релацијама, хијерархијама, особинама и још много тога. Настао је из Dynamics 365 апликација и отворен је на GitHub-у са преко 260 стандардних ентитета. Велики систем унутрашњих и спољних партнера доприноси индустријским концептима платформи Common Data Model.

Више система и платформи данас примењује Common Data Model, укључујући Power BI токове података и Azure Data Services. То је већ подржано у услугама Common Data Service, Dynamics 365, Power Apps, Power BI и предстојећим Azure услугама података, које директно прикупљају вредност према [Отвореној иницијативи за податке](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Шеме Customer Insights ентитета

Да бисмо успоставили свеобухватан поглед на клијента и учинили Customer Insights моделе доступним платформи Common Data Model ради проширивости, објавили смо следеће шеме ентитета:

| Ентитет | Опис |
|---------|---------|
|[CustomerActivity](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Активност коју обавља корисник која има посматрачку вредност за предузеће. |
|[CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Особа или организација која је или обављала или има потенцијал да се бави пословним активностима. |
|[MeasureDefinition](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Дефиниција KPI-ова издељених у нула или више димензија (као што су Месечно активни корисници, Укупна потрошња по клијенту, Просечни трошкови куповине клијента) |
|[Segment](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Дефинише групу чланова са заједничким особинама. |
|[SegmentMembership](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Чланови који учествују у одређеном сегменту. |

За више информација, погледајте документацију о [Customer Insights шемама ентитета у платформи Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Приказ ентитета коришћењем Common Data Model навигатора ентитета

Можете прегледати ентитете у [Навигатору Common Data Model ентитета](https://microsoft.github.io/CDM/). Изаберите дугме **Учитај са GitHub-а!** и идите до **foundationCommon** > **crmCommon** > **решења** > **customerInsights**, где ћете наћи листу Customer Insights ентитета и њихове дефиниције.
> [!div class="mx-imgBorder"]
> ![Навигатор CDM ентитета који приказује ентитет CustomerActivity](media/CDM-entity-navigator.png "Навигатор CDM ентитета који приказује ентитет CustomerActivity")


[!INCLUDE[footer-include](../includes/footer-banner.md)]