---
title: Приказ и креирање димензија
description: Како да креирате, уређујете и бришете аспекте.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b575c5e84197d76f53a722bac60c5af928c917f9671720ede1de38c4a7478be4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034015"
---
# <a name="view-and-create-dimensions"></a>Приказ и креирање димензија

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Аспект је атрибут догађаја који може да опише, филтрира или групише податке. Ако на својој веб-локацији водите маркетиншку промоцију, можете да користите аспекте за сортирање посетилаца по новим и поновним корисницима.  

Увид у ангажовање укључује готове аспекте за својства догађаја. Примери укључују следеће:

- Назив прегледача
- Име странице
- Модел уређаја
- Оперативни систем
- Земља

## <a name="view-dimensions"></a>Приказ аспеката

Аспекти се заснивају на постојећим својствима догађаја. Када користите кôд за праћење за увиде у ангажман, системски аспекти се аутоматски креирају.

1. Идите на одељак **Подаци** у левом окну за навигацију. 
1. Изаберите **Аспекти** да бисте видели списак свих аспеката у радном простору. 
   > [!NOTE]
   > Системски генерисани аспекти су само за читање. Не можете их уређивати. Можете да креирате и уређујете само прилагођене аспекте.

## <a name="create-a-dimension"></a>Креирање димензије

Поред системски генерисаних аспеката, администратори окружења и радних простора могу да креирају прилагођене аспекте. Прилагођени аспекти се заснивају на подразумеваним својствима основних догађаја или их могу користити [прилагођена својства догађаја](advanced-SDK-implementation.md).

1. Идите на **Подаци** > **Аспекти**.
1. Изаберите **Додај аспект**.

   :::image type="content" source="media/add-dimension.png" alt-text="Додавање аспекта догађају.":::

1. У окну **Креирање аспекта** изаберите својство на којем ће се аспект заснивати. Листа својстава приказаће сва својства у радном простору која нису додељена аспекту.
1. Унесите назив у поље **Име за приказ**. Опционално, можете додати опис.
1. Изаберите **Креирај** да бисте сачували аспект. Може потрајати до једног минута да бисте почели да користите аспект у [прилагођеном извештају](custom-reports.md) или [сегменту](segments.md). 

## <a name="edit-a-dimension"></a>Уређивање аспекта

Можете да промените назив и опис аспекта.

1. Идите на **Подаци** > **Аспекти**.
1. Изаберите аспект који желите да избришете.
1. У окну **Уређивање аспекта** ажурирајте аспект.
1. Изаберите **Примени** да бисте сачували промене.

## <a name="delete-a-dimension"></a>Брисање аспекта

Можете да избришете само аспекте које су креирали корисници, али не можете да уклоните системске аспекте.

Брисање аспекта је трајно. Извештаји и сегменти који користе избрисани аспект више неће функционисати. 

1. Идите на **Подаци** > **Аспекти**.
1. Изаберите аспект који желите да избришете.
1. У окну **Уређивање аспекта** изаберите **Избриши аспект**.

   :::image type="content" source="media/delete-dimension.png" alt-text="Брисање аспекта догађаја.":::

1. Унесите **CONFIRM DELETE** (великим словима) да бисте потврдили брисање. 
1. Изаберите **Избриши**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]