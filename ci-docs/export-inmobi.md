---
title: Извези податке о увидима купаца у ИнМоби
description: Сазнајте како да конфигуришете везу и извезете у ИнМоби.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9059618"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Извоз листе сегмената и других података у ИнМоби (преглед)

Извезите листе сегмената или друге податке из инстанце "Увиди купаца" [у ИнМоби](https://www.inmobi.com/).

## <a name="prerequisites"></a>Предуслови

1. Имате [ИнМоби налог и](https://www.inmobi.com/) административне акредитиве.
1. Имате име Азуре Блоб налога за складиштење и одговарајући кључ налога. Више информација потражите у чланку [Управљање поставкама налога за складиштење на Азуре порталу](/azure/storage/common/storage-account-manage). Постоји контејнер на рачуну за складиштење у који треба извести ИнМоби податке. Више информација потражите у чланку [Креирање контејнера](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. ИнМоби ће креирати директну везу са вашим Блоб складиштем и конфигурисати аутоматски увоз ваших података у ИнМоби. Обратите се представнику ИнМобија да покренете процес.

## <a name="known-limitations"></a>Позната ограничења

1. За Азуре складиште блоба можете бирати између стандардних [перформанси и премиум перформанси](/azure/storage/blobs/storage-blob-performance-tiers). Ако одаберете ниво премијум перформанси, изаберите [премијум ове блоб објеката тип пословног контакта](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Подешавање везе са Азуре складиштем блоба и конфигурисање извоза

1. Следите упутства да [бисте подешавању везе са складиштем Азуре блоба](export-azure-blob-storage.md).
2. Следите упутства да бисте [конфигурисали извоз](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
