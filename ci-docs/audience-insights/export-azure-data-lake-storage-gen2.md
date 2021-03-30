---
title: Извезите Customer Insights податке у Azure Data Lake Storage Gen2
description: Сазнајте како да конфигуришете везу са услугом Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596657"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Конектор за Azure Data Lake Storage Gen2 (преглед)

Складиштите податке Customer Insights података у услугу Azure Data Lake Storage Gen2 или их користите за пренос података у друге апликације.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Конфигуришите конектор за Azure Data Lake Storage Gen2

1. У увидима о корисницима идите на **Администратор** > **Одредишта за извоз**.

1. Уз одељку **Azure Data Lake Storage Gen2** изаберите **Подеси**.

1. Дајте одредишту препознатљиво име у пољу **Име за приказ**.

1. Унесите **Назив пословног контакта**, **Кључ пословног контакта** и **Контејнер** за ваш Azure Data Lake Storage Gen2.
    - Да бисте сазнали како да направите налог за складиштење са којим ћете користити Azure Data Lake Storage Gen2, погледајте чланак [Креирање налога за складиштење](/azure/storage/blobs/create-data-lake-storage-account). 
    - Да бисте сазнали више о томе како да пронађете име пословног контакта за Azure Data Lake Gen2 складиште, погледајте чланак [Управљање подешавањима налога за складиштење на Azure порталу](/azure/storage/common/storage-account-manage).

1. Изаберите **Следеће**.

1. Изаберите поље поред сваког ентитета који желите да извезете на ово одредиште.

1. Изаберите ставку **Сачувај**.

## <a name="export-the-data"></a>Извоз података

Можете да [извезете податке на захтев](export-destinations.md#export-data-on-demand). Извоз ће се такође покренути са сваким [планираним освежавањем](system.md#schedule-tab).