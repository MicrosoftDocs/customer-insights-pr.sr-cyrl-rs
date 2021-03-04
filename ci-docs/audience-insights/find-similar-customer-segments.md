---
title: Пронађите сличне клијенте помоћу AI
description: Пронађите сличне сегменте клијента помоћу вештачке интелигенције.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: b9b2e7fa862b595c6a364a7208e42295b4f9df83
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268888"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="8f5e7-103">Слични купци (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="8f5e7-103">Similar Customers (preview)</span></span>

<span data-ttu-id="8f5e7-104">Ова функција вам омогућава да пронађете сличне клијенте у својој корисничкој бази користећи вештачку интелигенцију.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="8f5e7-105">Да бисте користили ову функцију, морате да имате бар један креиран сегмент.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="8f5e7-106">Проширење критеријума постојећег сегмента помаже у проналажењу клијената који су слични том сегменту.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="8f5e7-107">*Пронађите сличне купце* користи аутоматизована средства за процену података и прављење предвиђања на основу тих података, па се зато може користити као начин профилисања, термин који је дефинисан Општом уредбом о заштити података („GDPR“).</span><span class="sxs-lookup"><span data-stu-id="8f5e7-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="8f5e7-108">Клијентово коришћење ове функције за обраду података може да буде подложно GDPR-у или другим законима или прописима.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="8f5e7-109">Одговорни сте за то да користите Dynamics 365 Customer Insights, укључујући предвиђања, у складу са свим важећим законима и прописима, укључујући законе који се односе на приватност, личне податке, биометријске податке, заштиту података и поверљивост комуникација.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="8f5e7-110">Проналажење сличних клијената</span><span class="sxs-lookup"><span data-stu-id="8f5e7-110">Finding similar customers</span></span>

1. <span data-ttu-id="8f5e7-111">У увидима о корисницима идите на **Сегменти** и изаберите сегмент на којем желите да заснивате нови сегмент.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="8f5e7-112">То је ваш *изворни сегмент*.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="8f5e7-113">На траци радњи изаберите **Пронађи сличне купце**.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="8f5e7-114">Прегледајте предложени назив за свој нови сегмент и промените га ако је потребно.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="8f5e7-115">Прегледајте поља која дефинишу ваш нови сегмент.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="8f5e7-116">Ова поља дефинишу основу на којој ће систем покушати да нађе купце сличне вашем изворном сегменту.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="8f5e7-117">Систем ће подразумевано изабрати препоручена поља.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="8f5e7-118">Поља која могу значајно смањити перформансе модела аутоматски се искључују:</span><span class="sxs-lookup"><span data-stu-id="8f5e7-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="8f5e7-119">Поља са следећим типовима података: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="8f5e7-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="8f5e7-120">Поља са кардиналношћу (број елемената у пољу) мањом од 2 или више од 30</span><span class="sxs-lookup"><span data-stu-id="8f5e7-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="8f5e7-121">Изаберите да ли желите да укључите **Све купце** или само неке купце у **Специфични постојећи сегмент** у вашем новом сегменту.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="8f5e7-122">Искључите купце из свог изворног сегмента избором поља за потврду **Изузми све из изворног сегмента**.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="8f5e7-123">Систем подразумевано предлаже да у излазну вредност укључите само 20% циљне групе.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="8f5e7-124">Уредите ову граничну вредност по потреби.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-124">Edit this threshold as needed.</span></span> <span data-ttu-id="8f5e7-125">Повећање граничне вредности ће смањити прецизност.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="8f5e7-126">Изаберите **Покрени** у дну странице да бисте започели задатак бинарне класификације (вид машинског учења) који анализира скуп података.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="8f5e7-127">Прижажите сличан сегмент</span><span class="sxs-lookup"><span data-stu-id="8f5e7-127">View the similar segment</span></span>

<span data-ttu-id="8f5e7-128">Након обраде сличног сегмента, нови сегмент ћете наћи наведеног страници **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8f5e7-129">![Сегмент сличних клијената](media/expanded-segment.png "Сегмент сличних клијената")</span><span class="sxs-lookup"><span data-stu-id="8f5e7-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="8f5e7-130">Изаберите **Прикажи** на траци са радњама да бисте отворили детаље сегмента.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="8f5e7-131">Овај приказ садржи информације о расподели резултата кроз [оцене сличности](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="8f5e7-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="8f5e7-132">Такође ћете наћи сличности у вредностима резултата у **Преглед чланова сегмента**.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="8f5e7-133">Користите излаз сличног сегмента</span><span class="sxs-lookup"><span data-stu-id="8f5e7-133">Use the output of a similar segment</span></span>

<span data-ttu-id="8f5e7-134">Можете да [радите са излазном вредношћу сличног сегмента](segments.md) као и код других сегмената.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="8f5e7-135">На пример, извеите сегмент или изградите меру.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="8f5e7-136">Освежите и уредите сличан сегмент</span><span class="sxs-lookup"><span data-stu-id="8f5e7-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="8f5e7-137">Да бисте освежили сличан сегмент, изаберите га на страници **Сегменти**, а затим изаберите **Освежи** са траке радњи.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="8f5e7-138">Уређивањем сличног сегмента поново ћете обрадити ваше податке.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="8f5e7-139">Претходно креиран сегмент се ажурира уз освежене податке.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="8f5e7-140">Да бисте уредили сличан сегмент, изаберите га на страници **Сегменти**, а затим изаберите **Уреди** са траке радњи.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="8f5e7-141">Примените промене и изаберите **Покрени** да бисте започели обраду.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="8f5e7-142">Избришите сличан сегмент</span><span class="sxs-lookup"><span data-stu-id="8f5e7-142">Delete a similar segment</span></span>

<span data-ttu-id="8f5e7-143">Изаберите сегмент на страници **Сегменти**, а затим изаберите **Избриши** са траке радњи.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="8f5e7-144">Затим потврдите брисање.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="8f5e7-145">О оценама сличности</span><span class="sxs-lookup"><span data-stu-id="8f5e7-145">About similarity scores</span></span>

<span data-ttu-id="8f5e7-146">Модел машинског учења бинарне класификације додељује резултат купцима у сличном сегменту.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="8f5e7-147">Резултат је заснован на сличности са купцима у изворном сегменту.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="8f5e7-148">Резултати сличности испод 0,55 су купци које је систем класификово као *није слично* са купцима у изворном сегменту</span><span class="sxs-lookup"><span data-stu-id="8f5e7-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="8f5e7-149">Резултати сличности између 0,55 - 0,7 класификовани су као *помало слично*</span><span class="sxs-lookup"><span data-stu-id="8f5e7-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="8f5e7-150">Резултати сличности између 0,7 - 0,85 класификовани су као *слично*</span><span class="sxs-lookup"><span data-stu-id="8f5e7-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="8f5e7-151">Резултати сличности између 0,85 - 1 су купци које је систем класификово *врло слично*</span><span class="sxs-lookup"><span data-stu-id="8f5e7-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="8f5e7-152">Купци са резултатима сличности испод 0,4 нису укључени у излазну вредност модела.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="8f5e7-153">Систем их не сматра довољно сличним изворним сегментима.</span><span class="sxs-lookup"><span data-stu-id="8f5e7-153">The system doesn't consider them similar enough to the source segment.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]