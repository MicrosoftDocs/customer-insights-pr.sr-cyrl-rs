---
title: Извезите Customer Insights податке у Dynamics 365 Marketing
description: Сазнајте како да конфигуришете везу и извезете у Dynamics 365 Marketing.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 0bd2bfa7402ed19cb92ff1f35208b150cfec48c3
ms.sourcegitcommit: d168a738a08adb8b4b2e410bdaa3716d7b63cc9b
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/17/2022
ms.locfileid: "8455850"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Коришћење сегмената у услузи Dynamics 365 Marketing (верзија за преглед)



Користите [сегменте](segments.md) да бисте генерисали кампање и контактирали одређене групе клијената помоћу услуге Dynamics 365 Marketing. Више информација потражите у чланку [Коришћење сегмената из услуге Dynamics 365 Customer Insights у услузи Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Ако користите нове могућности услуге Dynamics 365 Marketing за оркестрацију пута који пређе корисник у реалном времену у Dataverse организацији, не морате да креирате стандардни извоз у Dynamics 365 Marketing. Контакти и сегменти из увида у циљну групу доступни су директно у услузи Dynamics 365 Marketing након повезивања услуга Marketing и Customer Insights. Пре него што избришете постојеће извозе, прегледајте документацију о томе [како да повежете увиде у циљну групу и Dynamics 365 Marketing оркестрацију пута који пређе корисник](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Предуслов за везу

- Записи контаката морају бити присутни у услузи Dynamics 365 Marketing да бисте могли да извезете сегмент из услуге Customer Insights у Marketing. Прочитајте више о томе како се уносе контакти у [Dynamics 365 Marketing помоћу услуге Microsoft Dataverse](connect-dataverse-managed-lake.md).

  > [!NOTE]
  > Извоз сегмената из увида о корисницима у Marketing неће креирати нове записе контаката у инстанцама услуге Marketing. Евиденција контаката из услуге Marketing мора се унети у увид о корисницима и користити као извор података. Такође их треба укључити у јединствени ентитет клијента да би се ID-ови клијената мапирали у ID-ове контаката да би сегменти могли да се извезу.

## <a name="set-up-connection-to-marketing"></a>Подешавање везе за Marketing

1. Идите на **Администратор** > **Везе**.

1. Изаберите **Додај везу** и бирајте **Dynamics 365 Marketing** да бисте конфигурисали везу.

1. Дајте вези препознатљиво име у пољу **Име за приказ**. Име за приказ и врста везе описују ову везу. Препоручујемо да одаберете назив који објашњава сврху и циљ везе.

1. Одаберите ко може да користи ову везу. Ако ништа не предузмете, подразумевани ће бити Администратори. За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Унесите URL организације за Marketing у поље **Адреса сервера**.

1. У одељку **Администраторски налог на серверу**, изаберите **Пријавите се** и изаберите Dynamics 365 Marketing налог.

1. Мапирај поље ИД контакта у ентитету купца у Дyнамицс 365 ИД контакта.

1. Изаберите **Сачувај** да бисте креирали везу. 

## <a name="configure-an-export"></a>Конфигурисање извоза

Овај извоз можете да конфигуришете ако имате приступ вези ове врсте. За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).

1. Идите на **Подаци** > **Извози**.

1. Да бисте креирали нови извоз, изаберите **Додај одредиште**.

1. У пољу **Веза за извоз**, одаберите везу из одељка Dynamics 365 Marketing. Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.

1. Изаберите један или више сегмената.

1. Изаберите ставку **Сачувај**.

Чување извоза не покреће извоз одмах.

Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab). Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
