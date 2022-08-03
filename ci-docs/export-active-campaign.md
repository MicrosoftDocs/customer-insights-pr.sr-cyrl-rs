---
title: Извоз сегмената у АцтивеЦампаигн
description: Сазнајте како да конфигуришете везу и извезете је у услугу ActiveCampaign.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 178d2df8edf1abcec72664e19d73a88f2b97f12d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195585"
---
# <a name="export-segments-to-activecampaign-preview"></a>Извоз сегмената у ActiveCampaign (верзија за преглед)

Извезите сегменте обједињених профила купаца у ActiveCampaign и користите их за маркетиншке активности.

## <a name="prerequisites"></a>Предуслови

- АцтивеЦампаигн [налог и](https://www.activecampaign.com/) одговарајући администраторски акредитиви.
- ИД [листе активногцампаигна](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).
- АцтивеЦампаигн [АПИ Кеy](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) и РЕСТ крајња тачка Хостнаме.
- [Конфигурисани сегменти у увидима](segments.md) купаца.
- Обједињени кориснички профили у извезеним сегментима садрже поље које представља адресу е-поште.

## <a name="known-limitations"></a>Позната ограничења

- До милион профила клијената по извозу у АцтивеЦампаигн, што може да потраје и до 90 минута. Број профила клијената које можете извести у ActiveCampaign зависи од вашег уговора са ActiveCampaign-ом.
- Само сегменти.

## <a name="set-up-connection-to-activecampaign"></a>Подесите везу са услугом ActiveCampaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Идите на **Администратор** > **Везе**.

1. Изаберите **додај везу** и одаберите **АцтивеЦампаигн**.

1. Дајте вези препознатљиво име у пољу **Име за приказ**. Име за приказ и врста везе описују ову везу. Препоручујемо да одаберете назив који објашњава сврху и циљ везе.

1. Одаберите ко може да користи ову везу. Подразумевано су то само администратори. За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Унесите свој ActiveCampaign API кључ и име хоста REST крајње тачке. Име хоста REST крајње тачке је само име хоста, без https://.

1. Прегледајте приватност [и усаглашеност података и](connections.md#data-privacy-and-compliance) изаберите И **слажем се**.

1. Кликните **на дугме** "Повежи" да бисте повезали везу.

1. Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.

1. Изаберите **Сачувај** да бисте креирали везу.

## <a name="configure-an-export"></a>Конфигурисање извоза

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Идите на **Подаци** > **Извози**.

1. Изаберите **Додај извоз**.

1. У пољу **Веза за извоз**, изаберите везу из одељка ActiveCampaign. Ако веза није доступна, обратите се администратору.

1. Унесите име за извоз.

1. Унесите **ИД** листе активногцампаигн.

1. У одељку **Подударање података**, у пољу **Е-пошта**, изаберите поље које представља е-адресу клијента.

1. Опционално, извезите **име**, **презиме Телефон** да бисте **креирали** персонализованије е-поруке. Изаберите **Додај атрибут** за мапирање ових поља.

1. Изаберите сегменте које желите да извезете.

1. Изаберите **Сачувај**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
