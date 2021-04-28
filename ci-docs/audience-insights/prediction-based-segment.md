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
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="da6f6-103">Креирање сегмента на основу модела предвиђања (преглед)</span><span class="sxs-lookup"><span data-stu-id="da6f6-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="da6f6-104">Резултати предвиђања понекад се односе само на подскуп ваших клијената.</span><span class="sxs-lookup"><span data-stu-id="da6f6-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="da6f6-105">Повећајте персонализацију препорука креирањем сегмената од резултата модела предвиђања.</span><span class="sxs-lookup"><span data-stu-id="da6f6-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="da6f6-106">На пример, можда ћете желети да дате конкретне препоруке клијентима који виже воле одређену врсту услуге.</span><span class="sxs-lookup"><span data-stu-id="da6f6-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="da6f6-107">Предуслови</span><span class="sxs-lookup"><span data-stu-id="da6f6-107">Prerequisites</span></span>

- <span data-ttu-id="da6f6-108">Барем [дозволе сарадника](permissions.md) у услузи Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="da6f6-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="da6f6-109">Модел препоруке производа, губитка трансакција, губитка претплата или трајне вредности клијента конфигурисан је у услузи Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="da6f6-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="da6f6-110">Прегледајте захтеве за постављање различитих модела:</span><span class="sxs-lookup"><span data-stu-id="da6f6-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="da6f6-111">Модел препоруке производа</span><span class="sxs-lookup"><span data-stu-id="da6f6-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="da6f6-112">Модел губитка претплата</span><span class="sxs-lookup"><span data-stu-id="da6f6-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="da6f6-113">Модел губитка трансакција</span><span class="sxs-lookup"><span data-stu-id="da6f6-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="da6f6-114">Модел трајне вредности клијента</span><span class="sxs-lookup"><span data-stu-id="da6f6-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="da6f6-115">Креирање сегмената клијената заснованих на предвиђањима</span><span class="sxs-lookup"><span data-stu-id="da6f6-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="da6f6-116">Идите на **Обавештавање** > **Предвиђања** и изаберите картицу **Моја предвиђања**.</span><span class="sxs-lookup"><span data-stu-id="da6f6-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="da6f6-117">Изаберите усправне три тачке поред модела који желите да прегледате и изаберите **Приказ**.</span><span class="sxs-lookup"><span data-stu-id="da6f6-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="da6f6-118">На страници резултата, изаберите **Направи сегмент**.</span><span class="sxs-lookup"><span data-stu-id="da6f6-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="da6f6-119">За више информација о страници резултата, погледајте чланак о моделу.</span><span class="sxs-lookup"><span data-stu-id="da6f6-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Снимак екрана странице резултата предвиђања са истицањем радње „Направи сегмент“.":::

1. <span data-ttu-id="da6f6-121">Креирајте нови сегмент на основу излазног ентитета изабраног модела.</span><span class="sxs-lookup"><span data-stu-id="da6f6-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="da6f6-122">Више информација потражите у одељку [Креирање и управљање сегментима](segments.md).</span><span class="sxs-lookup"><span data-stu-id="da6f6-122">For more information, see [Create and manage segments](segments.md).</span></span>