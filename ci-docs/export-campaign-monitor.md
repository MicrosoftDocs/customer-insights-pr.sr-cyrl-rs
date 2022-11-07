---
title: Извоз сегмената у Campaign Monitor (верзија за преглед)
description: Сазнајте како да конфигуришете везу и извезете садржај у Campaign Monitor.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 82303c7bcb269ee68419c9639ee743e13451f273
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724702"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Извоз сегмената у Campaign Monitor (верзија за преглед)

Извезите сегменте обједињених профила клијената у Campaign Monitor и користите их за маркетиншке активности.

## <a name="prerequisites"></a>Предуслови

- Налог [надгледања кампање и](https://www.campaignmonitor.com/) одговарајуће акредитиве администратора.
- [ИД листе надгледања кампање](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- Генерисани [АПИ кључ из поставки](https://www.campaignmonitor.com/api/getting-started/) налога **у програму** "Надгледање кампање" да бисте добили ИД АПИ листе.
- [Конфигурисани сегменти у увидима](segments.md) купаца.
- Обједињени кориснички профили у извезеним сегментима садрже поље које представља адресу е-поште.

## <a name="known-limitations"></a>Позната ограничења

- Приватна веза у комбинацији са "Донеси сопствено складиште" (БYОС) није подржана.
- До милион профила клијената по извозу у надгледање кампање, што може да потраје и до 20 минута. Број профила клијената које можете да извезете у надгледање кампање зависи од уговора са надгледање кампање.
- Само сегменти.

## <a name="set-up-connection-to-campaign-monitor"></a>Подешавање везе са услугом Campaign Monitor

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Идите на **Администратор** > **Везе**.

1. Изаберите **ставку Додај везу** и одаберите **надгледање кампање**.

1. Дајте вези препознатљиво име у пољу **Име за приказ**. Име за приказ и врста везе описују ову везу. Препоручујемо да одаберете назив који објашњава сврху и циљ везе.

1. Одаберите ко може да користи ову везу. Подразумевано су то само администратори. За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Прегледајте приватност [и усаглашеност података и](connections.md#data-privacy-and-compliance) изаберите И **слажем се**.

1. Изаберите **Повежите се** да би се иницијализовала веза са услугом Campaign Monitor.

1. Изаберите **Потврдите идентитет помоћу услуге Campaign Monitor** и обезбедите своје администраторске акредитиве за Campaign Monitor.

1. Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.

1. Изаберите **Сачувај** да бисте креирали везу.

## <a name="configure-an-export"></a>Конфигурисање извоза

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Идите на **Подаци** > **Извози**.

1. Да бисте креирали нови извоз, изаберите **Додај извоз**.

1. У пољу **Веза за извоз**, одаберите везу из одељка Campaign Monitor. Ако веза није доступна, обратите се администратору.

1. Унесите име за извоз.

1. Унесите ИД **листе надгледања кампање**.

1. У одељку **Подударање података**, у пољу **Е-пошта**, изаберите поље које представља е-адресу клијента. То је потребно да извезете сегменте у Campaign Monitor.

1. Изаберите сегменте које желите да извезете.

1. Изаберите **Сачувај**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
