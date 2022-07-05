---
title: Power Apps конектор (преглед)
description: Повежите се са услугама Power Apps и Power Automate.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 0b71f723d1e491d422d24b1be6616d2f33c95d40
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055278"
---
# <a name="power-apps-connector-preview"></a>Power Apps конектор (преглед)

Уведите обједињене корисничке профиле у своје персонализоване апликације помоћу програма Microsoft Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Повежите Power Apps и Dynamics 365 Customer Insights

Customer Insights је један од многих [доступних извора за податке у програму Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Погледајте Power Apps документацију да бисте сазнали како да [додате пренос података у апликацију](/powerapps/maker/canvas-apps/add-data-connection). Препоручујемо да такође прегледате [како Power Apps користи делегирање за обраду великих скупова података у апликацијама са подлогом](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Доступни ентитети

Када додате услугу Customer Insights као везу за пренос података, можете изабрати следеће ентитете у програму Power Apps:

- **Клијент**: за коришћење података из [обједињеног профила клијента](customer-profiles.md).
- **UnifiedActivity**: да бисте приказали [временску осу активности](activities.md) у апликацији.
- **ContactProfile**: да бисте приказали контакте клијента. Овај ентитет је доступан само у окружењима увида клијената за пословне налоге.

## <a name="limitations"></a>Ограничења

### <a name="retrievable-entities"></a>Повратни ентитети

Можете да преузмете само ентитете **Клијент**, **UnifiedActivity**, **Сегменти** и **ContactProfile** кроз Power Apps конектор. ЦонтацтПрофиле је доступан само у инстанци увида купаца за пословне налоге. Други ентитети се приказују јер их основни конектор подржава кроз окидаче у услузи Power Automate.

Можете да урадите највише 100 позива на 60 секунди. АПИ можете да позовете крајња тачка више пута помоћу параметра $ скип уређаја. [Сазнајте више о $ скип параметру](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Делегирање

Делегирање ради за ентитет **Клијент** и ентитет **UnifiedActivity**. 

- Делегирање за ентитет **Клијент**: Да бисте користили делегирање за овај ентитет, поља треба индексирати у одељку [Индекс претраге и филтрирања](search-filter-index.md).  
- Делегирање за ентитет **Обједињена активност**: Делегирање за овај ентитет ради само за поља **ActivityId** и **CustomerId**.  
- Делегирање за **ContactProfile**: делегирање за овај ентитет функционише само за поља **ContactId** и **CustomerId**. ЦонтацтПрофиле је доступан само у окружењима"Увиди купаца" за пословне налоге.

За више информација о делегирању идите на [Power Apps преносиве функције и операције](/powerapps/maker/canvas-apps/delegation-overview). 

## <a name="example-gallery-control"></a>Пример контроле галерије

Можете додати профиле клијената у [контролу галерије](/powerapps/maker/canvas-apps/add-gallery).

1. Додајте контролу **Галерија** у апликацију коју градите.

    > [!div class="mx-imgBorder"]
    > ![Додајте елемент галерије.](media/connector-powerapps9.png "Додајте елемент галерије.")

2. Изаберите **Клијент** као извор података за ставке.

    > [!div class="mx-imgBorder"]
    > ![Изаберите извор података.](media/choose-datasource-powerapps.png "Изаберите извор података.")

3. Можете да промените таблу са подацима на десној страни да бисте изабрали поље које ће ентитет Клијент приказати у галерији.

4. Ако желите да у галерији прикажете било које поље одабраног клијента, попуните својство **Текст** ознаке користећи **{Name_of_the_gallery}.Selected.{property_name}**  
    - На пример: _Gallery1.Selected.address1_city_

5. Да бисте приказали обједињену временску осу за клијента, додајте елемент галерије, па додајте својство **Ставке** користећи **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - На пример: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE [footer-include](includes/footer-banner.md)]
