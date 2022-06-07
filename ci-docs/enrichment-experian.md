---
title: Обогаћивање путем независног обогаћивања Experian
description: Опште информације о Experian независном обогаћивању.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6f5aa45316b9e0e99c7ba4389353063e9d3ce06c
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642983"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Обогатите профиле клијената демографским подацима из услуге Experian (верзија за преглед)

Experian је глобални лидер у извештавању о потрошачким и пословним кредитима и маркетиншким услугама. Користећи Experian услуге обогаћивања података, можете да развијете дубље разумевање својих клијената обогаћујући своје профиле клијената демографским подацима као што су величина домаћинства, приход и још много тога.

## <a name="prerequisites"></a>Предуслови

Да бисте конфигурисали Experian, морате испунити следеће предуслове:

- Имате активну претплату на Experian. Да бисте набавили претплату, [контактирајте Experian](https://www.experian.com/marketing-services/contact) директно. [Сазнајте више о Experian обогаћивању података](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Администратор је већ конфигурисао везу са услугом Experian *или* имате дозволе [администратора](permissions.md#admin). Такође су вам потребни ИД корисника, ИД странке и број модела за ваш SSH омогућени налог за безбедни транспорт (ST)који је услуга Experian креирала за вас.

## <a name="supported-countriesregions"></a>Подржане земље/региони

Тренутно подржавамо обогаћивање профила купаца само у Сједињеним Државама.

## <a name="configure-the-enrichment"></a>Конфигурисање обогаћивања

1. Идите до картице **Подаци** > **Обогаћивање** и изаберите картицу **Откриј**.

1. Изаберите **Обогати моје податке** на плочици Experian.

   > [!div class="mx-imgBorder"]
   > ![Experian плочица.](media/experian-tile.png "Experian tile")
   > 

1. Изаберите [везу](connections.md) са падајуће листе. Ако веза није доступна, обратите се администратору. Ако сте администратор, везу можете да направите ако изаберете **Додај везу** и бирате Experian са падајуће листе. 

1. Изаберите **Повежи се за услугом Experian** да бисте потврдили избор везе.

1.  Изаберите **Следеће** и бирајте **Скуп података о клијенту** који желите да обогатите демографским подацима из услуге Experian. Можете изабрати ентитет **Клијент** да бисте обогатили све ваше профиле клијената или изаберите ентитет сегмента да бисте обогатили само профиле клијената садржане у том сегменту.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Снимак екрана приликом одабира скупа података о клијентима.":::

1. Изаберите **Следеће** и дефинишите који тип поља из ваших обједињених профила треба да користите за тражење одговарајућих демографских података из услуге Experian. Обавезно је барем једно од поља **Име и адреса**, **Телефон** или **Е-пошта**. За већу прецизност подударања, могу се додати још два поља. Овај избор ће утицати на поља за мапирање којима имате приступ у следећем кораку.

    > [!TIP]
    > Више атрибута идентификатора кључа послатих услузи Experian повећавају вероватноћу постизања више стопе подударања.

1. Изаберите **Следеће** да бисте започели мапирање поља.

1. Дефинишите која поља из ваших обједињених профила треба да користите за тражење одговарајућих демографских података из услуге Experian. Обавезна поља су означена.

1. Обезбедите назив за обогаћивање и назив за излазни ентитет.

1. Изаберите **Сачувај обогаћивање** након прегледа ваших избора.

## <a name="configure-the-connection-for-experian"></a>Конфигурисање везе за Experian 

Морате бити администратор да бисте конфигурисали везе. Изаберите **Додај везу** када конфигуришете обогаћивање *или* идите на **Администратор** > **Везе** и изаберите **Подесити** на плочици Experian.

1. Изаберите **Први кораци**.

1. Унесите назив везе у поље **Име за приказ**.

1. Унесите важећи ИД корисника, ИД странке и број модела за свој налог за Experian безбедан транспорт.

1. Прегледајте и дајте сагласност за **Приватност података и усклађеност** избором опције **Слажем се**.

1. Изаберите **Верификуј** да бисте проверили ваљаност конфигурације.

1. По завршетку верификације, изаберите **Сачувај**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Окно за конфигурацију Experian везе.":::

## <a name="enrichment-results"></a>Резултати обогаћивања

Да бисте започели процес обогаћивања, изаберите **Покрени** са командне траке. Такође можете пустити да систем аутоматски покреће обогаћивање као део [планираног освежавања](system.md#schedule-tab). Време обраде зависиће од величине ваших података о клијенту и процеса обогаћивања које је за ваш налог подесио Experian.

Након завршетка процеса обогаћивања, податке о новообогаћеним корисничким профилима можете прегледати под опцијом **Моја обогаћивања**. Осим тога, пронаћи ћете време последњег ажурирања и број обогаћених профила.

Детаљном приказу сваког обогаћеног профила можете приступити ако изаберете **Прикажи обогаћене податке**.

## <a name="next-steps"></a>Следећи кораци

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Приватност података и усаглашеност

Када омогућите Dynamics 365 Customer Insights за пренос података у Experian, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци. Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Experian испуњава све обавезе приватности или безбедности које имате. За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Ваш Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони ово обогаћивање како бисте престали са коришћењем ове функционалности.


[!INCLUDE [footer-include](includes/footer-banner.md)]