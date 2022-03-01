---
title: Извезите Customer Insights податке у Marketo
description: Сазнајте како да конфигуришете везу са услугом Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34ccee2894f1f2b552d0c6a88a6810e2dfc677a3
ms.sourcegitcommit: 0b1d3ca11b8ba362a959da0eea15c37e9cdba084
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 11/18/2020
ms.locfileid: "4570421"
---
# <a name="connector-for-marketo-preview"></a>Конектор за Marketo (верзија за преглед)

Извезите сегменте обједињених профила клијената да бисте генерисали кампање, обезбедили маркетинг е-поштом и користили одређене групе клијената са услугом Marketo.

## <a name="prerequisites"></a>Предуслови

-   Имате [Marketo налог](https://login.marketo.com/) и одговарајуће акредитиве администратора.
-   Постоје постојеће листе у услузи Marketo и одговарајући ID-ови. За више информација погледајте [Marketo листе](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Имате [конфигурисане сегменте](segments.md).
-   Обједињени профили клијената у извезеним сегментима садрже поље које представља адресу е-поште.

## <a name="connect-to-marketo"></a>Повезивање са услугом Marketo

1. Идите на **Администратор** > **Одредишта за извоз**.

1. Под **Marketo**, изаберите **Подеси**.

1. Дајте одредишту за извоз препознатљиво име у пољу **Име за приказ**.

1. Унесите **[ Marketo ID клијента, тајну клијента и име хоста REST крајње тачке](https://developers.marketo.com/rest-api/authentication/)**.

1. Унесите **[ID Marketo листе](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. Изаберите **Слажем се** да бисте потврдили **Приватност података и усклађеност** и изаберите **Повежи се** ради успостављања везе са услугом Marketo.

1. Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Извезите снимак екрана за везу са услугом Marketo":::

1. Изаберите **Следеће** да бисте конфигурисали извоз.

## <a name="configure-the-connector"></a>Конфигурисање конектора

1. У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном профилу клијента које представља е-адресу клијента. 

1. По жељи можете да извезете **Име**, **Презиме**, **Град**, **Државу** и **Земљу/регион** као додатна поља за стварање персонализованих е-порука. Изаберите **Додај атрибут** за мапирање ових поља.

1. Изаберите сегменте које желите да извезете. У услузи Marketo можете укупно извести до 1 милион корисничких профила.

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Изаберите поља и сегменте за извоз у Marketo":::

1. Изаберите ставку **Сачувај**.

## <a name="export-the-data"></a>Извоз података

Можете да [извезете податке на захтев](export-destinations.md). Извоз ће се такође покренути са сваким [планираним освежавањем](system.md#schedule-tab). У Marketo-у сада можете пронаћи сегменте у одељку [Marketo листе](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

## <a name="known-limitations"></a>Позната ограничења

- До 1 милион профила по извозу у услузи Marketo.
- Извоз у Marketo је ограничен на сегменте.
- Извоз сегмената са укупно 1 милион профила може трајати до 3 сата. 
- Број профила које можете да извезете у Marketo зависи од и ограничен је вашим уговором са компанијом Marketo.

## <a name="data-privacy-and-compliance"></a>Приватност података и усаглашеност

Када омогућите да Dynamics 365 Customer Insights преноси податке у Marketo, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци. Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Marketo испуњава све обавезе приватности или безбедности које имате. За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.
