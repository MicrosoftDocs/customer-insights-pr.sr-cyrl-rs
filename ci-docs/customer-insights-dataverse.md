---
title: Customer Insights подаци у платформи Microsoft Dataverse
description: Користите Customer Insights ентитете као табеле у платформи Microsoft Dataverse.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 85995cbd7f797810bfb6ecdc8a24d56542f0b5a9
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643083"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Рад са Customer Insights подацима у платформи Microsoft Dataverse

Customer Insights пружа могућност омогућавања доступности излазних ентитета у платформи [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Ова интеграција омогућава лако дељење података и прилагођени развој путем ниског кода/без кодног приступа. Излазни [ентитети су](#output-entities) доступни као табеле у окружењу Dataverse. Податке можете да користите за било коју другу апликацију засновану на Dataverse табелама. Ове табеле омогућавају сценарије као што су аутоматизовани токови посла кроз Power Automate или израду апликација помоћу програма Power Apps. Тренутна имплементација углавном подржава приказе у којима се подаци из доступних ентитета Увиди клијената могу пренети за дати ИД купца.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Прилагање Dataverse окружења за Customer Insights

**Постојећа организација**

Администратори могу да конфигуришу увиде клијената [тако да користе постојеће Dataverse](create-environment.md) окружење када креирају окружење "Увиди купаца". Обезбеђивањем УРЛ адресе окружењу Dataverse, она се прилаже њиховом новом окружењу "Увиди купаца". Увиди клијената Dataverse и окружења морају бити хостована у истом региону. 

Ако не желите да користите постојеће окружење Dataverse, систем креира ново окружење за податке о увидима клијената у закупца. 

> [!NOTE]
> Ако ваше организације већ користе Dataverse код свог закупца, важно је да запамтите да [Dataverse креирање окружења контролише администратор](/power-platform/admin/control-environment-creation) . На пример, ако подешавате ново окружење "Увиди клијената" са организационим налогом, а администратор је онемогућио Dataverse креирање пробних окружења за све осим за администраторе, не можете да креирате ново пробно окружење.
> 
> Dataverse пробна окружења креирана у услузи Customer Insights имају 3 GB простора за складиштење који се неће рачунати у укупни капацитет који има право на закупца. Плаћене претплате добијају Dataverse право од 15 GB за базу података и 20 GB за складиштење датотека.

**Нова организација**

Ако приликом подешавања увида клијената креирате нову организацију, систем аутоматски креира ново окружење Dataverse у вашој организацији.

## <a name="output-entities"></a>Излазни ентитети

Неки излазни ентитети из "Увида купаца" доступни су као табеле у програму Dataverse. Одељци у наставку описују очекивану шему ових табела.

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
|EntityName        | String        | Име ентитета у увидима купаца. На пример: `contact1`        |
|AlternateValue    |String         |Алтернативни ID који се пресликава на ID клијента. Пример: `cntid_1078`         |
|KeyRing           | Текст у више редова        | JSON вредност  </br> Пример: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
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
| СегментПровидер      | String       | Апликација која објављује сегменте.      |
| СегментМемберсхипТyпе | String       | Тип купца овај запис чланства у сегментима. Подржава више типова као што су "Купац", "Контакт" или "Налог". Подразумевано : купац  |
| Сегменти       | JSON ниска  | Листа јединствених сегмената у којима је профил купца члан      |
| msdynci_identifier  | String   | Јединствени идентификатор записа чланства у сегменту. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Детерминистички ГУИД генерисан из`msdynci_identifier`          |
