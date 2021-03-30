---
title: Пример водича за предвиђање препорука производа
description: Користите овај пример водича да бисте испробали овај готови модел предвиђања препорука производа.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 20072d14b160e54f5ad044adc1de6c079bf790e4
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595291"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="fdf39-103">Пример водича за предвиђање препорука производа (преглед)</span><span class="sxs-lookup"><span data-stu-id="fdf39-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="fdf39-104">Објаснићемо вам комплетан пример предвиђања препоруке производа помоћу примера података наведених у наставку.</span><span class="sxs-lookup"><span data-stu-id="fdf39-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="fdf39-105">Сценарио</span><span class="sxs-lookup"><span data-stu-id="fdf39-105">Scenario</span></span>

<span data-ttu-id="fdf39-106">Contoso је компанија која производи висококвалитетну кафу и апарате за кафу, које продају путем свог веб-сајта Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="fdf39-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="fdf39-107">Циљ им је да разумеју које производе би требало да препоруче својим редовним клијентима.</span><span class="sxs-lookup"><span data-stu-id="fdf39-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="fdf39-108">Сазнање шта ће клијенти **вероватније купити** може им помоћи да уштеде маркетиншке напоре фокусирањем на одређене ставке.</span><span class="sxs-lookup"><span data-stu-id="fdf39-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fdf39-109">Предуслови</span><span class="sxs-lookup"><span data-stu-id="fdf39-109">Prerequisites</span></span>

- <span data-ttu-id="fdf39-110">Барем [дозволе сарадника](permissions.md) у услузи Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fdf39-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="fdf39-111">Препоручујемо да примените следеће кораке [у новом окружењу](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="fdf39-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="fdf39-112">1. задатак – Унос података</span><span class="sxs-lookup"><span data-stu-id="fdf39-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="fdf39-113">Прегледајте чланке [о уносу података](data-sources.md) и [увозу извора података помоћу Power Query конектора](connect-power-query.md) конкретно.</span><span class="sxs-lookup"><span data-stu-id="fdf39-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="fdf39-114">Следеће информације претпостављају да сте се упознали са уношењем података уопште.</span><span class="sxs-lookup"><span data-stu-id="fdf39-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="fdf39-115">Унесите податке о клијентима са платформе eCommerce</span><span class="sxs-lookup"><span data-stu-id="fdf39-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="fdf39-116">Направите извор података под именом **eCommerce**, изаберите опцију увоза и изаберите **Текст/CSV** конектор.</span><span class="sxs-lookup"><span data-stu-id="fdf39-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="fdf39-117">Унесите URL адресу за eCommerce контакте https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="fdf39-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="fdf39-118">Док уређујете податке, изаберите **Трансформација**, а затим **Користи први ред као заглавља**.</span><span class="sxs-lookup"><span data-stu-id="fdf39-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="fdf39-119">Ажурирајте тип података за доленаведене колоне:</span><span class="sxs-lookup"><span data-stu-id="fdf39-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="fdf39-120">**Датум рођења**: Датум</span><span class="sxs-lookup"><span data-stu-id="fdf39-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="fdf39-121">**Креирано**: Датум/време/зона</span><span class="sxs-lookup"><span data-stu-id="fdf39-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Трансформација датума рођења у датум.":::

5. <span data-ttu-id="fdf39-123">У пољу „Име“ у десном окну преименујте извор података из **Упит** у **eCommerce контакти**</span><span class="sxs-lookup"><span data-stu-id="fdf39-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="fdf39-124">**Сачувајте** извор података.</span><span class="sxs-lookup"><span data-stu-id="fdf39-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="fdf39-125">Унесите податке о куповини на мрежи</span><span class="sxs-lookup"><span data-stu-id="fdf39-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="fdf39-126">Додајте још један скуп податка у исти **eCommerce** извор података.</span><span class="sxs-lookup"><span data-stu-id="fdf39-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="fdf39-127">Поново изаберите конектор **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="fdf39-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="fdf39-128">Унесите URL за податке о **куповинама на мрежи** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="fdf39-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="fdf39-129">Док уређујете податке, изаберите **Трансформација**, а затим **Користи први ред као заглавља**.</span><span class="sxs-lookup"><span data-stu-id="fdf39-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="fdf39-130">Ажурирајте тип података за доленаведене колоне:</span><span class="sxs-lookup"><span data-stu-id="fdf39-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="fdf39-131">**Купљено дана**: Датум/време</span><span class="sxs-lookup"><span data-stu-id="fdf39-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="fdf39-132">**Укупна цена**: Валута</span><span class="sxs-lookup"><span data-stu-id="fdf39-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="fdf39-133">У пољу **Назив** у бочном окну преименујте извор података из **Упит** у **eCommerce куповине**.</span><span class="sxs-lookup"><span data-stu-id="fdf39-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="fdf39-134">Сачувајте извор података.</span><span class="sxs-lookup"><span data-stu-id="fdf39-134">Save the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="fdf39-135">Унесите податке о клијентима из шеме лојалности</span><span class="sxs-lookup"><span data-stu-id="fdf39-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="fdf39-136">Направите извор података под именом **Шема лојалности**, изаберите опцију увоза и изаберите **Текст/CSV** конектор.</span><span class="sxs-lookup"><span data-stu-id="fdf39-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="fdf39-137">Унесите URL адресу за eCommerce контакте https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="fdf39-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="fdf39-138">Док уређујете податке, изаберите **Трансформација**, а затим **Користи први ред као заглавља**.</span><span class="sxs-lookup"><span data-stu-id="fdf39-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="fdf39-139">Ажурирајте тип података за доленаведене колоне:</span><span class="sxs-lookup"><span data-stu-id="fdf39-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="fdf39-140">**Датум рођења**: Датум</span><span class="sxs-lookup"><span data-stu-id="fdf39-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="fdf39-141">**Наградни поени**: Цео број</span><span class="sxs-lookup"><span data-stu-id="fdf39-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="fdf39-142">**Креирано**: Датум/време</span><span class="sxs-lookup"><span data-stu-id="fdf39-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="fdf39-143">У пољу **Име** у десном окну преименујте извор података из **Упит** у **Лојални клијенти**.</span><span class="sxs-lookup"><span data-stu-id="fdf39-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="fdf39-144">Сачувајте извор података.</span><span class="sxs-lookup"><span data-stu-id="fdf39-144">Save the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="fdf39-145">2. задатак 2 – Обједињавање података</span><span class="sxs-lookup"><span data-stu-id="fdf39-145">Task 2 - Data unification</span></span>

<span data-ttu-id="fdf39-146">Након уноса података, сада започињемо процес **Мапирања, подударања, обједињавања** да бисмо креирали обједињени профил клијента.</span><span class="sxs-lookup"><span data-stu-id="fdf39-146">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="fdf39-147">За више информација погледајте [Обједињавање података](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="fdf39-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="fdf39-148">Мапирај</span><span class="sxs-lookup"><span data-stu-id="fdf39-148">Map</span></span>

1. <span data-ttu-id="fdf39-149">Након уноса података, мапирајте контакте са платформе eCommerce и из података о лојалности у уобичајене типове података.</span><span class="sxs-lookup"><span data-stu-id="fdf39-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="fdf39-150">Идите на **Подаци** > **Обједини** > **Мапирај**.</span><span class="sxs-lookup"><span data-stu-id="fdf39-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="fdf39-151">Изаберите ентитете који представљају профил клијента – **eCommerce контакти** и **Лојални клијенти**.</span><span class="sxs-lookup"><span data-stu-id="fdf39-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![обједините изворе података о платформ ecommerce и лојалности.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="fdf39-153">Изаберите **ID клијента** као примарни кључ за **eCommerce контакте** и **ID лојалности** као примарни кључ за **Лојалне клијенте**.</span><span class="sxs-lookup"><span data-stu-id="fdf39-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Обједините ID лојалности као примарни кључ.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="fdf39-155">Подударање</span><span class="sxs-lookup"><span data-stu-id="fdf39-155">Match</span></span>

1. <span data-ttu-id="fdf39-156">Идите у на картицу **Подударање** и изаберите **Подеси редослед**.</span><span class="sxs-lookup"><span data-stu-id="fdf39-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="fdf39-157">На падајућој листи **Примарно**, одаберите **eCommerce контакти: eCommerce** као примарни извор и укључите све записе.</span><span class="sxs-lookup"><span data-stu-id="fdf39-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="fdf39-158">На падајућој листи **Ентитет 2**, одаберите **Лојални клијенти: Шема лојалности** и укључите све записе.</span><span class="sxs-lookup"><span data-stu-id="fdf39-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Обједините подударање платформе eCommerce и лојалности.](media/unify-match-order.png)

4. <span data-ttu-id="fdf39-160">Изаберите **Креирај ново правило**</span><span class="sxs-lookup"><span data-stu-id="fdf39-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="fdf39-161">Додајте свој први услов користећи Име и презиме.</span><span class="sxs-lookup"><span data-stu-id="fdf39-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="fdf39-162">За eCommerce контакте одаберите **Име и презиме** на падајућој листи.</span><span class="sxs-lookup"><span data-stu-id="fdf39-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="fdf39-163">За Лојалне клијенте одаберите **Име и презиме** на падајућој листи.</span><span class="sxs-lookup"><span data-stu-id="fdf39-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="fdf39-164">Изаберите падајућу листу **Нормализација** и одаберите **Тип (телефон, име, адреса...)**.</span><span class="sxs-lookup"><span data-stu-id="fdf39-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="fdf39-165">Подесите **Ниво прецизности**: **Основни** и **Вредност**: **Висока**.</span><span class="sxs-lookup"><span data-stu-id="fdf39-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="fdf39-166">Унесите назив **Име и презиме, е-пошта** за ново правило.</span><span class="sxs-lookup"><span data-stu-id="fdf39-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="fdf39-167">Додајте други услов за адресу е-поште избором ставке **Додајте услов**</span><span class="sxs-lookup"><span data-stu-id="fdf39-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="fdf39-168">За ентитет eCommerce контакти одаберите **Е-пошта** у падајућем менију.</span><span class="sxs-lookup"><span data-stu-id="fdf39-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="fdf39-169">За ентитет Лојални клијенти одаберите **Е-пошта** у падајућем менију.</span><span class="sxs-lookup"><span data-stu-id="fdf39-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="fdf39-170">Оставите Нормализација празно.</span><span class="sxs-lookup"><span data-stu-id="fdf39-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="fdf39-171">Подесите **Ниво прецизности**: **Основни** и **Вредност**: **Висока**.</span><span class="sxs-lookup"><span data-stu-id="fdf39-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Обједините правило подударања за име и е-пошту.](media/unify-match-rule.png)

7. <span data-ttu-id="fdf39-173">Изаберите **Сачувај** и **Затвори**.</span><span class="sxs-lookup"><span data-stu-id="fdf39-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="fdf39-174">Обједини</span><span class="sxs-lookup"><span data-stu-id="fdf39-174">Merge</span></span>

1. <span data-ttu-id="fdf39-175">Идите на картицу **Обједињавање**.</span><span class="sxs-lookup"><span data-stu-id="fdf39-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="fdf39-176">На **ID контакта** за ентитет **Лојални клијенти** промените име за приказ у **ID контакта ЛОЈАЛНОСТ** да би се разликовало од осталих унетих ID-ова.</span><span class="sxs-lookup"><span data-stu-id="fdf39-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![Преименујте ID контакта из ID-а лојалности.](media/unify-merge-contactid.png)

1. <span data-ttu-id="fdf39-178">Изаберите **Сачувај** и **Покрени** да бисте започели поступак обједињавања.</span><span class="sxs-lookup"><span data-stu-id="fdf39-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="fdf39-179">Задатак 3 – Конфигуришите предвиђање препоруке производа</span><span class="sxs-lookup"><span data-stu-id="fdf39-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="fdf39-180">Када су обједињени профилима клијената спремни, сада можемо покренути предвиђање губитка претплата.</span><span class="sxs-lookup"><span data-stu-id="fdf39-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="fdf39-181">Иди на **Обавештавање** > **Предвиђање** и одаберите **Препорука производа**.</span><span class="sxs-lookup"><span data-stu-id="fdf39-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="fdf39-182">Изаберите **Први кораци**.</span><span class="sxs-lookup"><span data-stu-id="fdf39-182">Select **Get started**.</span></span>

1. <span data-ttu-id="fdf39-183">Именујте модел **Предвиђање модела препоруке OOB производа** а излазни ентитет **OOBProductRecommendationModelPrediction**.</span><span class="sxs-lookup"><span data-stu-id="fdf39-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="fdf39-184">Дефинишите три услова за модел:</span><span class="sxs-lookup"><span data-stu-id="fdf39-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="fdf39-185">**Број производа**: Подесите ову вредност на **5**.</span><span class="sxs-lookup"><span data-stu-id="fdf39-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="fdf39-186">Ово подешавање дефинише колико производа желите да препоручите својим клијентима.</span><span class="sxs-lookup"><span data-stu-id="fdf39-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="fdf39-187">**Предлажете производе које су клијенти недавно купили?**: Изаберите **Да** како бисте назначили да желите да додате производе у препоруку коју су ваши клијенти раније купили.</span><span class="sxs-lookup"><span data-stu-id="fdf39-187">**Suggest products customers have recently purchased?**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="fdf39-188">**Период за ревизију** Изаберите најмање **365 дана**.</span><span class="sxs-lookup"><span data-stu-id="fdf39-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="fdf39-189">Ово подешавање дефинише колико далеко уназад ће модел пратити активност клијента да би га користио као улаз за препоруке.</span><span class="sxs-lookup"><span data-stu-id="fdf39-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Жељена подешавања модела за модел препоруке производа.":::

1. <span data-ttu-id="fdf39-191">Изаберите **Обавезни подаци** и изаберите **Додај податке** за историју куповина.</span><span class="sxs-lookup"><span data-stu-id="fdf39-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="fdf39-192">Додајте ентитет **eCommerce куповине: eCommerce** и мапирајте поља из платформе eCommerce са одговарајућим пољима које тражи модел.</span><span class="sxs-lookup"><span data-stu-id="fdf39-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="fdf39-193">Придружите ентите **eCommerce куповине: eCommerce** са **eCommerce контакти: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="fdf39-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Придружите eCommerce ентитете.](media/model-purchase-join.png)

1. <span data-ttu-id="fdf39-195">Изаберите **Даље** да бисте поставили распоред модела.</span><span class="sxs-lookup"><span data-stu-id="fdf39-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="fdf39-196">Модел треба редовно да се обучава како би научио нове обрасце када дође до уноса нових података.</span><span class="sxs-lookup"><span data-stu-id="fdf39-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="fdf39-197">За овај пример изаберите **Месечно**.</span><span class="sxs-lookup"><span data-stu-id="fdf39-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="fdf39-198">Након прегледа свих детаља, изаберите **Сачувај и покрени**.</span><span class="sxs-lookup"><span data-stu-id="fdf39-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="fdf39-199">4. задатак – Преглед резултата модела и објашњења</span><span class="sxs-lookup"><span data-stu-id="fdf39-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="fdf39-200">Нека модел заврши обуку и оцењивање података.</span><span class="sxs-lookup"><span data-stu-id="fdf39-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="fdf39-201">Сада можете прегледати објашњења модела препорука производа.</span><span class="sxs-lookup"><span data-stu-id="fdf39-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="fdf39-202">За више информација погледајте [Прегледајте статус и резултате предвиђања](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="fdf39-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="fdf39-203">Задатак 5 – Направите сегмент производа који се често купују</span><span class="sxs-lookup"><span data-stu-id="fdf39-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="fdf39-204">Покретање производног модела ствара нови ентитет који можете да видите у одељку **Подаци** > **Ентитети**.</span><span class="sxs-lookup"><span data-stu-id="fdf39-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="fdf39-205">Можете да креирате нови сегмент на основу ентитета који је креирао модел.</span><span class="sxs-lookup"><span data-stu-id="fdf39-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="fdf39-206">Идите на **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="fdf39-206">Go to **Segments**.</span></span> <span data-ttu-id="fdf39-207">Изаберите **Ново** и **Направи од** > **Обавештавање**.</span><span class="sxs-lookup"><span data-stu-id="fdf39-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Креирајте сегмент са излазом модела.](media/segment-intelligence.png)

1. <span data-ttu-id="fdf39-209">Изаберите крајњу тачку **OOBProductRecommendationModelPrediction** и дефинишите сегмент:</span><span class="sxs-lookup"><span data-stu-id="fdf39-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="fdf39-210">Поље: ProductID</span><span class="sxs-lookup"><span data-stu-id="fdf39-210">Field: ProductID</span></span>
   - <span data-ttu-id="fdf39-211">Оператор: Вредност</span><span class="sxs-lookup"><span data-stu-id="fdf39-211">Operator: Value</span></span>
   - <span data-ttu-id="fdf39-212">Вредност: Изаберите прва три ID-а производа</span><span class="sxs-lookup"><span data-stu-id="fdf39-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Креирајте сегмент из резултата модела.":::

<span data-ttu-id="fdf39-214">Сада имате сегмент који се динамички ажурира и који идентификује клијенте који су спремнији да купе три најбоље препоручена производа</span><span class="sxs-lookup"><span data-stu-id="fdf39-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="fdf39-215">Више информација потражите у одељку [Креирање и управљање сегментима](segments.md).</span><span class="sxs-lookup"><span data-stu-id="fdf39-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]