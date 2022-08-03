---
title: Извези податке о увидима купаца у ИнМоби
description: Сазнајте како да конфигуришете везу и извезете у ИнМоби.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195906"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Извези податке о увидима клијената у ИнМоби (преглед)

Извезите листе сегмената или друге податке из инстанце "Увиди купаца" [у ИнМоби](https://www.inmobi.com/).

## <a name="prerequisites"></a>Предуслови

- ИнМоби [налог и](https://www.inmobi.com/) административни акредитиви.
- Име [Азуре Блоб Стораге налога](/azure/storage/blobs/create-data-lake-storage-account) и кључ налога. Да бисте пронашли име и кључ, погледајте чланак Управљање [поставкама налога за складиштење на Азуре порталу](/azure/storage/common/storage-account-manage).
- Азуре [Блоб Стораге контејнер у који ћете](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) извозити ИнМоби податке.
- ИнМоби ће креирати директну везу са вашим Блоб складиштем и конфигурисати аутоматски увоз ваших података у ИнМоби. Обратите се представнику ИнМобија да покренете процес.

## <a name="known-limitations"></a>Позната ограничења

- За Азуре Блоб Стораге одаберите између стандардних [перформанси и премиум перформанси](/azure/storage/blobs/storage-blob-performance-tiers). Ако одаберете ниво премијум перформанси, изаберите [премијум ове блоб објеката тип пословног контакта](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>Подешавање везе са складиштем Азуре блоб

[Подесите везу са Азуре складиштем блоба](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>Конфигурисање извоза

[Конфигуришите извоз](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
