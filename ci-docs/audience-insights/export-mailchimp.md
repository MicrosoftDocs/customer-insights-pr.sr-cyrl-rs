---
title: Извезите Customer Insights податке у Mailchimp
description: Сазнајте како да конфигуришете везу са услугом Mailchimp.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598219"
---
# <a name="connector-for-mailchimp-preview"></a>Конектор за Mailchimp (верзија за преглед)

Извезите сегменте обједињених профила клијената у Mailchimp да бисте креирали билтене и кампање е-поште.

## <a name="prerequisites"></a>Предуслови

-   Имате [Mailchimp налог](https://mailchimp.com/) и одговарајуће акредитиве администратора.
-   Постоји постојећа публика у Mailchimp-у и одговарајући ID-ови. За више информација погледајте [Mailchimp корисници](https://mailchimp.com/help/create-audience/).
-   Имате [конфигурисане сегменте](segments.md)
-   Обједињени профили клијената у извезеним сегментима садрже поље које представља адресу е-поште.

## <a name="connect-to-mailchimp"></a>Повежите се са услугом Mailchimp

1. Идите на **Администратор** > **Одредишта за извоз**.

1. Под **Mailchimp**, изаберите **Подеси**.

1. Дајте одредишту за извоз препознатљиво име у пољу **Име за приказ**.

1. Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.

1. Унесите **[Mailchimp ID корисника](https://mailchimp.com/help/find-audience-id/)** и изаберите **Повежите се** да бисте започели повезивање са Mailchimp-ом.

1. Изаберите **Потврдите идентитет у Mailchimp-у** и наведите акредитиве за Mailchimp.

1. Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Извезите снимак екрана за везу са услугом Mailchimp":::

1. Изаберите **Следеће** да бисте конфигурисали извоз.

## <a name="configure-the-connector"></a>Конфигурисање конектора

1. У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном профилу клијента које представља е-адресу клијента. 

1. По жељи можете да извезете **Име** и **Презиме** као додатна поља за стварање персонализованих е-порука. Изаберите **Додај атрибут** за мапирање ових поља.

1. Изаберите сегменте које желите да извезете. У услузи Mailchimp можете укупно извести до 1 милион корисничких профила.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Изаберите поља и сегменте за извоз у Mailchimp":::

1. Изаберите ставку **Сачувај**.

## <a name="export-the-data"></a>Извоз података

Можете да [извезете податке на захтев](export-destinations.md). Извоз ће се такође покренути са сваким [планираним освежавањем](system.md#schedule-tab). У Mailchimp-у сада можете пронаћи сегменте у одељку [Mailchimp корисници](https://mailchimp.com/help/create-audience/).

## <a name="known-limitations"></a>Позната ограничења

- До 1 милион профила по извозу у услузи Mailchimp.
- Извоз у Mailchimp је ограничен на сегменте.
- Извоз сегмената са укупно 1 милион профила може трајати до три сата због ограничења на страни добављача. 
- Број профила које можете да извезете у Mailchimp зависи од и ограничен је вашим уговором са компанијом Mailchimp.

## <a name="data-privacy-and-compliance"></a>Приватност података и усаглашеност

Када омогућите да Dynamics 365 Customer Insights преноси податке у Mailchimp, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци. Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Mailchimp испуњава све обавезе приватности или безбедности које имате. За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.


[!INCLUDE[footer-include](../includes/footer-banner.md)]