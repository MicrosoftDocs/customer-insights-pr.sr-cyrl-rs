---
title: Повежите Common Data Model податке са Azure Data Lake налогом
description: Радите са Common Data Model подацима користећи Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 247e4d9c47ff2373065ebf3c6d554323e45a120b
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267878"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="9cb69-103">Повежите се Common Data Model фасциклом која користи Azure Data Lake налог</span><span class="sxs-lookup"><span data-stu-id="9cb69-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="9cb69-104">Овај чланак пружа информације о томе како уносити податке из Common Data Model фасцикле помоћу Azure Data Lake Storage Gen2 налога.</span><span class="sxs-lookup"><span data-stu-id="9cb69-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="9cb69-105">Важна разматрања</span><span class="sxs-lookup"><span data-stu-id="9cb69-105">Important considerations</span></span>

- <span data-ttu-id="9cb69-106">Подаци у вашем Azure Data Lake треба да прате уобичајени стандард Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="9cb69-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="9cb69-107">Други формати тренутно нису подржани.</span><span class="sxs-lookup"><span data-stu-id="9cb69-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="9cb69-108">Унос података подржава само Azure Data Lake *Gen2* налоге за складиштење.</span><span class="sxs-lookup"><span data-stu-id="9cb69-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="9cb69-109">Не можете да користите Azure Data Lake Gen1 налоге за складиштење за унос података.</span><span class="sxs-lookup"><span data-stu-id="9cb69-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="9cb69-110">Да бисте потврдили идентитет помоћу принципала услуге Azure, уверите се да је конфигурисан у вашем закупцу.</span><span class="sxs-lookup"><span data-stu-id="9cb69-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="9cb69-111">За више информација погледајте [Повезивање увида о корисницима са Azure Data Lake Storage Gen2 налогом помоћу принципала Azure услуге](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="9cb69-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="9cb69-112">Azure Data Lake са којим желите да се повежете и унесете податке мора бити у истом Azure региону као и Dynamics 365 Customer Insights окружење.</span><span class="sxs-lookup"><span data-stu-id="9cb69-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="9cb69-113">Не подржавају се везе са Common Data Model фасциклом из језера података у другом Azure региону.</span><span class="sxs-lookup"><span data-stu-id="9cb69-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="9cb69-114">Да бисте сазнали Azure регион окружења, посетите **Администратор** > **Систем** > **Основни подаци** у увидима о корисницима.</span><span class="sxs-lookup"><span data-stu-id="9cb69-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="9cb69-115">Подаци који се чувају у услугама на мрежи могу се чувати на локацији која се разликује од оне на којој се подаци обрађују или чувају у услузи Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9cb69-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="9cb69-116"> Увозом или повезивањем података ускладиштених у мрежној услузи, слажете се да се подаци могу пренети и складиштити у услузи Dynamics 365 Customer Insights. [Сазнајте више у Microsoft центру за поузданост.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="9cb69-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="9cb69-117">Повежите се у фасциклу Common Data Model</span><span class="sxs-lookup"><span data-stu-id="9cb69-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="9cb69-118">У увидима о корисницима идите на **Подаци** > **Извори података**.</span><span class="sxs-lookup"><span data-stu-id="9cb69-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="9cb69-119">Изаберите **Додај извор података**.</span><span class="sxs-lookup"><span data-stu-id="9cb69-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="9cb69-120">Изаберите **Повежите се са Common Data Model фасциклом**, унесите **Име** за извор података и изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="9cb69-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="9cb69-121">Смернице за називе:</span><span class="sxs-lookup"><span data-stu-id="9cb69-121">Name guidelines:</span></span> 
   - <span data-ttu-id="9cb69-122">Започните словом.</span><span class="sxs-lookup"><span data-stu-id="9cb69-122">Start with a letter.</span></span>
   - <span data-ttu-id="9cb69-123">Користите само слова и бројеве.</span><span class="sxs-lookup"><span data-stu-id="9cb69-123">Use letters and numbers only.</span></span> <span data-ttu-id="9cb69-124">Посебни знакови и размаци нису дозвољени.</span><span class="sxs-lookup"><span data-stu-id="9cb69-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="9cb69-125">Користите између 3 и 64 знака.</span><span class="sxs-lookup"><span data-stu-id="9cb69-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="9cb69-126">Можете да бирате између коришћења опције засноване на ресурсима и опције засноване на претплати за потврду идентитета.</span><span class="sxs-lookup"><span data-stu-id="9cb69-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="9cb69-127">За више информација погледајте [Повезивање увида о корисницима са Azure Data Lake Storage Gen2 налогом помоћу принципала Azure услуге](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="9cb69-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="9cb69-128">Унесите информације о **Контејнеру** и изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="9cb69-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9cb69-129">![Дијалог за унос нових детаља везе за Azure Data Lake](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="9cb69-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="9cb69-130">Потребна вам је једна од следећих улога у контејнеру или налогу за складиштење поменутом горе да бисте могли да се повежете и креирате извор података:</span><span class="sxs-lookup"><span data-stu-id="9cb69-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="9cb69-131">Читач података складишта блоб објекта</span><span class="sxs-lookup"><span data-stu-id="9cb69-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="9cb69-132">Власник података складишта блоб објекта</span><span class="sxs-lookup"><span data-stu-id="9cb69-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="9cb69-133">Сарадник за податке складишта блоб објекта</span><span class="sxs-lookup"><span data-stu-id="9cb69-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="9cb69-134">У дијалогу **Изаберите Common Data Model фасциклу**, изаберите датотеку model.json или manifest.json из које желите да увезете податке, па изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="9cb69-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="9cb69-135">Ниједна датотека model.json или manifest.json повезана са другим извором података у окружењу неће се приказати на листи.</span><span class="sxs-lookup"><span data-stu-id="9cb69-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="9cb69-136">Листу доступних ентитета добићете у изабраној датотеци model.json или manifest.json.</span><span class="sxs-lookup"><span data-stu-id="9cb69-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="9cb69-137">Можете да прегледате ентитете и изаберете их са листе доступних ентитета, па изаберите **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="9cb69-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="9cb69-138">Сви изабрани ентитети биће унети из новог извора података.</span><span class="sxs-lookup"><span data-stu-id="9cb69-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9cb69-139">![Дијалог који приказује листу ентитета из датотеке model.json](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="9cb69-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="9cb69-140">Наведите ентитете података за које желите да омогућите профилисање података и изаберите **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="9cb69-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="9cb69-141">Профилисање података омогућава аналитику и друге могућности.</span><span class="sxs-lookup"><span data-stu-id="9cb69-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="9cb69-142">Можете одабрати читав ентитет који бира све атрибуте из ентитета или одабрати одређене атрибуте по свом избору.</span><span class="sxs-lookup"><span data-stu-id="9cb69-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="9cb69-143">Подразумевано ниједан ентитет није омогућен за профилисање података.</span><span class="sxs-lookup"><span data-stu-id="9cb69-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9cb69-144">![Дијалог који приказује профилисање података](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="9cb69-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="9cb69-145">Када сачувате изабране опције, отвориће се страница **Извори података**.</span><span class="sxs-lookup"><span data-stu-id="9cb69-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="9cb69-146">Сада би требало да видите везу Common Data Model фасцикле као извор података.</span><span class="sxs-lookup"><span data-stu-id="9cb69-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="9cb69-147">Датотека model.json или manifest.json може се повезати само са једним извором података у истом окружењу.</span><span class="sxs-lookup"><span data-stu-id="9cb69-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="9cb69-148">Међутим, иста датотека model.json или manifest.json може се користити за изворе података у више окружења.</span><span class="sxs-lookup"><span data-stu-id="9cb69-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="9cb69-149">Уредите извор података Common Data Model фасцикле</span><span class="sxs-lookup"><span data-stu-id="9cb69-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="9cb69-150">Можете да ажурирате приступни кључ за налог за складиштење који садржи Common Data Model фасциклу.</span><span class="sxs-lookup"><span data-stu-id="9cb69-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="9cb69-151">Такође можете променити датотеку model.json или manifest.json.</span><span class="sxs-lookup"><span data-stu-id="9cb69-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="9cb69-152">Да бисте се повезали на други контејнер са налога за складиштење или да промените име налога, [креирајте нову везу са извором података](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="9cb69-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="9cb69-153">У увидима о корисницима идите на **Подаци** > **Извори података**.</span><span class="sxs-lookup"><span data-stu-id="9cb69-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="9cb69-154">Поред извора података који желите да ажурирате, изаберите три тачке.</span><span class="sxs-lookup"><span data-stu-id="9cb69-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="9cb69-155">Изаберите опцију **Уреди** са листе.</span><span class="sxs-lookup"><span data-stu-id="9cb69-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="9cb69-156">Опционално, ажурирајте **Кључ за приступ** и изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="9cb69-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Дијалог за уређивање и ажурирање кључа за приступ за постојећи извор података](media/edit-access-key.png)

5. <span data-ttu-id="9cb69-158">По жељи можете да ажурирате са везе кључа налога на везу засновану на ресурсима или претплати.</span><span class="sxs-lookup"><span data-stu-id="9cb69-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="9cb69-159">За више информација погледајте [Повезивање увида о корисницима са Azure Data Lake Storage Gen2 налогом помоћу принципала Azure услуге](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="9cb69-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="9cb69-160">Не можете променити информације о **контејнеру** приликом ажурирања везе.</span><span class="sxs-lookup"><span data-stu-id="9cb69-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![Дијалог за унос детаља везе услуге Azure Data Lake са постојећим налогом за складиштење](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="9cb69-162">Потребна вам је једна од следећих улога у контејнеру или налогу за складиштење поменутом горе да бисте могли да се повежете и креирате извор података:</span><span class="sxs-lookup"><span data-stu-id="9cb69-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="9cb69-163">Читач података складишта блоб објекта</span><span class="sxs-lookup"><span data-stu-id="9cb69-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="9cb69-164">Власник података складишта блоб објекта</span><span class="sxs-lookup"><span data-stu-id="9cb69-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="9cb69-165">Сарадник за податке складишта блоб објекта</span><span class="sxs-lookup"><span data-stu-id="9cb69-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="9cb69-166">Опционално, одаберите другу датотеку model.json или manifest.json са различитим скупом ентитета из контејнера.</span><span class="sxs-lookup"><span data-stu-id="9cb69-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="9cb69-167">По жељи можете одабрати додатне ентитете за унос.</span><span class="sxs-lookup"><span data-stu-id="9cb69-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="9cb69-168">Такође можете уклонити све већ одабране ентитете ако нема зависних елемената.</span><span class="sxs-lookup"><span data-stu-id="9cb69-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="9cb69-169">Ако постоје зависности од постојеће датотеке model.json или manifest.json и скупа ентитета, видећете поруку о грешци и не можете да изаберете другу датотеку model.json или manifest.json.</span><span class="sxs-lookup"><span data-stu-id="9cb69-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="9cb69-170">Уклоните те зависности пре промене датотеке model.json или manifest.json или креирајте нови извор података са датотеком model.json или manifest.json коју желите да користите да бисте избегли уклањање зависности.</span><span class="sxs-lookup"><span data-stu-id="9cb69-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="9cb69-171">По жељи можете одабрати додатне атрибуте или ентитете како бисте омогућили профилисање података или онемогућили већ одабране.</span><span class="sxs-lookup"><span data-stu-id="9cb69-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]