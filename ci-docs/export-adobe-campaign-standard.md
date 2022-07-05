---
title: Извоз сегмената увида купаца у Adobe стандард кампање (преглед)
description: Сазнајте како да користите сегменте "Увиди купаца" у стандардној Adobe кампањи.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 9915591cd969bf825f5d1669de43ed4f9953f898
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082352"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Извоз сегмената увида купаца у Adobe стандард кампање (преглед)

Као корисник, можда Dynamics 365 Customer Insights сте креирали сегменте да бисте маркетиншке кампање били ефикаснији циљањем релевантних корисника локације. Да бисте користили сегмент из увида клијената у и Adobe Experience Platform апликације као што је Adobe Стандард кампање, потребно је да следите неколико корака наведених у овом чланку.

:::image type="content" source="media/ACS-flow.png" alt-text="Дијаграм процеса корака описаних у овом чланку.":::

## <a name="prerequisites"></a>Предуслови

- Dynamics 365 Customer Insights лиценца
- Лиценца за Adobe Campaign Standard
- Налог Azure складишта блоб објекта

## <a name="campaign-overview"></a>Преглед кампање

Да бисмо боље разумели како можете да користите сегменте из "Увида купаца" Adobe Experience Platform у, погледајмо фиктивну пробну кампању.

Претпоставимо да ваше предузеће нуди месечну услугу засновану на претплати за клијенте у Сједињеним Државама. Желите да идентификујете клијенте који треба да обнове претплате у наредних осам дана, али још увек нису обновили претплату. Да бисте задржали ове клијенте, треба да им пошаљете промотивну понуду путем е-поште користећи Adobe Campaign Standard.

У овом примеру желимо да једном покренемо промотивну кампању е-поште. Овај чланак не покрива случај коришћења са више покретања кампање. Међутим, увиди клијената и Adobe стандард кампање могу да се конфигуришу тако да раде и за периодични сценарио кампање.

## <a name="identify-your-target-audience"></a>Идентификујте своју циљну групу

У нашем сценарију, претпостављамо да су е-адресе клијената доступне и да су анализиране њихове промотивне преференције како би се идентификовали чланови сегмента.

Сегмент [који сте дефинисали у "Увидима купаца"](segments.md) зове се **ЦхурнПронеЦустомерс и планирате** да овим корисницима пошаљете промоцију е-поште.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Снимак екрана странице сегмената са креираним сегментом ChurnProneCustomers.":::

Е-порука са понудом коју желите да пошаљете садржи име, презиме и датум завршетка претплате клијента. Порука обавештава клијенте о попусту који ће добити ако обнове претплату пре него што се заврши.

## <a name="export-your-target-audience"></a>Извезите своју циљну групу

### <a name="configure-a-connection"></a>Конфигурисање везе

Са идентификованим корисници циљним датотекама, можемо да конфигуришемо извоз на Азуре Блоб Стораге налог.

1. У увидима клијената идите на **администраторски** > **конекцију**.

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

1. Сада мапирамо поља **Извор** из сегмента"Увиди купаца" у имена **поља** "Циљ" у шеми Adobe профила стандардне кампање.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Мапирање поља за Adobe Campaign Standard конектор.":::

   Ако желите да додате још атрибута, изаберите **Додај атрибут**. Циљно име се може разликовати од имена изворног поља тако да и даље можете мапирати излаз сегмента из "Увиди купаца Adobe " у стандард кампање ако поља немају исто име у два система.

   > [!NOTE]
   > Е -адреса се користи као поље идентитета, али можете да користите било који други идентификатор из профила клијента да бисте мапирали податке у стандард Adobe кампање.

1. Изаберите **Сачувај**.

Када сачувате одредиште за извоз, пронаћи ћете га у дијалогу **Подаци** > **Извози**.

Сада можете да [извозите сегмент на захтев](export-destinations.md#run-exports-on-demand). Извоз ће се такође покренути са сваким [планираним освежавањем](system.md).

> [!NOTE]
> Уверите се да је број записа у извезеном сегменту унутар дозвољеног ограничења ваше лиценце за услугу Adobe Campaign Standard.

Извезени подаци се чувају у контејнеру Azure складишта блоб објекта који сте раније конфигурисали. Следећа путања до фасцикле се аутоматски креира у вашем контејнеру:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Конфигурисање услуге Adobe Campaign Standard

Извезени сегменти садрже колоне које сте изабрали приликом дефинисања одредишта извоза у претходном кораку. Ови подаци се могу користити за [креирање профила у услузи Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Да бисмо користили сегмент у услузи Adobe Campaign Standard, морамо проширити шему профила у услузи Adobe Campaign Standard так ода укључује два додатна поља. Сазнајте како да [проширите ресурс профила](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) са новим пољима у услузи Adobe Campaign Standard.

У нашем примеру, ова поља су *Назив сегмента и Датум сегмента (опционално)*.

Ова поља ћемо користити за идентификацију профила у услузи Adobe Campaign Standard који желимо да циљамо за ову кампању.

Ако нема других записа у услузи Adobe Campaign Standard осим оног који ћете увести, можете прескочити овај корак.

## <a name="import-data-into-adobe-campaign-standard"></a>Увоз података у Adobe Campaign Standard

Сада када је све на свом месту, потребно је да увеземо припремљене податке корисници "Увиди купаца" у Adobe стандард кампање да бисмо креирали профиле. Сазнајте [како да увезете профиле у Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) користећи ток посла.

Ток посла увоза на слици испод конфигурисан је тако да ради сваких осам сати и тражи извезене сегменте увида купаца (.цсв датотека у Азуре складишту блоба). Ток посла издваја садржај .csv датотеке у наведеном редоследу колона. Овај ток посла је направљен да изврши основно руковање грешкама и да обезбеди да сваки запис има адресу е-поште пре него што унесе податке у Adobe Campaign Standard. Ток посла такође издваја назив сегмента из назива датотеке пре додавања у податке о Adobe Campaign Standard профилу.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Снимак екрана тока посла увоза у кориснички интерфејс услуге Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Преузимање циљне групе у услузи Adobe Campaign Standard

Када се подаци увезу у Adobe Campaign Standard, [можете креирати ток посла](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) и [поставити упит](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) клијентима на основу *назива сегмента* и *датума сегмента* да бисте изабрали профиле који су идентификовани за наш пример кампање.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Креирање и слање е-поште у услузи Adobe Campaign Standard

Креирајте садржај е-поруке, а затим [тестирајте и пошаљите](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) е-поруку.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Пример е-поруке са понудом за обнову из услуге Adobe Campaign Standard.":::
