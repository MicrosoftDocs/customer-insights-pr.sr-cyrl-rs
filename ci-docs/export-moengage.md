---
title: Извоз сегмената у МоЕнгаге
description: Сазнајте како да конфигуришете везу и извезете у МоЕнгаге.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ffc591c01a5a9434cde41f2da25fa930a515b8c1
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9199242"
---
# <a name="export-segments-to-moengage-preview"></a>Извоз сегмената у МоЕнгаге (преглед)

Извезите сегменте обједињених профила клијената у МоЕнгаге и користите их за маркетинг е-поште у МоЕнгагеу.

## <a name="prerequisites-for-a-connection"></a>Предуслови за везу

- [МоЕнгаге налог и](https://www.moengage.com/) одговарајући администраторски акредитиви.
- МоЕнгаге АПИ кључ из подешавања &гт; АПИ у МоЕнгагеу.
- [Конфигурисани сегменти у увидима](segments.md) купаца.

## <a name="known-limitations"></a>Позната ограничења

- До 100.000 профила купаца по извозу у МоЕнгаге, што може да потраје и до 15 минута. Број профила клијената које можете да извезете у МоЕнгаге зависи од вашег уговора са МоЕнгагеом.
- Само сегменти.

## <a name="set-up-connection-to-moengage"></a>Успостави везу са МоЕнгагеом

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Идите на **Администратор** > **Везе**.

1. Кликните **на дугме Додај** везу и одаберите **опцију МоЕнгаге** да бисте конфигурисали везу.

1. Дајте вези препознатљиво име у пољу **Име за приказ**. Име за приказ и врста везе описују ову везу. Препоручујемо да одаберете назив који објашњава сврху и циљ везе.

1. Одаберите ко може да користи ову везу. Ако ништа не предузмете, подразумевани ће бити Администратори. За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Унесите [Свој МоЕнгаге Дата АПИ ИД и АПИ кључ](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. Прегледајте приватност [и усаглашеност података и](connections.md#data-privacy-and-compliance) изаберите И **слажем се**.

1. Кликните **на дугме** "Повежи" да бисте повезали везу са моЕнгагеом.

1. Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.

1. Изаберите **Сачувај** да бисте креирали везу.

## <a name="configure-an-export"></a>Конфигурисање извоза

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Идите на **Подаци** > **Извози**.

1. Да бисте креирали нови извоз, изаберите **Додај извоз**.

1. У пољу **Веза за извоз** одаберите везу из одељка МоЕнгаге. Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.

1. У одељку **Подударање података**, у пољу **Е-пошта**, изаберите поље које представља е-адресу клијента. Поновите исте кораке за друга опционална поља.

1. Изаберите сегменте које желите да извезете. Креираћемо један или више сегмената са истим именом као изабрани сегменти у МоЕнгагеу у оквиру **"Сегменти прилагођених** > **сегмената"**.

1. Изаберите **Сачувај**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]