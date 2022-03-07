---
title: Извоз Customer Insights података у ActiveCampaign
description: Сазнајте како да конфигуришете везу и извезете је у услугу ActiveCampaign.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 089b9b0d76437e695f797f941ed384734d8f772e
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227827"
---
# <a name="export-segments-to-activecampaign-preview"></a>Извоз сегмената у ActiveCampaign (верзија за преглед)

Извезите сегменте обједињених профила купаца у ActiveCampaign и користите их за маркетиншке активности.

## <a name="prerequisites"></a>Предуслови

-   Имате [ActiveCampaign налог](https://www.activecampaign.com/) и одговарајуће акредитиве администратора.
-   [Конфигурисали сте сегменте](segments.md) у увидима о корисницима.
-   Обједињени кориснички профили у извезеним сегментима садрже поље са адресом е-поште.

## <a name="known-limitations"></a>Позната ограничења

- Можете извести до милион профила клијената по извозу у ActiveCampaign, а за то може бити потребно и до 90 минута.
- Извоз у ActiveCampaign је ограничен на сегменте.
- Број профила клијената које можете извести у ActiveCampaign зависи од вашег уговора са ActiveCampaign-ом.

## <a name="set-up-connection-to-activecampaign"></a>Подесите везу са услугом ActiveCampaign

1. Идите на **Администратор** > **Везе**.

1. Изаберите **Додај везу** и изаберите **ActiveCampaign** да бисте конфигурисали везу.

1. Дајте вези препознатљиво име у пољу **Име за приказ**. Име за приказ и врста везе описују ову везу. Препоручујемо да одаберете назив који објашњава сврху и циљ везе.

1. Одаберите ко може да користи ову везу. Подразумевано су то само администратори. За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Унесите свој [ActiveCampaign API кључ и име хоста REST крајње тачке](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key). Име хоста REST крајње тачке је само име хоста, без https://. 

1. Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.

1. Изаберите **Повежи се** за иницијализацију везе са услугом ActiveCampaign.

1. Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.

1. Изаберите **Сачувај** да бисте креирали везу.

## <a name="configure-an-export"></a>Конфигурисање извоза

Извоз можете да конфигуришете ако имате приступ вези ове врсте. За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).

1. Идите на **Подаци** > **Извози**.

1. Да бисте креирали нови извоз, изаберите **Додај одредиште**.

1. У пољу **Веза за извоз**, изаберите везу из одељка ActiveCampaign. Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.

1. Унесите [**ID ActiveCampaign листе**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).    

1. У одељку **Подударање података**, у пољу **Е-пошта**, изаберите поље које представља е-адресу клијента. У ActiveCampaign морате извозити сегменте. Опционално, можете да извезете поља Име, Презиме и Телефон да бисте креирали персонализованије адресе е-поште. Изаберите Додај атрибут за мапирање ових поља.

1. Изаберите ставку **Сачувај**.

Чување извоза не покреће извоз одмах.

Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab). Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Приватност података и усаглашеност

Када омогућите Dynamics 365 Customer Insights за пренос података у ActiveCampaign, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци. Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да ActiveCampaign испуњава све обавезе приватности или безбедности које имате. За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.
