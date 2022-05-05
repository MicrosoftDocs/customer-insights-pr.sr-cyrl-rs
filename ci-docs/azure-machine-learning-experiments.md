---
title: Експерименти Azure машинског учења
description: Користите моделе засноване на Azure машинском учењу у услузи Dynamics 365 Customer Insights.
ms.date: 12/02/2021
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: cefd037a021b669e827f0593d63b938d452963f7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643264"
---
# <a name="use-azure-machine-learning-based-models"></a>Користите моделе засноване на Azure машинском учењу

Обједињени подаци у услузи Dynamics 365 Customer Insights јесу извор за изградњу модела машинског учења који могу створити додатне пословне увиде. Customer Insights се интегрише са Azure машинским учењем како би користио ваше сопствене прилагођене моделе.

## <a name="prerequisites"></a>Предуслови

- Приступ у Customer Insights
- Активна Azure Enterprise претплата
- [Обједињени профил клијента](data-unification.md)
- [Извоз ентитета у Azure складиште блоб објеката](export-azure-blob-storage.md) је конфигурисан

## <a name="set-up-azure-machine-learning-workspace"></a>Подесите радни простор за Azure машинско учење

1. Погледајте [креирање радног простора за Azure машинско учење](/azure/machine-learning/concept-workspace#-create-a-workspace) за различите опције за креирање радног простора. За најбоље перформансе направите радни простор у Azure региону који је географски најближи вашем Customer Insights окружењу.

1. Приступите свом радном простору путем [услуге Azure Machine Learning Studio](https://ml.azure.com/). Има неколико [начина интеракције](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) са радним простором.

## <a name="work-with-azure-machine-learning-designer"></a>Радите са дизајнером за Azure машинско учење

Азуре Машинско учење обезбеђује визуелну подлогу на којој можете да превлачите и отпустите групе података и модуле. Групни канал креиран из дизајнера може се интегрисати у Customer Insights ако су конфигурисани у складу с тим. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Рад са SDK-ом за Azure машинско учење

Научници за податке и AI програмери користе [SDK за Azure машинско учење](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) за изградњу токова посла машинског учења. Тренутно модели обучени помоћу SDK-а не могу директно да се интегришу са услугом Customer Insights. Групни канал за закључивање који користи тај модел потребан је за интеграцију са услугом Customer Insights.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Захтеви за групни канал за интеграцију са услугом Customer Insights

### <a name="dataset-configuration"></a>Конфигурација скупа података

Морате да креирате скупове података да бисте користили податке ентитета од услуге Customer Insights до групног канала за закључивање. Ове скупове података треба регистровати у радном простору. Тренутно подржавамо само [табеларне скупове података](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) у .csv формату. За скупове података који одговарају подацима ентитета морају се одредити параметри као параметар канала.
   
* Параметри скупа података у дизајнеру
   
     У дизајнеру отворите **Изаберите колоне у скупу података** и изаберите **Постави као параметар канала** где дајете име за параметар.

     > [!div class="mx-imgBorder"]
     > ![Одређивање параметара скупа података у дизајнеру.](media/intelligence-designer-dataset-parameters.png "Одређивање параметара скупа података у дизајнеру")
   
* Параметар скупа података у SDK-у (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Групни канал за закључивање
  
* У дизајнеру се канал за обуку може користити за стварање или ажурирање канала за закључивање. Тренутно су подржани само групни канали за закључивање.

* Коришћењем SDK-а можете објавити канал на крајњој тачки. Тренутно се Customer Insights интегрише са подразумеваним каналом у крајњој тачки групног канала у радном простору за машинско учење.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Увезите податке о каналу у Customer Insights

* Дизајнер обезбеђује [модул за извоз података](/azure/machine-learning/algorithm-module-reference/export-data) који омогућава извоз излаза канала у Azure складиште. Тренутно модул мора да користи тип складишта података **Azure складиште блоб објеката** и да одреди параметре та **складиште података** и релативну **путању**. Customer Insights замењује оба ова параметра током извршавања канала помоћу складишта података и путање која је доступна производу.
   > [!div class="mx-imgBorder"]
   > ![Извоз конфигурације модула података.](media/intelligence-designer-importdata.png "Извоз конфигурације модула података")
   
* Када записујете излаз закључка помоћу кода, можете отпремити излаз на путању унутар *регистрованог складишта података* у радном простору. Ако су за путању и складиште података одређени параметри у каналу, Customer insights моћи ће да прочита и увезе излаз закључка. Тренутно је подржан један табеларни излаз у csv формату. Путања мора да садржи директоријум и име датотеке.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]