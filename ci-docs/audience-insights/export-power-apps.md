---
title: Power Apps конектор
description: Повежите се са услугама Power Apps и Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: fc0af656cd5b436d9efd65b2a2c75dde9c9deb9dbcdd56ffc6a960f5878a631f
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031813"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps конектор (преглед)

Уведите обједињене корисничке профиле у своје персонализоване апликације помоћу програма Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Повежите Power Apps и Dynamics 365 Customer Insights

Customer Insights је један од многих [доступних извора за податке у програму Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Погледајте Power Apps документацију да бисте сазнали како да [додате пренос података у апликацију](/powerapps/maker/canvas-apps/add-data-connection). Препоручујемо да такође прегледате [како Power Apps користи делегирање за обраду великих скупова података у апликацијама са подлогом](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Доступни ентитети

Када додате услугу Customer Insights као везу за пренос података, можете изабрати следеће ентитете у програму Power Apps:

- Клијент: да користите податке из [обједињеног профила клијента](customer-profiles.md).
- UnifiedActivity: да приказујете [временску осу активности](activities.md) у апликацији.

## <a name="limitations"></a>Ограничења

### <a name="retrievable-entities"></a>Повратни ентитети

Можете да повратите само ентитете **Клијент**, **Обједињена активност** и **Сегменти** кроз Power Apps конектор. Други ентитети се приказују јер их основни конектор подржава кроз окидаче у услузи Power Automate.  

### <a name="delegation"></a>Делегирање

Делегирање ради за ентитет Клијент и ентитет Обједињена активност. 

- Делегирање за ентитет **Клијент**: Да бисте користили делегирање за овај ентитет, поља треба индексирати у одељку [Индекс претраге и филтрирања](search-filter-index.md).  

- Делегирање за ентитет **Обједињена активност**: Делегирање за овај ентитет ради само за поља **ActivityId** и **CustomerId**.  

- За више информација о делегирању, погледајте [Power Apps преносиве функције и операције](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Пример контроле галерије

На пример, додајете профиле клијената у [контролу галерије](/powerapps/maker/canvas-apps/add-gallery).

1. Додајте контролу **Галерија** у апликацију коју градите.

> [!div class="mx-imgBorder"]
> ![Додајте елемент галерије.](media/connector-powerapps9.png "Додајте елемент галерије")

1. Изаберите **Клијент** као извор података за ставке.

    > [!div class="mx-imgBorder"]
    > ![Изаберите извор података.](media/choose-datasource-powerapps.png "Изаберите извор података")

1. Можете да промените таблу са подацима на десној страни да бисте изабрали поље које ће ентитет Клијент приказати у галерији.

1. Ако желите да у галерији прикажете било које поље одабраног клијента, попуните својство Текст ознаке: **{Name_of_the_gallery}.Selected.{property_name}**

    Пример: Gallery1.Selected.address1_city

1. Да бисте приказали обједињену временску осу за клијента, додајте елемент Галерија и додајте својство Ставке: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Пример: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]