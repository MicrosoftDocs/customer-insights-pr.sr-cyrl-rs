---
title: Извоз сегмената у RollWorks (верзија за преглед)
description: Сазнајте како да конфигуришете везу и извезете у RollWorks.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d857bf5d11de86521c4a9d4fc665c020496d89d2
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725143"
---
# <a name="export-segments-to-rollworks-preview"></a>Извоз сегмената у RollWorks (верзија за преглед)

Извезите сегменте обједињених профила клијената у RollWorks и користите их за оглашавање.

## <a name="prerequisites"></a>Предуслови

- РоллWоркс [налог и](https://www.rollworks.com/) одговарајући администраторски акредитиви.
- ИД [оглашивача роллWоркса](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Конфигурисани сегменти у увидима](segments.md) купаца.
- Обједињени кориснички профили у извезеним сегментима садрже поље које представља адресу е-поште.

## <a name="known-limitations"></a>Позната ограничења

- Приватна веза у комбинацији са "Донеси сопствено складиште" (БYОС) није подржана.
- До 250.000 профила купаца по извозу у РоллWоркс, што може да потраје и до 10 минута. Број профила купаца које можете да извезете у РоллWоркс зависи од уговора са роллWоркс-ом.
- Само сегменти.

## <a name="set-up-connection-to-rollworks"></a>Подешавање везе са услугом RollWorks

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Идите на **Администратор** > **Везе**.

1. Изаберите **додај везу и** одаберите **РоллWоркс**.

1. Дајте вези препознатљиво име у пољу **Име за приказ**. Име за приказ и врста везе описују ову везу. Препоручујемо да одаберете назив који објашњава сврху и циљ везе.

1. Одаберите ко може да користи ову везу.  Подразумевано су то само администратори. За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Прегледајте приватност [и усаглашеност података и](connections.md#data-privacy-and-compliance) изаберите И **слажем се**.

1. Кликните **на дугме** "Повежи" да бисте повезали везу.

1. Изаберите **Потврдите идентитет помоћу услуге RollWorks** и обезбедите своје администраторске акредитиве за RollWorks.

1. Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.

1. Изаберите **Сачувај** да бисте креирали везу.

## <a name="configure-an-export"></a>Конфигурисање извоза

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Идите на **Подаци** > **Извози**.

1. Изаберите **Додај извоз**.

1. У пољу **Веза за извоз**, одаберите везу из одељка RollWorks. Ако веза није доступна, обратите се администратору.

1. Унесите име за извоз.

1. Унесите ИД **оглашивача роллWоркса**.

1. У одељку **Подударање података**, у пољу **Е-пошта**, изаберите поље које представља е-адресу клијента.

1. Изаберите сегменте које желите да извезете.

1. Изаберите **Сачувај**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
