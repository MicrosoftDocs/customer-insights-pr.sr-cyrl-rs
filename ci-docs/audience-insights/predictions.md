---
title: Допуните делимичне податке користећи предвиђања
description: Користите предвиђања за попуњавање непотпуних података о клијентима.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 577232c7e901dfd54a195c3e9cfac5d1f0f866e6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268290"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="c2f32-103">Попуните своје делимичне податке предвиђањима</span><span class="sxs-lookup"><span data-stu-id="c2f32-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="c2f32-104">Предвиђања вам омогућавају да лако креирате предвиђене вредности које могу побољшати разумевање вашег клијента.</span><span class="sxs-lookup"><span data-stu-id="c2f32-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="c2f32-105">На страници **Обавештавање** > **Предвиђања** можете одабрати **Моја предвиђања** да бисте видели предвиђања која сте конфигурисали у другим деловима увида о корисницима и додатно их прилагодили.</span><span class="sxs-lookup"><span data-stu-id="c2f32-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="c2f32-106">Ову функцију не можете да користите ако окружење користи Azure Data Lake Gen 2 простор за складиштење.</span><span class="sxs-lookup"><span data-stu-id="c2f32-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="c2f32-107">Функција предвиђања користи аутоматизовано средство за оцењивање података и прављење предвиђања на основу тих података и због тога има могућност да се користи као метод профилисања, јер је тај појам дефинисан Општом уредбом о заштити података („GDPR“).</span><span class="sxs-lookup"><span data-stu-id="c2f32-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="c2f32-108">Клијентово коришћење ове функције за обраду података може да буде подложно GDPR-у или другим законима или прописима.</span><span class="sxs-lookup"><span data-stu-id="c2f32-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="c2f32-109">Одговорни сте за то да користите Dynamics 365 Customer Insights, укључујући предвиђања, у складу са свим важећим законима и прописима, укључујући законе који се односе на приватност, личне податке, биометријске податке, заштиту података и поверљивост комуникација.</span><span class="sxs-lookup"><span data-stu-id="c2f32-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c2f32-110">Предуслови</span><span class="sxs-lookup"><span data-stu-id="c2f32-110">Prerequisites</span></span>

<span data-ttu-id="c2f32-111">Пре него што организација буде могла да користи функцију предвиђања, следећи предуслови морају да буду испуњени:</span><span class="sxs-lookup"><span data-stu-id="c2f32-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="c2f32-112">Ваша организација има инстанцу [постављену у услузи Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) и у истој је организацији као и Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c2f32-112">Your organization has an instance [set up in the Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="c2f32-113">Ваше окружење је везано за вашу Common Data Service инстанцу.</span><span class="sxs-lookup"><span data-stu-id="c2f32-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="c2f32-114">Ако [креирате прво окружење](manage-environments.md), конфигуришите га у дијалогу **Креирање окружења** и изаберите ставку **Напредно**.</span><span class="sxs-lookup"><span data-stu-id="c2f32-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="c2f32-115">Ако сте већ креирали окружење, идите на његова подешавања и изаберите **Напредно**.</span><span class="sxs-lookup"><span data-stu-id="c2f32-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="c2f32-116">У сваком случају, у одељку **Користите предвиђања** унесите URL Common Data Service инстанце на који желите да прикачите своје окружење.</span><span class="sxs-lookup"><span data-stu-id="c2f32-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="c2f32-117">Креирање предвиђања у услузи Customer entity</span><span class="sxs-lookup"><span data-stu-id="c2f32-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="c2f32-118">У увидима о корисницима идите на **Подаци** > **Ентитети**.</span><span class="sxs-lookup"><span data-stu-id="c2f32-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="c2f32-119">Изаберите ентитет **Клијент**.</span><span class="sxs-lookup"><span data-stu-id="c2f32-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="c2f32-120">У ентитету **Клијент: CustomerInsights** изаберите ставку на картици **Поља**.</span><span class="sxs-lookup"><span data-stu-id="c2f32-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="c2f32-121">Пронађите име атрибута за које желите да предвидите вредности, а затим изаберите икону **Преглед** у колони **Резиме**.</span><span class="sxs-lookup"><span data-stu-id="c2f32-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c2f32-122">![Икона „Преглед“](media/intelligence-overviewicon.png "Икона „Преглед“")</span><span class="sxs-lookup"><span data-stu-id="c2f32-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="c2f32-123">Ако постоји висока стопа недостајућих вредности за атрибут, изаберите **Предвиди недостајуће вредности** да бисте наставили са предвиђањем.</span><span class="sxs-lookup"><span data-stu-id="c2f32-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c2f32-124">![Приказ статуса прегледа са приказаним дугметом за вредности које недостају](media/intelligence-overviewpredictmissingvalues.png "Приказ статуса прегледа са приказаним дугметом за вредности које недостају")</span><span class="sxs-lookup"><span data-stu-id="c2f32-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="c2f32-125">Наведите **Име за приказ** и **Назив излазног ентитета** за резултате предвиђања.</span><span class="sxs-lookup"><span data-stu-id="c2f32-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="c2f32-126">Унапред попуњена листа опција ће показати где можете да мапирате вредности у предвиђеној категорији.</span><span class="sxs-lookup"><span data-stu-id="c2f32-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="c2f32-127">У овом случају, само опције категорије ће бити 0 или 1 док се мапирају у тачно/нетачно или бинарну природу предвиђања.</span><span class="sxs-lookup"><span data-stu-id="c2f32-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="c2f32-128">У колони „Категорија“, вредности поља које бисте желели да се класификују као „0“ у коначном предвиђању мапирајте на „0“, а ставке које бисте желели да се класификују као „1“ у коначном предвиђању мапирајте на вредност „1“.</span><span class="sxs-lookup"><span data-stu-id="c2f32-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c2f32-129">![Пример који приказује мапиране вредности поља у категорије](media/intelligence-categorymapping.png "Пример који приказује мапиране вредности поља у категорије")</span><span class="sxs-lookup"><span data-stu-id="c2f32-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="c2f32-130">Изаберите **Готово** и предвиђање ће бити обрађено.</span><span class="sxs-lookup"><span data-stu-id="c2f32-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="c2f32-131">Обрада ће потрајати извесно време, у зависности од величине и сложености података.</span><span class="sxs-lookup"><span data-stu-id="c2f32-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="c2f32-132">Резултати ће бити доступни у новом ентитету на основу **Назива излазног ентитета** предвиђања које сте креирали.</span><span class="sxs-lookup"><span data-stu-id="c2f32-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="c2f32-133">Креирање предвиђања током креирања сегмента</span><span class="sxs-lookup"><span data-stu-id="c2f32-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="c2f32-134">Предвиђање недостајућих вредности за одређени атрибут избора је могуће и приликом креирања сегмента.</span><span class="sxs-lookup"><span data-stu-id="c2f32-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="c2f32-135">Посебно, када брзо креирате сегмент заснован на обједињеном ентитету Клијент или ентитету Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="c2f32-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="c2f32-136">У оквиру овог тока бираћете одређени атрибут на којем ће засновати сегмент, као што је задовољство клијента или износ набавке.</span><span class="sxs-lookup"><span data-stu-id="c2f32-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="c2f32-137">Након креирања сегмента, систем ће предложити метод за предвиђање свих недостајућих вредности за овај атрибут.</span><span class="sxs-lookup"><span data-stu-id="c2f32-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="c2f32-138">У увидима о клијентима идите на **Сегменти** и изаберите плочицу **Профили**.</span><span class="sxs-lookup"><span data-stu-id="c2f32-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="c2f32-139">Одаберите **Поље** за креирање сегмента и изаберите **Оператор**, а затим изаберите ставку **Преглед**.</span><span class="sxs-lookup"><span data-stu-id="c2f32-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="c2f32-140">Наведите **Име** и **Име за приказ** за сегмент.</span><span class="sxs-lookup"><span data-stu-id="c2f32-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="c2f32-141">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="c2f32-141">Select **Save**.</span></span>

5. <span data-ttu-id="c2f32-142">Ако сегмент који сте управо креирали нема потпуне податке у изворном пољу, можете да изаберете да предвидите вредности које недостају.</span><span class="sxs-lookup"><span data-stu-id="c2f32-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c2f32-143">![Дугме предвиђања](media/segments-predictoption.png "Дугме предвиђања")</span><span class="sxs-lookup"><span data-stu-id="c2f32-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="c2f32-144">Наведите **Име за приказ** и **Назив излазног ентитета** за резултате предвиђања.</span><span class="sxs-lookup"><span data-stu-id="c2f32-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="c2f32-145">Изаберите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="c2f32-145">Select **Done**.</span></span> <span data-ttu-id="c2f32-146">Предвиђање ће се ускоро генерисати у новом ентитету са именом које сте навели за **Име излазног ентитета**.</span><span class="sxs-lookup"><span data-stu-id="c2f32-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="c2f32-147">Приказ предвиђања</span><span class="sxs-lookup"><span data-stu-id="c2f32-147">View a prediction</span></span>

1. <span data-ttu-id="c2f32-148">У увидима о корисницима идите на **Обавештавање** > **Предвиђања** > **Моја предвиђања**.</span><span class="sxs-lookup"><span data-stu-id="c2f32-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="c2f32-149">Изаберите предвиђање које желите да прегледате.</span><span class="sxs-lookup"><span data-stu-id="c2f32-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="c2f32-150">Изаберите три тачке у колони **Радње** и изаберите ставку **Приказ**.</span><span class="sxs-lookup"><span data-stu-id="c2f32-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="c2f32-151">Видећете број тачака података у приказу предвиђања.</span><span class="sxs-lookup"><span data-stu-id="c2f32-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c2f32-152">![Страница предвиђања](media/intelligence-predictionsviewpage.png "Страница предвиђања")</span><span class="sxs-lookup"><span data-stu-id="c2f32-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="c2f32-153">**Предвиђене вредности** приказују мапирање које сте креирали током фазе мапирања вредности поља у категорију.</span><span class="sxs-lookup"><span data-stu-id="c2f32-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="c2f32-154">Ово су вредности у вашем скупу података које су мапиране у одређену категорију.</span><span class="sxs-lookup"><span data-stu-id="c2f32-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="c2f32-155">-**Најутицајнији фактори** су фактори у вашем скупу података који највероватније највише утичу на поверење предвиђања ваше вредности поља која се мапирају у одређену категорију.</span><span class="sxs-lookup"><span data-stu-id="c2f32-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="c2f32-156">**Перформансе** указују на начин на који се прогнозе обављају.</span><span class="sxs-lookup"><span data-stu-id="c2f32-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="c2f32-157">Изаберите везу да бисте сазнали више.</span><span class="sxs-lookup"><span data-stu-id="c2f32-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="c2f32-158">**Преглед** приказује узорке излазних група података из предвиђања и вероватноћу, или наше поверење, предвиђене вредности, где је 0 неизвесно, а 1 је сигурно.</span><span class="sxs-lookup"><span data-stu-id="c2f32-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="c2f32-159">Ажурирањe предвиђања</span><span class="sxs-lookup"><span data-stu-id="c2f32-159">Update a prediction</span></span>

1. <span data-ttu-id="c2f32-160">У увидима о корисницима идите на **Обавештавање** > **Предвиђања** > **Моја предвиђања**.</span><span class="sxs-lookup"><span data-stu-id="c2f32-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="c2f32-161">Изаберите предвиђање које желите да ажурирате и изаберите икону **Ажурирај**.</span><span class="sxs-lookup"><span data-stu-id="c2f32-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="c2f32-162">Предвиђање ће бити заказано за обраду.</span><span class="sxs-lookup"><span data-stu-id="c2f32-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="c2f32-163">Време кад је последњи пут ажурирано можете да видите у колони **Ажурирано** на страници **Предвиђања**.</span><span class="sxs-lookup"><span data-stu-id="c2f32-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="c2f32-164">Уређивање предвиђања</span><span class="sxs-lookup"><span data-stu-id="c2f32-164">Edit a prediction</span></span>

<span data-ttu-id="c2f32-165">Када креирате предвиђање, можете да прилагодите модел у програму AI Builder да бисте повећали ефикасност вашег модела.</span><span class="sxs-lookup"><span data-stu-id="c2f32-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="c2f32-166">У увидима о корисницима идите на **Обавештавање** > **Предвиђања** > **Моја предвиђања**.</span><span class="sxs-lookup"><span data-stu-id="c2f32-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="c2f32-167">Изаберите предвиђање које желите да уредите.</span><span class="sxs-lookup"><span data-stu-id="c2f32-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="c2f32-168">Изаберите три тачке у колони **Радње** и изаберите ставку **Приказ**.</span><span class="sxs-lookup"><span data-stu-id="c2f32-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="c2f32-169">Изаберите **Прилагодите у услузи AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="c2f32-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="c2f32-170">Ажурирајте модел у програму AI Builder.</span><span class="sxs-lookup"><span data-stu-id="c2f32-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="c2f32-171">[Сазнајте више о управљању моделима у програму AI Builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="c2f32-171">[Learn more about managing models in the AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="c2f32-172">Следеће покретање предвиђања користиће ажурирани модел који сте креирали.</span><span class="sxs-lookup"><span data-stu-id="c2f32-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="c2f32-173">Нови модели направљени у AI Builder-у неће се приказивати у увидима о корисницима, осим ако модел није направљен на основу горенаведених искустава.</span><span class="sxs-lookup"><span data-stu-id="c2f32-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="c2f32-174">Уклањање предвиђања</span><span class="sxs-lookup"><span data-stu-id="c2f32-174">Remove a prediction</span></span>

1. <span data-ttu-id="c2f32-175">У увидима о корисницима идите на **Обавештавање** > **Предвиђања** > **Моја предвиђања**.</span><span class="sxs-lookup"><span data-stu-id="c2f32-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="c2f32-176">Изаберите предвиђање које желите да избришете.</span><span class="sxs-lookup"><span data-stu-id="c2f32-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="c2f32-177">Изаберите три тачке у колони **Радње** и изаберите ставку **Избриши**.</span><span class="sxs-lookup"><span data-stu-id="c2f32-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="c2f32-178">Потврдите брисање.</span><span class="sxs-lookup"><span data-stu-id="c2f32-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="c2f32-179">Решавање проблема</span><span class="sxs-lookup"><span data-stu-id="c2f32-179">Troubleshooting</span></span>

<span data-ttu-id="c2f32-180">Ако не можете да довршите прилагање Common Data Service процеса због грешке, можете покушати да довршите поступак ручно.</span><span class="sxs-lookup"><span data-stu-id="c2f32-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="c2f32-181">Постоје два позната проблема која се могу појавити у процесу прилагања:</span><span class="sxs-lookup"><span data-stu-id="c2f32-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="c2f32-182">Решење Додатак за картицу клијента није инсталирано.</span><span class="sxs-lookup"><span data-stu-id="c2f32-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="c2f32-183">Довршите упутства за [инсталирање и конфигурисање решења](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="c2f32-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="c2f32-184">Дозволе за апликације нису додељене.</span><span class="sxs-lookup"><span data-stu-id="c2f32-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="c2f32-185">Идите на [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="c2f32-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="c2f32-186">Изаберите **Окружења**.</span><span class="sxs-lookup"><span data-stu-id="c2f32-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="c2f32-187">Изаберите три тачке поред окружења којем желите да додате дозволу и изаберите **Подешавања**.</span><span class="sxs-lookup"><span data-stu-id="c2f32-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="c2f32-188">Проширите одељак **Корисници + дозволе** и изаберите **Корисници**.</span><span class="sxs-lookup"><span data-stu-id="c2f32-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="c2f32-189">Изаберите **+ Ново** и изаберите **Корисник**.</span><span class="sxs-lookup"><span data-stu-id="c2f32-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="c2f32-190">Изаберите опцију **Корисник апликације** ако није већ изабрана и унесите следеће информације:</span><span class="sxs-lookup"><span data-stu-id="c2f32-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="c2f32-191">**Корисничко име:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c2f32-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="c2f32-192">**ID апликације** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="c2f32-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="c2f32-193">**Име:** Клијент</span><span class="sxs-lookup"><span data-stu-id="c2f32-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="c2f32-194">**Презиме:** Увиди</span><span class="sxs-lookup"><span data-stu-id="c2f32-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="c2f32-195">**Примарна е-адреса:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c2f32-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="c2f32-196">Изаберите **Сачувај и затвори**.</span><span class="sxs-lookup"><span data-stu-id="c2f32-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="c2f32-197">Изаберите корисника којег сте управо креирали.</span><span class="sxs-lookup"><span data-stu-id="c2f32-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="c2f32-198">Изаберите **Управљај улогама** у горњој траци менија.</span><span class="sxs-lookup"><span data-stu-id="c2f32-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="c2f32-199">Изаберите **Системски администратор**, а затим изаберите **У реду**.</span><span class="sxs-lookup"><span data-stu-id="c2f32-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]