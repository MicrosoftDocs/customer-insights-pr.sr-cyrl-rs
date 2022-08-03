---
title: Извоз сегмената у Дyнамицс 365 маркетинг (преглед)
description: Сазнајте како да конфигуришете везу и извезете у Dynamics 365 Marketing.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196642"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Извоз сегмената у Дyнамицс 365 маркетинг (преглед)

Користите [сегменте](segments.md) за генерисање кампања и контакт са одређеним групама купаца помоћу [Дyнамицс 365 маркетинга](/dynamics365/marketing/customer-insights-segments).

Ако користите нове могућности услуге Dynamics 365 Marketing за оркестрацију пута који пређе корисник у реалном времену у Dataverse организацији, не морате да креирате стандардни извоз у Dynamics 365 Marketing. Контакти и сегменти из увида клијената доступни су директно у дyнамицс 365 маркетингу након повезивања маркетинга и увида купаца. Пре него што избришете постојећи извоз, прегледајте документацију о томе како [да повежете корисничке увиде и Дyнамицс 365 маркетинг пут који пређе корисник оркестрацију](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>Предуслов

Записи контаката морају бити присутни у услузи Dynamics 365 Marketing да бисте могли да извезете сегмент из услуге Customer Insights у Marketing. Прочитајте више о томе како се уносе контакти у [Dynamics 365 Marketing помоћу услуге Microsoft Dataverse](connect-dataverse-managed-lake.md).

> [!NOTE]
> Извоз сегмената из увида купаца у маркетинг неће креирати нове записе контаката у маркетиншким инстанцама. Записи контаката из маркетинга морају бити унети у увиде клијената и користити се као извор података. Такође их треба укључити у јединствени ентитет клијента да би се ID-ови клијената мапирали у ID-ове контаката да би сегменти могли да се извезу.

## <a name="set-up-connection-to-marketing"></a>Подешавање везе за Marketing

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Идите на **Администратор** > **Везе**.

1. Изаберите **додај везу** и одаберите **Дyнамицс 365 маркетинг**.

1. Дајте вези препознатљиво име у пољу **Име за приказ**. Име за приказ и врста везе описују ову везу. Препоручујемо да одаберете назив који објашњава сврху и циљ везе.

1. Одаберите ко може да користи ову везу. Подразумевано су то само администратори. За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Унесите URL организације за Marketing у поље **Адреса сервера**.

1. У одељку **Администраторски налог на серверу**, изаберите **Пријавите се** и изаберите Dynamics 365 Marketing налог.

1. Мапирај поље ИД контакта у ентитету купца у Дyнамицс 365 ИД контакта.

1. Прегледајте приватност [и усаглашеност података и](connections.md#data-privacy-and-compliance) изаберите И **слажем се**.

1. Изаберите **Сачувај** да бисте креирали везу.

## <a name="configure-an-export"></a>Конфигурисање извоза

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Идите на **Подаци** > **Извози**.

1. Изаберите **Додај извоз**.

1. У пољу **Веза за извоз**, одаберите везу из одељка Dynamics 365 Marketing. Ако веза није доступна, обратите се администратору.

1. Унесите име за извоз.

1. Изаберите поље ИД контакта у ентитету купца које се подудара са Дyнамицс 365 ИД-ом контакта.

1. Изаберите сегменте које желите да извезете.

1. Изаберите **Сачувај**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
