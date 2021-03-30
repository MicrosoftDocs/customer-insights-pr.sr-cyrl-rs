---
title: Извоз Customer Insights података у Adobe платформу искуства
description: Сазнајте како се користе сегменти увида о корисницима у Adobe платформи искуства.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596287"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Коришћење Customer Insights сегмената у Adobe платформи искуства (верзија за преглед)

Као корисник увида о корисницима за Dynamics 365 Customer Insights, можда сте креирали сегменте да бисте маркетиншке кампање учинили ефикаснијим тако што ћете циљати релевантне циљне групе. Да бисте користили сегмент из увида о корисницима у Adobe платформи искуства и апликацијама попут Adobe Campaign Standard, потребно је да следите неколико корака наведених у овом чланку.

:::image type="content" source="media/AEP-flow.png" alt-text="Дијаграм процеса корака описаних у овом чланку.":::

## <a name="prerequisites"></a>Предуслови

-   Dynamics 365 Customer Insights лиценца
-   Лиценца за Adobe платформу искуства
-   Лиценца за Adobe Campaign Standard
-   Налог Azure складишта блоб објекта

## <a name="campaign-overview"></a>Преглед кампање

Да бисте боље разумели како можете да користите сегменте из увида о корисницима у Adobe платформи искуства, погледајмо фиктивни пример кампање.

Претпоставимо да ваше предузеће нуди месечну услугу засновану на претплати за клијенте у Сједињеним Државама. Желите да идентификујете клијенте који треба да обнове претплате у наредних осам дана, али још увек нису обновили претплату. Да бисте задржали ове клијенте, треба да им пошаљете промотивну понуду путем е-поште, користећи Adobe платформу искуства.

У овом примеру желимо да једном покренемо промотивну кампању е-поште. Овај чланак не покрива случај коришћења са више покретања кампање.

## <a name="identify-your-target-audience"></a>Идентификујте своју циљну групу

У нашем сценариј,у претпостављамо да су адресе е-поште клијената доступне у увидима о корисницима и да су анализиране њихове промотивне жељене опције како би се идентификовали чланови сегмента.

[Сегмент који сте дефинисали увидом о корисницима](segments.md) се зове **ChurnProneCustomers** и планирате да овим клијентима пошаљете е-поруку са промоцијом.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Снимак екрана странице сегмената са креираним сегментом ChurnProneCustomers.":::

Е-порука са понудом коју желите да пошаљете садржи име, презиме и датум завршетка претплате клијента. Порука обавештава клијенте о попусту који ће добити ако обнове претплату пре него што се заврши.

## <a name="export-your-target-audience"></a>Извезите своју циљну групу

Када је идентификована циљна група, можемо да конфигуришемо извоз из увида о корисницима на налог Azure складишта блоб објекта.

1. У увидима о корисницима идите на **Администратор** > **Одредишта за извоз**.

1. На плочици **Azure складиште блоб објекта** изаберите **Подеси**.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Плочица за конфигурацију за Azure складиште блоб објекта.":::

1. Наведите **име за приказ** за ово ново одредиште за извоз, а затим унесите **Назив налога**, **Кључ налога** и **Контејнер** налога Azure складишта блоб објекта у који желите да извезете сегмент.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Снимак екрана конфигурације налога складишта. "::: 

   - Да бисте сазнали више о проналажењу имена и кључа налога за Azure складиште блоб објекта, погледајте [Управљајте подешавањима налога за складиштење на Azure порталу](/azure/storage/common/storage-account-manage).

   - Да бисте сазнали како да креирате контејнер, погледајте чланак [Креирање контејнера](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Изаберите **Следеће**.

1. Одаберите сегмент које желите да извезете. У овом примеру, то је **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Снимак екрана корисничког интерфејса за одабир сегмента са изабраним сегментом ChurnProneCustomers.":::

1. Изаберите ставку **Сачувај**.

Када сачувате одредиште за извоз, пронаћи ћете га на листи **Администратор** > **Извози** > **Моја одредишта за извоз**.

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Снимак екрана са истакнутом листом извоза и узорком сегмента.":::

Сада можете да [извозите сегмент на захтев](export-destinations.md#export-data-on-demand). Извоз ће се такође покренути са сваким [планираним освежавањем](system.md).

> [!NOTE]
> Уверите се да је број записа у извезеном сегменту унутар дозвољеног ограничења ваше Adobe Campaign Standard лиценце.

Извезени подаци се чувају у контејнеру Azure складишта блоб објекта који сте раније конфигурисали. Следећа путања до фасцикле се аутоматски креира у вашем контејнеру:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

Датотека *model.json* за извезене ентитете налази се на нивоу *%ExportDestinationName%*.

Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Дефинишите модел података о искуству (XDM) на Adobe платформи искуства

Пре него што будемо могли да користимо извезене податке из увида о корисницима на Adobe платформи искуства, морамо да дефинишемо шему модела података искуства и [конфигуришемо податке за профил клијента у реалном времену](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Сазнајте [шта је то XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) и разјасните [основе састављања шеме](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Увезите податке у Adobe платформу искуства

Сада када је све на свом месту, треба да увеземо податке о циљној групи из увида о корисницима у Adobe платформи искуства.

Прво [креирајте изворну везу са Azure складиштем блоб објекта](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Када дефинишете изворну везу, [конфигуришите ток података](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) за групно повезивање са складиштем у облаку ради увоза излаза сегмента из увида о корисницима у Adobe платформу искуства.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Креирање корисника у услузи Adobe Campaign Standard

Да бисмо послали е-поруку за ову кампању, користићемо Adobe Campaign Standard. Након увоза података у Adobe платформу искуства, треба да [креирамо циљну групу](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) у услузи Adobe Campaign Standard користећи податке на Adobe платформи искуства.

Сазнајте како да [користите алатку за прављење сегмената](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) у услузи Adobe Campaign Standard да бисте дефинисали циљну групу на основу података у Adobe платформи искуства.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Креирајте и пошаљите е-поруку користећи Adobe Campaign Standard

Креирајте садржај е-поруке, а затим [тестирајте и пошаљите](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) е-поруку.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Пример е-поруке са понудом обнове претплате из услуге Adobe Campaign Standard.":::