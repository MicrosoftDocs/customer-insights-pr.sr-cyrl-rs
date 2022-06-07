---
title: Пример водича за предвиђање губитка трансакција
description: Користите овај пример водича да бисте испробали спреман модел предвиђања губитка трансакција.
ms.date: 05/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3edbf2a471313379c28db874d7f19c3265a23299
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741337"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Пример водича за предвиђање губитка трансакција

Овај водич вам објашњава вам комплетан пример предвиђања губитка трансакција у услузи Customer Insights помоћу података наведених у наставку. Сви подаци коришћени у овом водичу нису стварни подаци о клијентима и део су скупа података Contoso који се налази у *Демо* окружењу у оквиру претплате на Customer Insights.

## <a name="scenario"></a>Сценарио

Contoso је компанија која производи висококвалитетну кафу и апарате за кафу, које продају путем свог веб-сајта Contoso Coffee. Циљ им је да сазнају који ће клијенти који обично редовно купују њихове производе престати да буду активни клијенти у наредних 60 дана. Када знају које клијенте ће **вероватно изгубити**, могу да уштеде на маркетиншким кампањама и фокусирају се на њихово задржавање.

## <a name="prerequisites"></a>Предуслови

- Барем [дозволе сарадника](permissions.md) у услузи Customer Insights.
- Препоручујемо да примените следеће кораке [у новом окружењу](manage-environments.md).

## <a name="task-1---ingest-data"></a>1. задатак – Унос података

Посебно прегледајте чланке [о уношењу података](data-sources.md)[и увозу извора података помоћу Power Query линија спајања](connect-power-query.md). Следеће информације претпостављају да сте се упознали са уношењем података уопште. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Унесите податке о клијентима са платформе eCommerce

1. Направите извор података под називом **eCommerce**, изаберите опцију увоза, па изаберите конектор **Text/CSV**.

1. Унесите URL адресу за eCommerce контакте https://aka.ms/ciadclasscontacts.

1. Док уређујете податке, изаберите **Трансформација**, а затим **Користи први ред као заглавља**.

1. Ажурирајте тип података за доленаведене колоне:

   - **Датум рођења**: Датум
   - **Креирано**: Датум/време/зона

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Трансформишите датум рођења у датум.":::

1. У пољу **Име** у десном окну преименујте извор података из **Упит** у **eCommerce контакти**

1. Сачувајте извор података.

### <a name="ingest-online-purchase-data"></a>Унесите податке о куповини на мрежи

1. Додајте још један скуп податка у исти **eCommerce** извор података. Поново изаберите конектор **Текст/CSV**.

1. Унесите URL за податке о **куповинама на мрежи** https://aka.ms/ciadclassonline.

1. Док уређујете податке, изаберите **Трансформација**, а затим **Користи први ред као заглавља**.

1. Ажурирајте тип података за доленаведене колоне:

   - **Купљено дана**: Датум/време
   - **Укупна цена**: Валута
   
1. У пољу **Име** у десном окну преименујте извор података из **Упит** у **eCommerce куповине**.

1. Сачувајте извор података.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Унесите податке о клијентима из шеме лојалности

1. Направите извор података под именом **Шема лојалности**, изаберите опцију увоза и изаберите **Текст/CSV** конектор.

1. Унесите URL адресу за eCommerce контакте https://aka.ms/ciadclasscustomerloyalty.

1. Док уређујете податке, изаберите **Трансформација**, а затим **Користи први ред као заглавља**.

1. Ажурирајте тип података за доленаведене колоне:

   - **Датум рођења**: Датум
   - **Наградни поени**: Цео број
   - **Креирано**: Датум/време

1. У пољу **Име** у десном окну преименујте извор података из **Упит** у **Лојални клијенти**.

1. Сачувајте извор података.

## <a name="task-2---data-unification"></a>2. задатак 2 – Обједињавање података

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-transaction-churn-prediction"></a>3. задатак – Конфигуришите предвиђање губитка трансакција

Са обједињеним профилима клијената, сада можемо да покренемо трансакцију цхурн предвиђање. Детаљне кораке погледајте чланак [Трансацтион цхурн предвиђање](predict-transactional-churn.md). 

1. Идите на **Обавештавање** > **Откријте** и изаберите да користите **Модел губитка клијената**.

1. Изаберите опцију **Трансакција** и **Започните**.

1. Назовите модел **OOB предвиђање губитка eCommerce трансакција** и излазни ентитет **OOBeCommerceChurnPrediction**.

1. Дефинишите два услова за модел губитка:

   * **Прозор предвиђања**: **најмање 60** дана. Ово подешавање дефинише колико у будућности желимо да предвидимо губитак клијената.

   * **Дефиниција губитка**: **најмање 60** дана. Трајање без куповине након којег се клијент сматра изгубљеним.

     :::image type="content" source="media/model-levers.PNG" alt-text="Изаберите регулаторе модела Временски период предвиђања и Дефиниција губитка.":::

1. Изаберите **Историја куповине (обавезно)** и **Додајте податке** за историју куповине.

1. Додајте ентитет **eCommerce куповине: eCommerce** и мапирајте поља из платформе eCommerce са одговарајућим пољима које тражи модел.

1. Придружите ентите **eCommerce куповине: eCommerce** са **eCommerce контакти: eCommerce**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Придружите eCommerce ентитете.":::

1. Изаберите **Даље** да бисте поставили распоред модела.

   Модел треба редовно да се обучава како би научио нове обрасце када дође до уноса нових података. За овај пример изаберите **Месечно**.

1. Након прегледа свих детаља, изаберите **Сачувај и покрени**.

## <a name="task-4---review-model-results-and-explanations"></a>4. задатак – Преглед резултата модела и објашњења

Нека модел заврши обуку и оцењивање података. Сада можете да прегледате објашњења модела Цхурн. За више информација погледајте [Прегледајте статус и резултате предвиђања](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>5. задатак – Креирајте сегмент клијената са високим ризиком од губитка

Покретање производног модела ствара нови ентитет који можете да видите у одељку **Подаци** > **Ентитети**.   

Можете да креирате нови сегмент на основу ентитета који је креирао модел.

1.  Идите на **Сегменти**. Изаберите **Ново**, па **Направи од** > **Обавештавање**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Креирајте сегмент са излазом модела.":::

1. Изаберите **ООБеЦоммерцеЦхурнПредицтион** крајња тачка и дефинишите сегмент: 
   - Поље: Оцена губитка
   - Оператор: веће je од
   - Вредност: 0,6

Сада имате сегмент који се динамички ажурира и који идентификује купце са високим ризиком.

Више информација потражите у одељку [Креирање и управљање сегментима](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]