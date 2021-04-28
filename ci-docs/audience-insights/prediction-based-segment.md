---
title: Сегменти засновани на излазу предвиђања
description: Креирајте сегменте на основу излазног ентитета модела предвиђања.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741447"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Креирање сегмента на основу модела предвиђања (преглед)

Резултати предвиђања понекад се односе само на подскуп ваших клијената. Повећајте персонализацију препорука креирањем сегмената од резултата модела предвиђања. На пример, можда ћете желети да дате конкретне препоруке клијентима који виже воле одређену врсту услуге. 

## <a name="prerequisites"></a>Предуслови

- Барем [дозволе сарадника](permissions.md) у услузи Customer Insights.

- Модел препоруке производа, губитка трансакција, губитка претплата или трајне вредности клијента конфигурисан је у услузи Customer Insights. Прегледајте захтеве за постављање различитих модела:

  - [Модел препоруке производа](predict-product-recommendation.md)
  - [Модел губитка претплата](predict-subscription-churn.md)
  - [Модел губитка трансакција](predict-transactional-churn.md)
  - [Модел трајне вредности клијента](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>Креирање сегмената клијената заснованих на предвиђањима

1. Идите на **Обавештавање** > **Предвиђања** и изаберите картицу **Моја предвиђања**.

1. Изаберите усправне три тачке поред модела који желите да прегледате и изаберите **Приказ**.

1. На страници резултата, изаберите **Направи сегмент**. За више информација о страници резултата, погледајте чланак о моделу.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Снимак екрана странице резултата предвиђања са истицањем радње „Направи сегмент“.":::

1. Креирајте нови сегмент на основу излазног ентитета изабраног модела. Више информација потражите у одељку [Креирање и управљање сегментима](segments.md).