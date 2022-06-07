---
title: Рад са Customer Insights подацима у платформи Microsoft Dataverse
description: Сазнајте како да повежете увиде клијената Microsoft Dataverse и разумете излазне ентитете који се извозе у програм Dataverse.
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 3848e143bc7cb2f345bc698a274b92148ef00669
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833694"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Рад са Customer Insights подацима у платформи Microsoft Dataverse

Увиди клијената пружају опцију да излазни ентитети буду доступни као [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Ова интеграција омогућава лако дељење података и прилагођени развој путем ниског кода/без кодног приступа. Излазни [ентитети су](#output-entities) доступни као табеле у окружењу Dataverse. Податке можете да користите за било коју другу апликацију засновану на Dataverse табелама. Ове табеле омогућавају сценарије као што су аутоматизовани токови посла кроз Power Automate или израду апликација помоћу програма Power Apps.

Повезивање са окружењем Dataverse вам такође омогућава да уносите [податке из локални података помоћу Power Platform прилива података и мрежних пролаза](data-sources.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Предуслови

- Увиди клијената Dataverse и окружења морају бити хостована у истом региону.
- Морате имати улогу глобалног администратора у окружењу Dataverse. Проверите да [Dataverse ли је ово окружење](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) повезано са одређеним безбедносним групама и уверите се да сте додати тим безбедносним групама.
- Ниједно друго окружење"Увид у купце" већ није повезано са окружењем Dataverse које желите да повежете. Сазнајте како [да уклоните постојећу везу са окружењем Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).
- Окружење Microsoft Dataverse може да се повеже само са једним налогом за складиштење. Примењује се само ако конфигуришете окружење тако [да користи ваш Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Повезивање окружења Dataverse са увидом клијената

Овај **Microsoft Dataverse** корак вам омогућава да повежете увиде клијената са окружењем Dataverse приликом [креирања окружења "Увид у купце"](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="дељење података Microsoft Dataverse са аутоматски омогућеним за нето нова окружења.":::

Администратори могу да конфигуришу увиде клијената да повежу постојеће Dataverse окружење. Обезбеђивањем УРЛ адресе окружењу Dataverse, она се прилаже њиховом новом окружењу "Увиди купаца".

Ако не желите да користите постојеће окружење Dataverse, систем креира ново окружење за податке о увидима клијената у закупца. [Power Platform администратори могу да контролишу ко може да креира окружења](/power-platform/admin/control-environment-creation). Када подешавате ново окружење "Увиди купаца", а администратор је онемогућио Dataverse креирање окружења за све осим за администраторе, можда нећете моћи да креирате ново окружење.

**Омогућите дељење података** тако што Dataverse ћете потврдити избор у пољу за потврду за дељење података.

Ако користите сопствени налог за складиштење у језеру Са подацима, потребан вам је **и идентификатор дозвола**. За више информација о томе како да набавите идентификатор дозволе редигујте следећи одељак.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Омогући дељење података Dataverse са сопственим Azure Data Lake Storage (Преглед)

За омогућавање дељења података Microsoft Dataverse када окружење користи [сопствени налог потребна Azure Data Lake Storage је](own-data-lake-storage.md) додатна конфигурација. Корисник који подешава окружење "Увиди купаца" мора да има најмање **дозволе за складиштење блоб података читалац** *за контејнер "ЦустомерИнсигхтс* " у налогу Azure Data Lake Storage.

1. Креирајте две безбедносне групе на Азуре претплати - **једну читалац безбедносну** **групу и сарадник безбедносну** групу и подесите Microsoft Dataverse услугу као власника за обе безбедносне групе.
2. Управљајте листом контроле приступа (АЦЛ) на контејнеру ЦустомерИнсигхтс у налогу за складиштење путем ових безбедносних група. Додајте услугу Microsoft Dataverse и све Dataverse пословне апликације засноване на систему Дyнамицс 365 Маркетинг **читалац групу** са **дозволама само** за читање. Додајте *само* апликацију "Увиди клијената **" сарадник групу** да бисте доделили дозволе **за** читање и писање профила и увида.

### <a name="limitations"></a>Ограничења

Постоје два ограничења приликом коришћења Dataverse са сопственим налогом Azure Data Lake Storage:

- Постоји мапирање један на један између организације Dataverse и налога Azure Data Lake Storage. Када је Dataverse организација повезана са налогом за складиштење, не може да се повеже са другим налогом за складиштење. Ово ограничење спречава попуњавање Dataverse више налога за складиштење.
- Дељење података неће функционисати ако је потребно подешавање Азуре приватне везе за приступ Азуре Дата Лаке налогу за складиштење јер се налази иза заштитног зида. Dataverse тренутно не подржава везу са приватним крајњим тачкама путем приватне везе.

### <a name="set-up-powershell"></a>Подешавање ПоwерСхелл-а

Да бисте извршили ПоwерСхелл скрипте, прво морате да подесите ПоwерСхелл у складу са тим.

1. Инсталирајте најновију верзију [Azure Active Directory програма ПоwерСхелл за Грапх](/powershell/azure/active-directory/install-adv2).
   1. На рачунару изаберите тастер Windows на тастатури и потражите **Windows PowerShell** и изаберите **Покрени као администратор**.
   1. У PowerShell прозору који се отвори унесите `Install-Module AzureAD`.
2. Увези три модула.
    1. У прозору ПоwерСхелл унесите `Install-Module -Name Az.Accounts` и следите кораке.
    1. Поновите за `Install-Module -Name Az.Resources` и `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Кораци конфигурације

1. Преузмите две ПоwерСхелл скрипте које треба да покренете са [ГитХуб репоа нашег инжењера](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Потребне су вам *администраторске дозволе* закупца да бисте покренули ову ПоwерСхелл скрипту.
       - Ова ПоwерСхелл скрипта креира две безбедносне групе на Азуре претплати. Један за читалац групу и други за сарадник групу и учиниће Microsoft Dataverse услугу као власник обе ове безбедносне групе.
       - Извршите ову ПоwерСхелл скрипту у програму Wиндоwс ПоwерСхелл тако што ћете обезбедити ИД Азуре претплате који садржи ваш Azure Data Lake Storage. Отворите ПоwерСхелл скрипту у уређивачу да бисте прегледали додатне информације и примењену логику.
       - Сачувајте вредности ИД-а обе безбедносне групе које генерише ова скрипта јер ћемо их користити у скрипти `ByolSetup.ps1`.

        > [!NOTE]
        > Креирање безбедносне групе може бити онемогућено вашем станару. У том случају, биће потребно ручно подешавање и администратор ће Azure AD морати да омогући креирање [безбедносних група](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Потребне су вам *дозволе власника података за складиштење* на налогу/контејнеру за складиштење да бисте покренули ову скрипту или ће ова скрипта креирати једну за вас. Додељивање улоге може бити уклоњено ручно након успешног покретања скрипте.
        - Ова ПоwерСхелл скрипта додаје потребну контролу приступа засновану на толима (РБАЦ) за Microsoft Dataverse услугу и све пословне Dataverse апликације засноване на томе. Такође ажурира Листу контроле приступа (АЦЛ) на контејнеру ЦустомерИнсигхтс за безбедносне групе креиране помоћу скрипте `CreateSecurityGroups.ps1`. Група сарадник ће имати рwx *дозволу* и група читалаца ће имати само *р-x* дозволу.
        - Извршите ову ПоwерСхелл скрипту у програму Wиндоwс ПоwерСхелл тако што ћете обезбедити ИД Azure Data Lake Storage Азуре претплате који садржи ваше име налога за складиштење, име групе ресурса и ИД читалац и сарадник безбедносне групе. Отворите ПоwерСхелл скрипту у уређивачу да бисте прегледали додатне информације и примењену логику.
        - Копирајте излазну ниску након успешног покретања скрипте. Излазна ниска изгледа овако: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Унесите излазну ниску копирану одозго у **поље идентификатора** дозвола корака конфигурације окружења за Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Опције конфигурације да бисте омогућили дељење података из сопствених са Azure Data Lake Storage програмом Microsoft Dataverse .":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Уклањање постојеће везе са окружењем Dataverse

Када се повезујете са окружењем Dataverse, порука о грешци **Ова ЦДС организација је већ приложена другој инстанци увида клијената** значи Dataverse да се окружење већ користи у окружењу "Увиди купаца". Постојећу везу можете да уклоните као глобални администратор у окружењу Dataverse. Може да потраје неколико сати да се промене населе.

1. Иди на [Power Apps](https://make.powerapps.com).
1. Изаберите окружење од бирача окружења.
1. Иди на **решења**
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

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
