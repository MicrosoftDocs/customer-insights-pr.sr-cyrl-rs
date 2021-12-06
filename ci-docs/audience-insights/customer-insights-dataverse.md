---
title: Подаци о увиду клијената у Мицрософт Датаверсе
description: Користите ентитете увида купаца као табеле у Мицрософт Датаверсе.
ms.date: 11/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6f74559b34a95ed976a4e353c2dbabe59e1a8839
ms.sourcegitcommit: 9558ff772ee6c944fcb8db4bfc8cda13b38a1bff
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 11/29/2021
ms.locfileid: "7866952"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Рад са подацима увида клијената у Мицрософт Датаверсе

Увиди клијената пружају опцију да излазни ентитети буду доступни [у Мицрософт Датаверсе](/powerapps/maker/data-platform/data-platform-intro.md). Ова интеграција омогућава лако дељење података и прилагођени развој кроз приступ са мало кодирања / без кодирања. Излазни ентитети ће бити доступни као табеле у Датаверсе. Ове табеле омогућавају сценарије као што [су аутоматизовани токови посла Поwер Аутомате](/power-automate/getting-started), апликације са [моделима и апликације на](/powerapps/maker/model-driven-apps/)[платну](/powerapps/maker/canvas-apps/) путем Поwер Аппс. Податке можете да користите за било коју другу апликацију која се заснива на Датаверсе табеле. Тренутна примена углавном подржава проналажења где се подаци из доступних ентитета увида у циљне групе могу добити за дати ID клијента.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Прилагање Датаверсе окружења уз увиде клијената

**Организације са постојећим Датаверсе окружењима**

Организације које већ користе Датаверсе могу [да користе једно од постојећих Датаверсе окружења када администратор корисници](create-environment.md) увиде. Обезбеђивањем УРЛ адресе Датаверсе окружењу, она се придаје њиховом новом окружењу корисници увида. Да бисте обезбедили најбоље могуће перформансе, кориснички увиди и Датаверсе окружења морају бити хостована у истом региону.

**Нова организација**

Ако приликом подешавања увида купаца креирате нову организацију, аутоматски ћете добити нови Датаверсе окружења.

> [!NOTE]
> Ако ваше организације већ Датаверсе у свом закупу, важно [је да запамтите да Датаверсе окружења контролише администратор](/power-platform/admin/control-environment-creation.md) . На пример, ако подешавате ново окружење за корисници увиде са организационим налогом, а администратор је онемогућио креирање Датаверсе пробних окружења за све осим за администраторе, не можете да креирате ново пробно окружење.
> 
> Пробна Датаверсе окружења креирана у увидима клијената имају 3 ГБ простора за складиштење које се неће рачунати у односу на укупне капацитете који имају право на станара. Плаћене претплате добијају Датаверсе од 15 ГБ за базу података и 20 ГБ за складиштење датотека.

## <a name="output-entities"></a>Излазни ентитети

Неки излазни ентитети из корисници доступни су као табеле у Датаверсе. Одељци у наставку описују очекивану шему ових табела.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Обогаћивање](#enrichment)
- [Предвиђање](#prediction)
- [Чланство у сегментима](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Ова табела садржи обједињени профил клијента из услуге Customer Insights. Шема за обједињени профил клијента зависи од ентитета и атрибута који се користе у процесу обједињавања. Шема профила клијента обично садржи подскуп атрибута из [Common Data Model дефиниције профила клијента](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Табела AlternateKey садржи кључеве ентитета који су учествовали у процесу обједињавања.

|Column  |Тип  |Опис  |
|---------|---------|---------|
|DataSourceName    |String         | Назив извора података. На пример: `datasource5`        |
|EntityName        | String        | Назив ентитета у увидима у циљну групу. На пример: `contact1`        |
|AlternateValue    |String         |Алтернативни ID који се пресликава на ID клијента. Пример: `cntid_1078`         |
|KeyRing           | Текст у више редова        | JSON вредност  </br> Узорак : [{"датаСоурцеНаме":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"кеyс ":[" cntid_1078"]}]       |
|CustomerId         | String        | ID обједињеног профила клијента.         |
|AlternateKeyId     | GUID         |  AlternateKey одређени GUID заснован на параметру msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Пример: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Ова табела садржи активности корисника које су доступне у услузи Customer Insights.

| Column            | Тип        | Опис                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | ID профила клијента                                                                      |
| ActivityId        | String      | Интерни ID корисничке активности (примарни кључ)                                       |
| SourceEntityName  | String      | Назив изворног ентитета                                                                |
| SourceActivityId  | String      | Примарни кључ из изворног ентитета                                                       |
| ActivityType      | String      | Тип семантичке активности или назив прилагођене активности                                        |
| ActivityTimeStamp | DATETIME    | Временска ознака активности                                                                      |
| Назив             | String      | Наслов или назив активности                                                               |
| Опис       | String      | Опис активности                                                                     |
| URL адреса               | String      | Веза до спољне URL адресе специфичне за активност                                         |
| SemanticData      | JSON ниска | Садржи листу парова вредности кључева за поља семантичког мапирања специфична за врсту активности |
| RangeIndex        | String      | Unix временска ознака која се користи за сортирање на временској оси активности и ефикасним упитима о опсегу |
| mydynci_unifiedactivityid   | GUID | Интерни ID корисничке активности (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Ова табела садржи излазне податке корисничких мера заснованих на атрибутима.

| Column             | Тип             | Опис                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | ID профила клијента        |
| Мере           | JSON ниска      | Укључује листу парова вредности кључева за име мере и вредности за датог клијента | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | ID профила клијента |


### <a name="enrichment"></a>Обогаћивање

Ова табела садржи резултате процеса обогаћивања.

| Column               | Тип             |  Опис                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | ID профила клијента                                 |
| EnrichmentProvider   | String           | Назив добављача обогаћивања                                  |
| EnrichmentType       | String           | Тип обогаћивања                                      |
| Вредности               | JSON ниска      | Листа атрибута произведених поступком обогаћивања |
| msdynci_enrichmentid | GUID             | Детерминистички GUID генерисан из параметра msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Предвиђање

Ова табела садржи излаз предвиђања модела.

| Column               | Тип        | Опис                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | ID профила клијента                                  |
| ModelProvider        | String      | Назив добављача модела                                      |
| Модел                | String      | Назив модела                                                |
| Вредности               | JSON ниска | Листа атрибута које је направио модел |
| msdynci_predictionid | GUID        | Детерминистички GUID генерисан из параметра msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Чланство у сегментима

Ова табела садржи информације о чланству у сегменту профила купаца.

| Column        | Тип | Опис                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | ID профила клијента        |
| СегментПровидер      | String       | Апликација која објављује сегменте. Подразумевано : корисници увиди         |
| СегментМемберсхипТyпе | String       | Тип купца овај запис чланства у сегментима. Подржава више типова као што су "Купац", "Контакт" или "Налог". Подразумевано : купац  |
| Сегменти       | JSON ниска  | Листа јединствених сегмената у којима је профил купца члан      |
| msdynci_identifier  | String   | Јединствени идентификатор записа чланства у сегменту. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Детерминистички ГУИД генерисан из`msdynci_identifier`          |
