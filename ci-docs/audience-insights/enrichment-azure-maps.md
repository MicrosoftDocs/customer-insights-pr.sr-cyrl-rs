---
title: Обогатите профиле клијената подацима о локацији из програма Azure Maps
description: Опште информације о Azure Maps директном обогаћивању.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 63f241c27ec86f357c83a301d6797f9ff87c2241
ms.sourcegitcommit: 2acda3c5adf40bc3f5bbb4b2b4b6c22f84371da7
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466780"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Обогаћивање профила клијената уз Azure Maps (верзија за преглед)

Azure Maps пружа податке и услуге усредсређене на локацију како би пружио искуства заснована на просторним подацима са уграђеним обавештавањем о локацији. Услуге Azure Maps обогаћивања података побољшавају прецизност информација о локацији ваших клијената. Оне доносе могућности попут нормализације адреса и екстракције географске ширине и дужине у услугу Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Предуслови

Да бисте конфигурисали Azure Maps обогаћивање података, морају бити испуњени следећи предуслови:

- Имате активну претплату на Azure Maps. Да бисте добили претплату, можете да се [региструјете или добијете бесплатну пробну верзију](https://azure.microsoft.com/services/azure-maps/).

- Azure Maps [веза](connections.md) је доступна *или* имате дозволу [Администратора](permissions.md#administrator) и активни Azure Maps API кључ.

## <a name="configure-the-enrichment"></a>Конфигурисање обогаћивања

1. Идите на **Подаци** > **Обогаћивање**. 

1. На плочици **Локација** изаберите **Обогати моје податке**.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Azure Maps плочица.":::

1. Изаберите [везу](connections.md) са падајуће листе. Обратите се администратору ако није доступна веза са услугом Azure Maps. Ако сте администратор, можете да [конфигуришете везу за Azure Maps](#configure-the-connection-for-azure-maps). 

1. Изаберите **Следеће** да бисте потврдили избор.

1. Одаберите **Скуп података о клијентима** који желите да обогатите са подацима о локацији из услуге Azure Maps. Можете да изаберете ентитет **Клијент** за обогаћивање свих ваших обједињених профила клијената или да изаберете ентитет сегмента за обогаћивање само профила клијената садржаних у том сегменту.

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="Снимак екрана при избору скупа података о клијентима.":::

1. Одаберите желите ли да мапирате поља на примарну и/или секундарну адресу. Можете навести мапирање поља за обе адресе и засебно обогатити профиле за обе адресе – на пример, за кућну адресу и пословну адресу. Изаберите **Следеће**.

1. Дефинишите која поља из ваших обједињених профила да користите за подударање података о локацији из услуге Azure Maps. Поља **Улица 1** и **Поштански број** су обавезна за изабрану примарну и секундарну адресу. За већу прецизност подударања, можете додати још поља.

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Страница за конфигурацију обогаћивања услугом Azure Maps.":::

1. Изаберите **Следеће** да бисте довршили мапирање поља.

1. Процените да ли желите да измените **Напредна подешавања**. Она су обезбеђена да пруже максималну флексибилност у раду са напредним случајевима употребе, али подразумеване вредности ће у већини случајева бити одговарајуће:
   - **Тип адреса**: подразумевано понашање је да ће обогаћивање вратити најбоље подударање адресе чак и ако је непотпуно. Да бисте добили само потпуне адресе – на пример, адресе које укључују кућни број – обришите сва поља за потврду осим **Адресе тачака**. 
   - **Језик**: подразумевано се адресе враћају на језику за регион за који је утврђено да припада. Да бисте применили стандардизовани језик адресе, изаберите језик из падајућег менија. На пример, ако изаберете **Енглески** вратиће **Copenhagen, Denmark** уместо **København, Danmark**.

1. Наведите назив обогаћивања.

1. Прегледајте изборе, а затим изаберите **Сачувај обогаћивање**.

## <a name="configure-the-connection-for-azure-maps"></a>Конфигуришите везу за Azure Maps

Морате бити администратор у увидима у циљну групу да бисте конфигурисали везе. Изаберите **Додај везу** када конфигуришете обогаћивање или идите на **Администратор** > **Везе** и изаберите **Подеси** на плочици Azure Maps.

1. У поље **Име за приказ**, унесите назив везе.

1. Наведите важећи Azure Maps API кључ.

1. Прегледајте и дајте свој пристанак за **Приватност података и усаглашеност** тако што ћете изабрати поље за потврду **Слажем се**

1. Изаберите **Верификуј** да бисте проверили ваљаност конфигурације.

1. По завршетку верификације, изаберите **Сачувај**.

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Страница за конфигурацију везе са услугом Azure Maps.":::

## <a name="enrichment-results"></a>Резултати обогаћивања

Да бисте започели процес обогаћивања, изаберите **Покрени** са командне траке. Такође можете пустити да систем аутоматски покреће обогаћивање као део [планираног освежавања](system.md#schedule-tab). Време обраде ће зависити од величине ваших података о клијенту и времена одговора API-ја.

Након завршетка процеса обогаћивања, можете прегледати податке о новообогаћеним профилима клијената у оквиру опције **Моја обогаћивања**. Осим тога, пронаћи ћете време последњег ажурирања и број обогаћених профила.

Детаљном приказу сваког обогаћеног профила можете приступити ако изаберете **Прикажи обогаћене податке**.

## <a name="next-steps"></a>Следећи кораци

Надоградите на обогаћеним подацима о клијентима. Креирајте [сегменте](segments.md), [мере](measures.md), па чак и [извезите податке](export-destinations.md) да бисте пружили персонализована искуства својим клијентима.

## <a name="data-privacy-and-compliance"></a>Приватност података и усаглашеност

Када омогућите Dynamics 365 Customer Insights за пренос података у Azure Maps, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци. Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Azure Maps испуњава све обавезе приватности или безбедности које имате. За још информација посетите чланак [Microsoft изјава о приватности](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони ово обогаћивање како бисте престали са коришћењем ове функционалности.

[!INCLUDE[footer-include](../includes/footer-banner.md)]