---
title: Извезите Customer Insights податке у Azure складиште блоб објеката
description: Сазнајте како да конфигуришете везу са Azure складиштем блоб објеката.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 925b53260e7c633e17d7f172d2dd2d581e982e10
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667157"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Конектор за Azure складиште блоб објеката (преглед)

Ускладиштите Customer Insights податке у Azure складиште блоб објеката или их користите за пренос података у друге апликације.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Конфигурисање конектора за Azure складиште блоб објеката

1. У увидима о корисницима идите на **Администратор** > **Одредишта за извоз**.

1. У одељку **Azure складиште блоб објеката** изаберите **Подеси**.

1. Унесите **Назив налога**, **Кључ налога** и **Контејнер** за ваш налог за Azure складиште блоб објеката.
    - Да бисте сазнали више о проналажењу имена и кључа налога за Azure складиште блоб објекта, погледајте [Управљајте подешавањима налога за складиштење на Azure порталу](https://docs.microsoft.com/azure/storage/common/storage-account-manage).
    - Да бисте сазнали како да креирате контејнер, погледајте чланак [Креирање контејнера](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Дајте одредишту препознатљиво име у пољу **Име за приказ**.

1. Изаберите **Следеће**.

1. Изаберите поље поред сваког ентитета који желите да извезете на ово одредиште.

1. Изаберите ставку **Сачувај**.

Извезени подаци се чувају у контејнеру Azure складишта блоб објеката који сте конфигурисали. Следеће путање фасциклу се аутоматски креирају у вашем контејнеру:

- За изворне ентитете и ентитете које генерише систем: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Пример: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Model.json за извезене ентитете ће се налази на нивоу %ExportDestinationName%
  - Пример: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Извоз података

Можете да [извезете податке на захтев](/export-destinations.md#export-data-on-demand). Извоз ће се такође покренути са сваким [планираним освежавањем](system.md#schedule-tab).
