---
title: Пример водича за предвиђање губитка претплата
description: Користите овај пример водича да бисте испробали спреман модел предвиђања губитка претплата.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 324e5c19778230dd978b2f4e9156a2dd82b3d2bd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595536"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="67624-103">Пример водича за предвиђање губитка претплата (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="67624-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="67624-104">Објаснићемо вам комплетан пример предвиђања губитка претплата помоћу примера података наведених у наставку.</span><span class="sxs-lookup"><span data-stu-id="67624-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="67624-105">Сценарио</span><span class="sxs-lookup"><span data-stu-id="67624-105">Scenario</span></span>

<span data-ttu-id="67624-106">Contoso је компанија која производи висококвалитетну кафу и апарате за кафу, које продају путем свог веб-сајта Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="67624-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="67624-107">Недавно су покренули услугу претплате како би њихови клијенти редовно добијали кафу.</span><span class="sxs-lookup"><span data-stu-id="67624-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="67624-108">Циљ им је да разумеју који претплаћени клијенти би могли отказати претплату у наредних неколико месеци.</span><span class="sxs-lookup"><span data-stu-id="67624-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="67624-109">Када знају које клијенте ће **вероватно изгубити**, могу да уштеде на маркетиншким кампањама и фокусирају се на њихово задржавање.</span><span class="sxs-lookup"><span data-stu-id="67624-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="67624-110">Предуслови</span><span class="sxs-lookup"><span data-stu-id="67624-110">Prerequisites</span></span>

- <span data-ttu-id="67624-111">Барем [дозволе сарадника](permissions.md) у услузи Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="67624-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="67624-112">Препоручујемо да примените следеће кораке [у новом окружењу](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="67624-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="67624-113">1. задатак – Унос података</span><span class="sxs-lookup"><span data-stu-id="67624-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="67624-114">Прегледајте чланке [о уносу података](data-sources.md) и [увозу извора података помоћу Power Query конектора](connect-power-query.md) конкретно.</span><span class="sxs-lookup"><span data-stu-id="67624-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="67624-115">Следеће информације претпостављају да сте се упознали са уношењем података уопште.</span><span class="sxs-lookup"><span data-stu-id="67624-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="67624-116">Унесите податке о клијентима са платформе eCommerce</span><span class="sxs-lookup"><span data-stu-id="67624-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="67624-117">Направите извор података под именом **eCommerce**, изаберите опцију увоза и изаберите **Текст/CSV** конектор.</span><span class="sxs-lookup"><span data-stu-id="67624-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="67624-118">Унесите URL адресу за eCommerce контакте https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="67624-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="67624-119">Док уређујете податке, изаберите **Трансформација**, а затим **Користи први ред као заглавља**.</span><span class="sxs-lookup"><span data-stu-id="67624-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="67624-120">Ажурирајте тип података за доленаведене колоне:</span><span class="sxs-lookup"><span data-stu-id="67624-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="67624-121">**Датум рођења**: Датум</span><span class="sxs-lookup"><span data-stu-id="67624-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="67624-122">**Креирано**: Датум/време/зона</span><span class="sxs-lookup"><span data-stu-id="67624-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Трансформација датума рођења у датум.":::

1. <span data-ttu-id="67624-124">У пољу **Име** у десном окну преименујте извор података из **Упит** у **eCommerce контакти**</span><span class="sxs-lookup"><span data-stu-id="67624-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="67624-125">Сачувајте извор података.</span><span class="sxs-lookup"><span data-stu-id="67624-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="67624-126">Унесите податке о клијентима из шеме лојалности</span><span class="sxs-lookup"><span data-stu-id="67624-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="67624-127">Направите извор података под именом **Шема лојалности**, изаберите опцију увоза и изаберите **Текст/CSV** конектор.</span><span class="sxs-lookup"><span data-stu-id="67624-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="67624-128">Унесите URL адресу за eCommerce контакте https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="67624-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="67624-129">Док уређујете податке, изаберите **Трансформација**, а затим **Користи први ред као заглавља**.</span><span class="sxs-lookup"><span data-stu-id="67624-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="67624-130">Ажурирајте тип података за доленаведене колоне:</span><span class="sxs-lookup"><span data-stu-id="67624-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="67624-131">**Датум рођења**: Датум</span><span class="sxs-lookup"><span data-stu-id="67624-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="67624-132">**Наградни поени**: Цео број</span><span class="sxs-lookup"><span data-stu-id="67624-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="67624-133">**Креирано**: Датум/време</span><span class="sxs-lookup"><span data-stu-id="67624-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="67624-134">У пољу **Име** у десном окну преименујте извор података из **Упит** у **Лојални клијенти**.</span><span class="sxs-lookup"><span data-stu-id="67624-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="67624-135">Сачувајте извор података.</span><span class="sxs-lookup"><span data-stu-id="67624-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="67624-136">Унос информација о претплати</span><span class="sxs-lookup"><span data-stu-id="67624-136">Ingest subscription information</span></span>

1. <span data-ttu-id="67624-137">Направите извор података под именом **Историја претплата**, изаберите опцију увоза и изаберите **Текст/CSV** конектор.</span><span class="sxs-lookup"><span data-stu-id="67624-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="67624-138">Унесите URL адресу за eCommerce контакте https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="67624-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="67624-139">Док уређујете податке, изаберите **Трансформација**, а затим **Користи први ред као заглавља**.</span><span class="sxs-lookup"><span data-stu-id="67624-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="67624-140">Ажурирајте тип података за доленаведене колоне:</span><span class="sxs-lookup"><span data-stu-id="67624-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="67624-141">**ID претплате**: Цео број</span><span class="sxs-lookup"><span data-stu-id="67624-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="67624-142">**Износ претплате**: Валута</span><span class="sxs-lookup"><span data-stu-id="67624-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="67624-143">**Датум завршетка претплате**: Датум/време</span><span class="sxs-lookup"><span data-stu-id="67624-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="67624-144">**Датум почетка претплате**: Датум/време</span><span class="sxs-lookup"><span data-stu-id="67624-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="67624-145">**Датум трансакције**: Датум/време</span><span class="sxs-lookup"><span data-stu-id="67624-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="67624-146">**Да ли се понавља**: Тачно/нетачно</span><span class="sxs-lookup"><span data-stu-id="67624-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="67624-147">**Да_ли_се_аутоматски_обнавља**: Тачно/нетачно</span><span class="sxs-lookup"><span data-stu-id="67624-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="67624-148">**Учесталост понављања у месецима**: Цео број</span><span class="sxs-lookup"><span data-stu-id="67624-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="67624-149">У пољу **Име** у десном окну преименујте извор података из **Упит** у **Историја претплата**.</span><span class="sxs-lookup"><span data-stu-id="67624-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="67624-150">Сачувајте извор података.</span><span class="sxs-lookup"><span data-stu-id="67624-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="67624-151">Унесите податке о клијентима из рецензија на веб-сајту</span><span class="sxs-lookup"><span data-stu-id="67624-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="67624-152">Направите извор података под именом **Веб-сајт**, изаберите опцију увоза и изаберите **Текст/CSV** конектор.</span><span class="sxs-lookup"><span data-stu-id="67624-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="67624-153">Унесите URL адресу за eCommerce контакте https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="67624-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="67624-154">Док уређујете податке, изаберите **Трансформација**, а затим **Користи први ред као заглавља**.</span><span class="sxs-lookup"><span data-stu-id="67624-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="67624-155">Ажурирајте тип података за доленаведене колоне:</span><span class="sxs-lookup"><span data-stu-id="67624-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="67624-156">**Оцена из рецензија**: Цео број</span><span class="sxs-lookup"><span data-stu-id="67624-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="67624-157">**Датум рецензије**: Датум</span><span class="sxs-lookup"><span data-stu-id="67624-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="67624-158">У пољу „Име“ у десном окну преименујте извор података из **Упит** у **Рецензије на вебу**.</span><span class="sxs-lookup"><span data-stu-id="67624-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="67624-159">2. задатак 2 – Обједињавање података</span><span class="sxs-lookup"><span data-stu-id="67624-159">Task 2 - Data unification</span></span>

<span data-ttu-id="67624-160">Након уноса података, сада започињемо процес **Мапирања, подударања, обједињавања** да бисмо креирали обједињени профил клијента.</span><span class="sxs-lookup"><span data-stu-id="67624-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="67624-161">За више информација погледајте [Обједињавање података](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="67624-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="67624-162">Мапирај</span><span class="sxs-lookup"><span data-stu-id="67624-162">Map</span></span>

1. <span data-ttu-id="67624-163">Након уноса података, мапирајте контакте са платформе eCommerce и из података о лојалности у уобичајене типове података.</span><span class="sxs-lookup"><span data-stu-id="67624-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="67624-164">Идите на **Подаци** > **Обједини** > **Мапирај**.</span><span class="sxs-lookup"><span data-stu-id="67624-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="67624-165">Изаберите ентитете који представљају профил клијента – **eCommerce контакти** и **Лојални клијенти**.</span><span class="sxs-lookup"><span data-stu-id="67624-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="обједините изворе података о платформ ecommerce и лојалности.":::

1. <span data-ttu-id="67624-167">Изаберите **ID клијента** као примарни кључ за **eCommerce контакте** и **ID лојалности** као примарни кључ за **Лојалне клијенте**.</span><span class="sxs-lookup"><span data-stu-id="67624-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Обједините ID лојалности као примарни кључ.":::

### <a name="match"></a><span data-ttu-id="67624-169">Подударање</span><span class="sxs-lookup"><span data-stu-id="67624-169">Match</span></span>

1. <span data-ttu-id="67624-170">Идите у на картицу **Подударање** и изаберите **Подеси редослед**.</span><span class="sxs-lookup"><span data-stu-id="67624-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="67624-171">На падајућој листи **Примарно**, одаберите **eCommerce контакти: eCommerce** као примарни извор и укључите све записе.</span><span class="sxs-lookup"><span data-stu-id="67624-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="67624-172">На падајућој листи **Ентитет 2**, одаберите **Лојални клијенти: Шема лојалности** и укључите све записе.</span><span class="sxs-lookup"><span data-stu-id="67624-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Обједините подударање платформе eCommerce и лојалности.":::

1. <span data-ttu-id="67624-174">Изаберите **Креирај ново правило**</span><span class="sxs-lookup"><span data-stu-id="67624-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="67624-175">Додајте свој први услов користећи Име и презиме.</span><span class="sxs-lookup"><span data-stu-id="67624-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="67624-176">За eCommerce контакте одаберите **Име и презиме** на падајућој листи.</span><span class="sxs-lookup"><span data-stu-id="67624-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="67624-177">За Лојалне клијенте одаберите **Име и презиме** на падајућој листи.</span><span class="sxs-lookup"><span data-stu-id="67624-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="67624-178">Изаберите падајућу листу **Нормализација** и одаберите **Тип (телефон, име, адреса...)**.</span><span class="sxs-lookup"><span data-stu-id="67624-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="67624-179">Подесите **Ниво прецизности**: **Основни** и **Вредност**: **Висока**.</span><span class="sxs-lookup"><span data-stu-id="67624-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="67624-180">Унесите назив **Име и презиме, е-пошта** за ново правило.</span><span class="sxs-lookup"><span data-stu-id="67624-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="67624-181">Додајте други услов за адресу е-поште избором ставке **Додајте услов**</span><span class="sxs-lookup"><span data-stu-id="67624-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="67624-182">За ентитет eCommerce контакти одаберите **Е-пошта** у падајућем менију.</span><span class="sxs-lookup"><span data-stu-id="67624-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="67624-183">За ентитет Лојални клијенти одаберите **Е-пошта** у падајућем менију.</span><span class="sxs-lookup"><span data-stu-id="67624-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="67624-184">Оставите Нормализација празно.</span><span class="sxs-lookup"><span data-stu-id="67624-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="67624-185">Подесите **Ниво прецизности**: **Основни** и **Вредност**: **Висока**.</span><span class="sxs-lookup"><span data-stu-id="67624-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Обједините правило подударања за име и е-пошту.":::

7. <span data-ttu-id="67624-187">Изаберите **Сачувај** и **Затвори**.</span><span class="sxs-lookup"><span data-stu-id="67624-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="67624-188">Обједини</span><span class="sxs-lookup"><span data-stu-id="67624-188">Merge</span></span>

1. <span data-ttu-id="67624-189">Идите на картицу **Обједињавање**.</span><span class="sxs-lookup"><span data-stu-id="67624-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="67624-190">На **ID контакта** за ентитет **Лојални клијенти** промените име за приказ у **ID контакта ЛОЈАЛНОСТ** да би се разликовало од осталих унетих ID-ова.</span><span class="sxs-lookup"><span data-stu-id="67624-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="Преименујте ID контакта из ID-а лојалности.":::

1. <span data-ttu-id="67624-192">Изаберите **Сачувај** и **Покрени** да бисте започели поступак обједињавања.</span><span class="sxs-lookup"><span data-stu-id="67624-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="67624-193">3. задатак – Конфигуришите предвиђање губитка претплата</span><span class="sxs-lookup"><span data-stu-id="67624-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="67624-194">Када су обједињени профилима клијената спремни, сада можемо покренути предвиђање губитка претплата.</span><span class="sxs-lookup"><span data-stu-id="67624-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="67624-195">За детаљне кораке погледајте чланак [Предвиђање губитка претплата (верзија за преглед)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="67624-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="67624-196">Идите на **Обавештавање** > **Откријте** и изаберите да користите **Модел губитка клијената**.</span><span class="sxs-lookup"><span data-stu-id="67624-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="67624-197">Изаберите опцију **Претплата** и **Започните**.</span><span class="sxs-lookup"><span data-stu-id="67624-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="67624-198">Назовите модел **OOB предвиђање губитка клијената** и излазни ентитет **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="67624-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="67624-199">Дефинишите два услова за модел губитка:</span><span class="sxs-lookup"><span data-stu-id="67624-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="67624-200">**Број дана од завршетка претплате**: **најмање 60** дана.</span><span class="sxs-lookup"><span data-stu-id="67624-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="67624-201">Ако клијент не обнови претплату у овом периоду након њеног завршетка, сматра се да сте га изгубили.</span><span class="sxs-lookup"><span data-stu-id="67624-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="67624-202">**Дефиниција губитка**: **најмање 93** дана.</span><span class="sxs-lookup"><span data-stu-id="67624-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="67624-203">Трајање током којег може доћи до губитка клијената, по предвиђању модела.</span><span class="sxs-lookup"><span data-stu-id="67624-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="67624-204">Што даље гледате у будућност, то су резултати мање прецизни.</span><span class="sxs-lookup"><span data-stu-id="67624-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Изаберите регулаторе модела Временски период предвиђања и Дефиниција губитка.":::

1. <span data-ttu-id="67624-206">Изаберите **Додајте потребне податке** и **Додајте податке** за историју претплата.</span><span class="sxs-lookup"><span data-stu-id="67624-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="67624-207">Додајте ентитет **Претплата: Историја претплата** и мапирајте поља из платформе eCommerce са одговарајућим пољима које тражи модел.</span><span class="sxs-lookup"><span data-stu-id="67624-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="67624-208">Придружите ентитет **Претплата: Историја претплата** са **eCommerce контакти: eCommerce**, именујте однос **eCommerce претплата**.</span><span class="sxs-lookup"><span data-stu-id="67624-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Придружите eCommerce ентитете.":::

1. <span data-ttu-id="67624-210">У оквиру Активности клијената додајте ентитет **Рецензије на вебу: Веб-сајт** и мапирајте поља из Рецензија на вебу са одговарајућим пољима која тражи модел.</span><span class="sxs-lookup"><span data-stu-id="67624-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="67624-211">Примарни кључ: ID рецензије</span><span class="sxs-lookup"><span data-stu-id="67624-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="67624-212">Временска ознака: Датум рецензије</span><span class="sxs-lookup"><span data-stu-id="67624-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="67624-213">Догађај: Оцена из рецензија</span><span class="sxs-lookup"><span data-stu-id="67624-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="67624-214">Конфигуришите активност за рецензије са веб-сајта.</span><span class="sxs-lookup"><span data-stu-id="67624-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="67624-215">Изаберите активност **Рецензија** и придружите ентитет **Рецензије на вебу: Веб-сајт** са **eCommerce контакти: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="67624-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="67624-216">Изаберите **Даље** да бисте поставили распоред модела.</span><span class="sxs-lookup"><span data-stu-id="67624-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="67624-217">Модел треба редовно да се обучава како би научио нове обрасце када дође до уноса нових података.</span><span class="sxs-lookup"><span data-stu-id="67624-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="67624-218">За овај пример изаберите **Месечно**.</span><span class="sxs-lookup"><span data-stu-id="67624-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="67624-219">Након прегледа свих детаља, изаберите **Сачувај и покрени**.</span><span class="sxs-lookup"><span data-stu-id="67624-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="67624-220">4. задатак – Преглед резултата модела и објашњења</span><span class="sxs-lookup"><span data-stu-id="67624-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="67624-221">Нека модел заврши обуку и оцењивање података.</span><span class="sxs-lookup"><span data-stu-id="67624-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="67624-222">Сада можете прегледати објашњења модела губитка претплата.</span><span class="sxs-lookup"><span data-stu-id="67624-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="67624-223">За више информација погледајте [Прегледајте статус и резултате предвиђања](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="67624-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="67624-224">5. задатак – Креирајте сегмент клијената са високим ризиком од губитка</span><span class="sxs-lookup"><span data-stu-id="67624-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="67624-225">Покретање производног модела ствара нови ентитет који можете да видите у одељку **Подаци** > **Ентитети**.</span><span class="sxs-lookup"><span data-stu-id="67624-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="67624-226">Можете да креирате нови сегмент на основу ентитета који је креирао модел.</span><span class="sxs-lookup"><span data-stu-id="67624-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="67624-227">Идите на **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="67624-227">Go to **Segments**.</span></span> <span data-ttu-id="67624-228">Изаберите **Ново** и **Направи од** > **Обавештавање**.</span><span class="sxs-lookup"><span data-stu-id="67624-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Креирајте сегмент са излазом модела.":::

1. <span data-ttu-id="67624-230">Изаберите крајњу тачку **OOB предвиђање губитка клијената** и дефинишите сегмент:</span><span class="sxs-lookup"><span data-stu-id="67624-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="67624-231">Поље: Оцена губитка</span><span class="sxs-lookup"><span data-stu-id="67624-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="67624-232">Оператор: веће je од</span><span class="sxs-lookup"><span data-stu-id="67624-232">Operator: greater than</span></span>
   - <span data-ttu-id="67624-233">Вредност: 0,6</span><span class="sxs-lookup"><span data-stu-id="67624-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Подесите сегмент губитка претплате.":::

<span data-ttu-id="67624-235">Сада имате сегмент који се динамички ажурира и који идентификује клијенте са високим ризиком од губитка за ову услугу претплате.</span><span class="sxs-lookup"><span data-stu-id="67624-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="67624-236">Више информација потражите у одељку [Креирање и управљање сегментима](segments.md).</span><span class="sxs-lookup"><span data-stu-id="67624-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]