---
title: Предложени сегменти засновани на активности.
description: Нека вам машинско учење помогне да пронађете нове и занимљиве сегменте на основу активности клијената.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034111"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="6c80b-103">Предложени сегменти засновани на подацима о активности (преглед)</span><span class="sxs-lookup"><span data-stu-id="6c80b-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="6c80b-104">Откријте занимљиве сегменте својих клијената на основу података о активностима клијената који се уносе у Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6c80b-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="6c80b-105">Примери података о активностима су трансакције, трајање позива за подршку, куповине или повраћаји.</span><span class="sxs-lookup"><span data-stu-id="6c80b-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="6c80b-106">Да би предложили сегменте, подаци о активностима се анализирају на основу недавности, учесталости и новчане вредности (или трајања).</span><span class="sxs-lookup"><span data-stu-id="6c80b-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="6c80b-107">Можете и да генеришете [предложене сегменте за побољшање мере или за боље разумевање утицаја на атрибут](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="6c80b-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Картица Предложени сегменти приказује предлоге сегмената за сегменте засноване на активностима и сегменте засноване на атрибутима.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="6c80b-109">Категоризација клијената према активностима</span><span class="sxs-lookup"><span data-stu-id="6c80b-109">Categorize customers by activity</span></span>

<span data-ttu-id="6c80b-110">Са [подацима о активностима](activities.md) доступним у услузи Customer Insights, можемо да генеришемо предлоге који представљају групе клијената:</span><span class="sxs-lookup"><span data-stu-id="6c80b-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="6c80b-111">најактивнији клијенти</span><span class="sxs-lookup"><span data-stu-id="6c80b-111">most active customers</span></span> 
- <span data-ttu-id="6c80b-112">клијенти који су обавили највише куповина</span><span class="sxs-lookup"><span data-stu-id="6c80b-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="6c80b-113">клијенти који су остварили највише прихода</span><span class="sxs-lookup"><span data-stu-id="6c80b-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="6c80b-114">клијенти који у последње време нису били активни</span><span class="sxs-lookup"><span data-stu-id="6c80b-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="6c80b-115">клијенти који често комуницирају са вашим предузећем</span><span class="sxs-lookup"><span data-stu-id="6c80b-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="6c80b-116">Ако имате малопродају, могли бисте да сазнате који клијенти остварују највише прихода и наградите их купоном.</span><span class="sxs-lookup"><span data-stu-id="6c80b-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="6c80b-117">Или можете да идентификујете повремене клијенте и понудите им да се придруже програму награђивања како би чешће посећивали ваше предузеће.</span><span class="sxs-lookup"><span data-stu-id="6c80b-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="6c80b-118">Ако се бавите здравственом делатношћу која пружа јавну здравствену заштиту и ваш циљ је да смањите трошкове за појединачне пацијенте.</span><span class="sxs-lookup"><span data-stu-id="6c80b-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="6c80b-119">Могућ начин за то би било смањење поновљених посета пружањем најбоље могуће неге у што мање посета.</span><span class="sxs-lookup"><span data-stu-id="6c80b-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="6c80b-120">У овом случају, ваш циљ је да учесталост посета буде ниска и да минимизујете поновљене трошкове за пацијенте.</span><span class="sxs-lookup"><span data-stu-id="6c80b-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="6c80b-121">Или можете идентификовати сегменте пацијената који имају честе прегледе и високе трошкове који се понављају, па анализирати ове случајеве како бисте побољшали лечење појединца.</span><span class="sxs-lookup"><span data-stu-id="6c80b-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="6c80b-122">Обавезни подаци</span><span class="sxs-lookup"><span data-stu-id="6c80b-122">Required data</span></span>

<span data-ttu-id="6c80b-123">Предлози се генеришу на основу изабраних улазних података.</span><span class="sxs-lookup"><span data-stu-id="6c80b-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="6c80b-124">Кориснички профили: Сви клијенти или чланови одређеног сегмента.</span><span class="sxs-lookup"><span data-stu-id="6c80b-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="6c80b-125">Временски период: Прошли месец, прошла година или било који прилагођени временски оквир.</span><span class="sxs-lookup"><span data-stu-id="6c80b-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="6c80b-126">Тип активности: куповине, малопродајне трансакције, трансакције на мрежи, случајеви корисничке подршке, претплате итд.</span><span class="sxs-lookup"><span data-stu-id="6c80b-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="6c80b-127">Ентитет у услузи Customer Insights који садржи податке о активности: ентитет уједначене активности или ентитет за одређену активност.</span><span class="sxs-lookup"><span data-stu-id="6c80b-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="6c80b-128">Димензије које треба да обухвате: Недавна активност, учесталост или новчана димензија, у зависности од ваших пословних захтева.</span><span class="sxs-lookup"><span data-stu-id="6c80b-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="6c80b-129">Генеришите предложене сегменте</span><span class="sxs-lookup"><span data-stu-id="6c80b-129">Generate suggested segments</span></span>

1. <span data-ttu-id="6c80b-130">Идите на **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="6c80b-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="6c80b-131">Изаберите картицу **Предлози (преглед)**.</span><span class="sxs-lookup"><span data-stu-id="6c80b-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="6c80b-132">Изаберите **Пронађите нове предлоге** и одаберите **Погледајте или предвидите понашање клијената**.</span><span class="sxs-lookup"><span data-stu-id="6c80b-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="6c80b-133">Изаберите **Почетак** за покретање вођеног искуства.</span><span class="sxs-lookup"><span data-stu-id="6c80b-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Први корак чаробњака за конфигурацију за предложени сегмент на основу активности.":::

1. <span data-ttu-id="6c80b-135">Наведите потребне улазне податке и изаберите **Следеће** и наставите.</span><span class="sxs-lookup"><span data-stu-id="6c80b-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="6c80b-136">Одаберите клијенте: Укључите све клијенте или одређени сегмент.</span><span class="sxs-lookup"><span data-stu-id="6c80b-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="6c80b-137">Одаберите активност: Изаберите врсту активности и ентитете који описују активност.</span><span class="sxs-lookup"><span data-stu-id="6c80b-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="6c80b-138">Жељене поставке: Поставите временски период који треба узети у обзир, факторе за предлоге и мапирајте атрибуте.</span><span class="sxs-lookup"><span data-stu-id="6c80b-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="6c80b-139">Прегледајте свој унос и изаберите **Покрени** да бисте покренули модел и генерисали предлоге.</span><span class="sxs-lookup"><span data-stu-id="6c80b-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="6c80b-140">У зависности од броја корисничких профила и изабраних активности, може потрајати неколико минута.</span><span class="sxs-lookup"><span data-stu-id="6c80b-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="6c80b-141">Након генерисања предлога, можете их филтрирати према димензији или вредности која вас највише занима.</span><span class="sxs-lookup"><span data-stu-id="6c80b-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="6c80b-142">Приказ детаља предложеног сегмента</span><span class="sxs-lookup"><span data-stu-id="6c80b-142">View details of a suggested segment</span></span>

<span data-ttu-id="6c80b-143">Када се предлози генеришу, наћи ћете их на списку **Сегменти** > **Предлози (преглед)** у одељку **Предлози засновани на активностима**.</span><span class="sxs-lookup"><span data-stu-id="6c80b-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Проширено бочно окно које приказује детаљне податке о предложеном сегменту.":::

<span data-ttu-id="6c80b-145">Изаберите **Погледајте предлог** на предложеном сегменту да бисте видели детаље о том сегменту.</span><span class="sxs-lookup"><span data-stu-id="6c80b-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="6c80b-146">Бочно окно пружа детаље попут обима сваке димензије у поређењу са циљном групом.</span><span class="sxs-lookup"><span data-stu-id="6c80b-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="6c80b-147">Такође наглашава број потенцијалних чланова у сегменту и одговарајући проценат од укупног броја клијената.</span><span class="sxs-lookup"><span data-stu-id="6c80b-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="6c80b-148">Ако желите да предлог задржите као сегмент, изаберите **Направи сегмент**.</span><span class="sxs-lookup"><span data-stu-id="6c80b-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="6c80b-149">Чување предлога као сегмента</span><span class="sxs-lookup"><span data-stu-id="6c80b-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="6c80b-150">Идите на **Сегменти** > **Предлози (преглед)**.</span><span class="sxs-lookup"><span data-stu-id="6c80b-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="6c80b-151">Изаберите сегмент који желите да сачувате.</span><span class="sxs-lookup"><span data-stu-id="6c80b-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="6c80b-152">У бочном окну, изаберите **Направи сегмент**.</span><span class="sxs-lookup"><span data-stu-id="6c80b-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="6c80b-153">Када сачувате сегмент, приказаће се на листи сегмената на картици **Сви сегменти**. Сад може бити [освежен или избрисан као и било који други сегмент](segments.md).</span><span class="sxs-lookup"><span data-stu-id="6c80b-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="6c80b-154">Не можете да уређујете детаље сегмента.</span><span class="sxs-lookup"><span data-stu-id="6c80b-154">You can't edit the segment details.</span></span> <span data-ttu-id="6c80b-155">Међутим, можете променити критеријуме уноса за предлоге и генерисати различите предлоге.</span><span class="sxs-lookup"><span data-stu-id="6c80b-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="6c80b-156">Освежите или измените скуп предлога</span><span class="sxs-lookup"><span data-stu-id="6c80b-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="6c80b-157">Идите на **Сегменти** > **Предлози (преглед)** и потражите сегмент у одељку **Предлози засновани на активностима**.</span><span class="sxs-lookup"><span data-stu-id="6c80b-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="6c80b-158">Изаберите **Освежи предлоге** да бисте освежили предлоге уз задржавање конфигурисаних атрибута.</span><span class="sxs-lookup"><span data-stu-id="6c80b-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="6c80b-159">Или изаберите **Измени предлоге** да бисте изменили конфигурисане атрибуте.</span><span class="sxs-lookup"><span data-stu-id="6c80b-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="6c80b-160">Систем ће поново покренути поступак, генерисати предлоге за сегменте на основу најновијих података и заменити тренутне предлоге.</span><span class="sxs-lookup"><span data-stu-id="6c80b-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
