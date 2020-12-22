---
title: Пример водича за предвиђање губитка трансакција
description: Користите овај пример водича да бисте испробали спреман модел предвиђања губитка трансакција.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 055708ed3f9f468cad83ecf976a460814bf05199
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643611"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="2fb5c-103">Пример водича за предвиђање губитка трансакција (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="2fb5c-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="2fb5c-104">Овај водич вам објашњава вам комплетан пример предвиђања губитка трансакција у услузи Customer Insights помоћу података наведених у наставку.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="2fb5c-105">Сви подаци коришћени у овом водичу нису стварни подаци о клијентима и део су скупа података Contoso који се налази у *Демо* окружењу у оквиру претплате на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="2fb5c-106">Сценарио</span><span class="sxs-lookup"><span data-stu-id="2fb5c-106">Scenario</span></span>

<span data-ttu-id="2fb5c-107">Contoso је компанија која производи висококвалитетну кафу и апарате за кафу, које продају путем свог веб-сајта Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="2fb5c-108">Циљ им је да сазнају који ће клијенти који обично редовно купују њихове производе престати да буду активни клијенти у наредних 60 дана.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="2fb5c-109">Када знају које клијенте ће **вероватно изгубити**, могу да уштеде на маркетиншким кампањама и фокусирају се на њихово задржавање.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2fb5c-110">Предуслови</span><span class="sxs-lookup"><span data-stu-id="2fb5c-110">Prerequisites</span></span>

- <span data-ttu-id="2fb5c-111">Барем [дозволе сарадника](permissions.md) у услузи Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="2fb5c-112">Препоручујемо да примените следеће кораке [у новом окружењу](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="2fb5c-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="2fb5c-113">1. задатак – Унос података</span><span class="sxs-lookup"><span data-stu-id="2fb5c-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="2fb5c-114">Прегледајте чланке [о уносу података](data-sources.md) и [увозу извора података помоћу Power Query конектора](connect-power-query.md) конкретно.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="2fb5c-115">Следеће информације претпостављају да сте се упознали са уношењем података уопште.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="2fb5c-116">Унесите податке о клијентима са платформе eCommerce</span><span class="sxs-lookup"><span data-stu-id="2fb5c-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="2fb5c-117">Направите извор података под именом **eCommerce**, изаберите опцију увоза и изаберите **Текст/CSV** конектор.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="2fb5c-118">Унесите URL адресу за eCommerce контакте https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="2fb5c-119">Док уређујете податке, изаберите **Трансформација**, а затим **Користи први ред као заглавља**.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="2fb5c-120">Ажурирајте тип података за доленаведене колоне:</span><span class="sxs-lookup"><span data-stu-id="2fb5c-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="2fb5c-121">**Датум рођења**: Датум</span><span class="sxs-lookup"><span data-stu-id="2fb5c-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="2fb5c-122">**Креирано**: Датум/време/зона</span><span class="sxs-lookup"><span data-stu-id="2fb5c-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="2fb5c-123">![Трансформиши датум рођења у датум](media/ecommerce-dob-date.PNG "трансформација датума рођења у датум")</span><span class="sxs-lookup"><span data-stu-id="2fb5c-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="2fb5c-124">У пољу „Име“ у десном окну преименујте извор података из **Упит** у **eCommerce контакти**</span><span class="sxs-lookup"><span data-stu-id="2fb5c-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="2fb5c-125">Сачувајте извор података.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="2fb5c-126">Унесите податке о куповини на мрежи</span><span class="sxs-lookup"><span data-stu-id="2fb5c-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="2fb5c-127">Додајте још један скуп податка у исти **eCommerce** извор података.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="2fb5c-128">Поново изаберите конектор **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="2fb5c-129">Унесите URL за податке о **куповинама на мрежи** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="2fb5c-130">Док уређујете податке, изаберите **Трансформација**, а затим **Користи први ред као заглавља**.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="2fb5c-131">Ажурирајте тип података за доленаведене колоне:</span><span class="sxs-lookup"><span data-stu-id="2fb5c-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="2fb5c-132">**Купљено дана**: Датум/време</span><span class="sxs-lookup"><span data-stu-id="2fb5c-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="2fb5c-133">**Укупна цена**: Валута</span><span class="sxs-lookup"><span data-stu-id="2fb5c-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="2fb5c-134">У пољу „Име“ у десном окну преименујте извор података из **Упит** у **eCommerce куповине**.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-134">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="2fb5c-135">Сачувајте извор података.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="2fb5c-136">Унесите податке о клијентима из шеме лојалности</span><span class="sxs-lookup"><span data-stu-id="2fb5c-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="2fb5c-137">Направите извор података под именом **Шема лојалности**, изаберите опцију увоза и изаберите **Текст/CSV** конектор.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="2fb5c-138">Унесите URL адресу за eCommerce контакте https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="2fb5c-139">Док уређујете податке, изаберите **Трансформација**, а затим **Користи први ред као заглавља**.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="2fb5c-140">Ажурирајте тип података за доленаведене колоне:</span><span class="sxs-lookup"><span data-stu-id="2fb5c-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="2fb5c-141">**Датум рођења**: Датум</span><span class="sxs-lookup"><span data-stu-id="2fb5c-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="2fb5c-142">**Наградни поени**: Цео број</span><span class="sxs-lookup"><span data-stu-id="2fb5c-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="2fb5c-143">**Креирано**: Датум/време</span><span class="sxs-lookup"><span data-stu-id="2fb5c-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="2fb5c-144">У пољу „Име“ у десном окну преименујте извор података из **Упит** у **Лојални клијенти**.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-144">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="2fb5c-145">Сачувајте извор података.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="2fb5c-146">2. задатак 2 – Обједињавање података</span><span class="sxs-lookup"><span data-stu-id="2fb5c-146">Task 2 - Data unification</span></span>

<span data-ttu-id="2fb5c-147">Након уноса података, сада започињемо процес **Мапирања, подударања, обједињавања** да бисмо креирали обједињени профил клијента.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="2fb5c-148">За више информација погледајте [Обједињавање података](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="2fb5c-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="2fb5c-149">Мапирај</span><span class="sxs-lookup"><span data-stu-id="2fb5c-149">Map</span></span>

1. <span data-ttu-id="2fb5c-150">Након уноса података, мапирајте контакте са платформе eCommerce и из података о лојалности у уобичајене типове података.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="2fb5c-151">Идите на **Подаци** > **Обједини** > **Мапирај**.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="2fb5c-152">Изаберите ентитете који представљају профил клијента – **eCommerce контакти** и **Лојални клијенти**.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="обједините изворе података о платформ ecommerce и лојалности.":::

1. <span data-ttu-id="2fb5c-154">Изаберите **ID клијента** као примарни кључ за **eCommerce контакте** и **ID лојалности** као примарни кључ за **Лојалне клијенте**.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Обједините ID лојалности као примарни кључ.":::

### <a name="match"></a><span data-ttu-id="2fb5c-156">Подударање</span><span class="sxs-lookup"><span data-stu-id="2fb5c-156">Match</span></span>

1. <span data-ttu-id="2fb5c-157">Идите у на картицу **Подударање** и изаберите **Подеси редослед**.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="2fb5c-158">На падајућој листи **Примарно**, одаберите **eCommerce контакти: eCommerce** као примарни извор и укључите све записе.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-158">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="2fb5c-159">На падајућој листи **Ентитет 2**, одаберите **Лојални клијенти: Шема лојалности** и укључите све записе.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-159">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Обједините подударање платформе eCommerce и лојалности.":::

1. <span data-ttu-id="2fb5c-161">Изаберите **Креирај ново правило**</span><span class="sxs-lookup"><span data-stu-id="2fb5c-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="2fb5c-162">Додајте свој први услов користећи Име и презиме.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="2fb5c-163">За eCommerce контакте одаберите **Име и презиме** на падајућој листи.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-163">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="2fb5c-164">За Лојалне клијенте одаберите **Име и презиме** на падајућој листи.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-164">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="2fb5c-165">Изаберите падајућу листу **Нормализација** и одаберите **Тип (телефон, име, адреса...)**.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="2fb5c-166">Подесите **Ниво прецизности**: **Основни** и **Вредност**: **Висока**.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="2fb5c-167">Унесите назив **Име и презиме, е-пошта** за ново правило.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="2fb5c-168">Додајте други услов за адресу е-поште избором ставке **Додајте услов**</span><span class="sxs-lookup"><span data-stu-id="2fb5c-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="2fb5c-169">За ентитет eCommerce контакти одаберите **Е-пошта** у падајућем менију.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-169">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="2fb5c-170">За ентитет Лојални клијенти одаберите **Е-пошта** у падајућем менију.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-170">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="2fb5c-171">Оставите Нормализација празно.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="2fb5c-172">Подесите **Ниво прецизности**: **Основни** и **Вредност**: **Висока**.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Обједините правило подударања за име и е-пошту.":::

7. <span data-ttu-id="2fb5c-174">Изаберите **Сачувај** и **Затвори**.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="2fb5c-175">Обједини</span><span class="sxs-lookup"><span data-stu-id="2fb5c-175">Merge</span></span>

1. <span data-ttu-id="2fb5c-176">Идите на картицу **Обједињавање**.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="2fb5c-177">На **ID контакта** за ентитет **Лојални клијенти** промените име за приказ у **ID контакта ЛОЈАЛНОСТ** да би се разликовало од осталих унетих ID-ова.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="Преименујте ID контакта из ID-а лојалности.":::

1. <span data-ttu-id="2fb5c-179">Изаберите **Сачувај** и **Покрени** да бисте започели поступак обједињавања.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="2fb5c-180">3. задатак – Конфигуришите предвиђање губитка трансакција</span><span class="sxs-lookup"><span data-stu-id="2fb5c-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="2fb5c-181">Када су обједињени профилима клијената спремни, сада можемо покренути предвиђање губитка претплата.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="2fb5c-182">За детаљне кораке погледајте чланак [Предвиђање губитка претплата (верзија за преглед)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="2fb5c-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="2fb5c-183">Идите на **Обавештавање** > **Откријте** и изаберите да користите **Модел губитка клијената**.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="2fb5c-184">Изаберите опцију **Трансакција** и **Започните**.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="2fb5c-185">Назовите модел **OOB предвиђање губитка eCommerce трансакција** и излазни ентитет **OOBeCommerceChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="2fb5c-186">Дефинишите два услова за модел губитка:</span><span class="sxs-lookup"><span data-stu-id="2fb5c-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="2fb5c-187">**Прозор предвиђања**: **најмање 60** дана.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="2fb5c-188">Ово подешавање дефинише колико у будућности желимо да предвидимо губитак клијената.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="2fb5c-189">**Дефиниција губитка**: **најмање 60** дана.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="2fb5c-190">Трајање без куповине након којег се клијент сматра изгубљеним.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Изаберите регулаторе модела Временски период предвиђања и Дефиниција губитка.":::

1. <span data-ttu-id="2fb5c-192">Изаберите **Историја куповине (обавезно)** и **Додајте податке** за историју претплата.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-192">Select **Purchase History (required)** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="2fb5c-193">Додајте ентитет **eCommerce куповине: eCommerce** и мапирајте поља из платформе eCommerce са одговарајућим пољима које тражи модел.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="2fb5c-194">Придружите ентите **eCommerce куповине: eCommerce** са **eCommerce контакти: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Придружите eCommerce ентитете.":::

1. <span data-ttu-id="2fb5c-196">Изаберите **Даље** да бисте поставили распоред модела.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="2fb5c-197">Модел треба редовно да се обучава како би научио нове обрасце када дође до уноса нових података.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="2fb5c-198">За овај пример изаберите **Месечно**.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="2fb5c-199">Након прегледа свих детаља, изаберите **Сачувај и покрени**.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="2fb5c-200">4. задатак – Преглед резултата модела и објашњења</span><span class="sxs-lookup"><span data-stu-id="2fb5c-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="2fb5c-201">Нека модел заврши обуку и оцењивање података.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="2fb5c-202">Сада можете прегледати објашњења модела губитка претплата.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="2fb5c-203">За више информација погледајте [Прегледајте статус и резултате предвиђања](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="2fb5c-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="2fb5c-204">5. задатак – Креирајте сегмент клијената са високим ризиком од губитка</span><span class="sxs-lookup"><span data-stu-id="2fb5c-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="2fb5c-205">Покретање производног модела ствара нови ентитет који можете да видите у одељку **Подаци** > **Ентитети**.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="2fb5c-206">Можете да креирате нови сегмент на основу ентитета који је креирао модел.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="2fb5c-207">Идите на **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-207">Go to **Segments**.</span></span> <span data-ttu-id="2fb5c-208">Изаберите **Ново** и **Направи од** > **Обавештавање**.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Креирајте сегмент са излазом модела.":::

1. <span data-ttu-id="2fb5c-210">Изаберите крајњу тачку **OOB предвиђање губитка клијената** и дефинишите сегмент:</span><span class="sxs-lookup"><span data-stu-id="2fb5c-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="2fb5c-211">Поље: Оцена губитка</span><span class="sxs-lookup"><span data-stu-id="2fb5c-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="2fb5c-212">Оператор: веће je од</span><span class="sxs-lookup"><span data-stu-id="2fb5c-212">Operator: greater than</span></span>
   - <span data-ttu-id="2fb5c-213">Вредност: 0,6</span><span class="sxs-lookup"><span data-stu-id="2fb5c-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Подесите сегмент губитка претплате.":::

<span data-ttu-id="2fb5c-215">Сада имате сегмент који се динамички ажурира и који идентификује клијенте са високим ризиком од губитка за ову услугу претплате.</span><span class="sxs-lookup"><span data-stu-id="2fb5c-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="2fb5c-216">Више информација потражите у одељку [Креирање и управљање сегментима](segments.md).</span><span class="sxs-lookup"><span data-stu-id="2fb5c-216">For more information, see [Create and manage segments](segments.md).</span></span>
