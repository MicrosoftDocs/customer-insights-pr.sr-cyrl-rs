---
title: Извоз Customer Insights података у Campaign Monitor
description: Сазнајте како да конфигуришете везу и извезете садржај у Campaign Monitor.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 063de14c4ffd51b3afd89786606d7b37626695dc
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618999"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Извоз сегмената у Campaign Monitor (верзија за преглед)

Извезите сегменте обједињених профила клијената у Campaign Monitor и користите их за маркетиншке активности.

## <a name="prerequisites"></a>Предуслови

-   Имате [Campaign Monitor налог](https://www.campaignmonitor.com/) и одговарајуће акредитиве администратора.
-   [Конфигурисали сте сегменте](segments.md) у увидима о корисницима.
-   Обједињени кориснички профили у извезеним сегментима садрже поље које представља адресу е-поште.

## <a name="known-limitations"></a>Позната ограничења

- Можете извозити до милион корисничких профила по извозу у Campaign Monitor.
- Извоз у Campaign Monitor ограничен је на сегменте.
- Извоз до милион профила клијената у Campaign Monitor може потрајати до 20 минута. 
- Број профила клијената које можете извести у Campaign Monitor зависи и ограничен је на ваш уговор са Campaign Monitor-ом.

## <a name="set-up-connection-to-campaign-monitor"></a>Подешавање везе са услугом Campaign Monitor

1. Идите на **Администратор** > **Везе**.

1. Изаберите **Додај везу** и бирајте **Campaign Monitor** да бисте конфигурисали везу.

1. Дајте вези препознатљиво име у пољу **Име за приказ**. Име за приказ и врста везе описују ову везу. Препоручујемо да одаберете назив који објашњава сврху и циљ везе.

1. Одаберите ко може да користи ову везу. Ако ништа не предузмете, подразумевани ће бити Администратори. За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.

1. Изаберите **Повежите се** да би се иницијализовала веза са услугом Campaign Monitor.

1. Изаберите **Потврдите идентитет помоћу услуге Campaign Monitor** и обезбедите своје администраторске акредитиве за Campaign Monitor.

1. Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.

1. Изаберите **Сачувај** да бисте креирали везу.

## <a name="configure-an-export"></a>Конфигурисање извоза

Овај извоз можете да конфигуришете ако имате приступ вези ове врсте. За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).

1. Идите на **Подаци** > **Извози**.

1. Да бисте креирали нови извоз, изаберите **Додај одредиште**.

1. У пољу **Веза за извоз**, одаберите везу из одељка Campaign Monitor. Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.

1. Унесите [**ID Campaign Monitor листе**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).    
   Прво [генеришите API кључ](https://www.campaignmonitor.com/api/getting-started/) у одељку **Подешавања налога** у услузи Campaign Monitor да бисте видели ID API листе.  

1. У одељку **Подударање података**, у пољу **Е-пошта**, изаберите поље које представља е-адресу клијента. То је потребно да извезете сегменте у Campaign Monitor.

1. Изаберите ставку **Сачувај**.

Чување извоза не покреће извоз одмах.

Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab). Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Приватност података и усаглашеност

Када омогућите Dynamics 365 Customer Insights за пренос података у Campaign Monitor, дозвољавате пренос података изван граница усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци. Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Campaign Monitor испуњава све обавезе приватности или безбедности које имате. За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.
