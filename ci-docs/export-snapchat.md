---
title: Извоз Customer Insights података у Snapchat
description: Сазнајте како да конфигуришете везу и извезете у Snapchat.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 171b8bf0f4a034c78e872b671602ae7653271da7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643624"
---
# <a name="export-segments-to-snapchat-preview"></a>Извоз сегмената у Snapchat (верзија за преглед)

Извезите сегменте обједињених профила клијената у Snapchat и користите их за оглашавање. 

## <a name="prerequisites-for-a-connection"></a>Предуслови за везу

-   Имате [Snapchat Business налог](https://business.snapchat.com/), [Snapchat Ads налог](https://ads.snapchat.com/) и одговарајуће акредитиве администратора.
-   Конфигурисали [сте сегменте у програму](segments.md) "Увиди купаца".
-   Обједињени кориснички профили у извезеним сегментима садрже поље које представља адресу е-поште.

## <a name="known-limitations"></a>Позната ограничења

- Извоз у Snapchat ограничен је на сегменте.
- Извоз до 1 милиона профила клијената у Snapchat може потрајати до 15 минута. 

## <a name="set-up-connection-to-snapchat"></a>Подешавање везе у услузи Snapchat

1. Идите на **Администратор** > **Везе**.

1. Изаберите **Додај везу** и бирајте **Snapchat** да бисте конфигурисали везу.

1. Дајте вези препознатљиво име у пољу **Име за приказ**. Име за приказ и врста везе описују ову везу. Препоручујемо да одаберете назив који објашњава сврху и циљ везе.

1. Одаберите ко може да користи ову везу. Ако ништа не предузмете, подразумевани ће бити Администратори. За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.

1. Изаберите **Повежите се** да би се иницијализовала веза са услугом Snapchat.

1. Изаберите **Потврдите идентитет помоћу услуге Snapchat** и обезбедите своје администраторске акредитиве за Snapchat. 

1. Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.

1. Изаберите **Сачувај** да бисте креирали везу.

## <a name="configure-an-export"></a>Конфигурисање извоза

Овај извоз можете да конфигуришете ако имате приступ вези ове врсте. За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).

1. Идите на **Подаци** > **Извози**.

1. Да бисте креирали нови извоз, изаберите **Додај одредиште**.

1. У пољу **Веза за извоз**, одаберите везу из одељка Snapchat. Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.

1. Унесите [**ID циљне групе за Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).

1. У одељку **Подударање података**, у пољу **Е-пошта**, изаберите поље које представља е-адресу клијента. То је потребно да извезете сегменте у Snapchat.

1. Изаберите сегменте које желите да извезете. 

1. Изаберите ставку **Сачувај**.

Чување извоза не покреће извоз одмах.

Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab). Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Приватност података и усаглашеност

Када омогућите Dynamics 365 Customer Insights за пренос података у Snapchat, дозвољавате пренос података изван граница усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци. Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Snapchat испуњава све обавезе приватности или безбедности које имате. За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.