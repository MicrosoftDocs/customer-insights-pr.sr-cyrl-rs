---
title: Извоз сегмената у LinkedIn Ads (верзија за преглед)
description: Сазнајте како да конфигуришете везу и извозите у LinkedIn Ads.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 06eb915e352ad545f95e96e6108be0f81f43a451
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725326"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Извоз сегмената у LinkedIn Ads (верзија за преглед)

Извезите сегменте обједињених профила клијената у LinkedIn Ads да бисте креирали подударну циљну групу. Користите подударну циљну групу за циљање предузећа и циљање контаката.

## <a name="prerequisites"></a>Предуслови

- Налог [LinkedIn Campaign Manager и](https://business.linkedin.com/marketing-solutions/ads) одговарајуће акредитиве администратора.
- ИД [LinkedIn Campaign Manager налога](https://www.linkedin.com/help/lms/answer/a424270).
- [Конфигурисани сегменти у увидима](segments.md) купаца.
- Извезеним сегментима је потребно најмање једно одређено поље у зависности од тога да ли бирате [циљање контакта](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) или [циљање предузећа на](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) ЛинкедИн. Могућа поља су наведена у кораку подударања **са** подацима [приликом конфигурисања извоза](#configure-an-export).

## <a name="known-limitations"></a>Позната ограничења

- Приватна веза у комбинацији са "Донеси сопствено складиште" (БYОС) није подржана.
- До 100.000 профила купаца по извозу на ЛинкедИн Огласе, што може да потраје и до 10 минута.
- Само сегменти. Сегмент мора да садржи најмање 300 јединствених профила.

## <a name="set-up-connection-to-linkedin-ads"></a>Подешавање везе са ЛинкедИн огласима

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Идите на **Администратор** > **Везе**.

1. Изаберите **додај везу и** одаберите **ЛинкедИн Огласе**.

1. Дајте вези препознатљиво име у пољу **Име за приказ**. Име за приказ и врста везе описују ову везу. Препоручујемо да одаберете назив који објашњава сврху и циљ везе.

1. Одаберите ко може да користи ову везу. Подразумевано су то само администратори. За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Наведите ИД LinkedIn Campaign Manager налога.

1. Прегледајте приватност [и усаглашеност података и](connections.md#data-privacy-and-compliance) изаберите И **слажем се**.

1. Кликните **на дугме** "Повежи" да бисте повезали везу.

1. Изаберите **Потврдите идентитет помоћу услуге LinkedIn** и обезбедите своје администраторске акредитиве за LinkedIn Campaign Manager.

1. Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.

1. Изаберите **Сачувај** да бисте креирали везу.

## <a name="configure-an-export"></a>Конфигурисање извоза

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Идите на **Подаци** > **Извози**.

1. Изаберите **Додај извоз**.

1. У пољу **Веза за извоз**, одаберите везу из одељка LinkedIn Ads. Ако веза није доступна, обратите се администратору.

1. Унесите име за извоз.

1. Одаберите да ли желите да извезете податке да обавите [контакт циљање](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) или [циљање компаније](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) у услузи LinkedIn.

1. У одељку **Подударање података**, за циљање контаката изаберите најмање једно поље које представља е-адресу клијента, Apple Ad ID, ID Google огласа, Google ID корисника, или име и презиме. Ако одаберете циљање предузећа, изаберите барем једно поље које представља назив предузећа, домен е-поште, URL LinkedIn странице, симбол акције или веб-локацију.

1. Опционално, додајте поља да бисте додатно дефинисали извоз. Изаберите **Додај атрибут** за мапирање ових поља.

1. Изаберите сегменте које желите да извезете. Публика која се подудара у услузи LinkedIn Campaign Manager аутоматски ће се креирати са називом сегмената које сте изабрали за извоз. Сваки сегмент ће резултирати засебном подударном циљном групом.

1. Изаберите **Сачувај**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
