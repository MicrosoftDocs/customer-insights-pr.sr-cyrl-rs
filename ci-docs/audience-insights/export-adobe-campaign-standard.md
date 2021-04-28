---
title: Извезите Customer Insights податке у Adobe Campaign Standard
description: Сазнајте како се користе сегменти увида у кориснике у услузи Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: b6c010d84119c2fa8b3ef99017c65f9939bf28c4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760299"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Коришћење Customer Insights сегмената у услузи Adobe Campaign Standard (верзија за преглед)

Као корисник увида о корисницима за Dynamics 365 Customer Insights, можда сте креирали сегменте да бисте маркетиншке кампање учинили ефикаснијим тако што ћете циљати релевантне циљне групе. Да бисте користили сегмент из увида о корисницима у Adobe платформи искуства и апликацијама попут Adobe Campaign Standard, потребно је да следите неколико корака наведених у овом чланку.

:::image type="content" source="media/ACS-flow.png" alt-text="Дијаграм процеса корака описаних у овом чланку.":::

## <a name="prerequisites"></a>Предуслови

-   Dynamics 365 Customer Insights лиценца
-   Лиценца за Adobe Campaign Standard
-   Налог Azure складишта блоб објекта

## <a name="campaign-overview"></a>Преглед кампање

Да бисте боље разумели како можете да користите сегменте из увида о корисницима у Adobe платформи искуства, погледајмо фиктивни пример кампање.

Претпоставимо да ваше предузеће нуди месечну услугу засновану на претплати за клијенте у Сједињеним Државама. Желите да идентификујете клијенте који треба да обнове претплате у наредних осам дана, али још увек нису обновили претплату. Да бисте задржали ове клијенте, треба да им пошаљете промотивну понуду путем е-поште, користећи Adobe Campaign Standard.

У овом примеру желимо да једном покренемо промотивну кампању е-поште. Овај чланак не покрива случај коришћења са више покретања кампање. Међутим, увиди у кориснике и Adobe Campaign Standard могу се конфигурисати да раде и за понављајући сценарио кампање.

## <a name="identify-your-target-audience"></a>Идентификујте своју циљну групу

У нашем сценариј,у претпостављамо да су адресе е-поште клијената доступне у увидима о корисницима и да су анализиране њихове промотивне жељене опције како би се идентификовали чланови сегмента.

[Сегмент који сте дефинисали увидом о корисницима](segments.md) се зове **ChurnProneCustomers** и планирате да овим клијентима пошаљете е-поруку са промоцијом.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Снимак екрана странице сегмената са креираним сегментом ChurnProneCustomers.":::

Е-порука са понудом коју желите да пошаљете садржи име, презиме и датум завршетка претплате клијента. Порука обавештава клијенте о попусту који ће добити ако обнове претплату пре него што се заврши.

## <a name="export-your-target-audience"></a>Извезите своју циљну групу

### <a name="configure-a-connection"></a>Конфигурисање везе

Када је идентификована циљна група, можемо да конфигуришемо извоз из увида о корисницима на налог Azure складишта блоб објекта.

1. У увидима у циљне групе, идите на **Администратор** > **Везе**.

1. Изаберите **Додај везу** и бирајте **Adobe Campaign** да бисте конфигурисали везу или изаберите **Подешавање** на плочици **Adobe Campaign**

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Плочица за конфигурацију за Adobe Campaign Standard.":::

1. Дајте вези препознатљиво име у пољу **Име за приказ**. Име за приказ и врста везе описују ову везу. Препоручујемо да одаберете назив који објашњава сврху и циљ везе.

1. Одаберите ко може да користи ову везу. Ако ништа не предузмете, подразумевани ће бити Администратори. За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).

1. Унесите **Назив налога**, **Кључ налога** и **Контејнер** за ваш налог за Azure складиште блоб објекта у који желите да извезете сегмент.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Снимак екрана конфигурације налога складишта. "::: 

   - Да бисте сазнали више о проналажењу имена и кључа налога за Azure складиште блоб објекта, погледајте [Управљајте подешавањима налога за складиштење на Azure порталу](/azure/storage/common/storage-account-manage).

   - Да бисте сазнали како да креирате контејнер, погледајте чланак [Креирање контејнера](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Изаберите **Сачувај** да бисте креирали везу.

### <a name="configure-an-export"></a>Конфигурисање извоза

Овај извоз можете да конфигуришете ако имате приступ вези ове врсте. За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).

1. Идите на **Подаци** > **Извози**.

1. Да бисте креирали нови извоз, изаберите **Додај извоз**.

1. У пољу **Веза за извоз**, одаберите везу из одељка Adobe Campaign. Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.

1. Одаберите сегмент које желите да извезете. У овом примеру, то је **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Снимак екрана корисничког интерфејса за одабир сегмента са изабраним сегментом ChurnProneCustomers.":::

1. Изаберите **Следеће**.

1. Сада мапирамо поља **Извор** од сегмента увида у кориснике до имена поља **Циљ** у шеми Adobe Campaign Standard профила.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Мапирање поља за Adobe Campaign Standard конектор.":::

   Ако желите да додате још атрибута, изаберите **Додај атрибут**. Назив циља може се разликовати од имена изворног поља, тако да и даље можете мапирати излаз сегмента из увида у кориснике у услугу Adobe Campaign Standard ако поља немају исти назив у два система.

   > [!NOTE]
   > Адреса е-поште се користи као поље идентитета, али можете користити било који други идентификатор из вашег корисничког профила за увиде у кориснике да бисте мапирали податке у Adobe Campaign Standard.

1. Изаберите ставку **Сачувај**.

Када сачувате одредиште за извоз, пронаћи ћете га у дијалогу **Подаци** > **Извози**.

Сада можете да [извозите сегмент на захтев](export-destinations.md#run-exports-on-demand). Извоз ће се такође покренути са сваким [планираним освежавањем](system.md).

> [!NOTE]
> Уверите се да је број записа у извезеном сегменту унутар дозвољеног ограничења ваше Adobe Campaign Standard лиценце.

Извезени подаци се чувају у контејнеру Azure складишта блоб објекта који сте раније конфигурисали. Следећа путања до фасцикле се аутоматски креира у вашем контејнеру:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Конфигурисање услуге Adobe Campaign Standard

Када се извезе сегмент из увида у кориснике, он садржи колоне које сте изабрали приликом дефинисања одредишта извоза у претходном кораку. Ови подаци се могу користити за [креирање профила у услузи Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Да бисмо користили сегмент у услузи Adobe Campaign Standard, треба да проширимо шему профила у услузи Adobe Campaign Standard тако да укључује два додатна поља. Сазнајте како да [продужите ресурс профила](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) са новим пољима у услузи Adobe Campaign Standard.

У нашем примеру, ова поља су *Назив сегмента и Датум сегмента (опционално).*

Ова поља ћемо користити за идентификацију профила у програму Adobe Campaign Standard које желимо да циљамо за ову кампању.

Ако у програму Adobe Campaign Standard не постоје други записи осим оних које ћете увозити, можете прескочити овај корак.

## <a name="import-data-into-adobe-campaign-standard"></a>Увоз података у Adobe Campaign Standard

Сада када је све на свом месту, морамо припремити податке о корисницима из увида у кориснике у услузи Adobe Campaign Standard да бисмо креирали профиле. Сазнајте [како да увезете профиле у Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) користећи ток посла.

Ток посла увоза на доњој слици конфигурисан је за покретање сваких 8 сати и тражи извезене сегменте увида у кориснике (.csv датотека у Azure складишту блоб објекта). Ток посла издваја садржај .csv датотеке у наведеном редоследу колона. Овај ток посла направљен је да обави основно руковање грешкама и осигура да сваки запис има адресу е-поште пре попуне подацима у услузи Adobe Campaign Standard. Ток посла такође издваја име сегмента из имена датотеке пре додавања у податке ACS профила.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Снимак екрана тока посла увоза у корисничком интерфејсу услуге Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Преузимање корисника у услузи Adobe Campaign Standard

Када се подаци увезу у Adobe Campaign Standard, ви [можете да креирате ток посла](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) и [упит](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) да би клијенти засновани на *Називу сегмента* и *Датуму сегмента* изабрали профиле који су идентификовани за наш пример кампање.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Креирајте и пошаљите е-поруку користећи Adobe Campaign Standard

Креирајте садржај е-поруке, а затим [тестирајте и пошаљите](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) е-поруку.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Пример е-поруке са понудом обнове претплате из услуге Adobe Campaign Standard.":::
