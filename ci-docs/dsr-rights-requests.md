---
title: Захтеви на основу права субјекта података (DSR) у оквиру GDPR | Microsoft Docs
description: Одговорите на захтеве субјекта података за Dynamics 365 Customer Insights могућност увида о корисницима.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350287"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Захтеви на основу права субјекта података (DSR) у оквиру GDPR

Општа уредба о заштити података Европске уније (GDPR) на снази је од 25. маја 2018. Она даје значајна права појединцима у погледу њихових података. GDPR се односи на заштиту и омогућавање права на приватност појединаца. Можете прочитати више о посвећености компаније Microsoft безбедности и усклађености у [Microsoft центру за поузданост](https://www.microsoft.com/trust-center).

Посвећени смо помагању нашим клијентима да испуне захтеве GDPR-а. Обухвата право на брисање и извоз података који укључују личне информације као што су кориснички ID-ови, бројеви телефона и адресе е-поште. Администратори могу да примене захтеве корисника за брисање или извоз личних података.

## <a name="audience-insights"></a>Увиди у циљну групу

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Одговарање на захтеве за брисање GDPR субјекта података за Dynamics 365 Customer Insights могућност увида о корисницима

„Право на брисање“ уклањањем личних података из података о клијентима организације представља кључну заштиту у Општој уредби о заштити података (GDPR). Уклањање личних података укључује уклањање свих личних података и системски генерисаних евиденција, осим информација из евиденције надгледања.

#### <a name="manage-data-subject-delete-requests"></a>Управљање захтевима за брисање субјекта података

Увиди о корисницима нуде следеће искуство у вези са производом за брисање личних података одређеног клијента или Customer Insights корисника:

- **Управљајте захтевима брисање података о клијенту**: Подаци о клијенту у услузи Customer Insights унети су из оригиналних извора података који су спољашњи за Customer Insights. Сви GDPR захтеви за брисање морају се обавити у оригиналном извору података.
- **Управљајте захтевима за брисање корисничких података корисника услуге Customer Insights**: Податке за кориснике креира Customer Insights. Сви GDPR захтеви за брисање морају се обавити у услузи Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Управљање захтевима за брисање података о клијентима

Администратор услуге Customer Insights може да прати ове кораке за уклањање података о клијентима који су избрисани у извору података:

1. Пријавите се у Dynamics 365 Customer Insights.
2. У увидима о корисницима идите на **Подаци** > **Извори података**
3. За сваки извор података на листи који садржи избрисане податке о клијентима:
   1. Изаберите (...), па изаберите **Освежи**.
   2. Проверите статус извора података у одељку **Статус**. Знак потврде значи да је освежавање било успешно. Трокут упозорења значи да нешто није у реду. Ако се прикаже троугао упозорења, контактирајте D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Руковање GDPR захтевима за брисање података о клијентима.](audience-insights/media/gdpr-data-sources.png "Руковање GDPR захтевима за брисање података о клијентима")

##### <a name="manage-delete-requests-for-user-data"></a>Управљање захтевима за брисање података о корисницима

Администратор услуге Customer Insights може да следи следеће кораке за брисање података о Customer Insights корисницима:

1. Пријавите се у Dynamics 365 Customer Insights.
2. У увидима о корисницима идите на **Администратор** > **Дозволе**.
3. Изаберите поље за потврду за корисника којег желите да избришете.
4. Изаберите **Уклони**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Одговарање на GDPR захтеве за извоз субјекта података

Као део наше посвећености да заједно са вама сарађујемо на вашем путу до Опште уредбе о заштити података (GDPR), развили смо документацију која ће вам помоћи да се припремите. Ова документација описује кораке које данас можете предузети да бисте подржали поштовање GDPR-а када користите увиде о корисницима.

#### <a name="manage-export-and-view-requests"></a>Управљање извозом и приказ захтева

Право преносивости података омогућава субјектима података да затраже копију својих личних података у електронском формату (дефинисаном као "структурирани, уобичајено употребљив, машински читљив и интероперабилни формат") који се може пренети на другог контролора података.

##### <a name="export-customer-data-tenant-admin"></a>Извоз података о клијенту (администратор закупца)

Администратор закупца може да прати ове кораке за извоз података:

1. Пошаљите е-поруку на D365CI@microsoft.com наводећи адресу е-поште клијента у захтеву. Customer Insights тим ће послати е-поруку на регистровану адресу е-поште администратора регистрованог закупца, тражећи потврду за извоз података.
2. Потврдите потврду за извоз података за траженог клијента.
3. Примите извезене податке путем е-адресе администратора закупца.

##### <a name="export-user-data-tenant-admin"></a>Извоз података о кориснику (администратор закупца)

1. Пошаљите е-поруку на D365CI@microsoft.com наводећи адресу е-поште корисника у захтеву. Customer Insights тим ће послати е-поруку на регистровану адресу е-поште администратора регистрованог закупца, тражећи потврду за извоз података.
2. Прихватите потврду за извоз података за траженог корисника.
3. Примите извезене податке путем е-адресе администратора закупца.

## <a name="consent-management-preview"></a>Управљање сагласностима (преглед)

Могућност управљања пристанком не прикупља директно корисничке податке. Он увози и обрађује само податке о сагласности које корисници обезбеђују у другим апликацијама.

Да бисте уклонили податке о пристанку о одређеним корисницима, уклоните их у изворима података који су унети у могућност управљања пристанком. Након освежавања извор података, уклоњени подаци ће такође бити избрисани у Центру за сагласност. Апликације које користе ентитет сагласности ће такође избрисати податке који су уклоњени на извору након [освежавања](audience-insights/system.md#refresh-processes). Препоручујемо брзо освежавање извора података након одговора на захтев субјекта података за уклањање података корисника из свих других процеса и апликација.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]