---
title: Извоз података у Салесфорце Маркетинг Цлоуд (преглед)
description: Сазнајте како да конфигуришете везу и извезете је у Salesforce Marketing Cloud.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c3a6a40d9b9f08c8ebca8cb4a9196a1a79f03afa
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082625"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Извоз података у Салесфорце Маркетинг Цлоуд (преглед)

Користите податке о клијентима у услузи Salesforce Marketing Cloud тако што ћете их извести путем локације протокола сигурног преноса датотека (SFTP).

## <a name="prerequisites-for-connection"></a>Предуслови за везу

- Доступност SFTP хоста и одговарајућих администраторских акредитива. [Како поставити SFTP локације за Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Подешавање везе са услугом Salesforce Marketing Cloud

1. Идите на **Администратор** > **Везе**.

1. Изаберите **Додај везу** и изаберите **Salesforce Marketing Cloud** да бисте конфигурисали везу.

1. Дајте вези препознатљиво име у пољу **Име за приказ**. Име за приказ и врста везе описују ову везу. Препоручујемо да одаберете назив који објашњава сврху и циљ везе.

1. Одаберите ко може да користи ову везу. Ако ништа не предузмете, подразумевани ће бити Администратори. За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Наведите **корисничко име**, **лозинку**, **име хоста** и **фасциклу за извоз** за SFTP налог.

1. Изаберите **Верификуј** да тестирате везу.

1. Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.

1. Изаберите **Сачувај** да бисте креирали везу.

## <a name="configure-an-export"></a>Конфигурисање извоза

Овај извоз можете да конфигуришете ако имате приступ вези ове врсте. За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).

1. Идите на **Подаци** > **Извози**.

1. Да бисте креирали нови извоз, изаберите **Додај одредиште**.

1. У пољу **Веза за извоз**, одаберите везу из одељка SFTP. Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.

1. Одаберите да ли желите да извезете податке **спаковано** или **распаковано** и **сепаратор поља** за извезене датотеке.

1. Изаберите ентитете, на пример сегменте које желите да извезете.

   > [!NOTE]
   > Сваки изабрани ентитет биће подељен на до пет излазних датотека приликом извоза. 

1. Изаберите ставку **Сачувај**.

Чување извоза не покреће извоз одмах.

Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab). Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Извезите Customer Insights податке у са SFTP локације Salesforce Marketing Cloud

1. Креирајте [проширења података у услузи Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) за увоз Customer Insights датотеке података са SFTP локације.

2. [Увезите податке са SFTP локације](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) у Salesforce Marketing Cloud проширење података. 

3. Подесите аутоматизацију за увоз података у проширења података. Сазнајте више о [аутоматизацијама отпуштања датотека и заказаним аутоматизацијама](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Дефинишите [аутоматизацију отпуштања датотека](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) или [заказану аутоматизацију](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

Ево примера [аутоматизације са SFTP-ом](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Приватност података и усаглашеност

Када омогућите да Dynamics 365 Customer Insights преноси податке путем SFTP-а, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци. Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да одредиште за извоз испуњава све обавезе приватности или безбедности које имате. За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.

[!INCLUDE [footer-include](includes/footer-banner.md)]
