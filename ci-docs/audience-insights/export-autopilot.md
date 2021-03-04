---
title: Извезите Customer Insights податке у Autopilot
description: Сазнајте како да конфигуришете везу са услугом Autopilot.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269256"
---
# <a name="connector-for-autopilot-preview"></a>Конектор за Autopilot (преглед)

Извезите сегменте обједињених профила клијената у Autopilot и користите их за маркетинг путем е-поште у услузи Autopilot. 

## <a name="prerequisites"></a>Предуслови

-   Имате [Autopilot налог](https://www.autopilothq.com/) и одговарајуће акредитиве администратора.
-   [Конфигурисали сте сегменте](segments.md) у увидима о корисницима.
-   Обједињени профили клијената у извезеним сегментима садрже поље које представља адресу е-поште.

## <a name="connect-to-autopilot"></a>Повезивање са услугом Autopilot

1. Идите на **Администратор** > **Одредишта за извоз**.

1. У делу **Autopilot** изаберите **Подеси**.

1. Дајте одредишту за извоз препознатљиво име у пољу **Име за приказ**.

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Окно за конфигурацију за везу са услугом Autopilot.":::

1. Унесите свој **API кључ за Autopilot** [API кључ за Autopilot](https://autopilot.docs.apiary.io/#).

1. Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.

1. Изаберите **Повежи се** за иницијализацију везе са услугом Autopilot.

1. Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.

1. Изаберите **Следеће** да бисте конфигурисали извоз.

## <a name="configure-the-connector"></a>Конфигурисање конектора

1. У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном профилу клијента које представља е-адресу клијента. Поновите исте кораке за друга опционална поља као што су **Име**, **Презиме**.

1. Изаберите сегменте које желите да извезете. Изричито **препоручујемо да не извозите укупно више од 100.000 профила клијената** у Autopilot. 

1. Изаберите ставку **Сачувај**.

## <a name="export-the-data"></a>Извоз података

Можете да [извезете податке на захтев](export-destinations.md). Извоз ће се такође покренути са сваким [планираним освежавањем](system.md#schedule-tab).

## <a name="known-limitations"></a>Позната ограничења

- У услугу Autopilot можете да извезете укупно до 100.000 профила.
- Извоз у Autopilot је ограничен на сегменте.
- Извоз до 100.000 профила у Autopilot може да потраје до неколико сати. 
- Број профила које можете да извезете у Autopilot зависи од вашег уговора са компанијом Autopilot и ограничен је њиме.

## <a name="data-privacy-and-compliance"></a>Приватност података и усаглашеност

Када омогућите да Dynamics 365 Customer Insights преноси податке у Autopilot, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци. Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Autopilot испуњава све обавезе приватности или безбедности које имате. За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.


[!INCLUDE[footer-include](../includes/footer-banner.md)]