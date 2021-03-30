---
title: Креирање окружења и управљање њима
description: Сазнајте како се региструјете за услугу и како да управљате окружењима.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 1c2dfdd2889b5cb6c5285b4d7cc7f52a3d6de4d1
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598311"
---
# <a name="manage-environments"></a><span data-ttu-id="05d1a-103">Управљање окружењима</span><span class="sxs-lookup"><span data-stu-id="05d1a-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="05d1a-104">Овај чланак објашњава како да креирате нову организацију и обезбедите окружење.</span><span class="sxs-lookup"><span data-stu-id="05d1a-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="05d1a-105">Региструјте се и направите организацију</span><span class="sxs-lookup"><span data-stu-id="05d1a-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="05d1a-106">Идите на веб-локацију [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="05d1a-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="05d1a-107">Изаберите **Први кораци**.</span><span class="sxs-lookup"><span data-stu-id="05d1a-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="05d1a-108">Одаберите жељени сценарио пријаве и изаберите одговарајућу везу.</span><span class="sxs-lookup"><span data-stu-id="05d1a-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="05d1a-109">Прихватите услове и одредбе и изаберите **Настави** да бисте започели креирање организације.</span><span class="sxs-lookup"><span data-stu-id="05d1a-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="05d1a-110">Након креирања окружења, бићете преусмерени на [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="05d1a-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="05d1a-111">Користите демо окружење да истражите апликацију или креирајте ново окружење пратећи кораке у следећем одељку.</span><span class="sxs-lookup"><span data-stu-id="05d1a-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="05d1a-112">Када наведете подешавања окружења, изаберите **Креирај**.</span><span class="sxs-lookup"><span data-stu-id="05d1a-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="05d1a-113">Бићете пријављени након што је окружење успешно креирано.</span><span class="sxs-lookup"><span data-stu-id="05d1a-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="05d1a-114">Креирајте окружење у постојећој организацији</span><span class="sxs-lookup"><span data-stu-id="05d1a-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="05d1a-115">Постоје два начина за креирање новог окружења.</span><span class="sxs-lookup"><span data-stu-id="05d1a-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="05d1a-116">Можете да наведете потпуно нову конфигурацију или да копирате нека подешавања конфигурације из постојећег окружења.</span><span class="sxs-lookup"><span data-stu-id="05d1a-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="05d1a-117">Да бисте креирали окружења:</span><span class="sxs-lookup"><span data-stu-id="05d1a-117">To create an environment:</span></span>

1. <span data-ttu-id="05d1a-118">Изаберите бирач **Окружење** у заглављу апликације.</span><span class="sxs-lookup"><span data-stu-id="05d1a-118">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="05d1a-119">Изаберите **Ново**.</span><span class="sxs-lookup"><span data-stu-id="05d1a-119">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="05d1a-120">![Подешавања окружења](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="05d1a-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="05d1a-121">У дијалогу **Креирајте ново окружење**, изаберите **Ново окружење**.</span><span class="sxs-lookup"><span data-stu-id="05d1a-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="05d1a-122">Ако желите да [копирате податке из тренутног окружења](#additional-considerations-for-copy-configuration-preview), изаберите **Копирај из постојећег окружења**.</span><span class="sxs-lookup"><span data-stu-id="05d1a-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="05d1a-123">Видећете листу свих доступних окружења у вашој организацији, одакле можете копирати податке.</span><span class="sxs-lookup"><span data-stu-id="05d1a-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="05d1a-124">Наведите следеће детаље:</span><span class="sxs-lookup"><span data-stu-id="05d1a-124">Provide the following details:</span></span>
   - <span data-ttu-id="05d1a-125">**Назив**: Унесите назив овог окружења.</span><span class="sxs-lookup"><span data-stu-id="05d1a-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="05d1a-126">Ово поље је већ попуњено ако сте копирали постојеће окружење, али можете га променити.</span><span class="sxs-lookup"><span data-stu-id="05d1a-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="05d1a-127">**Регион**: Регион у којем је услуга примењена и хостована.</span><span class="sxs-lookup"><span data-stu-id="05d1a-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="05d1a-128">**Тип**: Изаберите да ли желите да креирате производно или Sandbox окружење.</span><span class="sxs-lookup"><span data-stu-id="05d1a-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="05d1a-129">По жељи можете одабрати **Напредна подешавања**:</span><span class="sxs-lookup"><span data-stu-id="05d1a-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="05d1a-130">**Сачувај све податке у**: Одређује где желите да сачувате излазне податке генерисане у услузи Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="05d1a-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="05d1a-131">Имаћете две могућности: **Customer Insights складиште** (Azure Data Lake којим управља Customer Insights тим) и **Azure Data Lake Storage Gen2** (ваш сопствени Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="05d1a-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="05d1a-132">Подразумевано је одабрана опција Customer Insights складишта.</span><span class="sxs-lookup"><span data-stu-id="05d1a-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="05d1a-133">Чувањем података у услузи Azure Data Lake Storage, слажете се да ће подаци бити пренети и ускладиштени на одговарајућој географској локацији за тај Azure налог за складиштење, која може да се разликује од места складиштења података у услузи Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="05d1a-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="05d1a-134">Сазнајте више у Microsoft центру за поузданост.</span><span class="sxs-lookup"><span data-stu-id="05d1a-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="05d1a-135">Тренутно се унети ентитети увек чувају у језеру података којим управља Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="05d1a-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="05d1a-136">Подржавамо само Azure Data Lake Gen2 налоге за складиштење из исте Azure регије коју сте изабрали приликом креирања окружења.</span><span class="sxs-lookup"><span data-stu-id="05d1a-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="05d1a-137">Ми подржавамо само налоге за складиштење које омогућује Azure Data Lake Gen2 хијерархијски простору имена (HNS).</span><span class="sxs-lookup"><span data-stu-id="05d1a-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="05d1a-138">За опцију Azure Data Lake Storage Gen2, можете да бирате између опције засноване на ресурсима и опције засноване на претплати за потврду идентитета.</span><span class="sxs-lookup"><span data-stu-id="05d1a-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="05d1a-139">За више информација погледајте [Повезивање увида о корисницима са Azure Data Lake Storage Gen2 налогом помоћу принципала Azure услуге](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="05d1a-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="05d1a-140">Назив **контејнера** се не може променити и биће „увиди о корисницима“.</span><span class="sxs-lookup"><span data-stu-id="05d1a-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="05d1a-141">Ако желите да користите [предвиђања](predictions.md) или конфигуришете дељење података са апликацијама и решењима засновано на платформи Microsoft Dataverse, обезбедите URL адресу Microsoft Dataverse окружења у делу **Конфигуришите дељење података са платформом Microsoft Dataverse и омогућите додатне могућности**.</span><span class="sxs-lookup"><span data-stu-id="05d1a-141">If you want to use [predictions](predictions.md) or configure data sharing with applications and solutions based on Microsoft Dataverse, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="05d1a-142">Изаберите **Омогући дељење података** да бисте делили Customer Insights излазне податке помоћу услуге Microsoft Dataverse Managed Data Lake.</span><span class="sxs-lookup"><span data-stu-id="05d1a-142">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="05d1a-143">Дељење података помоћу услуге Microsoft Dataverse Managed Data Lake тренутно није подржано када све податке чувате у сопственом Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="05d1a-143">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="05d1a-144">[Предвиђање вредности које недостају у ентитету](predictions.md) тренутно није подржано када омогућите дељење података са услугом Microsoft Dataverse Managed Data Lake.</span><span class="sxs-lookup"><span data-stu-id="05d1a-144">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="05d1a-145">![Опције конфигурације за омогућавање дељења података са услугом Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="05d1a-145">![Configuration options to enable data sharing with Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="05d1a-146">Када покренете процесе, попут уноса података или креирања сегмента, на налогу за складиштење који сте горе навели креираће се одговарајуће мапе.</span><span class="sxs-lookup"><span data-stu-id="05d1a-146">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="05d1a-147">Датотеке података и датотеке model.json ће бити креиране и додате у одговарајуће потфасикле на основу процеса који покрећете.</span><span class="sxs-lookup"><span data-stu-id="05d1a-147">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="05d1a-148">Ако креирате више окружења за Customer Insights и одлучите да сачувате излазне ентитете из тих окружења на свом налогу за складиштење, креираће се засебне фасцикле за свако окружење са ci_<environmentid> у контејнеру.</span><span class="sxs-lookup"><span data-stu-id="05d1a-148">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="05d1a-149">Додатна разматрања за конфигурацију копија (преглед)</span><span class="sxs-lookup"><span data-stu-id="05d1a-149">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="05d1a-150">Копирају се следећа подешавања конфигурације:</span><span class="sxs-lookup"><span data-stu-id="05d1a-150">The following configuration settings are copied:</span></span>

- <span data-ttu-id="05d1a-151">Конфигурације функција</span><span class="sxs-lookup"><span data-stu-id="05d1a-151">Feature configurations</span></span>
- <span data-ttu-id="05d1a-152">Унесени/увезени извори података</span><span class="sxs-lookup"><span data-stu-id="05d1a-152">Ingested/imported data sources</span></span>
- <span data-ttu-id="05d1a-153">Конфигурација обједињавања података (мапа, подударање, спајање)</span><span class="sxs-lookup"><span data-stu-id="05d1a-153">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="05d1a-154">Сегменти</span><span class="sxs-lookup"><span data-stu-id="05d1a-154">Segments</span></span>
- <span data-ttu-id="05d1a-155">Мере</span><span class="sxs-lookup"><span data-stu-id="05d1a-155">Measures</span></span>
- <span data-ttu-id="05d1a-156">Односи</span><span class="sxs-lookup"><span data-stu-id="05d1a-156">Relationships</span></span>
- <span data-ttu-id="05d1a-157">Активности</span><span class="sxs-lookup"><span data-stu-id="05d1a-157">Activities</span></span>
- <span data-ttu-id="05d1a-158">Индекс претраге и филтрирања</span><span class="sxs-lookup"><span data-stu-id="05d1a-158">Search & filter Index</span></span>
- <span data-ttu-id="05d1a-159">Одредишта за извоз</span><span class="sxs-lookup"><span data-stu-id="05d1a-159">Export destinations</span></span>
- <span data-ttu-id="05d1a-160">Планирано освежавање</span><span class="sxs-lookup"><span data-stu-id="05d1a-160">Scheduled refresh</span></span>
- <span data-ttu-id="05d1a-161">Обогаћивања</span><span class="sxs-lookup"><span data-stu-id="05d1a-161">Enrichments</span></span>
- <span data-ttu-id="05d1a-162">Управљање моделима</span><span class="sxs-lookup"><span data-stu-id="05d1a-162">Model management</span></span>
- <span data-ttu-id="05d1a-163">Додела улога</span><span class="sxs-lookup"><span data-stu-id="05d1a-163">Role assignments</span></span>

<span data-ttu-id="05d1a-164">Следећа подешавања се *не* копирају:</span><span class="sxs-lookup"><span data-stu-id="05d1a-164">The following settings are *not* copied:</span></span>

- <span data-ttu-id="05d1a-165">Профили клијената.</span><span class="sxs-lookup"><span data-stu-id="05d1a-165">Customer profiles.</span></span>
- <span data-ttu-id="05d1a-166">Акредитиви извора података.</span><span class="sxs-lookup"><span data-stu-id="05d1a-166">Data source credentials.</span></span> <span data-ttu-id="05d1a-167">Мораћете да доставите акредитиве за сваки извор података и ручно освежите изворе података.</span><span class="sxs-lookup"><span data-stu-id="05d1a-167">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="05d1a-168">Извори података из фасцикле Common Data Model и Common Data Service управљаног језера.</span><span class="sxs-lookup"><span data-stu-id="05d1a-168">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="05d1a-169">Те изворе података ћете морати да креирате ручно, с истим називом као у изворном окружењу.</span><span class="sxs-lookup"><span data-stu-id="05d1a-169">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="05d1a-170">Када копирате окружење, видећете поруку потврде да је креирано ново окружење.</span><span class="sxs-lookup"><span data-stu-id="05d1a-170">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="05d1a-171">Изаберите **Идите на изворе података** да бисте видели листу извора података.</span><span class="sxs-lookup"><span data-stu-id="05d1a-171">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="05d1a-172">Сви извори података ће показати статус **Потребни су акредитиви**.</span><span class="sxs-lookup"><span data-stu-id="05d1a-172">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="05d1a-173">Уредите изворе података и унесите акредитиве да бисте их освежили.</span><span class="sxs-lookup"><span data-stu-id="05d1a-173">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="05d1a-174">![Копирани извори података](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="05d1a-174">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="05d1a-175">Након освежавања извора података, идите на **Подаци** > **Обједини**.</span><span class="sxs-lookup"><span data-stu-id="05d1a-175">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="05d1a-176">Овде ћете пронаћи подешавања из изворног окружења.</span><span class="sxs-lookup"><span data-stu-id="05d1a-176">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="05d1a-177">Уредите их по потреби или изаберите **Покрени** да бисте покренули процес обједињавања података и креирали обједињени ентитет клијента.</span><span class="sxs-lookup"><span data-stu-id="05d1a-177">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="05d1a-178">Када обједињавање података буде довршено, идите на **Мере** и **Сегменти** да освежите и њих.</span><span class="sxs-lookup"><span data-stu-id="05d1a-178">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="05d1a-179">Уређивање постојећег окружења</span><span class="sxs-lookup"><span data-stu-id="05d1a-179">Edit an existing environment</span></span>

<span data-ttu-id="05d1a-180">Можете да измените неке детаље постојећих окружења.</span><span class="sxs-lookup"><span data-stu-id="05d1a-180">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="05d1a-181">Изаберите бирач **Окружење** у заглављу апликације.</span><span class="sxs-lookup"><span data-stu-id="05d1a-181">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="05d1a-182">Изаберите икону **Уређивање**.</span><span class="sxs-lookup"><span data-stu-id="05d1a-182">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="05d1a-183">У оквиру **Уреди окружење** можете ажурирати окружење **Име за приказ** окружења, али не можете да промените **Регион** или **Тип**.</span><span class="sxs-lookup"><span data-stu-id="05d1a-183">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="05d1a-184">Ако је окружење конфигурисано за чување података Azure Data Lake Storage Gen2, можете да ажурирате **Кључ налога**.</span><span class="sxs-lookup"><span data-stu-id="05d1a-184">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="05d1a-185">Међутим, не можете променити **Име налога** ни име **контејнера**.</span><span class="sxs-lookup"><span data-stu-id="05d1a-185">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="05d1a-186">По жељи можете да ажурирате са везе кључа налога на везу засновану на ресурсима или претплати.</span><span class="sxs-lookup"><span data-stu-id="05d1a-186">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="05d1a-187">Када их надоградите, не можете се вратити на кључ налога након ажурирања.</span><span class="sxs-lookup"><span data-stu-id="05d1a-187">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="05d1a-188">За више информација погледајте [Повезивање увида о корисницима са Azure Data Lake Storage Gen2 налогом помоћу принципала Azure услуге](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="05d1a-188">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="05d1a-189">Не можете променити информације о **контејнеру** приликом ажурирања везе.</span><span class="sxs-lookup"><span data-stu-id="05d1a-189">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="05d1a-190">Успостављање почетних вредности постојећег окружења</span><span class="sxs-lookup"><span data-stu-id="05d1a-190">Reset an existing environment</span></span>

<span data-ttu-id="05d1a-191">Као администратор, можете да вратите окружење на празно стање ако желите да избришете све конфигурације и уклоните унете податке.</span><span class="sxs-lookup"><span data-stu-id="05d1a-191">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="05d1a-192">Изаберите бирач **Окружење** у заглављу апликације.</span><span class="sxs-lookup"><span data-stu-id="05d1a-192">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="05d1a-193">Изаберите окружење које желите да ресетујете и изаберите три тачке **...**.</span><span class="sxs-lookup"><span data-stu-id="05d1a-193">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="05d1a-194">Изаберите опцију **Ресетуј**.</span><span class="sxs-lookup"><span data-stu-id="05d1a-194">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="05d1a-195">Да бисте потврдили брисање, унесите име окружења и изаберите **Ресетуј**.</span><span class="sxs-lookup"><span data-stu-id="05d1a-195">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="05d1a-196">Избришите постојеће окружење (доступно само за администраторе)</span><span class="sxs-lookup"><span data-stu-id="05d1a-196">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="05d1a-197">Као администратор можете да избришете окружење којим администрирате.</span><span class="sxs-lookup"><span data-stu-id="05d1a-197">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="05d1a-198">Изаберите бирач **Окружење** у заглављу апликације.</span><span class="sxs-lookup"><span data-stu-id="05d1a-198">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="05d1a-199">Изаберите окружење које желите да ресетујете и изаберите три тачке **...**.</span><span class="sxs-lookup"><span data-stu-id="05d1a-199">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="05d1a-200">Одаберите опцију **Избриши**.</span><span class="sxs-lookup"><span data-stu-id="05d1a-200">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="05d1a-201">Да бисте потврдили брисање, унесите назив окружења и изаберите **Избриши**.</span><span class="sxs-lookup"><span data-stu-id="05d1a-201">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]