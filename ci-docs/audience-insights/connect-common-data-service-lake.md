---
title: Повежите се са ентитетима у Common Data Service надгледаном језеру
description: Увоз података из Common Data Service управљаног језера података.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 18b6cd3fdaf5b738877a73b520b91dbc6ded40de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267832"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="60706-103">Повежите се са подацима у Common Data Service управљаном језеру података</span><span class="sxs-lookup"><span data-stu-id="60706-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="60706-104">Овај чланак пружа информације о томе како постојећи Dynamics 365 корисници могу брзо да се повежу са својим аналитичким ентитетима у Common Data Service управљаном језеру.</span><span class="sxs-lookup"><span data-stu-id="60706-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="60706-105">Морате бити администратор Common Data Service организације како бисте наставили и видели списак ентитета доступних у управљаном језеру.</span><span class="sxs-lookup"><span data-stu-id="60706-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="60706-106">Важна разматрања</span><span class="sxs-lookup"><span data-stu-id="60706-106">Important considerations</span></span>

<span data-ttu-id="60706-107">Подаци ускладиштени у мрежним услугама, као што је Azure Data Lake Storage, могу се складиштити на локацији различитој од оне на којој се подаци обрађују или складиште у услузи Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="60706-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="60706-108"> Увозом или повезивањем података ускладиштених у мрежној услузи, слажете се да се подаци могу пренети и складиштити у услузи Dynamics 365 Customer Insights. [Сазнајте више у Microsoft центру за поузданост.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="60706-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="60706-109">Повежите се са Common Data Service управљаним језером</span><span class="sxs-lookup"><span data-stu-id="60706-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="60706-110">У увидима о корисницима идите на **Подаци** > **Извори података**.</span><span class="sxs-lookup"><span data-stu-id="60706-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="60706-111">Изаберите **Додај извор података**.</span><span class="sxs-lookup"><span data-stu-id="60706-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="60706-112">Изаберите **Повезивање са услугом Common Data Service** и изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="60706-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="60706-113">Унесите **Назив** извора података и изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="60706-113">Enter a **Name** for the data source and select **Next**.</span></span> <span data-ttu-id="60706-114">Смернице за називе:</span><span class="sxs-lookup"><span data-stu-id="60706-114">Name guidelines:</span></span> 
   - <span data-ttu-id="60706-115">Започните словом.</span><span class="sxs-lookup"><span data-stu-id="60706-115">Start with a letter.</span></span>
   - <span data-ttu-id="60706-116">Користите само слова и бројеве.</span><span class="sxs-lookup"><span data-stu-id="60706-116">Use letters and numbers only.</span></span> <span data-ttu-id="60706-117">Посебни знакови и размаци нису дозвољени.</span><span class="sxs-lookup"><span data-stu-id="60706-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="60706-118">Користите између 3 и 64 знака.</span><span class="sxs-lookup"><span data-stu-id="60706-118">Use between 3 and 64 characters.</span></span>

5. <span data-ttu-id="60706-119">Наведите **Адресу сервера** за вашу Common Data Service организацију и изаберите **Пријавите се**.</span><span class="sxs-lookup"><span data-stu-id="60706-119">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="60706-120">![Дијалог за унос Common Data Service адресе сервера](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="60706-120">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="60706-121">Изаберите ентитете које желите да унесете са доступне листе.</span><span class="sxs-lookup"><span data-stu-id="60706-121">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="60706-122">Ако су неки ентитети већ изабрани, могу их користити друге Dynamics 365 апликације (као што су Dynamics 365 Sales Insights или Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="60706-122">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="60706-123">Не можете променити избор.</span><span class="sxs-lookup"><span data-stu-id="60706-123">You can't change the selection.</span></span> <span data-ttu-id="60706-124">Ови ентитети ће бити доступни након креирања извора података.</span><span class="sxs-lookup"><span data-stu-id="60706-124">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="60706-125">![Дијалог који приказује листу ентитета у Common Data Service организацији](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="60706-125">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="60706-126">Сачувајте свој избор да бисте започели синхронизацију изабраних ентитета са Common Data Service управљаним језером.</span><span class="sxs-lookup"><span data-stu-id="60706-126">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="60706-127">Новододату везу ћете пронаћи на страници **Извори података**.</span><span class="sxs-lookup"><span data-stu-id="60706-127">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="60706-128">Биће постављена у ред за освежавање и приказаће бројеве ентитета као 0 док се сви ентитети не синхронизују.</span><span class="sxs-lookup"><span data-stu-id="60706-128">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="60706-129">Само један извор података окружења може истовремено да користи исто Common Data Service надгледано језеро.</span><span class="sxs-lookup"><span data-stu-id="60706-129">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="60706-130">Уредите извор података за Common Data Service управљано језеро</span><span class="sxs-lookup"><span data-stu-id="60706-130">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="60706-131">Избор ентитета уређујете тек након што креирате извор података.</span><span class="sxs-lookup"><span data-stu-id="60706-131">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="60706-132">На пример, ако су додати додатни ентитети у услугу Common Data Service, а желите и да их увозите.</span><span class="sxs-lookup"><span data-stu-id="60706-132">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="60706-133">Да бисте се повезали са другом услугом Common Data Service, [креирајте нови извор података](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="60706-133">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="60706-134">У увидима о корисницима идите на **Подаци** > **Извори података**.</span><span class="sxs-lookup"><span data-stu-id="60706-134">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="60706-135">Поред извора података који желите да ажурирате, изаберите три тачке.</span><span class="sxs-lookup"><span data-stu-id="60706-135">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="60706-136">Изаберите опцију **Уреди** са листе.</span><span class="sxs-lookup"><span data-stu-id="60706-136">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="60706-137">Изаберите додатне ентитете с доступне листе ентитета и изаберите **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="60706-137">Select additional entities from the available list of entities and select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]