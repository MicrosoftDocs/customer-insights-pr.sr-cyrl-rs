---
title: Извоз сегмената у Клавиyо (преглед)
description: Сазнајте како да конфигуришете везу и извезете је у услугу Klaviyo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 075e6758f2c6992a1185756f9beecf852fdd0a96
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724651"
---
# <a name="export-segments-to-klaviyo-preview"></a>Извоз сегмената у Клавиyо (преглед)

Извезите сегменте обједињених профила клијената у Klaviyo и користите их за маркетиншке активности.

## <a name="prerequisites"></a>Предуслови

- [Клавиyо налог и одговарајући](https://www.klaviyo.com/) администраторски акредитиви.
- [Клавиyо АПИ кљуи](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys).
- ИД [Клавиyо листе](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).
- [Конфигурисани сегменти у увидима](segments.md) купаца.
- Обједињени кориснички профили у извезеним сегментима садрже поље које представља адресу е-поште.

## <a name="known-limitations"></a>Позната ограничења

- Приватна веза у комбинацији са "Донеси сопствено складиште" (БYОС) није подржана.
- До милион профила купаца по извозу у Клавиyо, што може да потраје и до 20 минута. Број профила купаца које можете да извезете у Клавиyо зависи од вашег уговора са Клавиyом.
- Само сегменти.

## <a name="set-up-connection-to-klaviyo"></a>Подешавање везе са услугом Klaviyo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Идите на **Администратор** > **Везе**.

1. Изаберите **Додај везу** и одаберите **Клавиyо**.

1. Дајте вези препознатљиво име у пољу **Име за приказ**. Име за приказ и врста везе описују ову везу. Препоручујемо да одаберете назив који објашњава сврху и циљ везе.

1. Одаберите ко може да користи ову везу. Подразумевано су то само администратори. За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Наведите свој Klaviyo API кључ да бисте наставили са пријављивањем.

1. Прегледајте приватност [и усаглашеност података и](connections.md#data-privacy-and-compliance) изаберите И **слажем се**.

1. Кликните **на дугме** "Повежи" да бисте повезали везу.

1. Изаберите **Потврдите аутентичност са услугом Klaviyo** и наведите администраторске акредитиве за Klaviyo.

1. Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.

1. Изаберите **Сачувај** да бисте креирали везу.

## <a name="configure-an-export"></a>Конфигурисање извоза

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Идите на **Подаци** > **Извози**.

1. Изаберите **Додај извоз**.

1. У пољу **Веза за извоз**, одаберите везу из одељка Klaviyo. Ако веза није доступна, обратите се администратору.

1. Унесите име за извоз.

1. Унесите **ИД Клавиyо листе**.

1. У одељку **Подударање података**, у пољу **Е-пошта**, изаберите поље које представља е-адресу клијента.

1. Изаберите сегменте које желите да извезете.

1. Изаберите **Сачувај**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
