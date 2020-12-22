---
title: Извезите Customer Insights податке у Dynamics 365 Marketing
description: Сазнајте како да конфигуришете везу са услугом Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643791"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Конектор за Dynamics 365 Marketing (преглед)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Користите [сегменте](segments.md) да бисте генерисали кампање и контактирали одређене групе клијената помоћу услуге Dynamics 365 Marketing. Више информација потражите у чланку [Коришћење сегмената из услуга Dynamics 365 Customer Insights уз Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Предуслов

Записи контаката [из Dynamics 365 Marketing унети помоћу услуге Common Data Service](connect-power-query.md).

## <a name="configure-the-connector-for-marketing"></a>Конфигуришите конектор за Marketing

1. У увидима о корисницима идите на **Администратор** > **Одредишта за извоз**.

1. У одељку **Dynamics 365 Marketing** изаберите **Подеси**.

1. Дајте одредишту за извоз препознатљиво име у пољу **Име за приказ**.

1. Унесите URL организације за Marketing у поље **Адреса сервера**.

1. У одељку **Администраторски налог на серверу**, изаберите **Пријавите се** и изаберите Dynamics 365 Marketing налог.

1. Мапирајте поље корисничког ID-а са Dynamics 365 ID-ом контакта.

1. Изаберите **Следеће**.

1. Изаберите један или више сегмената.

1. Изаберите ставку **Сачувај**.

## <a name="export-the-data"></a>Извоз података

Можете да [извезете податке на захтев](export-destinations.md). Извоз ће се такође покренути са сваким [планираним освежавањем](system.md#schedule-tab).
