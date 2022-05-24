---
title: Примери ОДата за Dynamics 365 Customer Insights АПИ-је
description: Често коришћени примери отвореног протокола података (ОДата) за упит АПИ-ја корисничких увида за редиговање података.
ms.date: 05/10/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 007278e1330e1a8e64d524ded8496acaf83b874c
ms.sourcegitcommit: a50c5e70d2baf4db41a349162fd1b1f84c3e03b6
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740075"
---
# <a name="odata-query-examples"></a>Примери упита ОДата

Опен Дата Протоцол (ОДата) је протокол за приступ подацима изграђен на основним протоколима као што је ХТТП. Он користи уобичајено прихваћене методологије као што је РЕСТ за Веб. Постоје разне врсте библиотека и алатки које се могу користити за конзумирање ОДата услуга.

Овај чланак наводи неке често тражене примере упита који вам помажу у изради сопствених имплементација на основу [АПИ-ја увида клијената](apis.md).

Морате да измените узорке упита да би они радили на циљним окружењима: 

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}` где се {instanceId} налази ГУИД окружења"Увиди купаца" које желите да испитате. Операција [ЛистАллИнстанцес вам](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) омогућава да пронађете приступ{InstanceId}.
- {CID}: ГУИД обједињеног записа купца. Пример: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: Идентификатор примарног кључа записа купца у извор података. Пример: `CNTID_1002`
- {DSname}: Ниска са именом ентитета извор података се уноси у увид купца. Пример: `Website_contacts`.
- {SegmentName}: Ниска са именом излазног ентитета сегмента у увидима купаца. Пример: `Male_under_40`.

## <a name="customer"></a>клијенту

Следећа табела садржи скуп пробних упита за ентитет *купца*.


|Тип упита |Пример  | Белешка  |
|---------|---------|---------|
|ИД једног купца     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Алтернативни кључ    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}' `         |  Алтернативни кључеви и даље постоје у обједињеном ентитету клијента       |
|Избор   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|За    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Алтернативни кључ + Ин   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Претражите  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Даје првих 10 резултата за ниску за тражење.      |
|Чланство у сегментима  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10  `     | Даје унапред одређени број редова из ентитета сегментације.      |

## <a name="unified-activity"></a>Обједињена активност

Следећа табела садржи скуп пробних упита за ентитет *обједињенеактивности*.

|Тип упита |Пример  | Белешка  |
|---------|---------|---------|
|Активност ЦИД-а     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Наводи активности одређеног профила клијента |
|Активност временски оквир    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Активности профила купца у временски оквир       |
|Тип активности    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Активност по име за приказ     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’ `        | |
|Сортирање активности    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Сортирање активности по растућем или опадајућем редоследу       |
|Активност проширена из чланства у сегментима  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Други примери

Следећа табела садржи скуп пробних упита за друге ентитете.

|Тип упита |Пример  | Белешка  |
|---------|---------|---------|
|Мере ЦИД-а    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Обогаћени брендови ЦИД-а    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Обогаћена интересовања ЦИД-а    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|Ин -Цлаусе + Еxпанд     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |
