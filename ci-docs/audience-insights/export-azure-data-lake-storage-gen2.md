---
title: Извезите Customer Insights податке у Azure Data Lake Storage Gen2
description: Сазнајте како да конфигуришете везу са услугом Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760069"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a>Подешавање везе са апликацијом Azure Data Lake Storage Gen2 (верзија за преглед)

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
