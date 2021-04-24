---
title: Подударање ентитета за обједињавање података
description: Подударите ентитете да бисте креирали обједињене профиле клијената.
ms.date: 02/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2eb84c44aa530346a73ba720106734d705a45f23
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595582"
---
# <a name="match-entities"></a>Подударање ентитета

Фаза подударања наводи како да комбинујете своје скупове података у обједињени скуп података профила клијента. Када довршите [корак мапирања](map-entities.md) у процесу обједињавања података, спремни сте да подударате ентитете. Фаза подударања захтева најмање два мапирана ентитета.

Страница за подударање састоји се од три одељка: 
- Кључне метрике које сумирају број подударних записа
- Редослед подударања и правила за међусобно подударање ентитета
- Правила за дедупликацију ентитета за подударање

## <a name="specify-the-match-order"></a>Наведите редослед подударања

Иди на **Подаци** > **Уједначавање** > **Подударање** и изаберите **Подеси редослед** да започнете фазу подударања.

Свако подударање обједињава два или више ентитета у један, обједињени ентитет. Истовремено, обједињавање чува јединствене записе о клијентима. На пример, изабрали смо два ентитета: **eCommerce:eCommerceContacts** као примарни ентитет и **LoyaltyScheme:loyCustomers** као други ентитет. Редослед ентитета одређује којим редоследом ће систем покушати да подудари записе.

:::image type="content" source="media/match-page.png" alt-text="Снимак екрана странице Подударање у области Обједињавање процеса обједињавања података.":::
  
Примарни ентитет *eCommerce:eCommerceContacts* се подудара са следећим ентитетом *LoyaltyScheme:loyCustomers*. Скуп података који је резултат првог корака подударања подудара се са следећим ентитетом ако имате више од два ентитета.

> [!IMPORTANT]
> Ентитет који сте одабрали као свој примарни ентитет послужиће као основа за скуп података обједињених профила. Додатни ентитети који су изабрани током фазе подударања биће додати овом ентитету. То не значи да ће обједињени ентитет садржати *све* податке обухваћене овим ентитетом.
>
> Постоје два разлога која вам могу помоћи да одаберете хијерархију својих ентитета:
>
> - Одаберите ентитет са најпотпунијим и најпоузданијим подацима о профилу о својим клијентима као примарни ентитет.
> - Одаберите ентитет који има неколико атрибута заједничких са другим ентитетима (нпр. име, број телефона или адреса е-поште) као примарни ентитет.

Када одредите редослед подударања, видећете дефинисане парове подударања у одељку **Детаљи подударних записа** у дијалогу **Подаци** > **Обједињавање** > **Подударање**. Кључне метрике ће бити празне док се поступак подударања не заврши.

## <a name="define-rules-for-match-pairs"></a>Дефинисање правила за подударне парове

Правила подударања одређују логику којом ће се одређени пар ентитета ускладити.

Упозорење **Захтева правила** поред назива ентитета сугерише да није одређено правило подударања за пар подударања. 

:::image type="content" source="media/match-rule-add.png" alt-text="Снимак екрана одељка Детаљи подударних записа са контролом за додавање истакнутих правила.":::

1. Изаберите **Додај правила** под ентитетом у одељку **Детаљи подударних записа** да бисте дефинисали правила подударања.

1. У окну **Креирање правила** конфигуришите услове за правило.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Снимак екрана отвореног правила подударања са додатим условима.":::

   - **Ентитет/поље (први ред)**: Изаберите повезани ентитет и атрибут да бисте одредили својство записа које је вероватно јединствено за клијента. На пример, број телефона или адреса е-поште. Избегавајте подударање по атрибутима типа активности. На пример, ID куповине вероватно неће наћи подударање у другим врстама записа.

   - **Ентитет/поље (други ред)**: Изаберите атрибут који се односи на атрибут ентитета наведеног у првом реду.

   - **Нормализација**: Изаберите неку од следећих опција нормализације за изабране атрибуте. 
     - Размак: Уклања све размаке. *Здраво свима* постаје *ЗдравоСвима*.
     - Симболи: Уклања све симболе и посебне знакове. *Глава & Рамена* постаје *ГлаваРамена*.
     - Текст малим словима: Претвара све знакове у мала слова. *ВЕЛИКА СЛОВА и Слова За Наслов* постаји *велика слова и слова за наслов*.
     - Из Уникода у ASCII: Претвара Уникод нотацију у ASCII знакове. */u00B2* постаје *2*.
     - Бројеви: Конвертује друге бројевне системе, као што су римски бројеви, у арапске бројеве. *VIII* постаје *8*.
     - Семантички типови: Стандардизује имена, наслове, бројеве телефона, адресе итд. 

   - **Прецизност**: Подесите ниво прецизности да се примењује за овај услов. 
     - **Основно**: Бирајте између *Ниско*, *Средње*, *Високо* и *Тачно*. Изаберите **Тачни** да бисте подударали само записе који се подударају 100 посто. Изаберите један од осталих нивоа да бисте подударали записе који нису 100 посто идентични.
     - **Прилагођено**: Подесите проценат са којим записи морају да се подударају. Систем ће се подударати само са записима који прелазе ову граничну вредност.

1. Наведите **Назив** правила.

1. [Додајте још услова](#add-conditions-to-a-rule) или изаберите **Готово** да бисте довршили правило.

1. Опционално, [додајте још правила](#add-rules-to-a-match-pair).

1. Изаберите **Сачувај** да примените промене.

### <a name="add-conditions-to-a-rule"></a>Додавање услова у правило

Да бисте подударали ентитете само ако атрибути испуњавају више услова, додајте још услова у правило подударања. Услови су повезани са логичким оператором И, па се стога извршавају само ако су испуњени сви услови.

1. Идите на **Подаци** > **Обједињавање** > **Подударање** и изаберите **Уреди** на правилу којем желите да додате услове.

1. У окну **Уређивање правила**, изаберите **Додајте услов**.

1. Изаберите **Готово** да бисте сачували правило.

### <a name="add-rules-to-a-match-pair"></a>Додавање правила пару за подударање

Правила за подударање представљају скупове услова. Да бисте подударили ентитете према условима заснованим на више атрибута, додајте још правила

1.  Идите на **Подаци** > **Обједињавање** > **Подударање** и изаберите **Додај правило** ентитету којем желите да додате правила.

2. Следите кораке у одељку [Дефинисање правила за парове за подударање](#define-rules-for-match-pairs).

> [!NOTE]
> Редослед правила је важан. Алгоритам подударања покушава да подудари садржај на основу вашег првог правила и наставља на друго правило само ако са првим правилом није идентификовано ниједно подударање.

## <a name="define-deduplication-on-a-match-entity"></a>Дефинишите дедупликацију на ентитету подударања

Поред [правила за међусобно подударање](#define-rules-for-match-pairs), такође можете да одредите правила за уклањање дупликата. *Дедупликација* је још један поступак при упаривању записа. Идентификује дупликате записа и спаја их у један запис. Изворни записи се повезују са обједињеним записом са алтернативним ID-овима.

Дедуплицирани записи ће се затим користити у процесу подударања међу ентитетима. Дедупликација се дешава на појединачним ентитетима и може се конфигурисати за сваки ентитет који се користи у паровима за подударање.

Навођење правила дедупликације није обавезно. Ако таква правила нису конфигурисана, примењују се системски дефинисана правила. Они комбинују све записе у један запис пре него што пренесу податке ентитета у међусобно удруживање ради побољшаних перформанси.

### <a name="add-deduplication-rules"></a>Додавање правила за дедупликацију

1. Идите на **Подаци** > **Обједињавање** > **Подударање**.

1. У одељку **Обједињени дупликати** изаберите **Подесите ентитете**. У случају да су правила за дедупликацију већ креирана, изаберите **Уреди**.

1. У окну **Жељена подешавања обједињавања** одаберите ентитете над којима желите да покренете дедупликацију.

1. Наведите како треба комбиновати дупликате записа и одаберите једну од три опције:
   - **Најпопуњенији**: Идентификује запис са највише попуњених атрибута као добитни запис. То је подразумевана опција обједињавања.
   - **Најновији**: Идентификује добитни запис на основу најскоријег времена. Захтева датум или нумеричко поље за дефинисање скорашњости.
   - **Најкаснији**: Идентификује добитни запис на основу најкаснијег времена. Захтева датум или нумеричко поље за дефинисање скорашњости.
 
   > [!div class="mx-imgBorder"]
   > ![Корак 1 за правила за дедупликацију](media/match-selfconflation.png "Корак 1 за правила за дедупликацију")
 
1. Када се ентитети изаберу и када се поставе жељене опције за обједињавање, изаберите **Додај правило** да бисте дефинисали правила дедупликације на нивоу ентитета.
   - **Изабери поље** наводи сва расположива поља из тог ентитета. Одаберите поље на којем желите да проверите да ли постоје дупликати. Одаберите поља која су вероватно јединствена за сваког клијента. На пример, адреса е-поште или комбинација имена, града и броја телефона.
   - Наведите подешавања нормализације и прецизности.
   - Дефинишите још додатних услова избором опције **Додај услов**.
 
   > [!div class="mx-imgBorder"]
   > ![Корак 2 за правила за дедупликацију](media/match-selfconflation-rules.png "Корак 2 за правила за дедупликацију")

  Можете да креирате више правила за дедупликацију за ентитет. 

1. Покретање процеса подударања сада групише записе на основу услова дефинисаних у правилима дедупликације. Након груписања записа, примењују се смернице обједињавања за идентификовање добитног записа.

1. Добитни запис се затим прослеђује на подударање са ентитетима, заједно са записима који нису добитни (на пример, алтернативни ID-ови) ради побољшања квалитета подударања.

1. Свако дефинисано правило за прилагођено подударање замењује правила за дуплицирање. Ако правило дедупликације идентификује подударне записе, а прилагођено правило подударања је подешено да се никада не подудара са тим записима, онда се ова два записа неће подударати.

1. Након [покретања процеса подударања](#run-the-match-process), видећете статистику дедупликације на плочицама кључне метрике.

### <a name="deduplication-output-as-an-entity"></a>Излаз поступка уклањања дупликата као ентитет

Процес дедупликације креира нови ентитет за сваки ентитет из парова за подударање како би се идентификовали дедуплицирани записи. Ови ентитети се могу наћи заједно са **ConflationMatchPairs:CustomerInsights** у одељку **Систем** на страници **Ентитети**, под називом **Deduplication_DataSource_Entity**.

Излазни ентитет уклањања дупликата садржи следеће информације:
- ID-ови/Кључеви
  - Поље примарног кључа и његово поље алтернативних ID-ова. Поље алтернативних ID-ова састоји се од свих алтернативних ID-ова идентификованих за запис.
  - Поље Deduplication_GroupId приказује групу или кластер идентификоване у оквиру ентитета који групише све сличне записе на основу наведених поља уклањања дупликата. Ово се користи у сврхе обраде система. Ако нису наведена ручна правила за уклањање дупликата и ако се примењују системски дефинисана правила за уклањање дупликата, ово поље можда нећете пронаћи у излазном ентитету уклањања дупликата.
  - Deduplication_WinnerId: Ово поље садржи ID победника из идентификованих група или кластера. Ако је Deduplication_WinnerId иста као вредност примарног кључа за запис, то значи да је тај запис добитни.
- Поља која се користе за дефинисање правила за уклањање дупликата.
- Одредите правила и оцените поља да означите која су од правила за уклањање дупликата примењена и који резултат враћа алгоритам за подударање.
   
## <a name="run-the-match-process"></a>Покретање поступка подударања

Са конфигурисаним правилима подударања, укључујући правила за подударање и дедупликацију међу ентитетима, можете покренути поступак подударања. 

Идите на **Подаци** > **Обједињавање** > **Подударање** и изаберите **Покрени** да бисте започели поступак. Алгоритму подударања треба неко време да се заврши и не можете да промените конфигурацију док се не заврши. Да бисте унели промене, можете отказати покренути поступак. Изаберите статус посла и изаберите **Откажи посао** у окну **Детаљи напредовања**.

Резултат успешног покретања, обједињени ентитет профила клијента, пронаћи ћете на страници **Ентитети**. Ваш обједињени ентитет клијента се зове **Клијенти** у одељку **Профили**. Прво успешно покретање подударања креира обједињени ентитет *Клијент*. Сва наредна покретања подударања проширују тај ентитет.

> [!TIP]
> Постоји [шест врста статуса](system.md#status-types) за задатке/процесе. Уз то, већина процеса [зависи од других процеса на нижем току](system.md#refresh-policies). Можете изабрати статус процеса да бисте видели детаље о току целог посла. Након избора опције **Види детаље** за један од задатака посла пронаћи ћете додатне информације: време обраде, датум последње обраде и све грешке и упозорења повезана са задатком.

## <a name="review-and-validate-your-matches"></a>Прегледајте и потврдите своја подударања

Идите на **Подаци** > **Обједињавање** > **Подударање** да бисте проценили квалитет ваших парова и по потреби их прецизирали.

Плочице на врху странице приказују кључне метрике, резимирајући број подударних записа и дупликата.

:::image type="content" source="media/match-KPIs.png" alt-text="Изрезани снимак екрана кључних метрика на страници Подударање са бројевима и детаљима.":::

- **Јединствени изворни записи** показује број појединачних изворних записа који су обрађени у последњем покретању подударања.
- **Подударни и неподударни записи** истиче колико јединствених записа остаје након обраде правила подударања.
- **Само одговарајући записи** показује број подударања у свим вашим паровима подударања.

Резултате сваког подударања и сваког пара за подударање можете проценити у табели **Детаљи о подударним записима**. Упоредите број записа који су произашли из пара за подударање са процентом успешно подударних записа.

Прегледајте правила парова за подударање да бисте видели проценат успешно подударних записа на нивоу правила. Изаберите три тачке (...), а затим изаберите **Преглед подударања** да бисте прегледали све ове записе на нивоу правила. Препоручујемо вам да погледате неке записе како бисте потврдили да су се правилно подударали.

Испробајте различите граничне вредности за прецизност у условима како бисте пронашли оптималну вредност.

  1. Изаберите три тачке (...) за правило са којим желите да експериментишете и изаберите **Уреди**.

  2. Промените вредности прецизности у условима које желите да ревидирате.

  3. Изаберите **Преглед**, па погледајте број подударних и неподударних записа за изабрани услов.

## <a name="manage-match-rules"></a>Управљање правилима за подударање

Можете да конфигуришете и фино подесите већину параметара подударања.

:::image type="content" source="media/match-rules-management.png" alt-text="Снимак екрана падајућег менија са опцијама правила подударања.":::

- **Промените редослед својих правила** ако сте дефинисали више правила. Правила подударања можете преуредити тако што ћете изабрати опције **Помери нагоре** и **Помери надоле** или превлачећи их.

- **Промените услове правила** избором опције **Уреди** и одаберите различита поља.

- **Деактивирајте правило** да задржите правило подударања док га искључујете из процеса подударања.

- **Дуплирајте правила** ако сте дефинисали правило за подударање и желите да направите слично правило са изменама, изаберите **Дуплирај**.

- **Избришите правило** избором симбола **Избриши**.

## <a name="specify-custom-match-conditions"></a>Наведите услове за прилагођено подударање

Можете да наведете услове за које би одређена правила требало увек да се подударају или никада да се не подударају. Ова правила се могу отпремити да би заменила стандардни поступак подударања. На пример, ако у записима постоје Пера Перић 1 и Пера Перић 2, систем их може подударати као једну особу. Правила за прилагођено подударање омогућавају вам да одредите да се њихови профили односе на различите људе. 

1. Идите на **Подаци** > **Обједињавање** > **Подударање** и изаберите **Прилагођено подударање** у одељку **Детаљи подударних записа**.

  :::image type="content" source="media/custom-match-create.png" alt-text="Снимак екрана одељка правила подударања са истакнутом контролом за прилагођено подударање.":::

1. Ако још увек нисте поставили правила за прилагођено подударање, видећете ново окно **Прилагођено подударање** са више детаља.

1. Изаберите **Попуните предложак** да бисте добили датотеку предлошка која може да одреди који ће се записи из којих ентитета увек подударати или се неће никад подударити. Морате засебно да попуните записе „увек се подудара“ и „никад се не подудара“ у две различите датотеке.

1. Предложак садржи поља за спецификацију ентитета и вредности примарног кључа ентитета које ће се користити у прилагођеном подударању. На пример, ако желите да се примарни кључ *12345* из ентитета *Продаја* увек подудара са примарним кључем *34567* из ентитета *Контакт*, попуните предложак:
    - Entity1: Продаја
    - Entity1Key: 12345
    - Entity2: Контакт
    - Entity2Key: 34567

   Иста датотека предлошка може одредити записе прилагођених подударања из више ентитета.
   
   Ако желите да наведете прилагођено подударање за уклањање дупликата на ентитету, наведите исти ентитет као и Entity1 и Entity2 и поставите различите вредности примарног кључа.

1. Када додате сва замењивања која желите да примените, сачувајте датотеку шаблона.

1. Идите на **Подаци** > **Извори података** и унесите датотеке предложака као нове ентитете. Када их унесете, можете их користити за одређивање конфигурације подударања.

1. Када отпремите датотеке и ентитете који су доступни, поново изаберите опцију **Прилагођено подударање**. Видећете опције за одређивање ентитета које желите да укључите. Изаберите потребне ентитете из падајућег менија.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Снимак екрана дијалога за одабир замене за сценарио прилагођеног подударања.":::

1. Изаберите ентитете које желите да користите за **Увек се подудара** и **Никад се не подудара**, изаберите **Готово**.

1. Изаберите **Сачувај** на страници **Подударање** да бисте применили конфигурације за прилагођено подударање.

1. Изаберите **Покрени** на страници **Подударање** да бисте започели поступак подударања. Остала наведена правила подударања се замењују конфигурацијом за прилагођено подударање.

> [!TIP]
> Идите на **Подаци** > **Ентитети** и прегледајте ентитет **ConflationMatchPair** да бисте потврдили да су замене примењене.

## <a name="next-step"></a>Следећи корак

Када довршите поступак подударања за најмање један пар подударања, можете решити могуће противречности у подацима тако што ћете проћи кроз тему [**Обједињавање**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]