---
title: Power Apps конектор
description: Повежите се са услугама Power Apps и Power Automate.
ms.date: 08/21/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b6ec103e29e218b2f27bfc1193300ea793a6b30b
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406835"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps конектор (преглед)

Уведите обједињене корисничке профиле у своје персонализоване апликације помоћу програма Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Повежите Power Apps и Dynamics 365 Customer Insights

Customer Insights је један од многих [доступних извора за податке у програму Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).

Погледајте Power Apps документацију да бисте сазнали како да [додате пренос података у апликацију](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection). Препоручујемо да такође прегледате [како Power Apps користи делегирање за обраду великих скупова података у апликацијама са подлогом](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Доступни ентитети

Када додате услугу Customer Insights као везу за пренос података, можете изабрати следеће ентитете у програму Power Apps:

- Клијент: да користите податке из [обједињеног профила клијента](customer-profiles.md).
- Активност обједињеног клијента: да приказујете [временску осу активности](activities.md) у апликацији.

## <a name="limitations"></a>Ограничења

### <a name="retrievable-entities"></a>Повратни ентитети

Можете да повратите само ентитете **Клијент**, **Обједињена активност** и **Сегменти** кроз Power Apps конектор. Други ентитети се приказују јер их основни конектор подржава кроз окидаче у услузи Power Automate.  

### <a name="delegation"></a>Делегирање

Делегирање ради за ентитет Клијент и ентитет Обједињена активност. 

- Делегирање за ентитет **Клијент**: Да бисте користили делегирање за овај ентитет, поља треба индексирати у одељку [Индекс претраге и филтрирања](search-filter-index.md).  

- Делегирање за ентитет **Обједињена активност**: Делегирање за овај ентитет ради само за поља **ActivityId** и **CustomerId**.  

- За више информација о делегирању, погледајте [Power Apps преносиве функције и операције](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Пример контроле галерије

На пример, додајете профиле клијената у [контролу галерије](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).

1. Додајте контролу **Галерија** у апликацију коју градите.

> [!div class="mx-imgBorder"]
> ![Додајте елемент галерије](media/connector-powerapps9.png "Додајте елемент галерије")

1. Изаберите **Клијент** као извор података за ставке.

    > [!div class="mx-imgBorder"]
    > ![Изаберите извор података](media/choose-datasource-powerapps.png "Изаберите извор података")

1. Можете да промените таблу са подацима на десној страни да бисте изабрали поље које ће ентитет Клијент приказати у галерији.

1. Ако желите да у галерији прикажете било које поље одабраног клијента, попуните својство Текст ознаке: **{Name_of_the_gallery}.Selected.{property_name}**

    Пример: Gallery1.Selected.address1_city

1. Да бисте приказали обједињену временску осу за клијента, додајте елемент Галерија и додајте својство Ставке: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Пример: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)
