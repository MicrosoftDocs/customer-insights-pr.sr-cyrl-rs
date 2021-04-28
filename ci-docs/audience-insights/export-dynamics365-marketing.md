---
title: Извезите Customer Insights податке у Dynamics 365 Marketing
description: Сазнајте како да конфигуришете везу и извезете у Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a13f6f81f5e2570d3302d88c02755f1d86321a01
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759655"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Коришћење сегмената у услузи Dynamics 365 Marketing (верзија за преглед)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Користите [сегменте](segments.md) да бисте генерисали кампање и контактирали одређене групе клијената помоћу услуге Dynamics 365 Marketing. Више информација потражите у чланку [Коришћење сегмената из услуга Dynamics 365 Customer Insights уз Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite-for-a-connection"></a>Предуслов за везу

- Записи контаката морају бити присутни у услузи Dynamics 365 Marketing да бисте могли да извезете сегмент из услуге Customer Insights у Marketing. Прочитајте више о томе како се уносе контакти у [Dynamics 365 Marketing помоћу услуге Common Data Services](connect-power-query.md).

  > [!NOTE]
  > Извоз сегмената из увида о корисницима у Marketing неће креирати нове записе контаката у инстанцама услуге Marketing. Евиденција контаката из услуге Marketing мора се унети у увид о корисницима и користити као извор података. Такође их треба укључити у јединствени ентитет клијента да би се ID-ови клијената мапирали у ID-ове контаката да би сегменти могли да се извезу.

## <a name="set-up-connection-to-marketing"></a>Подешавање везе за Marketing

1. Идите на **Администратор** > **Везе**.

1. Изаберите **Додај везу** и бирајте **Dynamics 365 Marketing** да бисте конфигурисали везу.

1. Дајте вези препознатљиво име у пољу **Име за приказ**. Име за приказ и врста везе описују ову везу. Препоручујемо да одаберете назив који објашњава сврху и циљ везе.

1. Одаберите ко може да користи ову везу. Ако ништа не предузмете, подразумевани ће бити Администратори. За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Унесите URL организације за Marketing у поље **Адреса сервера**.

1. У одељку **Администраторски налог на серверу**, изаберите **Пријавите се** и изаберите Dynamics 365 Marketing налог.

1. Мапирајте поље корисничког ID-а са Dynamics 365 ID-ом контакта.

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
