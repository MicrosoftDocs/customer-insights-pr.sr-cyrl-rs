---
title: Креирање сегмената и управљање њима
description: Направите сегменте клијената да бисте их груписали на основу различитих атрибута.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597076"
---
# <a name="create-and-manage-segments"></a>Креирање сегмената и управљање њима

Сегменти вам омогућавају да групишете клијенте на основу демографских, трансакционих или атрибута понашања. Можете да користите сегменте за циљање промотивних кампања, продајних активности и активности подршке клијената како бисте постигли своје пословне циљеве.

Можете дефинисати сложене филтере око ентитета Профил клијента и с њим повезаних ентитета. Сваки сегмент након обраде креира скуп корисничких записа које можете да извозити и за које можете да предузимате неке кораке. Нека [ограничења услуга](service-limits.md) се примењују.

Ако није другачије назначено, сви сегменти су **Динамички сегменти**, који се освежавају по редовном распореду.

Следећи пример илуструје коришћење могућности сегментације. Дефинисали смо сегмент за клијенте који су наручили робу за најмање 500 USD у последњих 90 дана *и* који су били укључени у позив корисничке службе који је прослеђен.

> [!div class="mx-imgBorder"]
> ![Више група](media/segmentation-group1-2.png "Више група")

## <a name="create-a-new-segment"></a>Креирајте нови сегмент

Сегментима се управља на страници **Сегменти**.

1. У увидима о корисницима идите на страницу **Сегменти**.

1. Изаберите **Ново** > **Празан сегмент**.

1. У окну **Нови сегмент** одаберите тип сегмента и наведите **Име**.

   Опционално, унесите име за приказ и опис који помаже у препознавању сегмента.

1. Изаберите **Следеће** да дођете на страницу **Градитељ сегмената** на којој дефинишете групу. Група је скуп клијената.

1. Одаберите ентитет који обухвата атрибуте по којима желите да сегментирате.

1. Одаберите атрибут по сегменту. Овај атрибут може имати један од четири типа вредности: нумерички, ниска, датум или логички.

1. Одаберите оператор и вредност за изабрани атрибут.

   > [!div class="mx-imgBorder"]
   > ![Прилагођени филтер групе](media/customer-group-numbers.png "Филтер групе клијената")

   |Број |Дефиниција  |
   |---------|---------|
   |1     |Entity          |
   |2     |Атрибут          |
   |3    |Оператор         |
   |4    |Вредност         |

8. Ако је ентитет повезан путем обједињеног ентитета клијента путем [односа](relationships.md), морате дефинисати путању односа да бисте креирали важећи сегмент. Додајте ентитете из путање односа док не будете могли да изаберете ентитет **Клијент: CustomerInsights** из падајуће листе. Затим одаберите **Сви записи** за сваки услов.

   > [!div class="mx-imgBorder"]
   > ![Путања односа током креирања сегмента](media/segments-multiple-relationships.png "Путања односа током креирања сегмента")

1. Подразумевано, сегменти генеришу излазни ентитет који садржи све атрибуте корисничких профила који се подударају са дефинисаним филтерима. Ако се сегмент заснива на другим ентитетима осим на ентитету *Клијент*, излазном ентитету можете додати више атрибута из тих ентитета. Изаберите **Атрибути пројекта** да бисте одабрали атрибуте који ће бити додати излазном ентитету.  

   
   Пример: Сегмент се заснива на ентитету који садржи податке о активностима клијената који су повезани са ентитетом *Клијент*. Сегмент тражи све клијенте који су позвали техничку подршку у последњих 60 дана. Можете одабрати да додате трајање позива и број позива свим подударним записима клијената у излазном ентитету. Ове информације могу бити корисне за слање е-поште са корисним везама до чланака помоћи на мрежи и често постављаних питања клијентима који су често звали.

1. Изаберите **Сачувај** да бисте сачували сегмент. Ваш сегмент ће бити сачуван и обрађен уколико су сви захтеви потврђени. У супротном, биће сачуван као радна верзија.

1. Изаберите **Назад на сегменте** да бисте се вратили на страницу **Сегменти**.

## <a name="manage-existing-segments"></a>Управљање постојећим сегментима

На страници **Сегменти**, можете видети све сачуване сегменте и њима управљати.

Сваки сегмент представљен је редом који садржи додатне информације о сегменту.

Сегменте можете сортирати у колони одабиром наслова колоне.

Користите поље **Претрага** у горњем десном углу да бисте филтрирали сегменте.

> [!div class="mx-imgBorder"]
> ![Опције за управљање постојећим сегментом](media/segments-selected-segment.png "Опције за управљање постојећим сегментом")

Следећа радња је доступна када одаберете сегмент:

- **Приказ** детаља сегмента, укључујући тренд броја чланова, преглед чланова сегмента.
- **Уредите** сегмент да бисте променили његова својства.
- **Направите дупликат** сегмента. Можете одабрати да уредите његова својства или једноставно сачувате дупликат.
- **Освежите** сегмент тако да укључује најновије податке.
- **Активирајте** или **Деактивирајте** сегмент. Сегменти имају два могућа стања - активно или неактивно. Ова стања добро дођу приликом уређивања сегмента. За неактивне сегменте дефиниција сегмента постоји, али још увек не садржи клијенте. Када активирате сегмент, његово стање се мења из „неактиван“ у „активан“ и он почиње да тражи клијенте који одговарају дефиницији сегмента. Ако је [заказано освежавање](system.md#schedule-tab) конфигурисано, неактивни сегменти имају **Статус** наведен као **Прескочено**, што указује да освежавање није ни покушано. Када се активира неактивни сегмент, освежиће се и биће укључен у заказана освежавања.
  Алтернативно, можете да користите функционалност **Испланирај за касније** у падајућој листи **Активирај/Деактивирај** да наведете будући датум и време за активацију и деактивацију одређеног сегмента.
- **Преименујте** сегмент.
- **Преузмите** листу чланова као .CSV датотеку.
- Опција **Додај у** шаље листу ID-ова клијената у сегменту на обраду у другој апликацији.
- **Избришите** сегмент.

## <a name="refresh-segments"></a>Освежавање сегмената

Можете да освежите све сегменте одједном ако изаберете **Освежите све** на страници **Сегменти**, а можете и да освежити један или више сегмената када их изаберете, па одаберете **Освежи** из опција. Алтернативно, можете конфигурисати понављајуће освежавање у одељку **Администратор** > **Систем** > **Распоред**.

> [!TIP]
> Постоји [шест врста статуса](system.md#status-types) за задатке/процесе. Уз то, већина процеса [зависи од других процеса на нижем току](system.md#refresh-policies). Можете изабрати статус процеса да бисте видели детаље о току целог посла. Након избора опције **Види детаље** за један од задатака посла пронаћи ћете додатне информације: време обраде, датум последње обраде и све грешке и упозорења повезана са задатком.

## <a name="download-and-export-segments"></a>Преузимање и извоз сегмената

Можете преузети своје сегменте у CSV датотеку или их извести у Dynamics 365 Sales.

### <a name="download-segments-to-a-csv-file"></a>Преузмите сегменте у CSV датотеку

1. У увидима о корисницима идите на страницу **Сегменти**.

2. Изаберите три тачке на плочици одређеног сегмента.

3. Изаберите **Преузми као CSV** са падајуће листе радњи.

### <a name="export-segments-to-dynamics-365-sales"></a>Извоз сегмената у Dynamics 365 Sales

Пре извоза сегмената у Dynamics 365 Sales, администратор треба [креирај одредиште за извоз](export-destinations.md) за Dynamics 365 Sales.

1. У увидима о корисницима идите на страницу **Сегменти**.

2. Изаберите три тачке на плочици одређеног сегмента.

3. Изаберите **Додај у** из падајуће листе радњи и изаберите одредиште за извоз у које желите да пошаљете податке.

## <a name="draft-mode-for-segments"></a>Режим радне верзије за сегменте

Ако нису испуњени сви захтеви за обраду сегмента, можете да сачувате сегмент као радну верзију и приступите му са странице **Сегменти**.

Биће сачуван као неактиван сегмент и нећете моћи да га активирате док не постане важећи.

## <a name="add-more-conditions-to-a-group"></a>Додајте више услова групи

Да бисте групи додали више услова, можете да користите два логичка оператора:

- Оператор **И**: Оба услова морају да буду испуњена као део процеса сегментације. Ова опција је најкориснија када дефинишете услове у различитим ентитетима.

- Оператор **ИЛИ**: Било који од услова мора бити испуњен као део процеса сегментације. Ова опција је најкориснија када дефинишете више услова у истом ентитету.

   > [!div class="mx-imgBorder"]
   > ![Оператор ИЛИ где је потребно испунити било који услов](media/segmentation-either-condition.png "Оператор ИЛИ где је потребно испунити било који услов")

Тренутно је могуће угнездити оператор **ИЛИ** унутар оператора **И**, али не и обрнуто.

## <a name="combine-multiple-groups"></a>Комбиновање више група

Свака група производи одређени скуп клијената. Можете комбиновати ове групе да бисте укључили клијенте потребне за ваш предмет пословања.

1. У увидима о клијентима идите на страницу **Сегменти** и изаберите сегмент.

2. Изаберите **Додај групу**.

   > [!div class="mx-imgBorder"]
   > ![Група клијената додај групу](media/customer-group-add-group.png "Група клијената додај групу")

3. Изаберите један од следећих скупа оператора: **Унија**, **Пресек** или **Изузимање**.

   > [!div class="mx-imgBorder"]
   > ![Група клијената додај унију](media/customer-group-union.png "Група клијената додај унију")

   Изаберите оператор скупа да бисте дефинисали нову групу. Чување различитих група ради одређивања који подаци се задржавају:

   - **Унија** обједињује две групе.

   - **Пресек** преклапа две групе. Само подаци који *су заједнички* за обе групе задржавају се у обједињеној групи.

   - **Осим** комбинује две групе. Само подаци у групи А који *нису заједнички* са подацима из групе Б задржавају се.

## <a name="view-processing-history-and-segment-members"></a>Погледајте историју обраде и чланове сегмента

Консолидоване податке о сегменту можете видети тако што ћете прегледати његове детаље.

На страници **Сегменти** изаберите сегмент који желите да прегледате.

Горњи део странице садржи графикон тренда који визуелно приказује промене у броју чланова. Задржите показивач изнад тачака података да бисте видели број чланова одређеног датума.

Можете да ажурирате временски оквир визуелизације.

> [!div class="mx-imgBorder"]
> ![Временски период сегмента](media/segment-time-range.png "Временски период сегмента")

Доњи део садржи листу чланова сегмента.

> [!NOTE]
> Поља која се појављују на овој листи заснивају се на атрибутима ентитета вашег сегмента.
>
>Листа је преглед одговарајућих чланова сегмента и показује првих 100 записа вашег сегмента тако да га можете брзо проценити и прегледати његове дефиниције, ако је потребно. Да бисте видели све одговарајуће записе, морате да [извезете сегмент](export-destinations.md).

## <a name="quick-segments"></a>Брзи сегменти

Поред алатке за прављење сегмената, постоји још један пут за креирање сегмената. Брзи сегменти вам омогућавају да направите једноставне сегменте, са једним оператором, брзо и уз тренутне увиде.

1. На страници **Сегменти** изаберите **Нова** > **Брзо креирајте од**.

   - Изаберите опцију **Профили** за изградњу сегмента који је заснован на обједињеном ентитету Клијент.
   - Изаберите опцију **Мере** за изградњу сегмента око сваке врсте мера атрибута клијента које сте претходно креирали на страници **Мере**.
   - Изаберите опцију **Обавештавање** да изградите сегмент око једног од излазних ентитета које сте генерисали користећи могућности **Предвиђања** или **Прилагођени модели**.

2. У дијалогу **Нови брзи сегмент** изаберите атрибут из падајуће листе **Поље**.

3. Систем ће вам пружити неке додатне увиде који ће вам помоћи да створите боље сегменте својих клијената.
   - За категоријска поља приказаћемо 10 главних бројева клијента. Одаберите **Вредност** и изабрали **Преглед**.

   - За нумерички атрибут, систем ће показати која вредност атрибута спада испод сваког процента клијента. Одаберите **Оператор** и **Вредност**, а затим изаберите **Преглед**.

4. Систем ће вам пружити **Процењену величину сегмента**. Можете одабрати да ли да генеришете сегмент који сте дефинисали или да га прво прегледате како бисте добили другу величину сегмента.

    > [!div class="mx-imgBorder"]
    > ![Назив и процена за брзи сегмент](media/quick-segment-name.png "Назив и процена за брзи сегмент")

5. Наведите **Назив** за сегмент. Опционално, наведите **Име за приказ**.

6. Изаберите **Сачувај** да бисте креирали сегмент.

7. Након завршетка обраде сегмента, можете га прегледати као и било који други сегмент који сте креирали.

За следеће сценарије, саветујемо употребу алата за прављење сегмената уместо препоручених могућности сегмената:

- Стварање сегмената са филтерима на категоријским пољима где је оператор другачији од оператора **Да ли је**
- Креирање сегмената са филтерима на нумеричким пољима где је оператор другачији од оператора **Између**, **Веће од** и **Мање од**
- Креирање сегмената са филтерима на пољима типа датума

## <a name="next-steps"></a>Следећи кораци

[Извезите сегмент](export-destinations.md) и истражите [картицу клијента](customer-card-add-in.md) и [конекторе](export-power-bi.md) да бисте добили увид на нивоу клијента.


[!INCLUDE[footer-include](../includes/footer-banner.md)]