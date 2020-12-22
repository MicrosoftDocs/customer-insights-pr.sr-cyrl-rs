---
title: Обогаћивање помоћу обогаћивања треће стране HERE Technologies
description: Опште информације о HERE Technologies обогаћивању треће стране.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668696"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Обогаћивање профила клијената уз HERE Technologies (верзија за преглед)

верзија за преглед је компанија за платформу локације која пружа податке и услуге усмерене на локацију. Помоћу услуга обогаћивања података компаније HERE Technologies можете да изградите прецизније разумевање локације својих клијената помоћу нормализације адреса, издвајања географске ширине и дужине и још много тога.

## <a name="prerequisites"></a>Предуслови

Да бисте конфигурисали верзија за преглед обогаћивања, морају бити испуњени следећи предуслови:

- Морате имати активну претплату за HERE Technologies. Да бисте добили претплату, можете [да се региструјете овде](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) или [контактирајте HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) директно. [Сазнајте више о HERE Technologies обогаћивању локације.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Имате HERE Technologies API кључ.

- Имате [администраторске](permissions.md#administrator) дозволе.

## <a name="configuration"></a>Конфигурисање

1. Идите на **Подаци** > **Обогаћивање**.

1. На HERE Technologies плочици изаберите **Обогати моје податке**.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies плочица](media/HERE-tile.png "HERE Technologies плочица")

1. Унесите активан **HERE Technologies API кључ**. Прегледајте и дајте свој пристанак за **Приватност података и усаглашеност** тако што ћете изабрати поље за потврду **Слажем се**. 

1. Потврдите оба улаза избором опције **Повежите се на HERE**.

1. Изаберите **Додајте податке** и одаберите да ли желите да мапирате поља са примарном и/или секундарном адресом. Можете да наведете мапирање поља за обе адресе (на пример, кућну и пословну адресу) и засебно обогатити профиле за обе адресе. Изаберите **Следеће**.

1. Дефинишите која поља из ваших обједињених профила треба користити за подударање података о локацији од компаније HERE Technologies. Поља **Улица 1** и **Поштански број** су обавезна за одабрану примарну и/или секундарну адресу. За већу прецизност подударања може се додати више поља.

   > [!div class="mx-imgBorder"]
   > ![Страница за конфигурацију HERE Technologies обогаћивања](media/enrichment-HERE-configuration.png "Страница за конфигурацију HERE Technologies обогаћивања")

1. Изаберите **Примени** да довршите мапирање поља.

## <a name="enrichment-results"></a>Резултати обогаћивања

Да бисте започели процес обогаћивања, изаберите **Покрени** са командне траке. Такође можете пустити да систем аутоматски покреће обогаћивање као део [планираног освежавања](system.md#schedule-tab). Време обраде зависиће од величине података о клијентима и времена одзива API-ја компаније HERE Technologies.

Након завршетка процеса обогаћивања, податке о новообогаћеним профилима клијената можете прегледати под опцијом **Моја обогаћивања**. Осим тога, пронаћи ћете време последњег ажурирања и број обогаћених профила.

Детаљном приказу сваког обогаћеног профила можете приступити ако изаберете **Прикажи обогаћене податке**.

## <a name="next-steps"></a>Следећи кораци

Надоградите на обогаћеним подацима о клијентима. Креирајте [сегменте](segments.md), [мере](measures.md), па чак и [извезите податке](export-destinations.md) да бисте пружили персонализована искуства својим клијентима.

## <a name="data-privacy-and-compliance"></a>Приватност података и усаглашеност

Када омогућите да Dynamics 365 Customer Insights преноси податке у HERE Technologies, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци. Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да HERE Technologies испуњава све обавезе приватности или безбедности које имате. За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони ово обогаћивање како бисте престали са коришћењем ове функционалности.
