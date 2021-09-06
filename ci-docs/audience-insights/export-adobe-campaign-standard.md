---
title: Извоз Customer Insights података у услугу Adobe Campaign Standard
description: Сазнајте како да користите сегменте увида у циљну групу у услузи Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d301b4f0cb875303fb3d373b77177acd1c1f5219cd6f23c2a1d29ce67a222eab
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032181"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Користите Customer Insights сегменте у услузи Adobe Campaign Standard (верзија за преглед)

Као корисник увида у циљну групу у услузи Dynamics 365 Customer Insights, можда сте креирали сегменте да бисте маркетиншке кампање учинили ефикаснијим циљајући релевантне циљне групе. Да бисте користили сегмент из увида у циљну групу у услузи Adobe Experience Platform и апликацијама попут Adobe Campaign Standard, морате да следите неколико корака описаних у овом чланку.

:::image type="content" source="media/ACS-flow.png" alt-text="Дијаграм процеса корака описаних у овом чланку.":::

## <a name="prerequisites"></a>Предуслови

-   Dynamics 365 Customer Insights лиценца
-   Лиценца за Adobe Campaign Standard
-   Налог Azure складишта блоб објекта

## <a name="campaign-overview"></a>Преглед кампање

Да бисте боље разумели како можете да користите сегменте из увида у циљну групу у услузи Adobe Experience Platform, погледајмо измишљени пример кампање.

Претпоставимо да ваше предузеће нуди месечну услугу засновану на претплати за клијенте у Сједињеним Државама. Желите да идентификујете клијенте који треба да обнове претплате у наредних осам дана, али још увек нису обновили претплату. Да бисте задржали ове клијенте, треба да им пошаљете промотивну понуду путем е-поште користећи Adobe Campaign Standard.

У овом примеру желимо да једном покренемо промотивну кампању е-поште. Овај чланак не покрива случај коришћења са више покретања кампање. Међутим, увиди у циљну групу и Adobe Campaign Standard могу да се конфигуришу и тако да функционишу и за сценарио понављајуће кампање.

## <a name="identify-your-target-audience"></a>Идентификујте своју циљну групу

У нашем сценариј,у претпостављамо да су адресе е-поште клијената доступне у увидима о корисницима и да су анализиране њихове промотивне жељене опције како би се идентификовали чланови сегмента.

[Сегмент који сте дефинисали увидом о корисницима](segments.md) се зове **ChurnProneCustomers** и планирате да овим клијентима пошаљете е-поруку са промоцијом.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Снимак екрана странице сегмената са креираним сегментом ChurnProneCustomers.":::

Е-порука са понудом коју желите да пошаљете садржи име, презиме и датум завршетка претплате клијента. Порука обавештава клијенте о попусту који ће добити ако обнове претплату пре него што се заврши.

## <a name="export-your-target-audience"></a>Извезите своју циљну групу

### <a name="configure-a-connection"></a>Конфигурисање везе

Када је идентификована циљна група, можемо да конфигуришемо извоз из увида о корисницима на налог Azure складишта блоб објекта.

1. У увидима у циљне групе, идите на **Администратор** > **Везе**.

1. Изаберите **Додај везу** и бирајте **Adobe кампања** да бисте конфигурисали везу или изаберите **Подешавање** на плочици **Adobe кампања**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Плочица конфигурације за Adobe Campaign Standard.":::

1. Дајте вези препознатљиво име у пољу **Име за приказ**. Име за приказ и врста везе описују ову везу. Препоручујемо да одаберете назив који објашњава сврху и циљ везе.

1. Одаберите ко може да користи ову везу. Ако ништа не предузмете, подразумевани ће бити Администратори. За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).

1. Унесите **Назив налога**, **Кључ налога** и **Контејнер** за ваш налог за Azure складиште блоб објекта у који желите да извезете сегмент.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Снимак екрана конфигурације налога складишта. "::: 

   - Да бисте сазнали више о проналажењу имена и кључа налога за Azure складиште блоб објекта, погледајте чланак [Управљање подешавањима налога за складиштење на Azure порталу](/azure/storage/common/storage-account-manage).

   - Да бисте сазнали како да креирате контејнер, погледајте чланак [Креирање контејнера](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Изаберите **Сачувај** да бисте креирали везу.

### <a name="configure-an-export"></a>Конфигурисање извоза

Овај извоз можете да конфигуришете ако имате приступ вези ове врсте. За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).

1. Идите на **Подаци** > **Извози**.

1. Да бисте креирали нови извоз, изаберите **Додај извоз**.

1. У пољу **Веза за извоз**, одаберите везу из одељка Adobe Campaign. Ако не видите назив овог одељка, тада вам нису доступне везе овог типа.

1. Одаберите сегмент које желите да извезете. У овом примеру, то је **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Снимак екрана корисничког интерфејса за одабир сегмента са изабраним сегментом ChurnProneCustomers.":::

1. Изаберите **Следеће**.

1. Сада мапирамо **изворна** поља из сегмента увида у циљну групу у називе **циљних** поља у Adobe Campaign Standard шеми профила.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Мапирање поља за Adobe Campaign Standard конектор.":::

   Ако желите да додате још атрибута, изаберите **Додај атрибут**. Назив циља се може разликовати од назива изворног поља, тако да и даље можете мапирати излаз сегмента из увида у циљну групу у Adobe Campaign Standard ако поља немају исти назив у два система.

   > [!NOTE]
   > Адреса е-поште се користи као поље идентитета, али можете користити било који други идентификатор из профила клијента увида у циљну групу да бисте мапирали податке на Adobe Campaign Standard.

1. Изаберите ставку **Сачувај**.

Када сачувате одредиште за извоз, пронаћи ћете га у дијалогу **Подаци** > **Извози**.

Сада можете да [извозите сегмент на захтев](export-destinations.md#run-exports-on-demand). Извоз ће се такође покренути са сваким [планираним освежавањем](system.md).

> [!NOTE]
> Уверите се да је број записа у извезеном сегменту унутар дозвољеног ограничења ваше лиценце за услугу Adobe Campaign Standard.

Извезени подаци се чувају у контејнеру Azure складишта блоб објекта који сте раније конфигурисали. Следећа путања до фасцикле се аутоматски креира у вашем контејнеру:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Конфигурисање услуге Adobe Campaign Standard

Када се извезе сегмент из увида у кориснике, он садржи колоне које сте изабрали приликом дефинисања одредишта извоза у претходном кораку. Ови подаци се могу користити за [креирање профила у услузи Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Да бисмо користили сегмент у услузи Adobe Campaign Standard, морамо проширити шему профила у услузи Adobe Campaign Standard так ода укључује два додатна поља. Сазнајте како да [проширите ресурс профила](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) са новим пољима у услузи Adobe Campaign Standard.

У нашем примеру, ова поља су *Назив сегмента и Датум сегмента (опционално)*.

Ова поља ћемо користити за идентификацију профила у услузи Adobe Campaign Standard који желимо да циљамо за ову кампању.

Ако нема других записа у услузи Adobe Campaign Standard осим оног који ћете увести, можете прескочити овај корак.

## <a name="import-data-into-adobe-campaign-standard"></a>Увоз података у Adobe Campaign Standard

Сада када је све на свом месту, треба да увеземо припремљене податке о циљној групи из увида о циљној групи у услугу Adobe Campaign Standard да бисмо креирали профиле. Сазнајте [како да увезете профиле у Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) користећи ток посла.

Ток посла увоза на доњој слици конфигурисан је да се покреће сваких осам сати и тражи извезене сегменте увида у циљну групу (.csv датотека у Azure складишту блоб објекта). Ток посла издваја садржај .csv датотеке у наведеном редоследу колона. Овај ток посла је направљен да изврши основно руковање грешкама и да обезбеди да сваки запис има адресу е-поште пре него што унесе податке у Adobe Campaign Standard. Ток посла такође издваја назив сегмента из назива датотеке пре додавања у податке о Adobe Campaign Standard профилу.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Снимак екрана тока посла увоза у кориснички интерфејс услуге Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Преузимање циљне групе у услузи Adobe Campaign Standard

Када се подаци увезу у Adobe Campaign Standard, [можете креирати ток посла](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) и [поставити упит](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) клијентима на основу *назива сегмента* и *датума сегмента* да бисте изабрали профиле који су идентификовани за наш пример кампање.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Креирање и слање е-поште у услузи Adobe Campaign Standard

Креирајте садржај е-поруке, а затим [тестирајте и пошаљите](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) е-поруку.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Пример е-поруке са понудом за обнову из услуге Adobe Campaign Standard.":::
