---
title: Извезите Customer Insights податке у Google огласима
description: Сазнајте како да конфигуришете везу са Google огласима.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d9a25af3913e755cccec745c532b35aef3cccf9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598265"
---
# <a name="connector-for-google-ads-preview"></a>Конектор за Google огласе (верзија за преглед)

Извезите сегменте обједињених профила клијената у листу корисника Google огласа и користите их за оглашавање у Google претрази, на Gmail-у, YouTube-у и Google мрежи мултимедијалног оглашавања. 

## <a name="prerequisites"></a>Предуслови

-   Имате [налог Google огласа](https://ads.google.com/) и одговарајуће акредитиве администратора.
-   Постоји постојећа публика у Google огласима и одговарајући ID-ови. За више информација погледајте [Корисници Google огласа](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Имате [конфигурисане сегменте](segments.md)
-   Обједињени профили клијената у извезеним сегментима садрже поља која представљају адресу е-поште, име и презиме

## <a name="connect-to-google-ads"></a>Повежите се са Google огласима

1. Идите на **Администратор** > **Одредишта за извоз**.

1. У одељку **Google огласи**, изаберите **Подеси**.

1. Дајте одредишту за извоз препознатљиво име у пољу **Име за приказ**.

1. Унесите **[ID клијента за Google огласе](https://support.google.com/google-ads/answer/1704344)**.

1. Унесите **[токен одобреног програмера за Google огласе](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.

1. Унесите **[ID корисника за Google огласе](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** и изаберите **Повежите се** да бисте започели повезивање са Google огласима.

1. Изаберите **Потврдите идентитет у Google огласима** и наведите акредитиве за Google огласе.

1. Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Извезите снимак екрана за везу са Google огласима":::

1. Изаберите **Следеће** да бисте конфигурисали извоз.

## <a name="configure-the-connector"></a>Конфигурисање конектора

1. У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном профилу клијента које представља е-адресу клијента. Поновите исте кораке за поља **Име** и **Презиме**.

1. Изаберите сегменте које желите да извезете. У Google огласима можете укупно извести до 1 милион корисничких профила.

1. Изаберите ставку **Сачувај**.

## <a name="export-the-data"></a>Извоз података

Можете да [извезете податке на захтев](export-destinations.md). Извоз ће се такође покренути са сваким [планираним освежавањем](system.md#schedule-tab). У Google огласима сада можете пронаћи сегменте у одељку [Корисници Google огласа](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>Позната ограничења

- До 1 милион профила по извозу у Google огласима.
- Извоз у Google огласе је ограничен на сегменте.
- Извоз сегмената са укупно 1 милион профила може трајати до 5 минута због ограничења на страни добављача. 
- Подударање у Google огласима може да потраје до 48 сати.

## <a name="data-privacy-and-compliance"></a>Приватност података и усаглашеност

Када омогућите да Dynamics 365 Customer Insights преноси податке у Google огласе, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци. Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Google огласи испуњавају све обавезе приватности или безбедности које имате. За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.


[!INCLUDE[footer-include](../includes/footer-banner.md)]