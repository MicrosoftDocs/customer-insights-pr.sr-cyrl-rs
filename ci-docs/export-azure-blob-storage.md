---
title: Извоз Customer Insights података у Azure складиште блоб објекта
description: Сазнајте како да конфигуришете везу и извезете садржај у складиште блоб објекта.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 42095f369c47553e5ddf5fada54e559202c943a9
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643431"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Извоз листе сегмената и других података у Azure складиште блоб објекта (преглед)

Складиштите Customer Insights податке у складиште блоб објекта или их користите за пренос података у друге апликације.

## <a name="known-limitations"></a>Позната ограничења

1. За складиште Azure блоб објекта можете бирати између [нивоа стандардних перформанси и премијум перформанси](/azure/storage/blobs/storage-blob-performance-tiers). Ако одаберете ниво премијум перформанси, изаберите [премијум ове блоб објеката тип пословног контакта](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-blob-storage"></a>Подесите везу са складиштем блоб објекта

1. Идите на **Администратор** > **Везе**.

1. Изаберите **Додај везу** и бирајте **Azure складиште блоб објекта** да бисте конфигурисали везу.

1. Дајте вези препознатљиво име у пољу **Име за приказ**. Име за приказ и врста везе описују ову везу. Препоручујемо да одаберете назив који објашњава сврху и циљ везе.

1. Одаберите ко може да користи ову везу. Ако ништа не предузмете, подразумевани ће бити Администратори. За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Унесите **Назив налога**, **Кључ налога** и **Контејнер** за свој налог складишта блоб објекта.
    - Да бисте сазнали више о томе како да пронађете назив налога складишта блоб објекта и кључ налога, погледајте [Управљање подешавањима налога за складиштење на Azure порталу](/azure/storage/common/storage-account-manage).
    - Да бисте сазнали како да креирате контејнер, погледајте чланак [Креирање контејнера](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Изаберите **Сачувај** да бисте креирали везу. 

## <a name="configure-an-export"></a>Конфигурисање извоза

Овај извоз можете да конфигуришете ако имате приступ вези ове врсте. За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> Ако сте укључили подешавање меког брисања за налог Azure складишта блоб објекта, извоз неће успети. Искључите меко брисање за извоз података у блоб објекте. За више информација погледајте [Омогућавање меког брисања блоб објеката](/azure/storage/blobs/soft-delete-blob-enable.md)

1. Идите на **Подаци** > **Извози**.

1. Да бисте креирали нови извоз, изаберите **Додај одредиште**.

1. У пољу **Веза за извоз**, одаберите везу из одељка Azure складишта блоб објекта. Ако не видите назив овог одељка, тада вам нису доступне везе овог типа.

1. Изаберите поље поред сваког ентитета који желите да извезете на ово одредиште.

1. Изаберите ставку **Сачувај**.

Чување извоза не покреће извоз одмах.

Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab).     

Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand). 

Извезени подаци се чувају у контејнеру складишта блоб објекта који сте конфигурисали. Следеће путање фасциклу се аутоматски креирају у вашем контејнеру:

- За изворне ентитете и ентитете које генерише систем:   
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - Пример: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
 
- Датотека model.json за извезене ентитете биће на нивоу %ExportDestinationName%.  
  - Пример: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE [footer-include](includes/footer-banner.md)]
