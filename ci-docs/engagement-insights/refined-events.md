---
title: Креирање и измена изабраних догађаја
description: Како да креирате и измените изабране догађаје.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034792"
---
# <a name="create-and-modify-refined-events"></a>Креирање и измена изабраних догађаја

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


Догађај је податак који представља понашање корисника, попут активности на веб-локацији.

- *Основни* догађај бележи када корисник прикаже страницу (догађај приказа) или ступи у интеракцију са садржајем (догађај радње).
- *Пречишћени* догађај је виртуелни приказ основног догађаја. Пречишћене догађаје дефинишете уклањањем и додавањем својстава или филтрирањем догађаја на основу вредности својстава.

Користите пречишћене догађаје да бисте смањили опсег основног догађаја да [извози](export-events.md) или уклања својства која нису потребна за излагање.

## <a name="create-refined-events"></a>Направите истанчане догађаје

Постоје три начина за креирање пречишћеног догађаја из основног догађаја. 

1. Идите на **Подаци**> **Догађаји** и одаберите једну од следећих опција:
    - Изаберите **Нови догађаји**, а затим изаберите **Креирај пречишћене догађаје**.
    - Изаберите основни догађај да бисте отворили детаљан приказ, па са горњег менија изаберите **Креирај пречишћене догађаје**.
    - Изаберите **Још [...]** да бисте отворили мени са пречицама за основни догађај. Затим изаберите **Креирај пречишћене догађаје**.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="Опције за креирање пречишћених догађаја.":::

1. У дијалогу **Креирање пречишћених догађаја** унесите следеће податке:

- Изаберите догађај са падајуће листе **Основни догађаји** ако креирате нови догађај.
- Унесите назив у поље **Име за приказ пречишћених догађаја**.
- Опционо, ажурирајте предложено **Стварно име** не користећи размаке.

3. Изаберите **Креирај** да бисте применили своја подешавања.

1. У детаљном приказу вашег пречишћеног догађаја изаберите **Додавање и уклањање својстава** да бисте отворити окно **Измена својства**. 

1. Користите поља за потврду да бисте изабрали својства која желите да прикажете и она која желите да сакријете. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Уредите својства за пречишћене догађаје.":::

1. Изаберите **Потврди** да бисте применили избор.

1. Изаберите **Сачувај** да бисте сачували конфигурацију.

## <a name="edit-refined-events"></a>Уређивање пречишћених догађаја

Можете да промените назив и својства пречишћеног догађаја.

### <a name="edit-event-name"></a>Уређивање назива догађаја

1. Идите на **Подаци** > **Догађаји**. 
1. Изаберите **Још [...]** за догађај и изаберите **Уреди назив**.
1. Ажурирајте назив догађаја и изаберите **Преименуј**.

### <a name="edit-selected-properties"></a>Уређивање изабраних својстава

1. Идите на **Подаци** > **Догађаји** и изаберите пречишћене догађаје да бисте отворили детаљан приказ.
1. Изаберите **Додавање и уклањање својстава**. 
1. Уредите избор поља за потврду.
1. Изаберите **Потврди**, а затим **Сачувај** да бисте применили промене.

За информације о извозу догађаја, погледајте [Извоз догађаја](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]