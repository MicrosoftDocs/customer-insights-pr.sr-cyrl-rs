---
title: Захтеви на основу права субјекта података (DSR) у оквиру GDPR | Microsoft Docs
description: Одговорите на захтеве субјекта података за Dynamics 365 Customer Insights могућност увида о корисницима.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed9aa09fba938606611c6ce86c2b250c5e19c606
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268704"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="f1641-103">Захтеви на основу права субјекта података (DSR) у оквиру GDPR</span><span class="sxs-lookup"><span data-stu-id="f1641-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="f1641-104">Одговарање на захтеве за брисање GDPR субјекта података за Dynamics 365 Customer Insights могућност увида о корисницима</span><span class="sxs-lookup"><span data-stu-id="f1641-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="f1641-105">„Право на брисање“ уклањањем личних података из података о клијентима организације представља кључну заштиту у Општој уредби о заштити података (GDPR).</span><span class="sxs-lookup"><span data-stu-id="f1641-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="f1641-106">Уклањање личних података укључује уклањање свих личних података и системски генерисаних евиденција, осим информација из евиденције надгледања.</span><span class="sxs-lookup"><span data-stu-id="f1641-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="f1641-107">Управљање захтевима за брисање субјекта података</span><span class="sxs-lookup"><span data-stu-id="f1641-107">Manage data subject delete requests</span></span>

<span data-ttu-id="f1641-108">Увиди о корисницима нуде следеће искуство у вези са производом за брисање личних података одређеног клијента или Customer Insights корисника:</span><span class="sxs-lookup"><span data-stu-id="f1641-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="f1641-109">**Управљајте захтевима брисање података о клијенту**: Подаци о клијенту у услузи Customer Insights унети су из оригиналних извора података који су спољашњи за Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f1641-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="f1641-110">Сви GDPR захтеви за брисање морају се обавити у оригиналном извору података.</span><span class="sxs-lookup"><span data-stu-id="f1641-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="f1641-111">**Управљајте захтевима за брисање корисничких података корисника услуге Customer Insights**: Податке за кориснике креира Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f1641-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="f1641-112">Сви GDPR захтеви за брисање морају се обавити у услузи Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f1641-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="f1641-113">Управљање захтевима за брисање података о клијентима</span><span class="sxs-lookup"><span data-stu-id="f1641-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="f1641-114">Администратор услуге Customer Insights може да прати ове кораке за уклањање података о клијентима који су избрисани у извору података:</span><span class="sxs-lookup"><span data-stu-id="f1641-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="f1641-115">Пријавите се у Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f1641-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="f1641-116">У увидима о корисницима идите на **Подаци** > **Извори података**</span><span class="sxs-lookup"><span data-stu-id="f1641-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="f1641-117">За сваки извор података на листи који садржи избрисане податке о клијентима:</span><span class="sxs-lookup"><span data-stu-id="f1641-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="f1641-118">Изаберите (...), па изаберите **Освежи**.</span><span class="sxs-lookup"><span data-stu-id="f1641-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="f1641-119">Проверите статус извора података у одељку **Статус**.</span><span class="sxs-lookup"><span data-stu-id="f1641-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="f1641-120">Знак потврде значи да је освежавање било успешно.</span><span class="sxs-lookup"><span data-stu-id="f1641-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="f1641-121">Трокут упозорења значи да нешто није у реду.</span><span class="sxs-lookup"><span data-stu-id="f1641-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="f1641-122">Ако се прикаже троугао упозорења, контактирајте D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="f1641-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f1641-123">![Руковање GDPR захтевима за брисање података о клијентима](media/gdpr-data-sources.png "Руковање GDPR захтевима за брисање података о клијентима")</span><span class="sxs-lookup"><span data-stu-id="f1641-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="f1641-124">Управљање захтевима за брисање података о корисницима</span><span class="sxs-lookup"><span data-stu-id="f1641-124">Manage delete requests for user data</span></span>

<span data-ttu-id="f1641-125">Администратор услуге Customer Insights може да следи следеће кораке за брисање података о Customer Insights корисницима:</span><span class="sxs-lookup"><span data-stu-id="f1641-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="f1641-126">Пријавите се у Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f1641-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="f1641-127">У увидима о корисницима идите на **Администратор** > **Дозволе**.</span><span class="sxs-lookup"><span data-stu-id="f1641-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="f1641-128">Изаберите поље за потврду за корисника којег желите да избришете.</span><span class="sxs-lookup"><span data-stu-id="f1641-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="f1641-129">Изаберите **Уклони**.</span><span class="sxs-lookup"><span data-stu-id="f1641-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f1641-130">![Управљање GDPR захтевима за брисање података о корисницима](media/gdpr-permissions.png "Управљање GDPR захтевима за брисање података о корисницима")</span><span class="sxs-lookup"><span data-stu-id="f1641-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="f1641-131">Одговарање на GDPR захтеве за извоз субјекта података</span><span class="sxs-lookup"><span data-stu-id="f1641-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="f1641-132">Као део наше посвећености да заједно са вама сарађујемо на вашем путу до Опште уредбе о заштити података (GDPR), развили смо документацију која ће вам помоћи да се припремите.</span><span class="sxs-lookup"><span data-stu-id="f1641-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="f1641-133">Ова документација описује кораке које данас можете предузети да бисте подржали поштовање GDPR-а када користите увиде о корисницима.</span><span class="sxs-lookup"><span data-stu-id="f1641-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="f1641-134">Управљање извозом и приказ захтева</span><span class="sxs-lookup"><span data-stu-id="f1641-134">Manage export and view requests</span></span>

<span data-ttu-id="f1641-135">Право преносивости података омогућава субјектима података да затраже копију својих личних података у електронском формату (дефинисаном као "структурирани, уобичајено употребљив, машински читљив и интероперабилни формат") који се може пренети на другог контролора података.</span><span class="sxs-lookup"><span data-stu-id="f1641-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="f1641-136">Извоз података о клијенту (администратор закупца)</span><span class="sxs-lookup"><span data-stu-id="f1641-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="f1641-137">Администратор закупца може да прати ове кораке за извоз података:</span><span class="sxs-lookup"><span data-stu-id="f1641-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="f1641-138">Пошаљите е-поруку на D365CI@microsoft.com наводећи адресу е-поште клијента у захтеву.</span><span class="sxs-lookup"><span data-stu-id="f1641-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="f1641-139">Customer Insights тим ће послати е-поруку на регистровану адресу е-поште администратора регистрованог закупца, тражећи потврду за извоз података.</span><span class="sxs-lookup"><span data-stu-id="f1641-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="f1641-140">Потврдите потврду за извоз података за траженог клијента.</span><span class="sxs-lookup"><span data-stu-id="f1641-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="f1641-141">Примите извезене податке путем е-адресе администратора закупца.</span><span class="sxs-lookup"><span data-stu-id="f1641-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="f1641-142">Извоз података о кориснику (администратор закупца)</span><span class="sxs-lookup"><span data-stu-id="f1641-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="f1641-143">Пошаљите е-поруку на D365CI@microsoft.com наводећи адресу е-поште корисника у захтеву.</span><span class="sxs-lookup"><span data-stu-id="f1641-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="f1641-144">Customer Insights тим ће послати е-поруку на регистровану адресу е-поште администратора регистрованог закупца, тражећи потврду за извоз података.</span><span class="sxs-lookup"><span data-stu-id="f1641-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="f1641-145">Прихватите потврду за извоз података за траженог корисника.</span><span class="sxs-lookup"><span data-stu-id="f1641-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="f1641-146">Примите извезене податке путем е-адресе администратора закупца.</span><span class="sxs-lookup"><span data-stu-id="f1641-146">Receive the exported data through the tenant admin email address.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]