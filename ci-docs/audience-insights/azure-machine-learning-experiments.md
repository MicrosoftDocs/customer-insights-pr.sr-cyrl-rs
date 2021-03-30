---
title: Експерименти Azure машинског учења
description: Користите моделе засноване на Azure машинском учењу у услузи Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: edd2cf488b52cef87b09b90336e48fdc7f470a68
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597437"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="e991a-103">Користите моделе засноване на Azure машинском учењу</span><span class="sxs-lookup"><span data-stu-id="e991a-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="e991a-104">Обједињени подаци у услузи Dynamics 365 Customer Insights јесу извор за изградњу модела машинског учења који могу створити додатне пословне увиде.</span><span class="sxs-lookup"><span data-stu-id="e991a-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="e991a-105">Customer Insights се интегрише са Machine Learning Studio (класични) и Azure машинским учењем да би користио ваше прилагођене моделе.</span><span class="sxs-lookup"><span data-stu-id="e991a-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="e991a-106">Погледајте [Machine Learning Studio (класични) експерименте](machine-learning-studio-experiments.md) за примере експеримената изграђених на основу услуге Machine Learning Studio (класичан).</span><span class="sxs-lookup"><span data-stu-id="e991a-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="e991a-107">Предуслови</span><span class="sxs-lookup"><span data-stu-id="e991a-107">Prerequisites</span></span>

- <span data-ttu-id="e991a-108">Приступ у Customer Insights</span><span class="sxs-lookup"><span data-stu-id="e991a-108">Access to Customer Insights</span></span>
- <span data-ttu-id="e991a-109">Активна Azure Enterprise претплата</span><span class="sxs-lookup"><span data-stu-id="e991a-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="e991a-110">Обједињени профил клијента</span><span class="sxs-lookup"><span data-stu-id="e991a-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="e991a-111">[Извоз ентитета у Azure складиште блоб објеката](export-azure-blob-storage.md) је конфигурисан</span><span class="sxs-lookup"><span data-stu-id="e991a-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="e991a-112">Подесите радни простор за Azure машинско учење</span><span class="sxs-lookup"><span data-stu-id="e991a-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="e991a-113">Погледајте [креирање радног простора за Azure машинско учење](/azure/machine-learning/concept-workspace#-create-a-workspace) за различите опције за креирање радног простора.</span><span class="sxs-lookup"><span data-stu-id="e991a-113">See [create a Azure Machine Learning workspace](/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="e991a-114">За најбоље перформансе направите радни простор у Azure региону који је географски најближи вашем Customer Insights окружењу.</span><span class="sxs-lookup"><span data-stu-id="e991a-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="e991a-115">Приступите свом радном простору путем [услуге Azure Machine Learning Studio](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="e991a-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="e991a-116">Има неколико [начина интеракције](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) са радним простором.</span><span class="sxs-lookup"><span data-stu-id="e991a-116">There are several [ways to interact](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="e991a-117">Радите са дизајнером за Azure машинско учење</span><span class="sxs-lookup"><span data-stu-id="e991a-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="e991a-118">Дизајнер за Azure машинско учење пружа визуелну подлогу по којој можете превлачити и отпуштати скупове података и модуле, слично као Machine Learning Studio (класични).</span><span class="sxs-lookup"><span data-stu-id="e991a-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="e991a-119">Групни канал креиран из дизајнера може се интегрисати у Customer Insights ако су конфигурисани у складу с тим.</span><span class="sxs-lookup"><span data-stu-id="e991a-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="e991a-120">Рад са SDK-ом за Azure машинско учење</span><span class="sxs-lookup"><span data-stu-id="e991a-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="e991a-121">Научници за податке и AI програмери користе [SDK за Azure машинско учење](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) за изградњу токова посла машинског учења.</span><span class="sxs-lookup"><span data-stu-id="e991a-121">Data scientists and AI developers use the [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) to build machine learning workflows.</span></span> <span data-ttu-id="e991a-122">Тренутно модели обучени помоћу SDK-а не могу директно да се интегришу са услугом Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e991a-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="e991a-123">Групни канал за закључивање који користи тај модел потребан је за интеграцију са услугом Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e991a-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="e991a-124">Захтеви за групни канал за интеграцију са услугом Customer Insights</span><span class="sxs-lookup"><span data-stu-id="e991a-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="e991a-125">Конфигурација скупа података</span><span class="sxs-lookup"><span data-stu-id="e991a-125">Dataset Configuration</span></span>

<span data-ttu-id="e991a-126">Морате да креирате скупове података да бисте користили податке ентитета од услуге Customer Insights до групног канала за закључивање.</span><span class="sxs-lookup"><span data-stu-id="e991a-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="e991a-127">Ове скупове података треба регистровати у радном простору.</span><span class="sxs-lookup"><span data-stu-id="e991a-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="e991a-128">Тренутно подржавамо само [табеларне скупове података](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) у .csv формату.</span><span class="sxs-lookup"><span data-stu-id="e991a-128">Currently, we only support [tabular datasets](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="e991a-129">За скупове података који одговарају подацима ентитета морају се одредити параметри као параметар канала.</span><span class="sxs-lookup"><span data-stu-id="e991a-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="e991a-130">Параметри скупа података у дизајнеру</span><span class="sxs-lookup"><span data-stu-id="e991a-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="e991a-131">У дизајнеру отворите **Изаберите колоне у скупу података** и изаберите **Постави као параметар канала** где дајете име за параметар.</span><span class="sxs-lookup"><span data-stu-id="e991a-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="e991a-132">![Одређивање параметара скупа података у дизајнеру](media/intelligence-designer-dataset-parameters.png "Одређивање параметара скупа података у дизајнеру")</span><span class="sxs-lookup"><span data-stu-id="e991a-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="e991a-133">Параметар скупа података у SDK-у (Python)</span><span class="sxs-lookup"><span data-stu-id="e991a-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="e991a-134">Групни канал за закључивање</span><span class="sxs-lookup"><span data-stu-id="e991a-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="e991a-135">У дизајнеру се канал за обуку може користити за стварање или ажурирање канала за закључивање.</span><span class="sxs-lookup"><span data-stu-id="e991a-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="e991a-136">Тренутно су подржани само групни канали за закључивање.</span><span class="sxs-lookup"><span data-stu-id="e991a-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="e991a-137">Коришћењем SDK-а можете објавити канал на крајњој тачки.</span><span class="sxs-lookup"><span data-stu-id="e991a-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="e991a-138">Тренутно се Customer Insights интегрише са подразумеваним каналом у крајњој тачки групног канала у радном простору за машинско учење.</span><span class="sxs-lookup"><span data-stu-id="e991a-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="e991a-139">Увезите податке о каналу у Customer Insights</span><span class="sxs-lookup"><span data-stu-id="e991a-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="e991a-140">Дизајнер обезбеђује [модул за извоз података](/azure/machine-learning/algorithm-module-reference/export-data) који омогућава извоз излаза канала у Azure складиште.</span><span class="sxs-lookup"><span data-stu-id="e991a-140">The designer provides the [Export Data module](/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="e991a-141">Тренутно модул мора да користи тип складишта података **Azure складиште блоб објеката** и да одреди параметре та **складиште података** и релативну **путању**.</span><span class="sxs-lookup"><span data-stu-id="e991a-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="e991a-142">Customer Insights замењује оба ова параметра током извршавања канала помоћу складишта података и путање која је доступна производу.</span><span class="sxs-lookup"><span data-stu-id="e991a-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e991a-143">![Извоз конфигурације модула података](media/intelligence-designer-importdata.png "Извоз конфигурације модула података")</span><span class="sxs-lookup"><span data-stu-id="e991a-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="e991a-144">Када записујете излаз закључка помоћу кода, можете отпремити излаз на путању унутар *регистрованог складишта података* у радном простору.</span><span class="sxs-lookup"><span data-stu-id="e991a-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="e991a-145">Ако су за путању и складиште података одређени параметри у каналу, Customer insights моћи ће да прочита и увезе излаз закључка.</span><span class="sxs-lookup"><span data-stu-id="e991a-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="e991a-146">Тренутно је подржан један табеларни излаз у csv формату.</span><span class="sxs-lookup"><span data-stu-id="e991a-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="e991a-147">Путања мора да садржи директоријум и име датотеке.</span><span class="sxs-lookup"><span data-stu-id="e991a-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE[footer-include](../includes/footer-banner.md)]