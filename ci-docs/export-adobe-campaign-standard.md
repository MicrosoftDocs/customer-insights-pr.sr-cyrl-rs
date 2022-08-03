---
title: Извоз сегмената увида купаца у Adobe стандард кампање (преглед)
description: Сазнајте како да користите сегменте "Увиди купаца" у стандардној Adobe кампањи.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195538"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Извоз сегмената увида купаца у Adobe стандард кампање (преглед)

Извезите сегменте који циљају релевантне групе корисника локације Adobe у стандард кампање.

:::image type="content" source="media/ACS-flow.png" alt-text="Дијаграм процеса корака описаних у овом чланку.":::

## <a name="prerequisites"></a>Предуслови

- Лиценца Adobe за стандард кампање.
- Име [Азуре Блоб Стораге налога](/azure/storage/blobs/create-data-lake-storage-account) и кључ налога. Да бисте пронашли име и кључ, погледајте чланак Управљање [поставкама налога за складиштење на Азуре порталу](/azure/storage/common/storage-account-manage).
- Азуре [Блоб складишни контејнер](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Преглед кампање

Да бисмо боље разумели како можете да користите сегменте из "Увида купаца" Adobe Experience Platform у, погледајмо фиктивну пробну кампању.

Претпоставимо да ваше предузеће нуди месечну услугу засновану на претплати за клијенте у Сједињеним Државама. Желите да идентификујете клијенте који треба да обнове претплате у наредних осам дана, али још увек нису обновили претплату. Да бисте задржали ове клијенте, треба да им пошаљете промотивну понуду путем е-поште користећи Adobe Campaign Standard.

У овом примеру желимо да једном покренемо промотивну кампању е-поште. Овај чланак не покрива случај коришћења са више покретања кампање. Међутим, увиди клијената и Adobe стандард кампање могу да се конфигуришу тако да раде и за периодични сценарио кампање.

## <a name="identify-your-target-audience"></a>Идентификујте своју циљну групу

У нашем сценарију, претпостављамо да су е-адресе клијената доступне у увидима клијената и да су њихове промотивне преференције анализиране како би се идентификовали чланови сегмента.

Сегмент [који сте дефинисали у "Увидима купаца"](segments.md) зове се **ЦхурнПронеЦустомерс и планирате** да овим корисницима пошаљете промоцију е-поште.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Снимак екрана странице сегмената са креираним сегментом ChurnProneCustomers.":::

Е-порука са понудом коју желите да пошаљете садржи име, презиме и датум завршетка претплате клијента. Порука обавештава клијенте о попусту који ће добити ако обнове претплату пре него што се заврши.

## <a name="export-your-target-audience"></a>Извезите своју циљну групу

### <a name="set-up-connection-to-adobe-campaign"></a>Подешавање везе са кампањом Adobe

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Идите на **Администратор** > **Везе**.

1. Изаберите **додај везу и** одаберите ставку **Adobe Кампања**.

1. Дајте вези препознатљиво име у пољу **Име за приказ**. Име за приказ и врста везе описују ову везу. Препоручујемо да одаберете назив који објашњава сврху и циљ везе.

1. Одаберите ко може да користи ову везу. Подразумевано су то само администратори. За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Унесите **име налога**, **кључ налога** и контејнер **за** налог за складиштење блоба.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Снимак екрана конфигурације налога складишта. ":::

1. Прегледајте приватност [и усаглашеност података и](connections.md#data-privacy-and-compliance) изаберите И **слажем се**.

1. Изаберите **Сачувај** да бисте креирали везу.

### <a name="configure-an-export"></a>Конфигурисање извоза

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Идите на **Подаци** > **Извози**.

1. Изаберите **Додај извоз**.

1. У пољу **Веза за извоз**, одаберите везу из одељка Adobe Campaign. Ако веза није доступна, обратите се администратору.

1. Унесите име за извоз.

1. Одаберите сегмент које желите да извезете. У овом примеру, то је **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Снимак екрана корисничког интерфејса за одабир сегмента са изабраним сегментом ChurnProneCustomers.":::

1. Изаберите **Следеће**.

1. Мапирај **поља** Извор из сегмента"Увиди купаца" у **имена** поља "Циљ" у шеми Adobe профила стандардне кампање.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Мапирање поља за Adobe Campaign Standard конектор.":::

   Ако желите да додате још атрибута, изаберите **Додај атрибут**. Циљно име се може разликовати од имена изворног поља тако да и даље можете мапирати излаз сегмента из "Увиди купаца Adobe " у стандард кампање ако поља немају исто име у два система.

   > [!NOTE]
   > Е -адреса се користи као поље идентитета, али можете да користите било који други идентификатор из профила клијента да бисте мапирали податке у стандард Adobe кампање.

1. Изаберите **Сачувај**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Уверите се да је број записа у извезеном сегменту унутар дозвољеног ограничења ваше лиценце за услугу Adobe Campaign Standard.

Извезени подаци се чувају у контејнеру Azure складишта блоб објекта који сте раније конфигурисали. У контејнеру се аутоматски креира следећа путања фасцикле: *%ContainerName% /CustomerInsights_ %instanceID% /% еxпортдестинатион-наме% _%segmentname%_%timestamp% .цсв*

Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Конфигурисање услуге Adobe Campaign Standard

Извезени сегменти садрже колоне које сте изабрали приликом конфигурисања извоза. Ови подаци се могу користити за [креирање профила у услузи Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Да бисте користили сегмент у стандардној Adobe кампањи, проширите [шему профила у стандардној](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing)Adobe кампањи да бисте укључили два додатна поља.

У нашем примеру, ова поља су име сегмента и датум сегмента. Ова поља ћемо користити за идентификацију профила у услузи Adobe Campaign Standard који желимо да циљамо за ову кампању.

Ако у стандардној кампањи нема других Adobe записа, осим онога што ћете увести, прескочите овај корак.

## <a name="import-data-into-adobe-campaign-standard"></a>Увоз података у Adobe Campaign Standard

Увезите припремљене корисници из увида клијената у Adobe стандард кампање да бисте креирали [профиле помоћу тока посла](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).

Ток посла увоза на слици испод конфигурисан је тако да ради сваких осам сати и тражи извезене сегменте увида купаца (.цсв датотека у Азуре складишту блоба). Ток посла издваја садржај .csv датотеке у наведеном редоследу колона. Овај ток посла је направљен да изврши основно руковање грешкама и да обезбеди да сваки запис има адресу е-поште пре него што унесе податке у Adobe Campaign Standard. Ток посла такође издваја назив сегмента из назива датотеке пре додавања у податке о Adobe Campaign Standard профилу.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Снимак екрана тока посла увоза у кориснички интерфејс услуге Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Преузимање циљне групе у услузи Adobe Campaign Standard

Када се подаци увезу у стандард кампање, креирајте Adobe [ток](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) посла и [испитате купце](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) на основу имена сегмента и датума сегмента да бисте изабрали профиле који су идентификовани за нашу пробну кампању.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Креирање и слање е-поште у услузи Adobe Campaign Standard

Креирајте садржај е-поруке, а затим [тестирајте и пошаљите](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) е-поруку.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Пример е-поруке са понудом за обнову из услуге Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
