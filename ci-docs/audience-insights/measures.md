---
title: Креирање мера и управљање њима
description: Дефинишите мере за анализу и одраз учинка вашег пословања.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654750"
---
# <a name="define-and-manage-measures"></a>Дефинишите и управљајте мерама

Мере вам помажу да боље разумете понашање клијената и пословне перформансе преузимањем релевантних вредности из [обједињених профила](data-unification.md). На пример, предузеће жели да види *укупну потрошњу по клијенту* да би разумело историју куповине појединачног клијента. Или мери *укупну продају предузећа* да би разумело приход на збирном нивоу у целом предузећу.  

Мере се креирају помоћу креатора мера, платформе за упите података са различитим оператерима и једноставним опцијама мапирања. Омогућава вам да филтрирате податке, групишете резултате, откривате [путање релација између ентитета](relationships.md) и прегледате излаз.

Користите креатор мера за планирање пословних активности тако што ћете потражити податке о клијентима и извући увиде. На пример, креирање мере *укупна потрошња по клијенту* и *укупан повраћај по клијенту* помаже у идентификовању групе клијената са високом потрошњом, али и високим повраћајем. Можете да [креирате сегмент](segments.md) да бисте покренули следеће најбоље радње. 

## <a name="create-a-measure"></a>Креирање мере

Овај одељак вас води кроз креирање нове мере од почетка. Можете да израдите меру са атрибутима података од ентитета података који имају успостављену релацију за повезивање са ентитетом Клијент. 

1. У увидима о корисницима идите на **Мере**.

1. Изаберите **Ново**.

1. Изаберите **Уређивање назива** и наведите **Назив** за меру. 
   > [!NOTE]
   > Ако ваша нова конфигурација мере има само два поља, за пример, CustomerID и један прорачун, излаз ће бити додат као нова колона системски генерисаном ентитету под називом Customer_Measure. И моћи ћете да видите вредност мере у обједињеном профилу клијента. Друге мере ће генерисати сопствене ентитете.

1. У области конфигурације, одаберите агрегатну функцију из падајућег менија **Изаберите функцију**. Агрегатне функције укључују: 
   - **Збир**
   - **Просек**
   - **Преборјавање**
   - **Број јединствених**
   - **Максимум**
   - **Минимум**
   - **Први**: узима прву вредност записа података
   - **Последњи**: узима последњу вредност која је додата у запис података

   :::image type="content" source="media/measure-operators.png" alt-text="Оператори за прорачун мера.":::

1. Изаберите **Додај атрибут** да бисте изабрали податке који су вам потребни за креирање ове мере.
   
   1. Изаберите картицу **Атрибути**. 
   1. Ентитет података: Изаберите ентитет који укључује атрибут који желите да мерите. 
   1. Атрибут података: Изаберите атрибут који желите да користите у агрегатној функцији за израчунавање мере. Истовремено можете да изаберете само један атрибут.
   1. Такође можете изабрати атрибут података из постојеће мере избором картице **Мере**. Или можете да претражите назив ентитета или назив мере. 
   1. Изаберите **Додај** да бисте мери додали изабрани атрибут.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Изаберите атрибут који ћете користити у прорачунима.":::

1. Да бисте изградили сложеније мере, можете додати више атрибута или користити математичке операторе на својој функцији мере.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Креирајте сложену меру помоћу математичких оператора.":::

1. Да бисте додали филтере, изаберите **Филтер** у области конфигурације. 
  
   1. У одељку **Додај атрибут** окна **Филтери**, изаберите атрибут који желите да користите за креирање филтера.
   1. Поставите операторе филтера да дефинишу филтер за сваки изабрани атрибут.
   1. Изаберите **Примени** да бисте мери додали филтере.

1. Да бисте додали димензије, изаберите **Димензија** у области конфигурације. Димензије ће се приказати као колоне у излазном ентитету мере.
   1. Изаберите **Уређивање димензија** да бисте додавали атрибуте података по којима желите да групишете вредности мере. На пример, град или пол. Подразумевано, димензија *CustomerID* се бира за креирање *мера на нивоу клијента*. Можете да уклоните подразумевану димензију ако желите да креирате *мере на нивоу предузећа*.
   1. Изаберите **Готово** да бисте мери додали димензије.

1. Ако постоји више путања између ентитета података који сте мапирали и ентитета *Клијент*, морате одабрати једну од идентификованих [путања релација између ентитета](relationships.md). Резултати мерења могу се разликовати у зависности од изабране путање. 
   1. Изаберите **Жељене опције података** и одаберите путању ентитета коју треба користити за идентификацију ваше мере. Ако постоји само један пут до ентитета *Клијент*, ова контрола се неће приказати.
   1. Изаберите **Готово** да примените свој избор. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Изаберите путању ентитета за меру.":::

1. Да бисте додали још прорачуна за меру, изаберите **Нови прорачун**. Ентитете на истој путањи ентитета можете користити само за нове прорачуне. Више прорачуна ће се приказати као нове колоне у излазном ентитету мере.

1. Изаберите **...** на прорачуну да бисте **направили дупликат**, **преименовали** или **уклонили** прорачун из мере.

1. У области **Преглед** видећете шему података излазног ентитета мере, укључујући филтере и димензије. Преглед динамички реагује на промене у конфигурацији.

1. Изаберите **Покрени** да бисте израчунали резултате за конфигурисану меру. Изаберите **Сачувај и затвори** ако желите да задржите тренутну конфигурацију и покренете меру касније.

1. Идите на **Мере** да бисте на листи видели новокреирану меру.

## <a name="manage-your-measures"></a>Управљање мерама

Када [креирате меру](#create-a-measure), видећете листу мера на страници **Мере**.

Пронаћи ћете информације о типу мере, аутору, датуму настанка, статусу и стању. Када изаберете меру са листе, можете да прегледате излаз и преузмете .CSV датотеку.

Да бисте истовремено освежили све мере, изаберите **Освежите све** без избора одређене мере.

> [!div class="mx-imgBorder"]
> ![Радње за управљање јединственим мерама](media/measure-actions.png "Радње за управљање јединственим мерама")

Изаберите меру са листе за следеће опције:

- Изаберите назив мере да бисте видели њене детаље.
- **Уредите** конфигурацију мере.
- **Освежите** меру на основу најновијих података.
- **Преименујте** меру.
- **Избришите** меру.
- **Активирајте** или **Деактивирајте**. Неактивне мере се неће освежавати током [заказаног освежавања](system.md#schedule-tab).

> [!TIP]
> Постоји [шест врста статуса](system.md#status-types) за задатке/процесе. Уз то, већина процеса [зависи од других процеса на нижем току](system.md#refresh-policies). Можете изабрати статус процеса да бисте видели детаље о току целог посла. Након избора опције **Види детаље** за један од задатака посла пронаћи ћете додатне информације: време обраде, датум последње обраде и све грешке и упозорења повезана са задатком.

## <a name="next-step"></a>Следећи корак

Можете користити постојеће мере за креирање [сегмента клијената](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]