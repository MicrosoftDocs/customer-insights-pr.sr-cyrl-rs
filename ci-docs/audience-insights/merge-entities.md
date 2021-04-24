---
title: Обједињавање ентитета код обједињавања података
description: Обједините ентитете да бисте креирали обједињене профиле клијената.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 737c593353878a5e322488d00de5dc5db5befda9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597851"
---
# <a name="merge-entities"></a>Обједињавање ентитета

Фаза спајања је последња фаза у процесу обједињавања података. Његова сврха је усклађивање неусаглашених података. Примери неусаглашених података могу укључивати корисничко име које се налази у два скупа података, али то се приказује мало другачије у сваком („Јован Дучић“ у односу на „Јово Дучић“) или телефонски број који се разликује у формату (нпр. 617-803-091 у односу на 617803091). Спајање тих неусаглашених тачака података обавља се на основу поређења атрибута.

Када се доврши [фаза подударања](match-entities.md), фазу спајања започињете одабиром плочице **Обједини** на страници **Уједначавање**.

## <a name="review-system-recommendations"></a>Преглед системских препорука

На страници **Спајање** можете изабрати и искључити атрибуте који ће се спајати унутар обједињеног ентитета профила клијента (резултат поступка конфигурације). Систем аутоматски спаја неке атрибуте.

### <a name="view-merged-attributes"></a>Приказ спојених атрибута

Да бисте видели атрибуте који су укључени у један од ваших аутоматски спојених атрибута, изаберите тај спојени атрибут. Два атрибута која чине тај спојени атрибут приказују се у два нова реда испод спојеног атрибута.

> [!div class="mx-imgBorder"]
> ![Избор спојеног атрибута](media/configure-data-merge-profile-attributes.png "Избор спојеног атрибута")

### <a name="separate-merged-attributes"></a>Одвајање спојених атрибута

Да бисте одвојили или раскинули било који од аутоматски спојених атрибута, пронађите атрибут у табели **Атрибути профила**.

1. Изаберите дугме са три тачке (...).
  
2. У падајућој листи изаберите **Одвоји поља**.

### <a name="remove-merged-attributes"></a>Уклањање спојених атрибута

Да бисте изузели атрибут из ентитета крајњег профила клијента, пронађите га у табели **Атрибути профила**.

1. Изаберите дугме са три тачке (...).
  
2. У падајућој листи изаберите **Не обједињуј**.

   Атрибут је премештен у одељак **Уклоњено из евиденције корисника**.

## <a name="manually-add-a-merged-attribute"></a>Ручно додајте спојени атрибут

Да бисте додали спојени атрибут, идите на страницу **Спајање**.

1. Изаберите **Додавање спојеног атрибута**.

2. Наведите **Име** да га касније идентификујете на страници **Спајање**.

3. Опционално, наведите **Име за приказ** које ће се приказати у обједињеном ентитету Профил клијента.

4. Конфигуришите **Изаберите атрибуте дупликата** да бисте изабрали атрибуте које желите да спојите из подударних ентитета. Такође можете да претражујете атрибуте.

5. Подесите **Поредак по важности** да један атрибут поставите изнад осталих. На пример, ако ентитет *WebAccountCSV* укључује најтачније податке о атрибуту *Пуна имена*, можете дати предност том ентитету у односу на *ContactCSV* тако што ћете изабрати *WebAccountCSV*. Као резултат, *WebAccountCSV* прелази на први приоритет, док *ContactCSV* прелази на други приоритет при повлачењу вредности за атрибут *Пуно име*.

## <a name="run-your-merge"></a>Покрените своје спајање

Без обзира да ли ручно спајате атрибуте или пуштате систем да их спаја, увек можете покренути спајање. Изаберите **Покрени** на страници **Спајање** да започнете процес.

> [!div class="mx-imgBorder"]
> ![Спајање података Сачувај и Покрени](media/configure-data-merge-save-run.png "Спајање података Сачувај и Покрени")

Да бисте унели додатне измене и поново покренули корак, можете отказати обједињавање које је у току. Изаберите текст **Освежавање у току...** и изаберите **Откажи посао** у бочном окну које се приказује.

Када се текст **Освежавање у току...** промени у **Успешно**, обједињавање је довршено и решило контрадикције у вашим подацима у складу са смерницама које сте дефинисали. Обједињени и необједињени атрибути су укључени у обједињени ентитет профила. Изузети атрибути нису укључени у обједињени ентитет профила.

Ако то није први пут да сте успешно извели обједињавање, сви процеси на нижем току, укључујући обогаћивање, сегментацију и мере, аутоматски ће се поново покренути. Након што су сви процеси на нижем току поново покренути, профили клијената одражавају све ваше измене.

> [!TIP]
> Постоји [шест врста статуса](system.md#status-types) за задатке/процесе. Уз то, већина процеса [зависи од других процеса на нижем току](system.md#refresh-policies). Можете изабрати статус процеса да бисте видели детаље о току целог посла. Након избора опције **Види детаље** за један од задатака посла пронаћи ћете додатне информације: време обраде, датум последње обраде и све грешке и упозорења повезана са задатком.

## <a name="next-step"></a>Следећи корак

Конфигуришите [активности](activities.md), [обогаћивање](enrichment-microsoft-graph.md) или [релације](relationships.md) да бисте остварили бољи увид у клијенте.

Ако сте већ конфигурисали активности, обогаћивање или релације или ако сте дефинисали сегменте, они ће се аутоматски обрадити како би се користили најновији подаци о клијентима.




[!INCLUDE[footer-include](../includes/footer-banner.md)]