---
title: Извезите Customer Insights податке у Azure Data Lake Storage Gen2
description: Сазнајте како да конфигуришете везу са услугом Azure Data Lake Storage Gen2.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 934c396559d4c4be8e640917d2265805753eb62d
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 10/06/2021
ms.locfileid: "7605921"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>Извоз листе сегмената и других података у Azure Data Lake Storage Gen2 (верзија за преглед)

Складиштите податке из услуге Customer Insights у Data Lake Storage Gen2 налог или их користите за пренос података у друге апликације.

## <a name="known-limitations"></a>Позната ограничења

1. За Azure Data Lake Storage Gen2 можете бирати између [нивоа стандардних перформанси и премијум перформанси](/azure/storage/blobs/create-data-lake-storage-account) када креирате налог за складиштење за своје језеро података. Ако одаберете ниво премијум перформанси, изаберите премијум ове блоб објеката тип пословног контакта. 


## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Подешавање везе са Azure Data Lake Storage Gen2 


1. Идите на **Администратор** > **Везе**.

1. Изаберите **Додај везу** и бирајте **Azure Data Lake Gen 2** да бисте конфигурисали везу.

1. Дајте вези препознатљиво име у пољу **Име за приказ**. Име за приказ и врста везе описују ову везу. Препоручујемо да одаберете назив који објашњава сврху и циљ везе.

1. Одаберите ко може да користи ову везу. Ако ништа не предузмете, подразумевани ће бити Администратори. За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Унесите **Назив пословног контакта**, **Кључ пословног контакта** и **Контејнер** за ваш Azure Data Lake Storage Gen2.
    - Да бисте сазнали како да направите налог за складиштење са којим ћете користити Azure Data Lake Storage Gen2, погледајте чланак [Креирање налога за складиштење](/azure/storage/blobs/create-data-lake-storage-account). 
    - Да бисте сазнали више о називу налога Azure Data Lake Gen2 складишта и кључу складишта, погледајте [Управљање подешавањима налога за складиштење на Azure порталу](/azure/storage/common/storage-account-manage).

1. Изаберите **Сачувај** да бисте креирали везу. 

## <a name="configure-an-export"></a>Конфигурисање извоза

Овај извоз можете да конфигуришете ако имате приступ вези ове врсте. За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).

1. Идите на **Подаци** > **Извози**.

1. Да бисте креирали нови извоз, изаберите **Додај извоз**.

1. У пољу **Веза за извоз**, одаберите везу из одељка **Azure Data Lake**. Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.

1. Изаберите поље поред сваког ентитета који желите да извезете на ово одредиште.

1. Изаберите ставку **Сачувај**.

Чување извоза не покреће извоз одмах.

Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab). Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand). 

Извезени подаци се чувају у Azure Data Lake Gen 2 контејнеру за складиштење који сте конфигурисали. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
