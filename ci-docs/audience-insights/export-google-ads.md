---
title: Извезите Customer Insights податке у Google огласима
description: Сазнајте како да конфигуришете везу и извезете у Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5977b3de9fbb0d97c0912e2ada6a313b0ab92498adf9cdbed48191c0e5143567
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031675"
---
# <a name="export-segments-to-google-ads-preview"></a>Извоз сегмената у Google Ads (верзија за преглед)

Извезите сегменте обједињених профила клијената на Google Ads листу циљних група и користите их за оглашавање на Google претрази, Gmail-у, YouTube-у и Google мрежи мултимедијалног оглашавања. 

## <a name="prerequisites-for-connection"></a>Предуслови за везу

-   Имате [налог Google огласа](https://ads.google.com/) и одговарајуће акредитиве администратора.
-   Имате [одобрени токен за Google Ads програмера](https://developers.google.com/google-ads/api/docs/first-call/dev-token). 
-   Испуњавате захтеве [политике подударања клијената](https://support.google.com/adspolicy/answer/6299717).
-   Испуњавате захтеве [за величине листа за поновно оглашавање](https://support.google.com/google-ads/answer/7558048).
-   Постоји постојећа публика у Google огласима и одговарајући ID-ови. За више информација погледајте [Корисници Google огласа](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Имате [конфигурисане сегменте](segments.md).
-   Обједињени кориснички профили у извезеним сегментима садрже поља која представљају адресу е-поште, име и презиме.

## <a name="known-limitations"></a>Позната ограничења

- До 1 милион профила по извозу у Google огласима.
- Извоз у Google огласе је ограничен на сегменте.
- Извоз сегмената са укупно 1 милион профила може трајати до 5 минута због ограничења на страни добављача. 
- Подударање у Google огласима може да потраје до 48 сати.

## <a name="set-up-connection-to-google-ads"></a>Подешавање везе са услугом Google Ads

1. Идите на **Администратор** > **Везе**.

1. Изаберите **Додај везу** и бирајте **Google Ads** да бисте конфигурисали везу.

1. Дајте вези препознатљиво име у пољу **Име за приказ**. Име за приказ и врста везе описују ову везу. Препоручујемо да одаберете назив који објашњава сврху и циљ везе.

1. Одаберите ко може да користи ову везу. Ако ништа не предузмете, подразумевани ће бити Администратори. За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Унесите **[ID клијента за Google огласе](https://support.google.com/google-ads/answer/1704344)**.

1. Унесите **[токен одобреног програмера за Google огласе](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.

1. Изаберите **Потврдите идентитет у Google огласима** и наведите акредитиве за Google огласе.

1. Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.

1. Изаберите **Сачувај** да бисте креирали везу. 

## <a name="configure-an-export"></a>Конфигурисање извоза

Овај извоз можете да конфигуришете ако имате приступ вези ове врсте. За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).

1. Идите на **Подаци** > **Извози**.

1. Да бисте креирали нови извоз, изаберите **Додај одредиште**.

1. У пољу **Веза за извоз**, одаберите везу из одељка Google Ads. Ако не видите назив овог одељка, тада вам нису доступне везе овог типа.

1. Унесите **[ID корисника за Google огласе](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** и изаберите **Повежите се** да бисте започели повезивање са Google огласима.

1. У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном корисничком профилу које представља е-адресу клијента.

1. Изаберите сегменте које желите да извезете. У Google огласима можете укупно извести до 1 милион корисничких профила.

Чување извоза не покреће извоз одмах.

Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab). 

Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Приватност података и усаглашеност

Када омогућите да Dynamics 365 Customer Insights преноси податке у Google огласе, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци. Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Google огласи испуњавају све обавезе приватности или безбедности које имате. За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
