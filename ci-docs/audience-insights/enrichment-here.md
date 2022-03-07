---
title: Обогаћивање путем независног обогаћивања HERE Technologies
description: Опште информације о HERE Technologies обогаћивању треће стране.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 1b46e8913c6d288b93cdf32e195b5e9387916e70
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230400"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Обогаћивање профила клијената уз HERE Technologies (верзија за преглед)

верзија за преглед је компанија за платформу локације која пружа податке и услуге усмерене на локацију. Помоћу услуга обогаћивања података компаније HERE Technologies можете да изградите прецизније разумевање локације својих клијената помоћу нормализације адреса, издвајања географске ширине и дужине и још много тога.

## <a name="prerequisites"></a>Предуслови

Да бисте конфигурисали верзија за преглед обогаћивања, морају бити испуњени следећи предуслови:

- Морате имати активну претплату за HERE Technologies. Да бисте добили претплату, можете [да се региструјете овде](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) или директно [контактирајте HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Сазнајте више о HERE Technologies обогаћивању локације.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- HERE [веза](connections.md) је доступна *или* имате дозволе [администратора](permissions.md#administrator) и HERE Technologies API кључ.

## <a name="configure-the-enrichment"></a>Конфигурисање обогаћивања

1. Идите на **Подаци** > **Обогаћивање**. 

1. Изаберите **Обогати моје податке** на плочици HERE Technologies и изаберите **Започни**.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies плочица.](media/HERE-tile.png "HERE Technologies плочица")

1. Изаберите [везу](connections.md) са падајуће листе. Ако веза није доступна, обратите се администратору. Ако сте администратор, везу можете да направите избором **Додај везу**. Одаберите **HERE Technologies** са падајуће листе. 

1. Изаберите **Повежите се са HERE Technologies** да потврдите избор.

1.  Изаберите **Следеће** и одаберите **Скуп података клијента** који желите да обогатите са подацима о локацији компаније HERE Technologies. Можете изабрати ентитет **Клијент** да бисте обогатили све ваше профиле клијената или изаберите ентитет сегмента да бисте обогатили само профиле клијената садржане у том сегменту.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Снимак екрана приликом одабира скупа података о клијентима.":::

1. Одаберите да ли желите да мапирате поља са примарном и/или секундарном адресом. Можете одредити мапирање поља за обе адресе и обогатити профиле за обе адресе засебно. На пример, ако постоје кућна и пословна адреса. Изаберите **Следеће**.

1. Дефинишите која поља из ваших обједињених профила треба користити за подударање података о локацији од компаније HERE Technologies. Поља **Улица 1** и **Поштански број** су обавезна за одабрану примарну и/или секундарну адресу. За већу прецизност подударања може се додати више поља.

   > [!div class="mx-imgBorder"]
   > ![Страница за конфигурацију HERE Technologies обогаћивања.](media/enrichment-HERE-configuration.png "Страница за конфигурацију HERE Technologies обогаћивања")

1. Изаберите **Следеће** да бисте довршили мапирање поља.

1. Наведите назив обогаћивања. 

1. Изаберите **Сачувај обогаћивање** након прегледа ваших избора.

## <a name="configure-the-connection-for-here-technologies"></a>Конфигуришите везу за HERE Technologies 

Морате бити администратор да бисте конфигурисали везе. Изаберите **Додај везу** приликом конфигурисања обогаћивања *или* идите на **Администратор** > **Везе** и изаберите **Подешавање** на плочици HERE Technologies.

1. Унесите назив везе у поље **Име за приказ**.

1. Наведите важећи HERE Technologies API кључ.

1. Прегледајте и дајте сагласност за **Приватност података и усклађеност** избором опције **Слажем се**.

1. Изаберите **Верификуј** да бисте проверили ваљаност конфигурације.

1. По завршетку верификације, изаберите **Сачувај**.

   > [!div class="mx-imgBorder"]
   > ![Страница за конфигурацију везе за HERE Technologies.](media/enrichment-HERE-connection.png "Страница за конфигурацију везе за HERE Technologies")

## <a name="enrichment-results"></a>Резултати обогаћивања

Да бисте започели процес обогаћивања, изаберите **Покрени** са командне траке. Такође можете пустити да систем аутоматски покреће обогаћивање као део [планираног освежавања](system.md#schedule-tab). Време обраде зависиће од величине података о клијентима и времена одзива API-ја компаније HERE Technologies.

Након завршетка процеса обогаћивања, податке о новообогаћеним профилима клијената можете прегледати под опцијом **Моја обогаћивања**. Осим тога, пронаћи ћете време последњег ажурирања и број обогаћених профила.

Детаљном приказу сваког обогаћеног профила можете приступити ако изаберете **Прикажи обогаћене податке**.

## <a name="next-steps"></a>Следећи кораци

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Приватност података и усаглашеност

Када омогућите да Dynamics 365 Customer Insights преноси податке у HERE Technologies, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци. Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да HERE Technologies испуњава све обавезе приватности или безбедности које имате. За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Ваш Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони ово обогаћивање како бисте престали са коришћењем ове функционалности.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
