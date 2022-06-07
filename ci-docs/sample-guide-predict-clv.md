---
title: Водич кроз примере предвиђања трајне вредности клијента
description: Користите овај водич кроз примере да испробате модел предвиђања трајне вредности клијента.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 351946c734f5a1054eb3769b2d9cced3bed48e15
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740829"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Водич кроз примере предвиђања трајне вредности клијента (CLV)

Овај водич ће вам објаснити целокупан пример предвиђања трајне вредности клијента (CLV) у услузи Customer Insights коришћењем примера података.

## <a name="scenario"></a>Сценарио

Цонтосо је компанија која производи висококвалитетне апарате за кафу и кафу. Производе продају преко свог сајта Цонтосо Цоффее. Предузеће жели да разуме вредност (приход) коју њихови клијенти могу да генеришу у следећих 12 месеци. Познавање очекиване вредности клијената у следећих 12 месеци помоћи ће им да своје маркетиншке напоре усмере на клијенте високе вредности.

## <a name="prerequisites"></a>Предуслови

- Барем [дозволе сарадника](permissions.md) у услузи Customer Insights.
- Препоручујемо да примените следеће кораке [у новом окружењу](manage-environments.md).

## <a name="task-1---ingest-data"></a>1. задатак – Унос података

Прегледајте чланке [о уношењу података и](data-sources.md) увозу [извора података помоћу линија Power Query спајања](connect-power-query.md). Следеће информације претпостављају да сте се упознали са уношењем података уопште.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Унесите податке о клијентима са платформе eCommerce

1. Направите извор података под називом **eCommerce**, изаберите опцију увоза, па изаберите конектор **Text/CSV**.

1. Унесите URL адресу за eCommerce контакте [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Док уређујете податке, изаберите **Трансформација**, а затим **Користи први ред као заглавља**.

1. Ажурирајте тип података за доленаведене колоне:
   - **Датум рођења**: Датум
   - **Креирано**: Датум/време/зона

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Трансформација датума рођења у датум.":::

1. У пољу „Име“ у десном окну преименујте извор података из **Упит** у **eCommerce контакти**

1. **Сачувајте** извор података.

### <a name="ingest-online-purchase-data"></a>Унесите податке о куповини на мрежи

1. Додајте још један скуп податка у исти **eCommerce** извор података. Поново изаберите конектор **Текст/CSV**.

1. Унесите URL за податке о **куповинама на мрежи** https://aka.ms/ciadclassonline.

1. Док уређујете податке, изаберите **Трансформација**, а затим **Користи први ред као заглавља**.

1. Ажурирајте тип података за доленаведене колоне:
   - **Купљено дана**: Датум/време
   - **Укупна цена**: Валута

1. У пољу **Назив** у бочном окну преименујте извор података из **Упит** у **eCommerce куповине**.

1. **Сачувајте** извор података.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Унесите податке о клијентима из шеме лојалности

1. Направите извор података под именом **Шема лојалности**, изаберите опцију увоза и изаберите **Текст/CSV** конектор.

1. Унесите URL адресу за eCommerce контакте https://aka.ms/ciadclasscustomerloyalty.

1. Док уређујете податке, изаберите **Трансформација**, а затим **Користи први ред као заглавља**.

1. Ажурирајте тип података за доленаведене колоне:
   - **Датум рођења**: Датум
   - **Наградни поени**: Цео број
   - **Креирано**: Датум/време

1. У пољу **Име** у десном окну преименујте извор података из **Упит** у **Лојални клијенти**.

1. **Сачувајте** извор података.

### <a name="ingest-customer-data-from-website-reviews"></a>Унесите податке о клијентима из рецензија на веб-сајту

1. Направите извор података под именом **Веб-сајт**, изаберите опцију увоза и изаберите **Текст/CSV** конектор.

1. Унесите URL адресу за eCommerce контакте https://aka.ms/CI-ILT/WebReviews.

1. Док уређујете податке, изаберите **Трансформација**, а затим **Користи први ред као заглавља**.

1. Ажурирајте тип података за доленаведене колоне:

   - **ReviewRating**: децимални број
   - **Датум рецензије**: Датум

1. У пољу „Назив“ у десном окну, преименујте извор података из **Упит** у **Прегледи**.

1. **Сачувајте** извор података.

## <a name="task-2---data-unification"></a>2. задатак 2 – Обједињавање података

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>Задатак 3 – Конфигурисање предвиђања трајне вредности клијента

Са успостављеним обједињеним профилима клијената, сада можемо покренути предвиђање трајне вредности клијента. Детаљне кораке погледајте у чланку [Вредност доживотног купца предвиђање](predict-customer-lifetime-value.md).

1. Идите на **Обавештавање**  > **Предвиђања** и изаберите **Модел трајне вредности клијента**.

1. Пређите кроз информације у бочном окну и изаберите **Започни**.

1. Назовите модел **OOB eCommerce CLV Prediction** а излазни ентитет **OOBeCommerceCLVPrediction**.

1. Дефинишите жељене опције модела за CLV модел:
   - **Временски период предвиђања**: **12 месеци или 1 година**. Ово подешавање дефинише колико у будућности треба предвиђати трајну вредност клијента.
   - **Активни клијенти**: Наведите шта активни клијенти значе за ваше пословање. Подесите временски оквир претходног периода у којем је клијент морао имати барем једну трансакцију да би се сматрао активним. Модел ће предвидети CLV само за активне клијенте. Одаберите између допуштања моделу да израчуна временски период на основу историјских података о трансакцијама или наведите одређени временски оквир. У овом водичу кроз пример, ми **омогућавамо моделу да израчуна интервал куповине**, што је подразумевана опција.
   - **Клијенти велике вредности**: Клијенте високе вредности дефинишите као проценат клијената који највише плаћају. Модел користи овај улаз за пружање резултата који се уклапају у вашу пословну дефиницију клијената велике вредности. Можете одабрати да омогућите моделу да дефинише клијенте високе вредности. Користи хеуристичко правило које изводи перцентил. Клијенте високе вредности можете дефинисати као проценат клијената који ће највише плаћати у будућности. У овом водичу кроз примере, ручно дефинишемо клијенте велике вредности као **30% активних клијената који плаћају** и изаберите **Следећи**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Корак жељених опција у навођеном искуству за CLV модел.":::

1. У кораку **Потребни подаци**, изаберите **Додај податке** да бисте пружили податке о трансакцијама у претходном периоду.

1. Додајте ентитет **eCommercePurchases : eCommerce** и мапирајте атрибуте који су потребни моделу:
   - ID трансакције: eCommerce.eCommercePurchases.PurchaseId
   - Датум трансакције: eCommerce.eCommercePurchases.PurchaseId
   - Износ трансакције: eCommerce.eCommercePurchases.TotalPrice
   - ID производа: eCommerce.eCommercePurchases.ProductId

1. Изаберите **Следеће**.

1. Подесите релацију између ентитета **eCommercePurchases : eCommerce** и **eCommerceContacts : eCommerce**.

1. Корак **Додатни подаци (опционално)** вам омогућава да додате више података о активностима клијената. Ови подаци могу вам помоћи да добијете више увида о интеракцији клијената са вашим предузећем, што може допринети моделу CLV. Додавање кључних интеракција са клијентима попут веб-евиденције, евиденција корисничке службе или програма награђивања у претходном периоду може побољшати тачност предвиђања. Изаберите **Додај податке** да бисте укључили више података о активностима клијената.

1. Додајте ентитет активности клијента и мапирајте називе његових поља у одговарајућа поља која захтева модел:
   - Ентитет активности клијента: Reviews:Website
   - Примарни кључ: Website.Reviews.ReviewId
   - Временска ознака: Website.Reviews.ReviewDate
   - Догађај (назив активности): Website.Reviews.ActivityTypeDisplay
   - Детаљи (износ или вредност): Website.Reviews.ReviewRating

1. Изаберите **Следеће** и конфигуришите активност и релацију између података о трансакцији и података о клијенту:  
   - Тип активности: Одаберите постојећи
   - Ознака активности: Review
   - Одговарајућа ознака: Website.Reviews.UserId
   - Ентитет клијента: eCommerceContacts:eCommerce
   - Релација: WebsiteReviews

1. Изаберите **Даље** да бисте поставили распоред модела.

   Модел треба редовно тренирати да би научио нове обрасце када се уносе нови подаци. За овај пример, одаберите **Месечно**.

1. Након прегледа свих детаља, изаберите **Сачувај и покрени**.

## <a name="task-4---review-model-results-and-explanations"></a>4. задатак – Преглед резултата модела и објашњења

Нека модел заврши обуку и оцењивање података. Затим можете прегледати резултате и објашњења CLV модела. За више информација погледајте [Прегледајте статус и резултате предвиђања](predict-customer-lifetime-value.md#review-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-value-customers"></a>5. задатак – Креирање сегмента клијената велике вредности

Покретање модела креиран нови ентитет, који је наведен на **Подаци** > **Ентитети**. Можете да креирате нови сегмент клијената на основу ентитета који је креирао модел.

1. Идите на **Сегменти**. 

1. Изаберите **Ново**, па **Направи од** > **Обавештавање**.

   ![Креирајте сегмент са излазом модела.](media/segment-intelligence.png)

1. Изаберите ентитет **OOBeCommerceCLVPrediction** ентитет и дефинишите сегмент:
  - Поље: CLVScore
  - Оператор: веће je од
  - Вредност: 1500

1. Изаберите **Преглед** и **сачувајте** сегмент.

Сада имате сегмент који идентификује клијенте за које се предвиђа да ће остварити више од 1500 $ прихода у следећих 12 месеци. Овај сегмент се динамички ажурира ако се унесе више података.

Више информација потражите у одељку [Креирање и управљање сегментима](segments.md).