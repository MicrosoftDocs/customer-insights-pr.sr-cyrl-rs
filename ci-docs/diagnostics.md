---
title: Извоз дијагностичких евиденција (преглед)
description: Сазнајте како да пошаљете евиденције на монитор Microsoft Azure.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: c573c46fda895d36d29712e75fe28b261c9b399a
ms.sourcegitcommit: 0b5bfe0145dbd325fa518df4561d6a0a9a352264
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 08/25/2022
ms.locfileid: "9352819"
---
# <a name="export-diagnostic-logs-preview"></a>Извоз дијагностичких евиденција (преглед)

Проследите евиденције из увида клијената помоћу Азуре монитора. Евиденције ресурса Азуре монитора вам омогућава да надгледате и шаљете евиденције [у Азуре складиште](https://azure.microsoft.com/services/storage/), [Азуре аналитику евиденције](/azure/azure-monitor/logs/log-analytics-overview) или да их стримујете [у Азуре чворишта догађаја](https://azure.microsoft.com/services/event-hubs/).

Увиди купаца шаљу следеће евиденције догађаја:

- **Догађаји надгледања**
  - **АПИЕвент** - омогућава праћење промена путем УИ Dynamics 365 Customer Insights.
- **Оперативни догађаји**
  - **WоркфлоwЕвент** - омогућава вам да подесите изворе података [, уједините](data-sources.md), [обогатите](data-unification.md) и [извезете](enrichment-hub.md)[податке](export-destinations.md) у друге системе. Ови кораци могу да се ураде појединачно (на пример, да се покрене један извоз). Они такође могу да покрену оркестрирано (на пример, освежавање података из извора података који покрећу процес уједињења, који ће повући богаћења и извести податке у други систем). Више информација потражите у шеми [WоркфлоwЕвент](#workflow-event-schema).
  - **АПИЕвент** - шаље све АПИ позиве инстанце клијената на Dynamics 365 Customer Insights. Више информација потражите у апиевент [шеми](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Подешавање дијагностичких поставки

### <a name="prerequisites"></a>Предуслови

- Активна [Азуре претплата](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- [Администраторске](permissions.md#admin) дозволе у увидима клијената.
- Важећи ресурс на Азуре који следи након одредишних [захтева](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) за Азуре складиште, Азуре чвориште догађаја или Аналитику евиденције Азуре.
- [сарадник и администратор корисничког приступа на](/azure/role-based-access-control/role-assignments-portal) одредишном ресурсу на Азуре. Ресурс може бити налог Azure Data Lake Storage, чвориште Азуре догађаја или радни простор Азуре аналитике евиденције. Ова дозвола је неопходна током конфигурисања дијагностичких поставки у програму Цустомер Инсигхтс, али се може променити након успешног подешавања.
- Барем улога читалац **групи** ресурса којој ресурс припада.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Подешавање дијагностике помоћу Азуре монитора

1. У фасцикли "Увиди купаца" идите на **администраторски** > **систем и** изаберите картицу **Дијагностика**.

1. Изаберите **ставку Додај одредиште**.

   :::image type="content" source="media/diagnostics-pane.png" alt-text="Дијагностичка веза.":::

1. Наведите име у одредишном **пољу Име за дијагностику**.

1. Изаберите тип **ресурса** (Налог складишта, Чвориште догађаја или Аналитика евиденције).

1. Изаберите **претплату**, **групу ресурса** и ресурс **за** одредишни ресурс. Више информација [о дозволи и евиденцији потражите у чланку](#configuration-on-the-destination-resource) Конфигурација одредишног ресурса.

1. Прегледајте приватност [и усаглашеност података и](connections.md#data-privacy-and-compliance) изаберите И **слажем се**.

1. Изаберите опцију **Повежи се са системом** да бисте се повезали са одредишним ресурсом. Евиденције почињу да се појављују на одредишту после 15 минута, ако је АПИ у употреби и генерише догађаје.

## <a name="configuration-on-the-destination-resource"></a>Конфигурација одредишног ресурса

На основу вашег избора типа ресурса, аутоматски долази до следећих промена:

### <a name="storage-account"></a>Налог складишта

Директор услуге"Увид у кориснике" **добија сарадник налога** за складиштење на изабраном ресурсу и креира два контејнера под изабраним простором за име:

- `insight-logs-audit` који садрже догађаје **надгледања**
- `insight-logs-operational` који садрже оперативне **догађаје**

### <a name="event-hub"></a>Чвориште догађаја

Директор услуге "Цустомер Инсигхтс" **добија дозволу чворишта догађаја Азуре власника** података за ресурс и креира два чворишта догађаја под изабраним простором за име:

- `insight-logs-audit` који садрже догађаје **надгледања**
- `insight-logs-operational` који садрже оперативне **догађаје**

### <a name="log-analytics"></a>Евидентирај аналитику

Директор услуге "Увиди корисника" добија дозволу **за сарадник евиденције** о ресурсу. Евиденције су доступне у оквиру евиденције **Табела** > **за евиденцију** > **на** изабраном радном простору аналитике евиденције. Развијте решење **за управљање евиденцијом** и пронађите табеле `CIEventsAudit` `CIEventsOperational` и табеле.

- `CIEventsAudit` који садрже догађаје **надгледања**
- `CIEventsOperational` који садрже оперативне **догађаје**

У прозору **Упити** проширите решење **надзора** и пронађите пример упита наведених претраживањем `CIEvents` .

## <a name="remove-a-diagnostics-destination"></a>Уклањање одредишта дијагностике

1. Идите на **администраторски** > **систем и** изаберите картицу **Дијагностика** .

1. Изаберите одредиште дијагностике са листе.

   > [!TIP]
   > Уклањање одредишта зауставља прослеђивање евиденције, али не брише ресурс на Азуре претплати. Да бисте избрисали ресурс у Азуре, изаберите везу у колони **Радње** да бисте отворили портал Азуре за изабрани ресурс и тамо га избрисали. Затим избришите одредиште дијагностике.

1. У колони **Радње** изаберите икону **"Избриши** ".

1. Потврдите брисање да бисте уклонили одредиште и зауставили прослеђивање евиденције.

## <a name="log-categories-and-event-schemas"></a>Евидентирај категорије и шеме догађаја

Тренутно су [подржани АПИ](apis.md) догађаји и догађаји тока посла и примењују се следеће категорије и шеме.
Шема евиденције прати заједничку шему [Азуре монитора](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema) .

### <a name="categories"></a>Категорије

Увиди купаца обезбеђују две категорије:

- **Догађаји надгледања** : [АПИ догађаји](#api-event-schema) за праћење промена конфигурације на услузи. `POST|PUT|DELETE|PATCH` операције иду у ову категорију.
- **Оперативни догађаји** : [АПИ догађаји или догађаји](#api-event-schema) тока [посла](#workflow-event-schema) генерисани током коришћења услуге.  На пример, захтеви `GET` или догађаји извршавања тока посла.

## <a name="event-schemas"></a>Шеме догађаја

АПИ догађаји и догађаји тока посла имају заједничку структуру, али уз неколико разлика. Више информација потражите у апИ [шеми догађаја или шеми](#api-event-schema) догађаја [тока посла](#workflow-event-schema) .

### <a name="api-event-schema"></a>Шема АПИ догађаја

| Поље             | Типподатака  | Обавезно/опционално | Опис       | Пример        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Временска ознака | Потребно          | Тиместамп догађаја (УТЦ)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Потребно          | ИД ресурса инстанце која је емигрирао догађај         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Потребно          | Име операције представљене овим догађајем.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Потребно          | Евидентирај категорију догађаја. Или `Operational` или `Audit` . Алл ПОСТ/ПУТ/ПАТЦХ/ДЕЛЕТЕ ХТТП Реqуестс аре таггед wитх `Audit` , све остало са `Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Потребно          | Статус догађаја. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Опционално          | Статус резултата догађаја. Ако операција одговара РЕСТ АПИ позиву, то је ХТТП статусни кôд.        | `200`             |
| `durationMs`      | Дугачак      | Опционално          | Трајање операције у милисекундама.     | `133`     |
| `callerIpAddress` | String    | Опционално          | ИП адреса позиваоца, ако операција одговара АПИ позиву који долази са јавно доступне ИП адресе.                                                 | `144.318.99.233`         |
| `identity`        | String    | Опционално          | ЈСОН објекат који описује идентитет корисника или апликације која је урадила операцију.       | Погледајте [одељак](#identity-schema)  Идентитет.     |  
| `properties`      | String    | Опционално          | ЈСОН објекат са више својстава према одређеној категорији догађаја.      | Погледајте [одељак Својства](#api-properties-schema) .    |
| `level`           | String    | Потребно          | Ниво озбиљности догађаја.    | `Informational`, `Warning` , , `Error` или `Critical` .           |
| `uri`             | String    | Опционално          | Апсолутни захтев УРИ.    |               |

#### <a name="identity-schema"></a>Шема идентитета

ЈСОН `identity` објекат има следећу структуру

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Поље                         | Опис                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Додељена улога за корисника или апликацију. Више информација потражите у корисничким [дозволама](permissions.md) .                                     |
| `Authorization.RequiredRoles` | Потребне улоге за операцију. `Admin` улога је дозвољена за све операције.                                                    |
| `Claims`                      | Тврдње корисника или апликације ЈСОН Wеб токен (ЈWТ). Својства захтева се разликују по организацији и Azure Active Directory конфигурацији. |

#### <a name="api-properties-schema"></a>Шема АПИ својстава

[АПИ догађаји имају](apis.md) следећа својства.

| Поље                        | Опис                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | `ApiEvent` Увек , означавање догађаја евиденције као АПИ догађаја.                                                                 |
| `properties.userAgent`       | Агент прегледача шаље захтев или `unknown` .                                                                        |
| `properties.method`          | ХТТП метод: `GET/POST/PUT/PATCH/HEAD` .                                                                                |
| `properties.path`            | Релативна путања захтева.                                                                                          |
| `properties.origin`          | УРИ који показује одакле долази допремање или `unknown` .                                                                  |
| `properties.operationStatus` | `Success` за ХТТП статусни кôд < 400 <br> `ClientError` за ХТТП статусни кôд < 500 <br> `Error` за ХТТП Статус >= 500 |
| `properties.tenantId`        | ID организације                                                                                                        |
| `properties.tenantName`      | Назив организације.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ИД објекта позиваоца.                                                                         |
| `properties.instanceId`      | Увиди купаца `instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Шема догађаја тока посла

Ток посла садржи више корака. [Унести извори података, уједините](data-sources.md) , [обогатите](data-unification.md) [и](enrichment-hub.md) извезите [податке](export-destinations.md) . Сви ти кораци могу да се покрећу појединачно или да се оркестрира са следећим процесима.

#### <a name="operation-types"></a>Типови операција

| OperationType     | Групиши                                     |
| ----------------- | ----------------------------------------- |
| Ингестион         | [Извори података](data-sources.md)           |
| Преспремање података   | [Извори података](data-sources.md)           |
| Мапирај               | [Уједначавање података](data-unification.md)   |
| Подударање             | [Уједначавање података](data-unification.md)   |
| Обједини             | [Уједначавање података](data-unification.md)   |
| Историја профила      | [Профили клијената](customer-profiles.md) |
| Претражите            | [Профили клијената](customer-profiles.md) |
| Активност          | [Активности](activities.md)                  |
| АтрибутМеасурес | [Сегменти и мере](segments.md)      |
| ЕнтитетМеасурес    | [Сегменти и мере](segments.md)      |
| Мере          | [Сегменти и мере](segments.md)      |
| Сегментација      | [Сегменти и мере](segments.md)      |
| Обогаћивање        | [Обогаћивање](enrichment-hub.md)                                          |
| Информације      | [Предвиђања](predictions-overview.md)                                          |
| АиБуилдер         | [Предвиђања](predictions-overview.md)                                          |
| Увиди          | [Предвиђања](predictions-overview.md)                                          |
| Export            | [Извоз](export-destinations.md)                                          |
| МоделМанагемент   | [Предвиђања](custom-models.md)                                           |
| Релација      | [Уједначавање података](relationships.md)                                           |

#### <a name="field-description"></a>Опис поља

| Поље           | Типподатака  | Обавезно/опционално | Опис                                                                                                                                                   | Пример                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Временска ознака | Потребно          | Тиместамп догађаја (УТЦ).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Потребно          | ИД ресурса инстанце која је емитује догађај.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Потребно          | Име операције представљене овим догађајем. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Погледајте [типове операција](#operation-types) за референцу. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Потребно          | Евидентирај категорију догађаја. Увек `Operational` за догађаје тока посла                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | Потребно          | Статус догађаја. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Дугачак      | Опционално          | Трајање операције у милисекундама.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Опционално          | ЈСОН објекат са више својстава према одређеној категорији догађаја.                                                                                        | Погледајте подсе одсек " [Својства тока посла"](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Потребно          | Ниво озбиљности догађаја.                                                                                                                                  | `Informational`, `Warning` или `Error`                                                                                                                                   |

#### <a name="workflow-properties-schema"></a>Шема својстава тока посла

Догађаји тока посла имају следећа својства.

| Поље              | Workflow | Задатак | Опис            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Да      | Да  | Увек `WorkflowEvent` , означавање догађаја као догађаја тока посла.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Да      | Да  | Идентификатор тока посла. Сви догађаји тока посла и задатака у оквиру извршавања тока посла имају исти `workflowJobId` .                                                                                                                                   |
| `properties.operationType`                   | Да      | Да  | Идентификатор операције, погледајте типове [операција](#operation-types) .                                                                                                                                                                               |
| `properties.tasksCount`                      | Да      | No   | Само ток посла. Број задатака које ток посла покреће.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Да      | No   | Опционално. Само догађаји тока посла. ИД Azure Active Directory [објекта корисника који је активирао](/azure/marketplace/find-tenant-object-id#find-user-object-id) ток посла, погледајте такође `properties.workflowSubmissionKind` .                                   |
| `properties.workflowType`                    | Да      | No   | `full` или освежити `incremental` .                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Да      | No   | `OnDemand` или `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Да      | No   | `Running` или  `Successful` .                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Да      | Да  | УТЦ Тиместамп `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Да      | Да  | УТЦ Тиместамп `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Да      | Да  | УТЦ Тиместамп `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Да      | Да  | Увиди купаца `instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Да  | - За ОператионТyпе = `Export` , идентификатор је гуид конфигурације извоза. <br> - За ОператионТyпе = `Enrichment` , то је гуид богаћења <br> - За ОператионТyпе `Measures` `Segmentation` и , идентификатор је име ентитета. |
| `properties.friendlyName`                    | No       | Да  | Кориснички прилагођено име извоза или ентитета који се обрађује.                                                                                                                                                                                           |
| `properties.error`                           | No       | Да  | Опционално. Порука о грешци са више детаља.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Да  | Опционално. Само за ОператионТyпе `Export` . Идентификује тип извоза. Више информација потражите у [прегледу извозних одредишта](export-destinations.md) .                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Да  | Опционално. Само за ОператионТyпе `Export` . Садржи листу конфигурисаних ентитета у извозу.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Да  | Опционално. Само за ОператионТyпе `Export` . Детаљна порука за извоз.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Да  | Опционално. Само за ОператионТyпе `Segmentation` . Означава укупан број чланова које сегмент има.                                                                                                                                                    |

[!INCLUDE [footer-include](includes/footer-banner.md)]
