---
title: Извоз података у Салесфорце Маркетинг Цлоуд (преглед)
description: Сазнајте како да конфигуришете везу и извезете је у Salesforce Marketing Cloud.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197056"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Извоз података у Салесфорце Маркетинг Цлоуд (преглед)

Користите податке о клијентима у услузи Salesforce Marketing Cloud тако што ћете их извести путем локације протокола сигурног преноса датотека (SFTP).

## <a name="prerequisites"></a>Предуслови

- СФТП [домаћин за Салесфорце Маркетинг Цлоуд и](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) одговарајуће административне акредитиве.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Подешавање везе са Салесфорце маркетиншким облаком

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Идите на **Администратор** > **Везе**.

1. Изаберите **додај везу** и одаберите **Салесфорце Маркетинг Цлоуд**.

1. Дајте вези препознатљиво име у пољу **Име за приказ**. Име за приказ и врста везе описују ову везу. Препоручујемо да одаберете назив који објашњава сврху и циљ везе.

1. Одаберите ко може да користи ову везу. Подразумевано су то само администратори. За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Наведите **корисничко име**, **лозинку**, **име хоста** и **фасциклу за извоз** за SFTP налог.

1. Изаберите **Верификуј** да тестирате везу.

1. Прегледајте приватност [и усаглашеност података и](connections.md#data-privacy-and-compliance) изаберите И **слажем се**.

1. Изаберите **Сачувај** да бисте креирали везу.

## <a name="configure-an-export"></a>Конфигурисање извоза

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Идите на **Подаци** > **Извози**.

1. Изаберите **Додај извоз**.

1. У пољу **Веза за извоз**, одаберите везу из одељка SFTP. Ако веза није доступна, обратите се администратору.

1. Унесите име за извоз.

1. Одаберите да ли желите да извезете податке **спаковано** или **распаковано** и **сепаратор поља** за извезене датотеке.

1. Изаберите ентитете, нпр.

   > [!NOTE]
   > Сваки изабрани ентитет ће бити подељен на највише пет излазних датотека када се извезе.

1. Изаберите **Сачувај**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Извезите Customer Insights податке у са SFTP локације Salesforce Marketing Cloud

1. Креирајте [проширења података у услузи Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) за увоз Customer Insights датотеке података са SFTP локације.

2. [Увезите податке са SFTP локације](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) у Salesforce Marketing Cloud проширење података.

3. Подесите аутоматизацију за увоз података у проширења података. Сазнајте више о [аутоматизацијама отпуштања датотека и заказаним аутоматизацијама](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Дефинишите [аутоматизацију отпуштања датотека](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) или [заказану аутоматизацију](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

Ево примера [аутоматизације са SFTP-ом](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
