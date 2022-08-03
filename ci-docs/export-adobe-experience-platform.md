---
title: Извоз сегмената у Adobe Experience Platform (преглед)
description: Сазнајте како да користите сегменте "Увид купца" у Adobe Experience Platform.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195308"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Извоз сегмената у Adobe Experience Platform (преглед)

Извези сегменте који циљају релевантне групе корисника локације у Adobe Experience Platform.

:::image type="content" source="media/AEP-flow.png" alt-text="Дијаграм процеса корака описаних у овом чланку.":::

## <a name="prerequisites"></a>Предуслови

- Дозвола Adobe Experience Platform.
- Лиценца Adobe за стандард кампање.
- Име [Азуре Блоб Стораге налога](/azure/storage/blobs/create-data-lake-storage-account) и кључ налога. Да бисте пронашли име и кључ, погледајте чланак Управљање [поставкама налога за складиштење на Азуре порталу](/azure/storage/common/storage-account-manage).
- Азуре [Блоб складишни контејнер](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

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

Конфигурисаћемо извоз из увида купаца у Азуре Блоб Стораге налог.

### <a name="set-up-connection-to-azure-blob-storage"></a>Подешавање везе са складиштем Азуре блоб

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Идите на **Администратор** > **Везе**.

1. Изаберите **Додај везу** и одаберите **Азуре складиште блоба**.

1. Дајте вези препознатљиво име у пољу **Име за приказ**. Име за приказ и врста везе описују ову везу. Препоручујемо да одаберете назив који објашњава сврху и циљ везе.

1. Одаберите ко може да користи ову везу. Подразумевано су то само администратори. За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Унесите **Назив налога**, **Кључ налога** и **Контејнер** за ваш налог за складиште блоб објекта у који желите да извезете сегмент.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Снимак екрана конфигурације налога складишта. ":::

1. Прегледајте приватност [и усаглашеност података и](connections.md#data-privacy-and-compliance) изаберите И **слажем се**.

1. Изаберите **Сачувај** да бисте креирали везу.

### <a name="configure-an-export"></a>Конфигурисање извоза

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Идите на **Подаци** > **Извози**.

1. Изаберите **Додај извоз**.

1. У пољу **Веза за извоз**, одаберите везу из одељка Azure складишта блоб објекта. Ако веза није доступна, обратите се администратору.

1. Унесите име за извоз.

1. Одаберите сегмент које желите да извезете. У овом примеру, то је **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Снимак екрана корисничког интерфејса за одабир сегмента са изабраним сегментом ChurnProneCustomers.":::

1. Изаберите **Сачувај**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Уверите се да је број записа у извезеном сегменту унутар дозвољеног ограничења ваше лиценце за услугу Adobe Campaign Standard.

Извезени подаци се складиште у контејнеру Азуре блоб складишта који сте конфигурисали. Следеће путање фасциклу се аутоматски креирају у вашем контејнеру:

- За изворне ентитете и ентитете које генерише систем:  

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- Датотека *model.json* за извезене ентитете налази се на нивоу *%ExportDestinationName%*.

  Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Дефинисање модел података о искуству (XDM) у услузи Adobe Experience Platform

Пре него што се извезени подаци из увида клијената могу користити у оквиру Adobe Experience Platform, дефинишите шему модела података искуства и конфигуришите податке [за профил купца у реалном времену](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Сазнајте [шта је то XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) и разјасните [основе састављања шеме](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Увоз података у услугу Adobe Experience Platform

Увезите припремљене корисници података из увида купаца у Adobe Experience Platform.

1. [Креирајте Азуре блоб стораге изворну везу](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).

1. [Конфигуришите ток података за](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) групну везу складишта у облаку да бисте увезли излаз сегмента из увида купаца у Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Креирање циљне групе у услузи Adobe Campaign Standard

Да бисмо послали е-пошту за ову кампању, користићемо услугу Adobe Campaign Standard.

1. [Креирајте корисници стандарду](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission)Adobe кампање користећи податке у програму Adobe Experience Platform.

1. [Користите израду сегмената](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html)Adobe у стандардној кампањи да бисте корисници на основу података у програму Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Креирање и слање е-поште у услузи Adobe Campaign Standard

Креирајте садржај е-поруке, а затим [тестирајте и пошаљите](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) е-поруку.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Пример е-поруке са понудом за обнову из услуге Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
