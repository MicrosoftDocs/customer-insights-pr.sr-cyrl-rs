---
title: Извезите Customer Insights податке у DotDigital
description: Сазнајте како да конфигуришете везу са услугом DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 573a22e24f84c65fc4d21faf823cace801cc7ea3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269118"
---
# <a name="connector-for-dotdigital-preview"></a>Конектор за DotDigital (верзија за преглед)

Извезите сегменте обједињених профила купаца у DotDigital адресаре и користите их за кампање, маркетинг путем е-поште и за изградњу сегмената купаца помоћу услуге DotDigital. 

## <a name="prerequisites"></a>Предуслови

-   Имате [DotDigital налог](https://dotdigital.com/) и одговарајуће акредитиве администратора.
-   Постоји постојећа публика у адресарима у услузи DotDigital и одговарајући ID-ови. ID се може наћи у URL-у када одаберете и отворите адресар. За више информација погледајте [адресаре за DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   [Конфигурисали сте сегменте](segments.md) у увидима о корисницима.
-   Обједињени профили клијената у извезеним сегментима садрже поље које представља адресу е-поште.

## <a name="connect-to-dotdigital"></a>Повезивање са услугом DotDigital

1. Идите на **Администратор** > **Одредишта за извоз**.

1. У одељку **DotDigital**, изаберите **Подеси**.

1. Дајте одредишту за извоз препознатљиво име у пољу **Име за приказ**.

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Окно за конфигурацију извоза услуге DotDigital.":::

1. Унесите своје **корисничко име и лозинку за DotDigital**.

1. Унесите **[ID DotDigital адресара](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.

1. Изаберите **Повежи се** за иницијализацију везе са услугом DotDigital.

1. Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.

1. Изаберите **Следеће** да бисте конфигурисали извоз.

## <a name="configure-the-connector"></a>Конфигурисање конектора

1. У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном профилу клијента које представља е-адресу клијента. Поновите исте кораке за друга опционална поља као што су **Име**, **Презиме**, **Пуно име**, **Пол** и **Поштански број**.

1. Изаберите сегменте које желите да извезете. У услузи DotDigital можете укупно извести до 1 милион корисничких профила.

1. Изаберите ставку **Сачувај**.

## <a name="export-the-data"></a>Извоз података

Можете да [извезете податке на захтев](export-destinations.md). Извоз ће се такође покренути са сваким [планираним освежавањем](system.md#schedule-tab). У услузи DotDigital сада можете да пронађете своје сегменте у [DotDigital адресарима](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

## <a name="known-limitations"></a>Позната ограничења

- До 1 милион профила по извозу у услузи DotDigital.
- Извоз у DotDigital је ограничен на сегменте.
- Извоз сегмената са укупно 1 милион профила може трајати до 3 сата због ограничења на страни добављача. 
- Број профила које можете да извезете у DotDigital зависи од и ограничен је вашим уговором са компанијом DotDigital.

## <a name="data-privacy-and-compliance"></a>Приватност података и усаглашеност

Када омогућите да Dynamics 365 Customer Insights преноси податке у DotDigital, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци. Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да DotDigital испуњава све обавезе приватности или безбедности које имате. За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.


[!INCLUDE[footer-include](../includes/footer-banner.md)]