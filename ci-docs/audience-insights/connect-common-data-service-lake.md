---
title: Повежите се са ентитетима у Common Data Service надгледаном језеру
description: Увоз података из Common Data Service управљаног језера података.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643416"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="15b5b-103">Повежите се са подацима у Common Data Service управљаном језеру података</span><span class="sxs-lookup"><span data-stu-id="15b5b-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="15b5b-104">Овај чланак пружа информације о томе како постојећи Dynamics 365 корисници могу брзо да се повежу са својим аналитичким ентитетима у Common Data Service управљаном језеру.</span><span class="sxs-lookup"><span data-stu-id="15b5b-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="15b5b-105">Морате бити администратор Common Data Service организације како бисте наставили и видели списак ентитета доступних у управљаном језеру.</span><span class="sxs-lookup"><span data-stu-id="15b5b-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="15b5b-106">Важна разматрања</span><span class="sxs-lookup"><span data-stu-id="15b5b-106">Important considerations</span></span>

<span data-ttu-id="15b5b-107">Подаци ускладиштени у мрежним услугама, као што је Azure Data Lake Storage, могу се складиштити на локацији различитој од оне на којој се подаци обрађују или складиште у услузи Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="15b5b-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="15b5b-108"> Увозом или повезивањем података ускладиштених у мрежној услузи, слажете се да се подаци могу пренети и складиштити у услузи Dynamics 365 Customer Insights. [Сазнајте више у Microsoft центру за поузданост.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="15b5b-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="15b5b-109">Повежите се са Common Data Service управљаним језером</span><span class="sxs-lookup"><span data-stu-id="15b5b-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="15b5b-110">У увидима о корисницима идите на **Подаци** > **Извори података**.</span><span class="sxs-lookup"><span data-stu-id="15b5b-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="15b5b-111">Изаберите **Додај извор података**.</span><span class="sxs-lookup"><span data-stu-id="15b5b-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="15b5b-112">Изаберите **Повезивање са услугом Common Data Service** и изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="15b5b-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="15b5b-113">Унесите **Назив** извора података и изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="15b5b-113">Enter a **Name** for the data source and select **Next**.</span></span>

5. <span data-ttu-id="15b5b-114">Наведите **Адресу сервера** за вашу Common Data Service организацију и изаберите **Пријавите се**.</span><span class="sxs-lookup"><span data-stu-id="15b5b-114">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="15b5b-115">![Дијалог за унос Common Data Service адресе сервера](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="15b5b-115">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="15b5b-116">Изаберите ентитете које желите да унесете са доступне листе.</span><span class="sxs-lookup"><span data-stu-id="15b5b-116">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="15b5b-117">Ако су неки ентитети већ изабрани, могу их користити друге Dynamics 365 апликације (као што су Dynamics 365 Sales Insights или Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="15b5b-117">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="15b5b-118">Не можете променити избор.</span><span class="sxs-lookup"><span data-stu-id="15b5b-118">You can't change the selection.</span></span> <span data-ttu-id="15b5b-119">Ови ентитети ће бити доступни након креирања извора података.</span><span class="sxs-lookup"><span data-stu-id="15b5b-119">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="15b5b-120">![Дијалог који приказује листу ентитета у Common Data Service организацији](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="15b5b-120">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="15b5b-121">Сачувајте свој избор да бисте започели синхронизацију изабраних ентитета са Common Data Service управљаним језером.</span><span class="sxs-lookup"><span data-stu-id="15b5b-121">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="15b5b-122">Новододату везу ћете пронаћи на страници **Извори података**.</span><span class="sxs-lookup"><span data-stu-id="15b5b-122">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="15b5b-123">Биће постављена у ред за освежавање и приказаће бројеве ентитета као 0 док се сви ентитети не синхронизују.</span><span class="sxs-lookup"><span data-stu-id="15b5b-123">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="15b5b-124">Само један извор података окружења може истовремено да користи исто Common Data Service надгледано језеро.</span><span class="sxs-lookup"><span data-stu-id="15b5b-124">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="15b5b-125">Уредите извор података за Common Data Service управљано језеро</span><span class="sxs-lookup"><span data-stu-id="15b5b-125">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="15b5b-126">Избор ентитета уређујете тек након што креирате извор података.</span><span class="sxs-lookup"><span data-stu-id="15b5b-126">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="15b5b-127">На пример, ако су додати додатни ентитети у услугу Common Data Service, а желите и да их увозите.</span><span class="sxs-lookup"><span data-stu-id="15b5b-127">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="15b5b-128">Да бисте се повезали са другом услугом Common Data Service, [креирајте нови извор података](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="15b5b-128">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="15b5b-129">У увидима о корисницима идите на **Подаци** > **Извори података**.</span><span class="sxs-lookup"><span data-stu-id="15b5b-129">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="15b5b-130">Поред извора података који желите да ажурирате, изаберите три тачке.</span><span class="sxs-lookup"><span data-stu-id="15b5b-130">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="15b5b-131">Изаберите опцију **Уреди** са листе.</span><span class="sxs-lookup"><span data-stu-id="15b5b-131">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="15b5b-132">Изаберите додатне ентитете с доступне листе ентитета и изаберите **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="15b5b-132">Select additional entities from the available list of entities and select **Save**.</span></span>
