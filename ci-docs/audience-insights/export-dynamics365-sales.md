---
title: Извезите Customer Insights податке у Dynamics 365 Sales
description: Сазнајте како да конфигуришете везу са услугом Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643836"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Конектор за Dynamics 365 Sales (преглед)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Користите податке о клијентима да бисте креирали маркетиншке спискове, пратили токове посла и слали промоције са услугом Dynamics 365 Sales.

## <a name="prerequisite"></a>Предуслов

Записи контаката [из Dynamics 365 Sales унетих помоћу услуге Common Data Service](connect-power-query.md).

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
