---
title: Планирање освежавања система
description: Планирање времена освежавања система
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: ce10fcfe9906d33209270f8f6930a51b045b13e2
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246437"
---
# <a name="schedule-system-refresh"></a>Планирање освежавања система

Планирајте аутоматско освежавање свих [нанетих извора података](data-sources.md). Аутоматско освежавање осигурава да се исправке из извора података приказују на обједињеним профилима корисника.

> [!NOTE]
> Power Query изворе података којима управљате освежавате по сопственим распоредима. Да бисте испланирали освежавање Power Query ових извора података, конфигуришите поставке освежавања на извор података страници **извора података**.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Поставке освежавања датафлоw-а.":::

## <a name="set-system-refresh-schedule"></a>Подешавање распореда освежавања система

1. Идите на **администраторски** > **систем и** изаберите картицу **"Распоред** ".

   :::image type="content" source="media/schedule_refresh.png" alt-text="Планирање картице&quot;Освежавање&quot; са странице &quot;Систем&quot;.":::

1. Подразумевано стање за планирано освежавање је **Искључено**. Да бисте омогућили планирана освежавања, промените преклопник на врху екрана на **Укључено**.

1. Изаберите између **Недељног** (подразумевано) и **Свакодневног** освежавања. Ако намеравате да закажете недељно освежавање, изаберите један или више дана у којима желите да покренете освежавање.

1. Подесите **временску зону**, а затим помоћу падајућег менија **Време** подесите време освежавања. Ако желите да закажете више освежавања у једном дану, изаберите **Додај друго време**.

1. Изаберите **Сачувај** да примените промене.

[!INCLUDE [footer-include](includes/footer-banner.md)]
