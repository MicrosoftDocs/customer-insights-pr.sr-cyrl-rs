---
title: Прилагођени модели машинског учења | Microsoft Docs
description: Радите са прилагођеним моделима из Azure машинског учења у услузи Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668921"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="d4f29-103">Прилагођени модели машинског учења</span><span class="sxs-lookup"><span data-stu-id="d4f29-103">Custom machine learning models</span></span>

<span data-ttu-id="d4f29-104">**Обавештавање** > **Прилагођени модели** вам омогућавају управљање токовима посла на основу Azure модела машинског учења.</span><span class="sxs-lookup"><span data-stu-id="d4f29-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="d4f29-105">Токови посла помажу вам да одаберете податке од којих желите да генеришете увид и да резултате мапирате са обједињеним подацима о клијентима.</span><span class="sxs-lookup"><span data-stu-id="d4f29-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="d4f29-106">За више информација о изради прилагођених ML модела погледајте [Користите моделе засноване на Azure машинском учењу](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="d4f29-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="d4f29-107">Одговорни AI</span><span class="sxs-lookup"><span data-stu-id="d4f29-107">Responsible AI</span></span>

<span data-ttu-id="d4f29-108">Предвиђања нуде могућности за стварање бољег корисничког искуства, побољшање пословних прилика и токова прихода.</span><span class="sxs-lookup"><span data-stu-id="d4f29-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="d4f29-109">Препоручујемо вам да уравнотежите вредност предвиђања са утицајем који има и одступањима која се могу увести на етичан начин.</span><span class="sxs-lookup"><span data-stu-id="d4f29-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="d4f29-110">Сазнајте више о томе како Microsoft [примењује одговоран AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="d4f29-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="d4f29-111">Такође можете сазнати о [техникама и процесима за одговорно машинско учење](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) специфичним за Azure машинско учење.</span><span class="sxs-lookup"><span data-stu-id="d4f29-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d4f29-112">Предуслови</span><span class="sxs-lookup"><span data-stu-id="d4f29-112">Prerequisites</span></span>

- <span data-ttu-id="d4f29-113">Тренутно ова функција подржава веб-услуге објављене путем [Machine Learning Studio (класичног)](https://studio.azureml.net) и [групних канала Azure машинског учења](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="d4f29-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="d4f29-114">Да бисте користили ову функцију, потребан вам је Azure Data Lake Gen2 налог за складиштење повезан са Azure Studio инстанцом.</span><span class="sxs-lookup"><span data-stu-id="d4f29-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="d4f29-115">За више информација погледајте [Направите Azure Data Lake Storage Gen2 налог за складиштење података](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="d4f29-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="d4f29-116">Додавање новог тока посла</span><span class="sxs-lookup"><span data-stu-id="d4f29-116">Add a new workflow</span></span>

1. <span data-ttu-id="d4f29-117">Идите на **Обавештавање** > **Прилагођени модели** и изаберите **Нови ток посла**.</span><span class="sxs-lookup"><span data-stu-id="d4f29-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="d4f29-118">Дајте прилагођеном моделу препознатљиво име у пољу **Име**.</span><span class="sxs-lookup"><span data-stu-id="d4f29-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d4f29-119">![Снимак екрана окна „Нови ток посла“](media/new-workflowv2.png "Снимак екрана окна „Нови ток посла“")</span><span class="sxs-lookup"><span data-stu-id="d4f29-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="d4f29-120">Изаберите организацију која садржи веб-услугу у **закупцу који садржи вашу веб-услугу**.</span><span class="sxs-lookup"><span data-stu-id="d4f29-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="d4f29-121">Ако је претплата на Azure машинско учење у другом закупцу у односу на Customer Insights, одаберите **Пријавите се** помоћу акредитива за одабрану организацију.</span><span class="sxs-lookup"><span data-stu-id="d4f29-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="d4f29-122">Изаберите **Радне просторе** повезане са вашом веб-услугом.</span><span class="sxs-lookup"><span data-stu-id="d4f29-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="d4f29-123">Наведена су два одељка, један за Azure машинско учење в1 (Machine Learning Studio (класични)) и Azure машинско учење в2 (Azure машинско учење).</span><span class="sxs-lookup"><span data-stu-id="d4f29-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="d4f29-124">Ако нисте сигурни који је радни простор прави за вашу Machine Learning Studio (класичан) веб-услугу, изаберите **Било који**.</span><span class="sxs-lookup"><span data-stu-id="d4f29-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="d4f29-125">Изаберите Machine Learning Studio (класична) веб-услугу или канал Azure машинског учења у падајућем менију **Веб-услуга која садржи ваш модел**.</span><span class="sxs-lookup"><span data-stu-id="d4f29-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="d4f29-126">Затим изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="d4f29-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="d4f29-127">Сазнајте више о [објављивању веб-услуге у Machine Learning Studio (класичном)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="d4f29-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="d4f29-128">Сазнајте више о [објављивању канала у Azure машинском учењу помоћу дизајнера](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) или [ SDK-а](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="d4f29-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> 
     > [!NOTE]
     > <span data-ttu-id="d4f29-129">Ваш канал мора бити објављен под [крајњом тачком канала](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="d4f29-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="d4f29-130">За сваки **Унос веб-услуге**, изаберите одговарајући **Ентитет** из увида о корисницима и изаберите **Даље**.</span><span class="sxs-lookup"><span data-stu-id="d4f29-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d4f29-131">![Конфигурисање тока посла](media/intelligence-screen2-updated.png "Конфигурисање тока посла")</span><span class="sxs-lookup"><span data-stu-id="d4f29-131">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="d4f29-132">У кораку **Излазни параметри модела** поставите следећа својства:</span><span class="sxs-lookup"><span data-stu-id="d4f29-132">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="d4f29-133">Machine Learning Studio (класични)</span><span class="sxs-lookup"><span data-stu-id="d4f29-133">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="d4f29-134">Унесите излаз **Назив ентитета** у који желите да се преносе излазни резултати веб-услуга.</span><span class="sxs-lookup"><span data-stu-id="d4f29-134">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="d4f29-135">Azure машинско учење</span><span class="sxs-lookup"><span data-stu-id="d4f29-135">Azure Machine Learning</span></span>
      1. <span data-ttu-id="d4f29-136">Унесите излаз **Назив ентитета** у који желите да се преносе излазни резултати канала.</span><span class="sxs-lookup"><span data-stu-id="d4f29-136">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="d4f29-137">Изаберите **Назив излазног параметра складишта података** за групни канал из падајућег менија.</span><span class="sxs-lookup"><span data-stu-id="d4f29-137">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="d4f29-138">Изаберите **Назив излазног параметра путање** за групни канал из падајућег менија.</span><span class="sxs-lookup"><span data-stu-id="d4f29-138">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="d4f29-139">![Окно излазних параметара модела](media/intelligence-screen3-outputparameters.png "Окно излазних параметара модела")</span><span class="sxs-lookup"><span data-stu-id="d4f29-139">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="d4f29-140">Изаберите одговарајући атрибут из падајуће листе **ID клијента у резултатима** која идентификује клијенте и изаберите **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="d4f29-140">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d4f29-141">![Повежите резултате са окном података клијената](media/intelligence-screen4-relatetocustomer.png "Повежите резултате са окном података клијената")</span><span class="sxs-lookup"><span data-stu-id="d4f29-141">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="d4f29-142">Видећете екран **Ток посла је сачуван** са детаљима о току посла.</span><span class="sxs-lookup"><span data-stu-id="d4f29-142">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="d4f29-143">Ако сте конфигурисали ток посла за канал Azure машинског учења, увиди о корисницима ће се приложити у радни простор који садржи канал.</span><span class="sxs-lookup"><span data-stu-id="d4f29-143">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="d4f29-144">Увиди у публику ће добити улогу **Сарадник** у Azure радном простору.</span><span class="sxs-lookup"><span data-stu-id="d4f29-144">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="d4f29-145">Изаберите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d4f29-145">Select **Done**.</span></span>

1. <span data-ttu-id="d4f29-146">Сада можете покренути ток посла са странице **Прилагођени модели**.</span><span class="sxs-lookup"><span data-stu-id="d4f29-146">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="d4f29-147">Измена тока посла</span><span class="sxs-lookup"><span data-stu-id="d4f29-147">Edit a workflow</span></span>

1. <span data-ttu-id="d4f29-148">На страници **Прилагођени модели** изаберите усправне три тачке у колони **Радње** поред тока посла који сте претходно креирали и изаберите **Уреди**.</span><span class="sxs-lookup"><span data-stu-id="d4f29-148">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="d4f29-149">Препознатљиво име тока посла можете ажурирати у пољу **Име за приказ**, али не можете да промените конфигурисану веб-услугу или канал.</span><span class="sxs-lookup"><span data-stu-id="d4f29-149">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="d4f29-150">Изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="d4f29-150">Select **Next**.</span></span>

1. <span data-ttu-id="d4f29-151">За сваки **Унос веб-услуге**, можете да ажурирате одговарајући **Ентитет** из увида о корисницима.</span><span class="sxs-lookup"><span data-stu-id="d4f29-151">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="d4f29-152">Затим изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="d4f29-152">Then, select **Next**.</span></span>

1. <span data-ttu-id="d4f29-153">У кораку **Излазни параметри модела** поставите следећа својства:</span><span class="sxs-lookup"><span data-stu-id="d4f29-153">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="d4f29-154">Machine Learning Studio (класични)</span><span class="sxs-lookup"><span data-stu-id="d4f29-154">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="d4f29-155">Унесите излаз **Назив ентитета** у који желите да се преносе излазни резултати веб-услуга.</span><span class="sxs-lookup"><span data-stu-id="d4f29-155">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="d4f29-156">Azure машинско учење</span><span class="sxs-lookup"><span data-stu-id="d4f29-156">Azure Machine Learning</span></span>
      1. <span data-ttu-id="d4f29-157">Унесите излаз **Назив ентитета** у који желите да се преносе излазни резултати канала.</span><span class="sxs-lookup"><span data-stu-id="d4f29-157">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="d4f29-158">Изаберите **Назив излазног параметра складишта података** за пробни канал.</span><span class="sxs-lookup"><span data-stu-id="d4f29-158">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="d4f29-159">Изаберите **Назив излазног параметра путање** за пробни канал.</span><span class="sxs-lookup"><span data-stu-id="d4f29-159">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="d4f29-160">Изаберите одговарајући атрибут из падајуће листе **ID клијента у резултатима** која идентификује клијенте и изаберите **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="d4f29-160">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="d4f29-161">Морате да одаберете атрибут из излаза закључка са вредностима сличним колони са ID-ом клијента ентитета клијента.</span><span class="sxs-lookup"><span data-stu-id="d4f29-161">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="d4f29-162">Ако немате такву колону скупу података, одаберите атрибут који јединствено идентификује ред.</span><span class="sxs-lookup"><span data-stu-id="d4f29-162">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="d4f29-163">Покрени ток посла</span><span class="sxs-lookup"><span data-stu-id="d4f29-163">Run a workflow</span></span>

1. <span data-ttu-id="d4f29-164">На страници **Прилагођени модели** изаберите усправне три тачке у колони **Радње** поред тока посла који сте претходно креирали.</span><span class="sxs-lookup"><span data-stu-id="d4f29-164">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="d4f29-165">Изаберите **Покрени**.</span><span class="sxs-lookup"><span data-stu-id="d4f29-165">Select **Run**.</span></span>

<span data-ttu-id="d4f29-166">Ток посла се такође покреће аутоматски са сваким заказаним освежавањем.</span><span class="sxs-lookup"><span data-stu-id="d4f29-166">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="d4f29-167">Сазнајте више о [постављању заказаних освежавања](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d4f29-167">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="d4f29-168">Брисање тока посла</span><span class="sxs-lookup"><span data-stu-id="d4f29-168">Delete a workflow</span></span>

1. <span data-ttu-id="d4f29-169">На страници **Прилагођени модели** изаберите усправне три тачке у колони **Радње** поред тока посла који сте претходно креирали.</span><span class="sxs-lookup"><span data-stu-id="d4f29-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="d4f29-170">Изаберите **Избриши** и потврдите брисање.</span><span class="sxs-lookup"><span data-stu-id="d4f29-170">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="d4f29-171">Ваш ток посла ће бити избрисан.</span><span class="sxs-lookup"><span data-stu-id="d4f29-171">Your workflow will be deleted.</span></span> <span data-ttu-id="d4f29-172">[Ентитет](entities.md) који је креиран када сте креирали ток посла опстаје и може се прегледати са странице **Ентитети**.</span><span class="sxs-lookup"><span data-stu-id="d4f29-172">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>
