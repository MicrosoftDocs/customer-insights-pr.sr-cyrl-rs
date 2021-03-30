---
title: Извезите Customer Insights податке у Dynamics 365 Sales
description: Сазнајте како да конфигуришете везу са услугом Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598127"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Конектор за Dynamics 365 Sales (преглед)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Користите податке о клијентима да бисте креирали маркетиншке спискове, пратили токове посла и слали промоције са услугом Dynamics 365 Sales.

## <a name="prerequisite"></a>Предуслов

1. Записи контаката морају бити присутни у услузи Dynamics 365 Sales да бисте могли да извезете сегмент из услуге Customer Insights у Sales. Прочитајте више о томе како се уносе контакти у [Dynamics 365 Sales помоћу услуге Common Data Services](connect-power-query.md).

   > [!NOTE]
   > Извоз сегмената из увида о корисницима у Sales неће креирати нове записе контаката у инстанцама услуге Sales. Евиденција контаката из услуге Sales мора се унети у увид о корисницима и користити као извор података. Такође их треба укључити у јединствени ентитет клијента да би се ID-ови клијената мапирали у ID-ове контаката да би сегменти могли да се извезу.

## <a name="configure-the-connector-for-sales"></a>Конфигуришите конектор за Sales

1. У увидима о корисницима идите на **Администратор** > **Одредишта за извоз**.

1. У одељку **Dynamics 365 Sales** изаберите **Подеси**.

1. Дајте одредишту за извоз препознатљиво име у пољу **Име за приказ**.

1. Унесите URL организације за Sales у поље **Адреса сервера**.

1. У одељку **Администраторски налог на серверу**, изаберите **Пријавите се** и изаберите Dynamics 365 Sales налог.

1. Мапирајте поље корисничког ID-а са Dynamics 365 ID-ом контакта.

1. Изаберите **Следеће**.

1. Изаберите један или више сегмената.

1. Изаберите ставку **Сачувај**.

## <a name="export-the-data"></a>Извоз података

Можете да [извезете податке на захтев](export-destinations.md). Извоз ће се такође покренути са сваким [планираним освежавањем](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]