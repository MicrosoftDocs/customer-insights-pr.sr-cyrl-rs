---
title: Извоз сегмената у Adobe Experience Platform (преглед)
description: Сазнајте како да користите сегменте "Увид купца" у Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: c29b8264019669ffd954a298ce3a633c852477fa
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052529"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Извоз сегмената у Adobe Experience Platform (преглед)

Као корисник, можда Dynamics 365 Customer Insights сте креирали сегменте да бисте маркетиншке кампање били ефикаснији циљањем релевантних корисника локације. Да бисте користили сегмент из увида клијената у и Adobe Experience Platform апликације као што је Adobe Стандард кампање, потребно је да следите неколико корака наведених у овом чланку.

:::image type="content" source="media/AEP-flow.png" alt-text="Дијаграм процеса корака описаних у овом чланку.":::

## <a name="prerequisites"></a>Предуслови

-   Dynamics 365 Customer Insights лиценца
-   Adobe Experience Platform лиценца
-   Лиценца за Adobe Campaign Standard
-   Налог Azure складишта блоб објекта

## <a name="campaign-overview"></a>Преглед кампање

Да бисмо боље разумели како можете да користите сегменте из "Увида купаца" Adobe Experience Platform у, погледајмо фиктивну пробну кампању.

Претпоставимо да ваше предузеће нуди месечну услугу засновану на претплати за клијенте у Сједињеним Државама. Желите да идентификујете клијенте који треба да обнове претплате у наредних осам дана, али још увек нису обновили претплату. Да бисте задржали ове клијенте, треба да им пошаљете промотивну понуду путем е-поште користећи Adobe Experience Platform.

У овом примеру желимо да једном покренемо промотивну кампању е-поште. Овај чланак не покрива случај коришћења са више покретања кампање.

## <a name="identify-your-target-audience"></a>Идентификујте своју циљну групу

У нашем сценарију, претпостављамо да су е-адресе клијената доступне у увидима клијената и да су њихове промотивне преференције анализиране како би се идентификовали чланови сегмента.

Сегмент [који сте дефинисали у "Увидима купаца"](segments.md) зове се **ЦхурнПронеЦустомерс и планирате** да овим корисницима пошаљете промоцију е-поште.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Снимак екрана странице сегмената са креираним сегментом ChurnProneCustomers.":::

Е-порука са понудом коју желите да пошаљете садржи име, презиме и датум завршетка претплате клијента. Порука обавештава клијенте о попусту који ће добити ако обнове претплату пре него што се заврши.

## <a name="export-your-target-audience"></a>Извезите своју циљну групу

Са идентификованим циљним корисници, можемо да конфигуришемо извоз из увида купаца у Азуре Блоб Стораге налог.

### <a name="configure-a-connection"></a>Конфигурисање везе

1. Идите на **Администратор** > **Везе**.

1. Изаберите **Додај везу** и бирајте **Azure складиште блоб објекта** или изаберите **Подеси** на плочици **Azure складиште блоб објекта** да бисте конфигурисали везу.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Плочица за конфигурацију за Azure складиште блоб објекта."::: 

1. Дајте вези препознатљиво име у пољу **Име за приказ**. Име за приказ и врста везе описују ову везу. Препоручујемо да одаберете назив који објашњава сврху и циљ везе.

1. Одаберите ко може да користи ову везу. Ако ништа не предузмете, подразумевани ће бити Администратори. За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Унесите **Назив налога**, **Кључ налога** и **Контејнер** за ваш налог за складиште блоб објекта у који желите да извезете сегмент.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Снимак екрана конфигурације налога складишта. "::: 
   
    - Да бисте сазнали више о томе како да пронађете назив налога складишта блоб објекта и кључ налога, погледајте [Управљање подешавањима налога за складиштење на Azure порталу](/azure/storage/common/storage-account-manage).
    - Да бисте сазнали како да креирате контејнер, погледајте чланак [Креирање контејнера](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Изаберите **Сачувај** да бисте креирали везу. 

### <a name="configure-an-export"></a>Конфигурисање извоза

Овај извоз можете да конфигуришете ако имате приступ вези ове врсте. За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).

1. Идите на **Подаци** > **Извози**.

1. Да бисте креирали нови извоз, изаберите **Додај извоз**.

1. У пољу **Веза за извоз**, одаберите везу из одељка Azure складишта блоб објекта. Ако не видите назив овог одељка, тада вам нису доступне везе овог типа.

1. Одаберите сегмент које желите да извезете. У овом примеру, то је **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Снимак екрана корисничког интерфејса за одабир сегмента са изабраним сегментом ChurnProneCustomers.":::

1. Изаберите ставку **Сачувај**.

Када сачувате одредиште за извоз, пронаћи ћете га у дијалогу **Подаци** > **Извози**.

Сада можете да [извозите сегмент на захтев](export-destinations.md#run-exports-on-demand). Извоз ће се такође покренути са сваким [планираним освежавањем](system.md).

> [!NOTE]
> Уверите се да је број записа у извезеном сегменту унутар дозвољеног ограничења ваше лиценце за услугу Adobe Campaign Standard.

Извезени подаци се чувају у контејнеру Azure складишта блоб објекта који сте раније конфигурисали. Следећа путања до фасцикле се аутоматски креира у вашем контејнеру:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

Датотека *model.json* за извезене ентитете налази се на нивоу *%ExportDestinationName%*.

Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Дефинисање модел података о искуству (XDM) у услузи Adobe Experience Platform

Да би извезени подаци из увида клијената могли да се користе у оквиру Adobe Experience Platform програма, потребно је да дефинишемо шему модела података "Еxпериенце" и конфигуришемо податке [за профил купца у реалном времену](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Сазнајте [шта је то XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) и разјасните [основе састављања шеме](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Увоз података у услугу Adobe Experience Platform

Сада када је све на свом месту, морамо да увеземо припремљене корисници податке из Увида купаца у Adobe Experience Platform.

Прво [креирајте изворну везу са Azure складиштем блоб објекта](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Након дефинисања изворне везе, конфигуришите [ток података за](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) везу групе складишта у облаку да бисте увезли излаз сегмента из увида купца у Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Креирање циљне групе у услузи Adobe Campaign Standard

Да бисмо послали е-пошту за ову кампању, користићемо услугу Adobe Campaign Standard. Након увоза података у Adobe Experience Platform, треба да [направимо циљну групу](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) у услузи Adobe Campaign Standard користећи податке у услузи Adobe Experience Platform.


Сазнајте како да [користите алатку за креирање сегмената](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) у услузи Adobe Campaign Standard да бисте дефинисали циљну групу на основу података у услузи Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Креирање и слање е-поште у услузи Adobe Campaign Standard

Креирајте садржај е-поруке, а затим [тестирајте и пошаљите](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) е-поруку.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Пример е-поруке са понудом за обнову из услуге Adobe Campaign Standard.":::
