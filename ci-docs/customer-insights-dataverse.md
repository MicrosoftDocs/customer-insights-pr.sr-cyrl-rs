---
title: Рад са Customer Insights подацима у платформи Microsoft Dataverse
description: Сазнајте како да повежете увиде клијената Microsoft Dataverse и разумете излазне ентитете који се извозе у програм Dataverse.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 0d536259f310b41fe12922baeebdc4569937db08
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303847"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Рад са Customer Insights подацима у платформи Microsoft Dataverse

Customer Insights пружа могућност омогућавања доступности излазних ентитета у платформи [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Ова интеграција омогућава лако дељење података и прилагођени развој путем ниског кода/без кодног приступа. Излазни [ентитети су](#output-entities) доступни као табеле у окружењу Dataverse. Податке можете да користите за било коју другу апликацију засновану на Dataverse табелама. Ове табеле омогућавају сценарије као што су аутоматизовани токови посла кроз Power Automate или израду апликација помоћу програма Power Apps.

Повезивање са окружењем Dataverse вам такође омогућава да уносите [податке из локални података помоћу Power Platform прилива података и мрежних пролаза](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Предуслови

- Увиди клијената Dataverse и окружења морају бити хостована у истом региону.
- Глобална улога администратора постављена у окружењу Dataverse. Проверите да [Dataverse ли је ово окружење](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) повезано са одређеним безбедносним групама и уверите се да сте додати тим безбедносним групама.
- Ниједно друго окружење "Увиди купаца" већ није повезано са окружењем Dataverse које желите да повежете. Сазнајте како [да уклоните постојећу везу са окружењем Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).
- Окружење Microsoft Dataverse повезано са једним налогом за складиштење ако конфигуришете окружење тако [да користи Azure Data Lake Storage](own-data-lake-storage.md) ваш.

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse право на складишни капацитет

Претплата"Увиди клијената" вам даје право на додатни капацитет постојећег капацитета складиштења ваше [Dataverse организације](/power-platform/admin/capacity-storage). Додатни капацитет зависи од броја профила које ваша претплата користи.

**Пример:**

Под претпоставком да добијете складиште базе података од 15 ГБ и 20 ГБ складишта датотека на 100.000 профила клијената. Ако претплата укључује 300.000 профила клијената, укупан капацитет складиштења је складиште базе података од 45 ГБ (3 x 15 ГБ) и складиште датотека од 60 ГБ (3 x 20 ГБ). Слично томе, ако имате претплату на Б-на-Б са 30K налога, укупан капацитет складиштења је складиште базе података од 45 ГБ (3 x 15 ГБ) и складиште датотека од 60 ГБ (3 x 20 ГБ).

Капацитет евиденције није постепен и фиксиран за вашу организацију.

Више информација о правима на детаљне капацитете потражите у Водичу [за лиценцирање за Дyнамицс 365](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Повезивање окружења Dataverse са увидом клијената

Овај **Microsoft Dataverse** корак вам омогућава да повежете увиде клијената са окружењем Dataverse приликом [креирања окружења "Увид у купце"](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="дељење података Microsoft Dataverse са аутоматски омогућеним за нова окружења.":::

1. Обезбедите УРЛ адресу свом окружењу Dataverse или оставите празну да би она била креирана за вас.

   > [!NOTE]
   > Након успостављања везе између увида клијената и Dataverse, немојте мењати име организације за окружење Dataverse. Име организације се користи у УРЛ адреси и Dataverse промењено име прекида везу са увидом клијента.

   [Power Platform администратори могу да контролишу ко може да креира нова Dataverse окружења](/power-platform/admin/control-environment-creation). Ако покушавате да подесите ново окружење "Увиди купаца", а не може, администратор је можда Dataverse онемогућио креирање окружења за све осим за администраторе.

1. Ако користите сопствени Дата Лаке Стораге налог:
   1. Изаберите **опцију Омогући дељење података** помоћу програм Dataverse.
   1. Унесите **идентификатор дозвола**. Да бисте добили идентификатор дозволе, [омогућите дељење података Dataverse са сопственим Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Омогући дељење података Dataverse са сопственим Azure Data Lake Storage (преглед)

На [свом налогу Azure Data Lake Storage](own-data-lake-storage.md) проверите да ли корисник који подешава окружење "Увиди купаца **" има најмање дозволе за складиштење блоб података читалац**`customerinsights` на контејнеру у налогу за складиштење.

### <a name="limitations"></a>Ограничења

- Само мапирање један на један између организације Dataverse и налога Azure Data Lake Storage. Када је Dataverse организација повезана са налогом за складиштење, не може да се повеже са другим налогом за складиштење. Ово ограничење спречава попуњавање Dataverse више налога за складиштење.
- Дељење података неће функционисати ако је за приступ налогу потребно Azure Data Lake Storage подешавање Азуре приватне везе јер се налази иза заштитног зида. Dataverse тренутно не подржава везу са приватним крајњим тачкама путем приватне везе.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Сами подесите безбедносне групе Azure Data Lake Storage

1. Креирајте две безбедносне групе на Азуре претплати - **једну читалац безбедносну** **групу и сарадник безбедносну** групу и подесите Microsoft Dataverse услугу као власника за обе безбедносне групе.

1. Управљајте Листом контроле приступа (АЦЛ) на контејнеру `customerinsights` у налогу за складиштење преко ових безбедносних група.
   1. Додајте услугу Microsoft Dataverse и све Dataverse пословне апликације засноване на систему Дyнамицс 365 Маркетинг **читалац групу** са **дозволама само** за читање.
   1. Додајте *само* апликацију "Увиди клијената **" сарадник групу** да бисте доделили дозволе **за** читање и писање профила и увида.

### <a name="set-up-powershell"></a>Подешавање ПоwерСхелл-а

Подесите ПоwерСхелл да извршава ПоwерСхелл скрипте.

1. Инсталирајте најновију верзију [Azure Active Directory програма ПоwерСхелл за Грапх](/powershell/azure/active-directory/install-adv2).
   1. На рачунару изаберите тастер Windows на тастатури и потражите **Windows PowerShell** и изаберите **Покрени као администратор**.
   1. У PowerShell прозору који се отвори унесите `Install-Module AzureAD`.

1. Увези три модула.
   1. У прозору ПоwерСхелл унесите `Install-Module -Name Az.Accounts` и следите кораке.
   1. Поновите за `Install-Module -Name Az.Resources` и `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Извршавање ПоwерСхелл скрипти и добијање идентификатора дозволе

1. Преузмите две ПоwерСхелл скрипте које треба да покренете са [ГитХуб репоа нашег инжењера](https://github.com/trin-msft/byol).
   - `CreateSecurityGroups.ps1`: Потребне су администраторске дозволе закупца.
   - `ByolSetup.ps1`: Захтева дозволе власника података за складиштење на нивоу налога/контејнера за складиштење. Ова скрипта ће креирати дозволу за вас. Додељивање улоге може бити уклоњено ручно након успешног покретања скрипте.

1. Извршите у програму Wиндоwс ПоwерСхелл тако што ћете обезбедити ИД Азуре претплате `CreateSecurityGroups.ps1` који садржи ваш Azure Data Lake Storage. Отворите ПоwерСхелл скрипту у уређивачу да бисте прегледали додатне информације и примењену логику.

   Ова скрипта креира две безбедносне групе на Азуре претплати: једну за читалац групу, а другу за сарадник групу. Microsoft Dataverse услуга је власник обе ове безбедносне групе.

1. Сачувајте ИД вредности обе безбедносне групе које генерише ова скрипта да бисте их користили у скрипти `ByolSetup.ps1`.

   > [!NOTE]
   > Креирање безбедносне групе може бити онемогућено вашем станару. У том случају, биће потребно ручно подешавање и администратор ће Azure AD морати да омогући креирање [безбедносних група](/azure/active-directory/enterprise-users/groups-self-service-management).

1. Извршите `ByolSetup.ps1` у програму Wиндоwс ПоwерСхелл тако што ћете обезбедити ИД Azure Data Lake Storage Азуре претплате који садржи име налога за складиштење, име групе ресурса и читалац и сарадник ИД безбедносне групе. Отворите ПоwерСхелл скрипту у уређивачу да бисте прегледали додатне информације и примењену логику.

   Ова скрипта додаје потребну контролу приступа засновану на улози за услугу и Microsoft Dataverse све пословне апликације Dataverse засноване на улози. Такође ажурира Листу контроле приступа (АЦЛ) на контејнеру за безбедносне `customerinsights` групе креиране помоћу скрипте `CreateSecurityGroups.ps1`. Група сарадник добила дозволу *за рwx*, а група читалаца само *р-x* дозволу.

1. Копирај излазну ниску која изгледа као: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Унесите копирану излазну ниску у **поље идентификатора дозвола** корака конфигурације окружења за Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Опције конфигурације да бисте омогућили дељење података из сопствених са Azure Data Lake Storage програмом Microsoft Dataverse .":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Уклањање постојеће везе са окружењем Dataverse

Када се повезујете са окружењем Dataverse, порука о грешци **Ова ЦДС организација је већ приложена другој инстанци увида клијената** значи Dataverse да се окружење већ користи у окружењу "Увиди купаца". Постојећу везу можете да уклоните као глобални администратор у окружењу Dataverse. Може да потраје неколико сати да се промене населе.

1. Иди на [Power Apps](https://make.powerapps.com).
1. Изаберите окружење од бирача окружења.
1. Идите на **решења**.
1. Деинсталирајте или избришите решење под именом **Dynamics 365 Customer Insights "Програмски додатак картице купца " (преглед)**.

ИЛИ

1. Отворите своју Dataverse околину.
1. Идите на решења **за више опција** > **за поставке**.
1. Деинсталирајте **ЦустомерИнсигхтсЦустомерЦард** решење.

Ако уклањање везе не успе због зависности, морате да уклоните и зависности. Више информација потражите у чланку [Уклањање зависности](/power-platform/alm/removing-dependencies).

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

Ова табела садржи обједињени профил клијента из услуге Customer Insights. Шема за обједињени профил клијента зависи од ентитета и атрибута који се користе у процесу уједињења података. Шема профила клијента обично садржи подскуп атрибута из [Common Data Model дефиниције профила клијента](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

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
| Титула             | String      | Наслов или назив активности                                                               |
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
| СегментМемберсхипТyпе | String       | Врста купца за овај запис чланства у сегментима. Подржава више типова као што су "Купац", "Контакт" или "Налог". Подразумевано : купац  |
| Сегменти       | JSON ниска  | Листа јединствених сегмената у којима је профил купца члан      |
| msdynci_identifier  | String   | Јединствени идентификатор записа чланства у сегменту. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Детерминистички ГУИД генерисан из`msdynci_identifier`          |


[!INCLUDE [footer-include](includes/footer-banner.md)]
