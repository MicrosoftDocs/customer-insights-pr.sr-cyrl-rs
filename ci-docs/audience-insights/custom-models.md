---
title: Прилагођени модели машинског учења | Microsoft Docs
description: Радите са прилагођеним моделима из Azure машинског учења у услузи Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34489faaecc5da1ce3dd68d799b3e0e0d9672ab7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267252"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="67af1-103">Прилагођени модели машинског учења</span><span class="sxs-lookup"><span data-stu-id="67af1-103">Custom machine learning models</span></span>

<span data-ttu-id="67af1-104">**Обавештавање** > **Прилагођени модели** вам омогућавају управљање токовима посла на основу Azure модела машинског учења.</span><span class="sxs-lookup"><span data-stu-id="67af1-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="67af1-105">Токови посла помажу вам да одаберете податке од којих желите да генеришете увид и да резултате мапирате са обједињеним подацима о клијентима.</span><span class="sxs-lookup"><span data-stu-id="67af1-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="67af1-106">За више информација о изради прилагођених ML модела погледајте [Користите моделе засноване на Azure машинском учењу](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="67af1-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="67af1-107">Одговорни AI</span><span class="sxs-lookup"><span data-stu-id="67af1-107">Responsible AI</span></span>

<span data-ttu-id="67af1-108">Предвиђања нуде могућности за стварање бољег корисничког искуства, побољшање пословних прилика и токова прихода.</span><span class="sxs-lookup"><span data-stu-id="67af1-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="67af1-109">Препоручујемо вам да уравнотежите вредност предвиђања са утицајем који има и одступањима која се могу увести на етичан начин.</span><span class="sxs-lookup"><span data-stu-id="67af1-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="67af1-110">Сазнајте више о томе како Microsoft [примењује одговоран AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="67af1-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="67af1-111">Такође можете сазнати о [техникама и процесима за одговорно машинско учење](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) специфичним за Azure машинско учење.</span><span class="sxs-lookup"><span data-stu-id="67af1-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="67af1-112">Предуслови</span><span class="sxs-lookup"><span data-stu-id="67af1-112">Prerequisites</span></span>

- <span data-ttu-id="67af1-113">Тренутно ова функција подржава веб-услуге објављене путем [Machine Learning Studio (класичног)](https://studio.azureml.net) и [групних канала Azure машинског учења](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="67af1-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="67af1-114">Да бисте користили ову функцију, потребан вам је Azure Data Lake Gen2 налог за складиштење повезан са Azure Studio инстанцом.</span><span class="sxs-lookup"><span data-stu-id="67af1-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="67af1-115">За више информација погледајте [Направите Azure Data Lake Storage Gen2 налог за складиштење података](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="67af1-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="67af1-116">Додавање новог тока посла</span><span class="sxs-lookup"><span data-stu-id="67af1-116">Add a new workflow</span></span>

1. <span data-ttu-id="67af1-117">Идите на **Обавештавање** > **Прилагођени модели** и изаберите **Нови ток посла**.</span><span class="sxs-lookup"><span data-stu-id="67af1-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="67af1-118">Дајте прилагођеном моделу препознатљиво име у пољу **Име**.</span><span class="sxs-lookup"><span data-stu-id="67af1-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="67af1-119">![Снимак екрана окна „Нови ток посла“](media/new-workflowv2.png "Снимак екрана окна „Нови ток посла“")</span><span class="sxs-lookup"><span data-stu-id="67af1-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="67af1-120">Изаберите организацију која садржи веб-услугу у **закупцу који садржи вашу веб-услугу**.</span><span class="sxs-lookup"><span data-stu-id="67af1-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="67af1-121">Ако је претплата на Azure машинско учење у другом закупцу у односу на Customer Insights, одаберите **Пријавите се** помоћу акредитива за одабрану организацију.</span><span class="sxs-lookup"><span data-stu-id="67af1-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="67af1-122">Изаберите **Радне просторе** повезане са вашом веб-услугом.</span><span class="sxs-lookup"><span data-stu-id="67af1-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="67af1-123">Наведена су два одељка, један за Azure машинско учење в1 (Machine Learning Studio (класични)) и Azure машинско учење в2 (Azure машинско учење).</span><span class="sxs-lookup"><span data-stu-id="67af1-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="67af1-124">Ако нисте сигурни који је радни простор прави за вашу Machine Learning Studio (класичан) веб-услугу, изаберите **Било који**.</span><span class="sxs-lookup"><span data-stu-id="67af1-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="67af1-125">Изаберите Machine Learning Studio (класична) веб-услугу или канал Azure машинског учења у падајућем менију **Веб-услуга која садржи ваш модел**.</span><span class="sxs-lookup"><span data-stu-id="67af1-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="67af1-126">Затим изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="67af1-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="67af1-127">Сазнајте више о [објављивању веб-услуге у Machine Learning Studio (класичном)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="67af1-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="67af1-128">Сазнајте више о [објављивању канала у Azure машинском учењу помоћу дизајнера](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) или [ SDK-а](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="67af1-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="67af1-129">Ваш канал мора бити објављен под [крајњом тачком канала](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="67af1-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="67af1-130">За сваки **Унос веб-услуге**, изаберите одговарајући **Ентитет** из увида о корисницима и изаберите **Даље**.</span><span class="sxs-lookup"><span data-stu-id="67af1-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="67af1-131">Ток посла прилагођеног модела примењиваће хеуристику за мапирање поља за унос веб-услуга у атрибуте ентитета на основу имена и типа података поља.</span><span class="sxs-lookup"><span data-stu-id="67af1-131">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="67af1-132">Видећете грешку ако поље веб-услуге не може да се преслика на ентитет.</span><span class="sxs-lookup"><span data-stu-id="67af1-132">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="67af1-133">![Конфигурисање тока посла](media/intelligence-screen2-updated.png "Конфигурисање тока посла")</span><span class="sxs-lookup"><span data-stu-id="67af1-133">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>
   
1. <span data-ttu-id="67af1-134">У кораку **Излазни параметри модела** поставите следећа својства:</span><span class="sxs-lookup"><span data-stu-id="67af1-134">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="67af1-135">Machine Learning Studio (класични)</span><span class="sxs-lookup"><span data-stu-id="67af1-135">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="67af1-136">Унесите излаз **Назив ентитета** у који желите да се преносе излазни резултати веб-услуга.</span><span class="sxs-lookup"><span data-stu-id="67af1-136">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="67af1-137">Azure машинско учење</span><span class="sxs-lookup"><span data-stu-id="67af1-137">Azure Machine Learning</span></span>
      1. <span data-ttu-id="67af1-138">Унесите излаз **Назив ентитета** у који желите да се преносе излазни резултати канала.</span><span class="sxs-lookup"><span data-stu-id="67af1-138">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="67af1-139">Изаберите **Назив излазног параметра складишта података** за групни канал из падајућег менија.</span><span class="sxs-lookup"><span data-stu-id="67af1-139">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="67af1-140">Изаберите **Назив излазног параметра путање** за групни канал из падајућег менија.</span><span class="sxs-lookup"><span data-stu-id="67af1-140">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="67af1-141">![Окно излазних параметара модела](media/intelligence-screen3-outputparameters.png "Окно излазних параметара модела")</span><span class="sxs-lookup"><span data-stu-id="67af1-141">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="67af1-142">Изаберите одговарајући атрибут из падајуће листе **ID клијента у резултатима** која идентификује клијенте и изаберите **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="67af1-142">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="67af1-143">![Повежите резултате са окном података клијената](media/intelligence-screen4-relatetocustomer.png "Повежите резултате са окном података клијената")</span><span class="sxs-lookup"><span data-stu-id="67af1-143">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="67af1-144">Видећете екран **Ток посла је сачуван** са детаљима о току посла.</span><span class="sxs-lookup"><span data-stu-id="67af1-144">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="67af1-145">Ако сте конфигурисали ток посла за канал Azure машинског учења, увиди о корисницима ће се приложити у радни простор који садржи канал.</span><span class="sxs-lookup"><span data-stu-id="67af1-145">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="67af1-146">Увиди у публику ће добити улогу **Сарадник** у Azure радном простору.</span><span class="sxs-lookup"><span data-stu-id="67af1-146">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="67af1-147">Изаберите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="67af1-147">Select **Done**.</span></span>

1. <span data-ttu-id="67af1-148">Сада можете покренути ток посла са странице **Прилагођени модели**.</span><span class="sxs-lookup"><span data-stu-id="67af1-148">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="67af1-149">Измена тока посла</span><span class="sxs-lookup"><span data-stu-id="67af1-149">Edit a workflow</span></span>

1. <span data-ttu-id="67af1-150">На страници **Прилагођени модели** изаберите усправне три тачке у колони **Радње** поред тока посла који сте претходно креирали и изаберите **Уреди**.</span><span class="sxs-lookup"><span data-stu-id="67af1-150">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="67af1-151">Препознатљиво име тока посла можете ажурирати у пољу **Име за приказ**, али не можете да промените конфигурисану веб-услугу или канал.</span><span class="sxs-lookup"><span data-stu-id="67af1-151">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="67af1-152">Изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="67af1-152">Select **Next**.</span></span>

1. <span data-ttu-id="67af1-153">За сваки **Унос веб-услуге**, можете да ажурирате одговарајући **Ентитет** из увида о корисницима.</span><span class="sxs-lookup"><span data-stu-id="67af1-153">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="67af1-154">Затим изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="67af1-154">Then, select **Next**.</span></span>

1. <span data-ttu-id="67af1-155">У кораку **Излазни параметри модела** поставите следећа својства:</span><span class="sxs-lookup"><span data-stu-id="67af1-155">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="67af1-156">Machine Learning Studio (класични)</span><span class="sxs-lookup"><span data-stu-id="67af1-156">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="67af1-157">Унесите излаз **Назив ентитета** у који желите да се преносе излазни резултати веб-услуга.</span><span class="sxs-lookup"><span data-stu-id="67af1-157">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="67af1-158">Azure машинско учење</span><span class="sxs-lookup"><span data-stu-id="67af1-158">Azure Machine Learning</span></span>
      1. <span data-ttu-id="67af1-159">Унесите излаз **Назив ентитета** у који желите да се преносе излазни резултати канала.</span><span class="sxs-lookup"><span data-stu-id="67af1-159">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="67af1-160">Изаберите **Назив излазног параметра складишта података** за пробни канал.</span><span class="sxs-lookup"><span data-stu-id="67af1-160">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="67af1-161">Изаберите **Назив излазног параметра путање** за пробни канал.</span><span class="sxs-lookup"><span data-stu-id="67af1-161">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="67af1-162">Изаберите одговарајући атрибут из падајуће листе **ID клијента у резултатима** која идентификује клијенте и изаберите **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="67af1-162">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="67af1-163">Морате да одаберете атрибут из излаза закључка са вредностима сличним колони са ID-ом клијента ентитета клијента.</span><span class="sxs-lookup"><span data-stu-id="67af1-163">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="67af1-164">Ако немате такву колону скупу података, одаберите атрибут који јединствено идентификује ред.</span><span class="sxs-lookup"><span data-stu-id="67af1-164">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="67af1-165">Покрени ток посла</span><span class="sxs-lookup"><span data-stu-id="67af1-165">Run a workflow</span></span>

1. <span data-ttu-id="67af1-166">На страници **Прилагођени модели** изаберите усправне три тачке у колони **Радње** поред тока посла који сте претходно креирали.</span><span class="sxs-lookup"><span data-stu-id="67af1-166">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="67af1-167">Изаберите **Покрени**.</span><span class="sxs-lookup"><span data-stu-id="67af1-167">Select **Run**.</span></span>

<span data-ttu-id="67af1-168">Ток посла се такође покреће аутоматски са сваким заказаним освежавањем.</span><span class="sxs-lookup"><span data-stu-id="67af1-168">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="67af1-169">Сазнајте више о [постављању заказаних освежавања](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="67af1-169">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="67af1-170">Брисање тока посла</span><span class="sxs-lookup"><span data-stu-id="67af1-170">Delete a workflow</span></span>

1. <span data-ttu-id="67af1-171">На страници **Прилагођени модели** изаберите усправне три тачке у колони **Радње** поред тока посла који сте претходно креирали.</span><span class="sxs-lookup"><span data-stu-id="67af1-171">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="67af1-172">Изаберите **Избриши** и потврдите брисање.</span><span class="sxs-lookup"><span data-stu-id="67af1-172">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="67af1-173">Ваш ток посла ће бити избрисан.</span><span class="sxs-lookup"><span data-stu-id="67af1-173">Your workflow will be deleted.</span></span> <span data-ttu-id="67af1-174">[Ентитет](entities.md) који је креиран када сте креирали ток посла опстаје и може се прегледати са странице **Ентитети**.</span><span class="sxs-lookup"><span data-stu-id="67af1-174">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]