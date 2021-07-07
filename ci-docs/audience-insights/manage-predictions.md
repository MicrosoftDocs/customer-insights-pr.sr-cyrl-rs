---
title: Заједнички задаци за сценарије предвиђања
description: Научите како да управљате предвиђањима, решавате их и прецизирате.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: dccb8dcca8f65f64973e46fed9d83034d58282e2
ms.sourcegitcommit: bcc47d15d4f0eacf008e4dbc09baac7f062b3ca8
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315896"
---
# <a name="manage-predictions"></a><span data-ttu-id="00002-103">Управљање предвиђањима</span><span class="sxs-lookup"><span data-stu-id="00002-103">Manage predictions</span></span>

<span data-ttu-id="00002-104">Овај чланак говори о неким задацима које дели већина сценарија предвиђања.</span><span class="sxs-lookup"><span data-stu-id="00002-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="00002-105">Решите проблем са неуспелим предвиђањем</span><span class="sxs-lookup"><span data-stu-id="00002-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="00002-106">Идите на **Обавештавање** > **Предвиђања** и изаберите картицу **Моја предвиђања**.</span><span class="sxs-lookup"><span data-stu-id="00002-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="00002-107">Изаберите вертикалне три тачке поред предвиђања за који желите да прегледате евиденције грешака.</span><span class="sxs-lookup"><span data-stu-id="00002-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="00002-108">Изаберите **Евиденције**.</span><span class="sxs-lookup"><span data-stu-id="00002-108">Select **Logs**.</span></span>

1. <span data-ttu-id="00002-109">Прегледајте све грешке.</span><span class="sxs-lookup"><span data-stu-id="00002-109">Review all the errors.</span></span> <span data-ttu-id="00002-110">Може се појавити неколико врста грешака и оне описују услов који је довео до грешке.</span><span class="sxs-lookup"><span data-stu-id="00002-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="00002-111">На пример, грешка да нема довољно података за тачно предвиђање обично се решава учитавањем додатних података у Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="00002-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="00002-112">Извештај о употребљивости улазних података</span><span class="sxs-lookup"><span data-stu-id="00002-112">Input data usability report</span></span>

<span data-ttu-id="00002-113">Извештај о употребљивости улазних података пружа консолидовани приказ грешака и упозорења која могу произвести ваша готова предвиђања.</span><span class="sxs-lookup"><span data-stu-id="00002-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="00002-114">Такође даје препоруке како да побољшате перформансе модела.</span><span class="sxs-lookup"><span data-stu-id="00002-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="00002-115">Извештај је доступан након што модел заврши свој процес обуке.</span><span class="sxs-lookup"><span data-stu-id="00002-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="00002-116">Креира се за сваки модел посебно, без обзира на то да ли је успешно завршен или не.</span><span class="sxs-lookup"><span data-stu-id="00002-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="00002-117">Погледајте извештај о употребљивости улазних података</span><span class="sxs-lookup"><span data-stu-id="00002-117">View the input data usability report</span></span>

<span data-ttu-id="00002-118">Када готов модел заврши свој корак обуке, погледајте извештај:</span><span class="sxs-lookup"><span data-stu-id="00002-118">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="00002-119">Изаберите три тачке поред назива модела и одаберите **Извештај о употребљивости улазних података**.</span><span class="sxs-lookup"><span data-stu-id="00002-119">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="00002-120">Изаберите статус модела и изаберите **Погледајте извештај о употребљивости улазних података** у бочном окну.</span><span class="sxs-lookup"><span data-stu-id="00002-120">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="00002-121">Изаберите један од модела са листе и изаберите **Извештај о употребљивости улазних података** у командној траци.</span><span class="sxs-lookup"><span data-stu-id="00002-121">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="00002-122">Отворите страницу резултата модела и изаберите **Извештај о употребљивости улазних података** у командној траци.</span><span class="sxs-lookup"><span data-stu-id="00002-122">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="00002-123">Информације у извештају о употребљивости улазних података</span><span class="sxs-lookup"><span data-stu-id="00002-123">Information in the input data usability report</span></span>

<span data-ttu-id="00002-124">Следеће колоне у извештају садрже корисне информације за побољшање података за модел.</span><span class="sxs-lookup"><span data-stu-id="00002-124">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Пример извештаја о употребљивости улазних података који приказује табелу са грешкама, упозорењима и препорукама.":::

- <span data-ttu-id="00002-126">Назив: Описни назив грешке, упозорења или препоруке.</span><span class="sxs-lookup"><span data-stu-id="00002-126">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="00002-127">Корак: Фаза модела, обуке или резултата на коју се информације односе.</span><span class="sxs-lookup"><span data-stu-id="00002-127">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="00002-128">Статус: Озбиљност информација (грешка, упозорење, препорука).</span><span class="sxs-lookup"><span data-stu-id="00002-128">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="00002-129">Назив колоне: Колона у ентитету коју треба изменити да би се побољшале перформансе модела.</span><span class="sxs-lookup"><span data-stu-id="00002-129">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="00002-130">Назив ентитета: Назив ентитета који треба изменити да би се побољшале перформансе модела.</span><span class="sxs-lookup"><span data-stu-id="00002-130">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="00002-131">Детаљи: Детаљи о грешци, упозорењу или препоруци.</span><span class="sxs-lookup"><span data-stu-id="00002-131">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="00002-132">Освежавање предвиђања</span><span class="sxs-lookup"><span data-stu-id="00002-132">Refresh a prediction</span></span>

<span data-ttu-id="00002-133">Предвиђања се аутоматски освежавају према истом [распореду за освежавање података](system.md#schedule-tab), као што је конфигурисано у подешавањима.</span><span class="sxs-lookup"><span data-stu-id="00002-133">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="00002-134">Можете их освежити и ручно.</span><span class="sxs-lookup"><span data-stu-id="00002-134">You can refresh them manually too.</span></span>

1. <span data-ttu-id="00002-135">Идите на **Обавештавање** > **Предвиђања** и изаберите картицу **Моја предвиђања**.</span><span class="sxs-lookup"><span data-stu-id="00002-135">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="00002-136">Одаберите усправне три тачке поред предвиђања које желите да освежите.</span><span class="sxs-lookup"><span data-stu-id="00002-136">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="00002-137">Изаберите **Освежи**.</span><span class="sxs-lookup"><span data-stu-id="00002-137">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="00002-138">Брисање предвиђања</span><span class="sxs-lookup"><span data-stu-id="00002-138">Delete a prediction</span></span>

<span data-ttu-id="00002-139">Брисањем предвиђања уклања се и његов излазни ентитет.</span><span class="sxs-lookup"><span data-stu-id="00002-139">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="00002-140">Идите на **Обавештавање** > **Предвиђања** и изаберите картицу **Моја предвиђања**.</span><span class="sxs-lookup"><span data-stu-id="00002-140">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="00002-141">Одаберите усправне три тачке поред предвиђања које желите да избришете.</span><span class="sxs-lookup"><span data-stu-id="00002-141">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="00002-142">Изаберите **Избриши**.</span><span class="sxs-lookup"><span data-stu-id="00002-142">Select **Delete**.</span></span>
