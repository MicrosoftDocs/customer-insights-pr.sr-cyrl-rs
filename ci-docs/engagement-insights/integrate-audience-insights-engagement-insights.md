---
title: Креирање везе између увида у циљне групе и увида у ангажовање
description: Креирајте активну везу између увида у циљну групу и увида у ангажовање да бисте омогућили двосмерно дељење података.
ms.date: 09/08/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 56adc206d83bc6e34a55f11383393b5ac66da531
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229890"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Креирање везе између увида у циљне групе и увида у ангажовање

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Интеграција између увида у ангажовање и увида у циљну групу повезује окружења из обе могућности и омогућава међусобно дељење података у оба смера.

Користите обједињене профиле и сегменте из увида у циљну групу за више опција анализе у увидима у ангажовање. Извезите догађаје који имају високу пословну вредност из увида у ангажовање. Помоћу ових догађаја додајте податке у обједињене профиле у увидима у циљну групу.

## <a name="prerequisites"></a>Предуслови

- корисници профила морају бити ускладиштени у налогу који Azure Data Lake Storage поседујете или у управљано језеро са [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro)&ndash; подацима. 
- Ваше окружење увида у циљну групу би требало да има придружено Dataverse окружење. А ако и то окружење користи Dataverse за складиштење података, проверите да ли је означена опција **Омогући дељење података** у увидима у циљну групу. За још информација погледајте [Креирање и конфигурисање окружења у увидима у циљну групу](../audience-insights/create-environment.md).
- Потребне су вам администраторске дозволе за окружења за увиде у ангажовање и за увида у циљну групу.
- Повезана окружења морају бити у истом географском региону.

> [!NOTE]
> - Ако је ваша претплата на увиде у циљну групу у пробној верзији која користи интерно управљано језеро података за увиде у циљну групу, контактирајте [pirequest@microsoft.com](mailto:pirequest@microsoft.com) за помоћ. 
> - Ако ваше окружење за увид у циљну групу користи вашу услугу Azure Data Lake Storage да бисте ускладиштили податке, морате да додате принципала услуге Azure увида у ангажовање на налог за складиштење. За детаље, погледајте чланак [Повежите се са Azure Data Lake Storage налогом с принципалом услуге Azure за увиде у циљну групу](../audience-insights/connect-service-principal.md). 


## <a name="create-an-environment-link"></a>Креирање везе окружења

Везу окружења можете да креирате ажурирањем подешавања **Администратор** > **Окружење** у увидима у ангажовање.

**Како се успоставља активна веза између увида у циљне групе и увида у ангажовање**

1. На страници **Администратор окружења** изаберите картицу **Повежите окружења**.

    :::image type="content" source="media/integrate1.png" alt-text="Конфигуришите окружење.":::

1. Изаберите **Подешавања окружења** у горњем левом углу или при дну екрана.

     :::image type="content" source="media/integrate2.png" alt-text="Изаберите окружење увида у циљну групу.":::

1. Изаберите окружење увида у циљну групу, а затим изаберите ***Следеће** да бисте завршили. Сада можете да изаберете опционалне функције за повезана окружења.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Омогућавање атрибута и сегмената обједињених профила увида у циљну групу

Када повежете окружења, можете да изаберете опционалне функције за повезана окружења. Ове функције омогућавају атрибуте и сегменте обједињених профила из увида у циљну групу за интерактивну анализу података о клијентима.

> [!IMPORTANT]
> Да би се сегменти увида у циљну групу приказали у увидима у ангажовање, морате прво [покренути обједињавања и последичне процесе](../audience-insights/merge-entities.md). Последични процеси су важни јер генеришу јединствену табелу која припрема сегменте увида у циљну групу за дељење са увидима у ангажовање. (Ако је освежавање система заказано, аутоматски ће укључити последичне процесе.)

**Како се анализирају веб-подаци у увидима у ангажовање**

1. На страници **Администратор окружења**, укључите прекидач **Делите податке из увида у циљну групу са увидима у ангажовање**, а затим изаберите **Следеће**.

    :::image type="content" source="media/integrate4.png" alt-text="Изаберите функције.":::

1. Изаберите атрибуте обједињених профила који ће постати аспекти у увидима у ангажовање. (Нису сви атрибути корисни аспекти. На пример, није вероватно да ће вам требати **Име** или **Презиме** као атрибут за анализу догађаја на вашој веб-локацији.)

    :::image type="content" source="media/integrate5.png" alt-text="Уређивање аспеката.":::

   >[!NOTE]
   > Сви атрибути профила увида у циљну групу који представљају идентификаторе (као што су **ID** и **алтернативни ID**) филтрирају се из доступних атрибута и постају аспекти увида у ангажовање.

1. Када завршите са одабиром атрибута, изаберите **Следеће**.
1. Додајте кориснике који могу да виде аспекте и сегменте профила увида у циљну групу у увидима у ангажовање.

    :::image type="content" source="media/integrate6.png" alt-text="Управљајте приступом подацима о клијенту.":::

   > [!IMPORTANT]
   > Ако у овом кораку не додате кориснике изричито, подаци ће бити сакривени од корисника у увидима у ангажовање.
   > Да би се сегменти увида у циљну групу приказали у увидима у ангажовање, морате прво [покренути обједињавања и последичне процесе](../audience-insights/merge-entities.md). Последични процеси су важни јер генеришу јединствену табелу која припрема сегменте увида у циљну групу за дељење са увидима у ангажовање. (Ако је освежавање система заказано, аутоматски ће укључити последичне процесе.)

1. Прегледајте изабране ставке, па изаберите **Заврши**.

    :::image type="content" source="media/integrate7.png" alt-text="Прегледајте подешавања података о клијентима.":::

## <a name="export-refined-events-to-audience-insights"></a>Извоз прецизираних догађаја у увиде у циљну групу

Када креирате везу између окружења, можете да извезете прецизиране догађаје из увида у ангажовање у увиде у циљну групу и унесете их као нови извор података. 

За више информација, погледајте чланак [Интеграција веб-података из увида у ангажовање у увидима у циљну групу](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
