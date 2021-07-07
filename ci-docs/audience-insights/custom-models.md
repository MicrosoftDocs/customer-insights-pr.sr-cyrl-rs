---
title: Прилагођени модели машинског учења | Microsoft Docs
description: Радите са прилагођеним моделима из Azure машинског учења у услузи Dynamics 365 Customer Insights.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 82f6f363497f8f1b45fa84acd49bcaed332e60e8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305667"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="05ca8-103">Прилагођени модели машинског учења</span><span class="sxs-lookup"><span data-stu-id="05ca8-103">Custom machine learning models</span></span>

<span data-ttu-id="05ca8-104">**Обавештавање** > **Прилагођени модели** вам омогућавају управљање токовима посла на основу Azure модела машинског учења.</span><span class="sxs-lookup"><span data-stu-id="05ca8-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="05ca8-105">Токови посла помажу вам да одаберете податке од којих желите да генеришете увид и да резултате мапирате са обједињеним подацима о клијентима.</span><span class="sxs-lookup"><span data-stu-id="05ca8-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="05ca8-106">За више информација о изради прилагођених ML модела погледајте [Користите моделе засноване на Azure машинском учењу](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="05ca8-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="05ca8-107">Одговорни AI</span><span class="sxs-lookup"><span data-stu-id="05ca8-107">Responsible AI</span></span>

<span data-ttu-id="05ca8-108">Предвиђања нуде могућности за стварање бољег корисничког искуства, побољшање пословних прилика и токова прихода.</span><span class="sxs-lookup"><span data-stu-id="05ca8-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="05ca8-109">Препоручујемо вам да уравнотежите вредност предвиђања са утицајем који има и одступањима која се могу увести на етичан начин.</span><span class="sxs-lookup"><span data-stu-id="05ca8-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="05ca8-110">Сазнајте више о томе како Microsoft [примењује одговоран AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="05ca8-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="05ca8-111">Такође можете сазнати о [техникама и процесима за одговорно машинско учење](/azure/machine-learning/concept-responsible-ml) специфичним за Azure машинско учење.</span><span class="sxs-lookup"><span data-stu-id="05ca8-111">You can also learn about [techniques and processes for responsible machine learning](/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="05ca8-112">Предуслови</span><span class="sxs-lookup"><span data-stu-id="05ca8-112">Prerequisites</span></span>

- <span data-ttu-id="05ca8-113">Тренутно ова функција подржава веб-услуге објављене путем [Machine Learning Studio (класичног)](https://studio.azureml.net) и [групних канала Azure машинског учења](/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="05ca8-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="05ca8-114">Да бисте користили ову функцију, потребан вам је Azure Data Lake Gen2 налог за складиштење повезан са Azure Studio инстанцом.</span><span class="sxs-lookup"><span data-stu-id="05ca8-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="05ca8-115">За више информација, погледајте чланак [Креирање Azure Data Lake Storage Gen2 налога за складиштење](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span><span class="sxs-lookup"><span data-stu-id="05ca8-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span></span>

- <span data-ttu-id="05ca8-116">За Azure радне просторе за машинско учење са каналима, требају вам администраторске дозволе власника или корисника да бисте приступили Azure радном простору за машинско учење.</span><span class="sxs-lookup"><span data-stu-id="05ca8-116">For Azure Machine Learning workspaces with pipelines, you need Owner or User Access Administrator permissions to the Azure Machine Learning Workspace.</span></span>

   > [!NOTE]
   > <span data-ttu-id="05ca8-117">Подаци се преносе између Customer Insights инстанци и изабраних Azure веб-услуга или канала у току посла.</span><span class="sxs-lookup"><span data-stu-id="05ca8-117">Data is transferred between your Customer Insights instances and the selected Azure web services or pipelines in the workflow.</span></span> <span data-ttu-id="05ca8-118">Када преносите податке у Azure услугу, уверите се да је услуга конфигурисана да обрађује податке на начин неопходан за поштовање свих законских или регулаторних захтева за те податке за вашу организацију, као и на локацији која је за то неопходна.</span><span class="sxs-lookup"><span data-stu-id="05ca8-118">When you transfer data to an Azure service, please ensure that service is configured to process data in the manner and location necessary to comply with any legal or regulatory requirements for that data for your organization.</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="05ca8-119">Додавање новог тока посла</span><span class="sxs-lookup"><span data-stu-id="05ca8-119">Add a new workflow</span></span>

1. <span data-ttu-id="05ca8-120">Идите на **Обавештавање** > **Прилагођени модели** и изаберите **Нови ток посла**.</span><span class="sxs-lookup"><span data-stu-id="05ca8-120">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="05ca8-121">Дајте прилагођеном моделу препознатљиво име у пољу **Име**.</span><span class="sxs-lookup"><span data-stu-id="05ca8-121">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="05ca8-122">![Снимак екрана окна „Нови ток посла“](media/new-workflowv2.png "Снимак екрана окна „Нови ток посла“")</span><span class="sxs-lookup"><span data-stu-id="05ca8-122">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="05ca8-123">Изаберите организацију која садржи веб-услугу у **закупцу који садржи вашу веб-услугу**.</span><span class="sxs-lookup"><span data-stu-id="05ca8-123">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="05ca8-124">Ако је претплата на Azure машинско учење у другом закупцу у односу на Customer Insights, одаберите **Пријавите се** помоћу акредитива за одабрану организацију.</span><span class="sxs-lookup"><span data-stu-id="05ca8-124">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="05ca8-125">Изаберите **Радне просторе** повезане са вашом веб-услугом.</span><span class="sxs-lookup"><span data-stu-id="05ca8-125">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="05ca8-126">Наведена су два одељка, један за Azure машинско учење в1 (Machine Learning Studio (класични)) и Azure машинско учење в2 (Azure машинско учење).</span><span class="sxs-lookup"><span data-stu-id="05ca8-126">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="05ca8-127">Ако нисте сигурни који је радни простор прави за вашу Machine Learning Studio (класичан) веб-услугу, изаберите **Било који**.</span><span class="sxs-lookup"><span data-stu-id="05ca8-127">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="05ca8-128">Изаберите Machine Learning Studio (класична) веб-услугу или канал Azure машинског учења у падајућем менију **Веб-услуга која садржи ваш модел**.</span><span class="sxs-lookup"><span data-stu-id="05ca8-128">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="05ca8-129">Затим изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="05ca8-129">Then, select **Next**.</span></span>
   - <span data-ttu-id="05ca8-130">Сазнајте више о [објављивању веб-услуге у Machine Learning Studio (класичном)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="05ca8-130">Learn more about [publishing a web service in Machine Learning Studio (classic)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="05ca8-131">Сазнајте више о [објављивању канала у Azure машинском учењу помоћу дизајнера](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) или [ SDK-а](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="05ca8-131">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="05ca8-132">Ваш канал мора бити објављен под [крајњом тачком канала](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="05ca8-132">Your pipeline must be published under a [pipeline endpoint](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="05ca8-133">За сваки **Унос веб-услуге**, изаберите одговарајући **Ентитет** из увида о корисницима и изаберите **Даље**.</span><span class="sxs-lookup"><span data-stu-id="05ca8-133">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="05ca8-134">Ток посла прилагођеног модела примењиваће хеуристику за мапирање поља за унос веб-услуга у атрибуте ентитета на основу имена и типа података поља.</span><span class="sxs-lookup"><span data-stu-id="05ca8-134">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="05ca8-135">Видећете грешку ако поље веб-услуге не може да се преслика на ентитет.</span><span class="sxs-lookup"><span data-stu-id="05ca8-135">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="05ca8-136">![Конфигурисање тока посла](media/intelligence-screen2-updated.png "Конфигурисање тока посла")</span><span class="sxs-lookup"><span data-stu-id="05ca8-136">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="05ca8-137">У кораку **Излазни параметри модела** поставите следећа својства:</span><span class="sxs-lookup"><span data-stu-id="05ca8-137">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="05ca8-138">Machine Learning Studio (класични)</span><span class="sxs-lookup"><span data-stu-id="05ca8-138">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="05ca8-139">Унесите излаз **Назив ентитета** у који желите да се преносе излазни резултати веб-услуга.</span><span class="sxs-lookup"><span data-stu-id="05ca8-139">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="05ca8-140">Azure машинско учење</span><span class="sxs-lookup"><span data-stu-id="05ca8-140">Azure Machine Learning</span></span>
      1. <span data-ttu-id="05ca8-141">Унесите излаз **Назив ентитета** у који желите да се преносе излазни резултати канала.</span><span class="sxs-lookup"><span data-stu-id="05ca8-141">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="05ca8-142">Изаберите **Назив излазног параметра складишта података** за групни канал из падајућег менија.</span><span class="sxs-lookup"><span data-stu-id="05ca8-142">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="05ca8-143">Изаберите **Назив излазног параметра путање** за групни канал из падајућег менија.</span><span class="sxs-lookup"><span data-stu-id="05ca8-143">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="05ca8-144">![Окно излазних параметара модела](media/intelligence-screen3-outputparameters.png "Окно излазних параметара модела")</span><span class="sxs-lookup"><span data-stu-id="05ca8-144">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="05ca8-145">Изаберите одговарајући атрибут из падајуће листе **ID клијента у резултатима** која идентификује клијенте и изаберите **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="05ca8-145">Select the matching attribute from the **Customer ID in results** dropdown list that identifies customers and select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="05ca8-146">![Повежите резултате са окном података клијената](media/intelligence-screen4-relatetocustomer.png "Повежите резултате са окном података клијената")</span><span class="sxs-lookup"><span data-stu-id="05ca8-146">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="05ca8-147">Видећете екран **Ток посла је сачуван** са детаљима о току посла.</span><span class="sxs-lookup"><span data-stu-id="05ca8-147">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="05ca8-148">Ако сте конфигурисали ток посла за канал Azure машинског учења, увиди о корисницима ће се приложити у радни простор који садржи канал.</span><span class="sxs-lookup"><span data-stu-id="05ca8-148">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="05ca8-149">Увиди у публику ће добити улогу **Сарадник** у Azure радном простору.</span><span class="sxs-lookup"><span data-stu-id="05ca8-149">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="05ca8-150">Изаберите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="05ca8-150">Select **Done**.</span></span>

1. <span data-ttu-id="05ca8-151">Сада можете покренути ток посла са странице **Прилагођени модели**.</span><span class="sxs-lookup"><span data-stu-id="05ca8-151">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="05ca8-152">Измена тока посла</span><span class="sxs-lookup"><span data-stu-id="05ca8-152">Edit a workflow</span></span>

1. <span data-ttu-id="05ca8-153">На страници **Прилагођени модели** изаберите усправне три тачке у колони **Радње** поред тока посла који сте претходно креирали и изаберите **Уреди**.</span><span class="sxs-lookup"><span data-stu-id="05ca8-153">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="05ca8-154">Препознатљиво име тока посла можете ажурирати у пољу **Име за приказ**, али не можете да промените конфигурисану веб-услугу или канал.</span><span class="sxs-lookup"><span data-stu-id="05ca8-154">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="05ca8-155">Изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="05ca8-155">Select **Next**.</span></span>

1. <span data-ttu-id="05ca8-156">За сваки **Унос веб-услуге**, можете да ажурирате одговарајући **Ентитет** из увида о корисницима.</span><span class="sxs-lookup"><span data-stu-id="05ca8-156">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="05ca8-157">Затим изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="05ca8-157">Then, select **Next**.</span></span>

1. <span data-ttu-id="05ca8-158">У кораку **Излазни параметри модела** поставите следећа својства:</span><span class="sxs-lookup"><span data-stu-id="05ca8-158">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="05ca8-159">Machine Learning Studio (класични)</span><span class="sxs-lookup"><span data-stu-id="05ca8-159">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="05ca8-160">Унесите излаз **Назив ентитета** у који желите да се преносе излазни резултати веб-услуга.</span><span class="sxs-lookup"><span data-stu-id="05ca8-160">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="05ca8-161">Azure машинско учење</span><span class="sxs-lookup"><span data-stu-id="05ca8-161">Azure Machine Learning</span></span>
      1. <span data-ttu-id="05ca8-162">Унесите излаз **Назив ентитета** у који желите да се преносе излазни резултати канала.</span><span class="sxs-lookup"><span data-stu-id="05ca8-162">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="05ca8-163">Изаберите **Назив излазног параметра складишта података** за пробни канал.</span><span class="sxs-lookup"><span data-stu-id="05ca8-163">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="05ca8-164">Изаберите **Назив излазног параметра путање** за пробни канал.</span><span class="sxs-lookup"><span data-stu-id="05ca8-164">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="05ca8-165">Изаберите одговарајући атрибут из падајуће листе **ID клијента у резултатима** која идентификује клијенте и изаберите **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="05ca8-165">Select the matching attribute from the **Customer ID in results** dropdown list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="05ca8-166">Одаберите атрибут из излаза закључка са вредностима сличним колони са ID-ом клијента ентитета клијента.</span><span class="sxs-lookup"><span data-stu-id="05ca8-166">Choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="05ca8-167">Ако немате такву колону скупу података, одаберите атрибут који јединствено идентификује ред.</span><span class="sxs-lookup"><span data-stu-id="05ca8-167">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="05ca8-168">Покрени ток посла</span><span class="sxs-lookup"><span data-stu-id="05ca8-168">Run a workflow</span></span>

1. <span data-ttu-id="05ca8-169">На страници **Прилагођени модели** изаберите усправне три тачке у колони **Радње** поред тока посла који сте претходно креирали.</span><span class="sxs-lookup"><span data-stu-id="05ca8-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="05ca8-170">Изаберите **Покрени**.</span><span class="sxs-lookup"><span data-stu-id="05ca8-170">Select **Run**.</span></span>

<span data-ttu-id="05ca8-171">Ток посла се такође покреће аутоматски са сваким заказаним освежавањем.</span><span class="sxs-lookup"><span data-stu-id="05ca8-171">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="05ca8-172">Сазнајте више о [постављању заказаних освежавања](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="05ca8-172">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="05ca8-173">Брисање тока посла</span><span class="sxs-lookup"><span data-stu-id="05ca8-173">Delete a workflow</span></span>

1. <span data-ttu-id="05ca8-174">На страници **Прилагођени модели** изаберите усправне три тачке у колони **Радње** поред тока посла који сте претходно креирали.</span><span class="sxs-lookup"><span data-stu-id="05ca8-174">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="05ca8-175">Изаберите **Избриши** и потврдите брисање.</span><span class="sxs-lookup"><span data-stu-id="05ca8-175">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="05ca8-176">Ваш ток посла ће бити избрисан.</span><span class="sxs-lookup"><span data-stu-id="05ca8-176">Your workflow will be deleted.</span></span> <span data-ttu-id="05ca8-177">[Ентитет](entities.md) који је креиран када сте креирали ток посла опстаје и може се прегледати са странице **Ентитети**.</span><span class="sxs-lookup"><span data-stu-id="05ca8-177">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>

## <a name="results"></a><span data-ttu-id="05ca8-178">Резултати</span><span class="sxs-lookup"><span data-stu-id="05ca8-178">Results</span></span>

<span data-ttu-id="05ca8-179">Резултати из тока посла се чувају у ентитету конфигурисаном током фазе излазних параметара модела.</span><span class="sxs-lookup"><span data-stu-id="05ca8-179">Results from a workflow are stored in the entity configured during the Model Output Parameter phase.</span></span> <span data-ttu-id="05ca8-180">Овим подацима можете приступити са [странице ентитета](entities.md) или помоћу [API приступа](apis.md).</span><span class="sxs-lookup"><span data-stu-id="05ca8-180">You can access this data from the [entities page](entities.md) or with [API access](apis.md).</span></span>

### <a name="api-access"></a><span data-ttu-id="05ca8-181">API приступ</span><span class="sxs-lookup"><span data-stu-id="05ca8-181">API Access</span></span>

<span data-ttu-id="05ca8-182">Да би одређени OData упит добио податке из ентитета прилагођеног модела, користите следећи формат:</span><span class="sxs-lookup"><span data-stu-id="05ca8-182">For the specific OData query to get data from a custom model entity, use the following format:</span></span>

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. <span data-ttu-id="05ca8-183">Замените `<your instance id>` са ID-ом вашег Customer Insights окружења, који ћете пронаћи у адресној траци свог прегледача када приступите услузи Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="05ca8-183">Replace `<your instance id>` with the ID of your Customer Insights environment, which you find in the in the address bar of your browser when accessing Customer Insights.</span></span>

1. <span data-ttu-id="05ca8-184">Замените `<custom model output entity>` називом ентитета које сте навели током корака параметара излазних параметара модела прилагођене конфигурације модела.</span><span class="sxs-lookup"><span data-stu-id="05ca8-184">Replace `<custom model output entity>` with the entity name you provided during the Model Output Parameters step of the custom model configuration.</span></span>

1. <span data-ttu-id="05ca8-185">Замените `<guid value>` ID-ом клијента чијем запису желите да приступите.</span><span class="sxs-lookup"><span data-stu-id="05ca8-185">Replace `<guid value>` with the Customer ID of the customer you'd like to access the record for.</span></span> <span data-ttu-id="05ca8-186">Тај ID обично можете пронаћи на [страница профила клијента](customer-profiles.md) у пољу CustomerID.</span><span class="sxs-lookup"><span data-stu-id="05ca8-186">You can usually find this ID on the [customer profiles page](customer-profiles.md) in the CustomerID field.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="05ca8-187">Најчешћа питања</span><span class="sxs-lookup"><span data-stu-id="05ca8-187">Frequently Asked Questions</span></span>

- <span data-ttu-id="05ca8-188">Зашто не могу да видим свој канал приликом подешавања тока посла прилагођеног модела?</span><span class="sxs-lookup"><span data-stu-id="05ca8-188">Why can't I see my pipeline when setting up a custom model workflow?</span></span>    
  <span data-ttu-id="05ca8-189">Овај проблем је често узрокован проблемом конфигурације у каналу.</span><span class="sxs-lookup"><span data-stu-id="05ca8-189">This issue is frequently caused by a configuration issue in the pipeline.</span></span> <span data-ttu-id="05ca8-190">Уверите се да је [улазни параметар конфигурисан](azure-machine-learning-experiments.md#dataset-configuration) и да су [излазни параметри складишта података и путање](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) такође конфигурисани.</span><span class="sxs-lookup"><span data-stu-id="05ca8-190">Ensure the [input parameter is configured](azure-machine-learning-experiments.md#dataset-configuration), and the [output datastore and path parameters](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) are also configured.</span></span>

- <span data-ttu-id="05ca8-191">Шта значи грешка „Не могу да сачувам ток посла обавештавања“?</span><span class="sxs-lookup"><span data-stu-id="05ca8-191">What does the error "Couldn't save intelligence workflow" mean?</span></span>    
  <span data-ttu-id="05ca8-192">Корисници обично виде ову поруку о грешци ако у радном простору немају администраторске привилегије приступа за власника или корисника.</span><span class="sxs-lookup"><span data-stu-id="05ca8-192">Users usually see this error message if they don't have Owner or User Access Administrator privileges on the workspace.</span></span> <span data-ttu-id="05ca8-193">Кориснику је потребан виши ниво дозвола да омогући услузи Customer Insights да обради ток посла као услугу, уместо да користи корисничке акредитиве за наредна покретања тока посла.</span><span class="sxs-lookup"><span data-stu-id="05ca8-193">The user needs a higher level of permissions to enable Customer Insights to process the workflow as a service rather than using the user credentials for subsequent runs of the workflow.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
