---
title: Преглед подржаних сценарија предвиђања
description: Сценарији и опције предвиђања покривени су апликацијом Dynamics 365 Customer Insights.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095747"
---
# <a name="predictions-overview"></a><span data-ttu-id="9d4a9-103">Преглед предвиђања</span><span class="sxs-lookup"><span data-stu-id="9d4a9-103">Predictions overview</span></span>

<span data-ttu-id="9d4a9-104">Dynamics 365 Customer Insights долази са разним опцијама које користе вештачка интелигенција и машинско учење за предвиђање података.</span><span class="sxs-lookup"><span data-stu-id="9d4a9-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="9d4a9-105">Готови модели</span><span class="sxs-lookup"><span data-stu-id="9d4a9-105">Out-of-box models</span></span>

<span data-ttu-id="9d4a9-106">Најлакши начин да започнете са предвиђањем података су унапред дефинисани модели, који се често називају „готови модели“.</span><span class="sxs-lookup"><span data-stu-id="9d4a9-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="9d4a9-107">Они само захтевају одређене податке и структуру да би брзо стекли увид.</span><span class="sxs-lookup"><span data-stu-id="9d4a9-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="9d4a9-108">Тренутно су доступни следећи модели:</span><span class="sxs-lookup"><span data-stu-id="9d4a9-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="9d4a9-109">[Трајна вредност клијента](predict-customer-lifetime-value.md): Предвиђа потенцијални приход клијента током читаве интеракције са предузећем.</span><span class="sxs-lookup"><span data-stu-id="9d4a9-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="9d4a9-110">[Препорука производа](predict-product-recommendation.md): Предлаже скупове предиктивних препорука за производе на основу понашања у куповини и клијената са сличним обрасцима куповине.</span><span class="sxs-lookup"><span data-stu-id="9d4a9-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="9d4a9-111">[Губитак претплате](predict-subscription-churn.md): Предвиђа да ли је клијент угрожен због тога што више не користи претплаћене производе или услуге вашег предузећа.</span><span class="sxs-lookup"><span data-stu-id="9d4a9-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="9d4a9-112">[Губитак трансакција](predict-transactional-churn.md): Предвидите да ли клијент више неће куповати ваше производе или услуге у одређеном временском оквиру.</span><span class="sxs-lookup"><span data-stu-id="9d4a9-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="9d4a9-113">Интеграција Azure машинског учења</span><span class="sxs-lookup"><span data-stu-id="9d4a9-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="9d4a9-114">Ако организација већ користи сценарије машинског учења засноване на експериментима Azure машинског учења, функција прилагођених модела у услузи Customer Insights помаже у повезивању тачака.</span><span class="sxs-lookup"><span data-stu-id="9d4a9-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="9d4a9-115">Направите токове посла који вам помажу да одаберете податке од којих желите да генеришете увиде и мапирате резултате у своје обједињене профиле клијената.</span><span class="sxs-lookup"><span data-stu-id="9d4a9-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="9d4a9-116">За више информација погледајте [Прилагођени модели машинског учења](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="9d4a9-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="9d4a9-117">AI Builder предвиђање</span><span class="sxs-lookup"><span data-stu-id="9d4a9-117">AI Builder prediction</span></span>

<span data-ttu-id="9d4a9-118">Понекад су скупови података непотпуни, а неке вредности недостају.</span><span class="sxs-lookup"><span data-stu-id="9d4a9-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="9d4a9-119">Customer Insights може помоћи у предвиђању вредности које недостају за ентитет и сегменте клијента.</span><span class="sxs-lookup"><span data-stu-id="9d4a9-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="9d4a9-120">За више информација, погледајте [Допуните своје делимичне податке предвиђањима](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="9d4a9-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
