---
title: Водич кроз примере предвиђања трајне вредности клијента
description: Користите овај водич кроз примере да испробате модел предвиђања трајне вредности клијента.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 19c1fbadb79ba22c0dc11aa7c3b5b2415add70a7
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306367"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="9d43d-103">Водич кроз примере предвиђања трајне вредности клијента (CLV)</span><span class="sxs-lookup"><span data-stu-id="9d43d-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="9d43d-104">Овај водич ће вам објаснити целокупан пример предвиђања трајне вредности клијента (CLV) у услузи Customer Insights коришћењем примера података.</span><span class="sxs-lookup"><span data-stu-id="9d43d-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="9d43d-105">Сценарио</span><span class="sxs-lookup"><span data-stu-id="9d43d-105">Scenario</span></span>

<span data-ttu-id="9d43d-106">Contoso је предузеће које производи висококвалитетну кафу и апарате за кафу.</span><span class="sxs-lookup"><span data-stu-id="9d43d-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="9d43d-107">Производе продају преко своје веб-локације Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="9d43d-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="9d43d-108">Предузеће жели да разуме вредност (приход) коју њихови клијенти могу да генеришу у следећих 12 месеци.</span><span class="sxs-lookup"><span data-stu-id="9d43d-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="9d43d-109">Познавање очекиване вредности клијената у следећих 12 месеци помоћи ће им да своје маркетиншке напоре усмере на клијенте високе вредности.</span><span class="sxs-lookup"><span data-stu-id="9d43d-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9d43d-110">Предуслови</span><span class="sxs-lookup"><span data-stu-id="9d43d-110">Prerequisites</span></span>

- <span data-ttu-id="9d43d-111">Најмање [дозволе сарадника](permissions.md) у увидима у циљну групу.</span><span class="sxs-lookup"><span data-stu-id="9d43d-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="9d43d-112">Препоручујемо да примените следеће кораке [у новом окружењу](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="9d43d-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="9d43d-113">1. задатак – Унос података</span><span class="sxs-lookup"><span data-stu-id="9d43d-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="9d43d-114">Прегледајте чланке [о уносу података](data-sources.md) и [увозу извора података помоћу Power Query конектора](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="9d43d-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="9d43d-115">Следеће информације претпостављају да сте се упознали са уношењем података уопште.</span><span class="sxs-lookup"><span data-stu-id="9d43d-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="9d43d-116">Унесите податке о клијентима са платформе eCommerce</span><span class="sxs-lookup"><span data-stu-id="9d43d-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="9d43d-117">Направите извор података под називом **eCommerce**, изаберите опцију увоза, па изаберите конектор **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="9d43d-118">Унесите URL адресу за eCommerce контакте [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="9d43d-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="9d43d-119">Док уређујете податке, изаберите **Трансформација**, а затим **Користи први ред као заглавља**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="9d43d-120">Ажурирајте тип података за доленаведене колоне:</span><span class="sxs-lookup"><span data-stu-id="9d43d-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="9d43d-121">**Датум рођења**: Датум</span><span class="sxs-lookup"><span data-stu-id="9d43d-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="9d43d-122">**Креирано**: Датум/време/зона</span><span class="sxs-lookup"><span data-stu-id="9d43d-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Трансформација датума рођења у датум.":::

1. <span data-ttu-id="9d43d-124">У пољу „Име“ у десном окну преименујте извор података из **Упит** у **eCommerce контакти**</span><span class="sxs-lookup"><span data-stu-id="9d43d-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="9d43d-125">**Сачувајте** извор података.</span><span class="sxs-lookup"><span data-stu-id="9d43d-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="9d43d-126">Унесите податке о куповини на мрежи</span><span class="sxs-lookup"><span data-stu-id="9d43d-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="9d43d-127">Додајте још један скуп податка у исти **eCommerce** извор података.</span><span class="sxs-lookup"><span data-stu-id="9d43d-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="9d43d-128">Поново изаберите конектор **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="9d43d-129">Унесите URL за податке о **куповинама на мрежи** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="9d43d-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="9d43d-130">Док уређујете податке, изаберите **Трансформација**, а затим **Користи први ред као заглавља**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="9d43d-131">Ажурирајте тип података за доленаведене колоне:</span><span class="sxs-lookup"><span data-stu-id="9d43d-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="9d43d-132">**Купљено дана**: Датум/време</span><span class="sxs-lookup"><span data-stu-id="9d43d-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="9d43d-133">**Укупна цена**: Валута</span><span class="sxs-lookup"><span data-stu-id="9d43d-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="9d43d-134">У пољу **Назив** у бочном окну преименујте извор података из **Упит** у **eCommerce куповине**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="9d43d-135">**Сачувајте** извор података.</span><span class="sxs-lookup"><span data-stu-id="9d43d-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="9d43d-136">Унесите податке о клијентима из шеме лојалности</span><span class="sxs-lookup"><span data-stu-id="9d43d-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="9d43d-137">Направите извор података под именом **Шема лојалности**, изаберите опцију увоза и изаберите **Текст/CSV** конектор.</span><span class="sxs-lookup"><span data-stu-id="9d43d-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="9d43d-138">Унесите URL адресу за eCommerce контакте https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="9d43d-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="9d43d-139">Док уређујете податке, изаберите **Трансформација**, а затим **Користи први ред као заглавља**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="9d43d-140">Ажурирајте тип података за доленаведене колоне:</span><span class="sxs-lookup"><span data-stu-id="9d43d-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="9d43d-141">**Датум рођења**: Датум</span><span class="sxs-lookup"><span data-stu-id="9d43d-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="9d43d-142">**Наградни поени**: Цео број</span><span class="sxs-lookup"><span data-stu-id="9d43d-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="9d43d-143">**Креирано**: Датум/време</span><span class="sxs-lookup"><span data-stu-id="9d43d-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="9d43d-144">У пољу **Име** у десном окну преименујте извор података из **Упит** у **Лојални клијенти**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="9d43d-145">**Сачувајте** извор података.</span><span class="sxs-lookup"><span data-stu-id="9d43d-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="9d43d-146">Унесите податке о клијентима из рецензија на веб-сајту</span><span class="sxs-lookup"><span data-stu-id="9d43d-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="9d43d-147">Направите извор података под именом **Веб-сајт**, изаберите опцију увоза и изаберите **Текст/CSV** конектор.</span><span class="sxs-lookup"><span data-stu-id="9d43d-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="9d43d-148">Унесите URL адресу за eCommerce контакте https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="9d43d-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="9d43d-149">Док уређујете податке, изаберите **Трансформација**, а затим **Користи први ред као заглавља**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="9d43d-150">Ажурирајте тип података за доленаведене колоне:</span><span class="sxs-lookup"><span data-stu-id="9d43d-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="9d43d-151">**ReviewRating**: децимални број</span><span class="sxs-lookup"><span data-stu-id="9d43d-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="9d43d-152">**Датум рецензије**: Датум</span><span class="sxs-lookup"><span data-stu-id="9d43d-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="9d43d-153">У пољу „Назив“ у десном окну, преименујте извор података из **Упит** у **Прегледи**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="9d43d-154">**Сачувајте** извор података.</span><span class="sxs-lookup"><span data-stu-id="9d43d-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="9d43d-155">2. задатак 2 – Обједињавање података</span><span class="sxs-lookup"><span data-stu-id="9d43d-155">Task 2 - Data unification</span></span>

<span data-ttu-id="9d43d-156">Након уноса података, сада започињемо поступак уједначавања података како бисмо креирали јединствени профил клијента.</span><span class="sxs-lookup"><span data-stu-id="9d43d-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="9d43d-157">За више информација погледајте [Обједињавање података](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="9d43d-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="9d43d-158">Мапирај</span><span class="sxs-lookup"><span data-stu-id="9d43d-158">Map</span></span>

1. <span data-ttu-id="9d43d-159">Након уноса података, мапирајте контакте са платформе eCommerce и из података о лојалности у уобичајене типове података.</span><span class="sxs-lookup"><span data-stu-id="9d43d-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="9d43d-160">Идите на **Подаци** > **Обједини** > **Мапирај**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="9d43d-161">Изаберите ентитете који представљају профил клијента – **eCommerce контакти** и **Лојални клијенти**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="9d43d-162">Затим изаберите **Примени**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-162">Then, select **Apply**.</span></span>

   ![обједините изворе података о платформ ecommerce и лојалности.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="9d43d-164">Изаберите **ID клијента** као примарни кључ за **eCommerce контакте** и **ID лојалности** као примарни кључ за **Лојалне клијенте**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Обједините ID лојалности као примарни кључ.](media/unify-loyaltyid.png)

1. <span data-ttu-id="9d43d-166">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="9d43d-167">Подударање</span><span class="sxs-lookup"><span data-stu-id="9d43d-167">Match</span></span>

1. <span data-ttu-id="9d43d-168">Идите у на картицу **Подударање** и изаберите **Подеси редослед**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="9d43d-169">У падајућој листи **Примарно** одаберите **eCommerceContacts : eCommerce** као примарни извор и укључите све записе.</span><span class="sxs-lookup"><span data-stu-id="9d43d-169">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="9d43d-170">У падајућој листи **Ентитет 2** одаберите **loyCustomers : LoyaltyScheme** и укључите све записе.</span><span class="sxs-lookup"><span data-stu-id="9d43d-170">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Обједините подударање платформе eCommerce и лојалности.](media/unify-match-order.png)

1. <span data-ttu-id="9d43d-172">Изаберите **Додај правило**</span><span class="sxs-lookup"><span data-stu-id="9d43d-172">Select **Add rule**</span></span>

1. <span data-ttu-id="9d43d-173">Додајте свој први услов користећи Име и презиме.</span><span class="sxs-lookup"><span data-stu-id="9d43d-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="9d43d-174">За eCommerceContacts изаберите **FullName** у падајућој листи.</span><span class="sxs-lookup"><span data-stu-id="9d43d-174">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="9d43d-175">За loyCustomers изаберите **FullName** у падајућој листи.</span><span class="sxs-lookup"><span data-stu-id="9d43d-175">For loyCustomers select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="9d43d-176">Изаберите падајућу листу **Нормализација** и одаберите **Тип (телефон, име, адреса, ...)**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-176">Select the **Normalize** dropdown and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="9d43d-177">Подесите **Ниво прецизности**: **Основни** и **Вредност**: **Висока**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="9d43d-178">Унесите назив **Име и презиме, е-пошта** за ново правило.</span><span class="sxs-lookup"><span data-stu-id="9d43d-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="9d43d-179">Додајте други услов за адресу е-поште избором ставке **Додајте услов**</span><span class="sxs-lookup"><span data-stu-id="9d43d-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="9d43d-180">За ентитет еЦоммерцеЦонтацтс, одаберите **EMail** у падајућој листи.</span><span class="sxs-lookup"><span data-stu-id="9d43d-180">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   - <span data-ttu-id="9d43d-181">За ентитет loyCustomers, одаберите **EMail** у падајућој листи.</span><span class="sxs-lookup"><span data-stu-id="9d43d-181">For entity loyCustomers, choose **EMail** in the dropdown.</span></span>
   - <span data-ttu-id="9d43d-182">Оставите Нормализација празно.</span><span class="sxs-lookup"><span data-stu-id="9d43d-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="9d43d-183">Подесите **Ниво прецизности**: **Основни** и **Вредност**: **Висока**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Обједините правило подударања за име и е-пошту.](media/unify-match-rule.png)

1. <span data-ttu-id="9d43d-185">Изаберите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-185">Select **Done**.</span></span>

1. <span data-ttu-id="9d43d-186">Изаберите **Сачувај** и **Затвори**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="9d43d-187">Обједини</span><span class="sxs-lookup"><span data-stu-id="9d43d-187">Merge</span></span>

1. <span data-ttu-id="9d43d-188">Идите на картицу **Обједињавање**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="9d43d-189">На **ID контакта** за ентитет **Лојални клијенти** промените име за приказ у **ID контакта ЛОЈАЛНОСТ** да би се разликовало од осталих унетих ID-ова.</span><span class="sxs-lookup"><span data-stu-id="9d43d-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![Преименујте ID контакта из ID-а лојалности.](media/unify-merge-contactid.png)

1. <span data-ttu-id="9d43d-191">Изаберите **Сачувај** и **Покрени процесе обједињавања и последичног премештања**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="9d43d-192">Задатак 3 – Конфигурисање предвиђања трајне вредности клијента</span><span class="sxs-lookup"><span data-stu-id="9d43d-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="9d43d-193">Са успостављеним обједињеним профилима клијената, сада можемо покренути предвиђање трајне вредности клијента.</span><span class="sxs-lookup"><span data-stu-id="9d43d-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="9d43d-194">За детаљне кораке, погледајте [Предвиђање трајне вредности клијента (верзија за преглед)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="9d43d-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="9d43d-195">Идите на **Обавештавање**  > **Предвиђања** и изаберите **Модел трајне вредности клијента**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="9d43d-196">Пређите кроз информације у бочном окну и изаберите **Започни**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="9d43d-197">Назовите модел **OOB eCommerce CLV Prediction** а излазни ентитет **OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="9d43d-198">Дефинишите жељене опције модела за CLV модел:</span><span class="sxs-lookup"><span data-stu-id="9d43d-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="9d43d-199">**Временски период предвиђања**: **12 месеци или 1 година**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="9d43d-200">Ово подешавање дефинише колико у будућности треба предвиђати трајну вредност клијента.</span><span class="sxs-lookup"><span data-stu-id="9d43d-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="9d43d-201">**Активни клијенти**: Наведите шта активни клијенти значе за ваше пословање.</span><span class="sxs-lookup"><span data-stu-id="9d43d-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="9d43d-202">Подесите временски оквир претходног периода у којем је клијент морао имати барем једну трансакцију да би се сматрао активним.</span><span class="sxs-lookup"><span data-stu-id="9d43d-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="9d43d-203">Модел ће предвидети CLV само за активне клијенте.</span><span class="sxs-lookup"><span data-stu-id="9d43d-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="9d43d-204">Одаберите између допуштања моделу да израчуна временски период на основу историјских података о трансакцијама или наведите одређени временски оквир.</span><span class="sxs-lookup"><span data-stu-id="9d43d-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="9d43d-205">У овом водичу кроз пример, ми **омогућавамо моделу да израчуна интервал куповине**, што је подразумевана опција.</span><span class="sxs-lookup"><span data-stu-id="9d43d-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="9d43d-206">**Клијенти велике вредности**: Клијенте високе вредности дефинишите као проценат клијената који највише плаћају.</span><span class="sxs-lookup"><span data-stu-id="9d43d-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="9d43d-207">Модел користи овај улаз за пружање резултата који се уклапају у вашу пословну дефиницију клијената велике вредности.</span><span class="sxs-lookup"><span data-stu-id="9d43d-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="9d43d-208">Можете одабрати да омогућите моделу да дефинише клијенте високе вредности.</span><span class="sxs-lookup"><span data-stu-id="9d43d-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="9d43d-209">Користи хеуристичко правило које изводи перцентил.</span><span class="sxs-lookup"><span data-stu-id="9d43d-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="9d43d-210">Клијенте високе вредности можете дефинисати као проценат клијената који ће највише плаћати у будућности.</span><span class="sxs-lookup"><span data-stu-id="9d43d-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="9d43d-211">У овом водичу кроз примере, ручно дефинишемо клијенте велике вредности као **30% активних клијената који плаћају** и изаберите **Следећи**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Корак жељених опција у навођеном искуству за CLV модел.":::

1. <span data-ttu-id="9d43d-213">У кораку **Потребни подаци**, изаберите **Додај податке** да бисте пружили податке о трансакцијама у претходном периоду.</span><span class="sxs-lookup"><span data-stu-id="9d43d-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="9d43d-214">Додајте ентитет **eCommercePurchases : eCommerce** и мапирајте атрибуте који су потребни моделу:</span><span class="sxs-lookup"><span data-stu-id="9d43d-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="9d43d-215">ID трансакције: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="9d43d-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="9d43d-216">Датум трансакције: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="9d43d-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="9d43d-217">Износ трансакције: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="9d43d-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="9d43d-218">ID производа: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="9d43d-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="9d43d-219">Изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-219">Select **Next**.</span></span>

1. <span data-ttu-id="9d43d-220">Подесите релацију између ентитета **eCommercePurchases : eCommerce** и **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="9d43d-221">Корак **Додатни подаци (опционално)** вам омогућава да додате више података о активностима клијената.</span><span class="sxs-lookup"><span data-stu-id="9d43d-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="9d43d-222">Ови подаци могу вам помоћи да добијете више увида о интеракцији клијената са вашим предузећем, што може допринети моделу CLV.</span><span class="sxs-lookup"><span data-stu-id="9d43d-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="9d43d-223">Додавање кључних интеракција са клијентима попут веб-евиденције, евиденција корисничке службе или програма награђивања у претходном периоду може побољшати тачност предвиђања.</span><span class="sxs-lookup"><span data-stu-id="9d43d-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="9d43d-224">Изаберите **Додај податке** да бисте укључили више података о активностима клијената.</span><span class="sxs-lookup"><span data-stu-id="9d43d-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="9d43d-225">Додајте ентитет активности клијента и мапирајте називе његових поља у одговарајућа поља која захтева модел:</span><span class="sxs-lookup"><span data-stu-id="9d43d-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="9d43d-226">Ентитет активности клијента: Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="9d43d-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="9d43d-227">Примарни кључ: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="9d43d-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="9d43d-228">Временска ознака: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="9d43d-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="9d43d-229">Догађај (назив активности): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="9d43d-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="9d43d-230">Детаљи (износ или вредност): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="9d43d-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="9d43d-231">Изаберите **Следеће** и конфигуришите активност и релацију између података о трансакцији и података о клијенту:</span><span class="sxs-lookup"><span data-stu-id="9d43d-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="9d43d-232">Тип активности: Одаберите постојећи</span><span class="sxs-lookup"><span data-stu-id="9d43d-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="9d43d-233">Ознака активности: Review</span><span class="sxs-lookup"><span data-stu-id="9d43d-233">Activity label: Review</span></span>
   - <span data-ttu-id="9d43d-234">Одговарајућа ознака: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="9d43d-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="9d43d-235">Ентитет клијента: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="9d43d-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="9d43d-236">Релација: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="9d43d-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="9d43d-237">Изаберите **Даље** да бисте поставили распоред модела.</span><span class="sxs-lookup"><span data-stu-id="9d43d-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="9d43d-238">Модел треба редовно тренирати да би научио нове обрасце када се уносе нови подаци.</span><span class="sxs-lookup"><span data-stu-id="9d43d-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="9d43d-239">За овај пример, одаберите **Месечно**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="9d43d-240">Након прегледа свих детаља, изаберите **Сачувај и покрени**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="9d43d-241">4. задатак – Преглед резултата модела и објашњења</span><span class="sxs-lookup"><span data-stu-id="9d43d-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="9d43d-242">Нека модел заврши обуку и оцењивање података.</span><span class="sxs-lookup"><span data-stu-id="9d43d-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="9d43d-243">Затим можете прегледати резултате и објашњења CLV модела.</span><span class="sxs-lookup"><span data-stu-id="9d43d-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="9d43d-244">За више информација погледајте [Прегледајте статус и резултате предвиђања](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="9d43d-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="9d43d-245">5. задатак – Креирање сегмента клијената велике вредности</span><span class="sxs-lookup"><span data-stu-id="9d43d-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="9d43d-246">Покретање модела креиран нови ентитет, који је наведен на **Подаци** > **Ентитети**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="9d43d-247">Можете да креирате нови сегмент клијената на основу ентитета који је креирао модел.</span><span class="sxs-lookup"><span data-stu-id="9d43d-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="9d43d-248">Идите на **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="9d43d-249">Изаберите **Ново**, па **Направи од** > **Обавештавање**.</span><span class="sxs-lookup"><span data-stu-id="9d43d-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Креирајте сегмент са излазом модела.](media/segment-intelligence.png)

1. <span data-ttu-id="9d43d-251">Изаберите ентитет **OOBeCommerceCLVPrediction** ентитет и дефинишите сегмент:</span><span class="sxs-lookup"><span data-stu-id="9d43d-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="9d43d-252">Поље: CLVScore</span><span class="sxs-lookup"><span data-stu-id="9d43d-252">Field: CLVScore</span></span>
  - <span data-ttu-id="9d43d-253">Оператор: веће je од</span><span class="sxs-lookup"><span data-stu-id="9d43d-253">Operator: greater than</span></span>
  - <span data-ttu-id="9d43d-254">Вредност: 1500</span><span class="sxs-lookup"><span data-stu-id="9d43d-254">Value: 1500</span></span>

1. <span data-ttu-id="9d43d-255">Изаберите **Преглед** и **сачувајте** сегмент.</span><span class="sxs-lookup"><span data-stu-id="9d43d-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="9d43d-256">Сада имате сегмент који идентификује клијенте за које се предвиђа да ће остварити више од 1500 $ прихода у следећих 12 месеци.</span><span class="sxs-lookup"><span data-stu-id="9d43d-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="9d43d-257">Овај сегмент се динамички ажурира ако се унесе више података.</span><span class="sxs-lookup"><span data-stu-id="9d43d-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="9d43d-258">Више информација потражите у одељку [Креирање и управљање сегментима](segments.md).</span><span class="sxs-lookup"><span data-stu-id="9d43d-258">For more information, see [Create and manage segments](segments.md).</span></span>
