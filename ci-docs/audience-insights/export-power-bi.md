---
title: Power BI конектор
description: Сазнајте како да користите Dynamics 365 Customer Insights конектор у услузи Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0607a4644ac7d7beb19e4faecf012efcd197d48c
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477106"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="4bd70-103">Конектор за Power BI (преглед)</span><span class="sxs-lookup"><span data-stu-id="4bd70-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="4bd70-104">Направите визуелизације за своје податке помоћу услуге Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="4bd70-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="4bd70-105">Генеришите додатне увиде и правите извештаје помоћу обједињених података о клијентима.</span><span class="sxs-lookup"><span data-stu-id="4bd70-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4bd70-106">Предуслови</span><span class="sxs-lookup"><span data-stu-id="4bd70-106">Prerequisites</span></span>

- <span data-ttu-id="4bd70-107">Имате обједињене профиле клијената.</span><span class="sxs-lookup"><span data-stu-id="4bd70-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="4bd70-108">Најновија верзија услуге [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) је инсталирана на вашем рачунару.</span><span class="sxs-lookup"><span data-stu-id="4bd70-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="4bd70-109">[Сазнајте више о Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="4bd70-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="4bd70-110">Конфигуришите конектор за Power BI</span><span class="sxs-lookup"><span data-stu-id="4bd70-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="4bd70-111">У програму Power BI Desktop, изаберите **Датотека** > **Преузми податке**.</span><span class="sxs-lookup"><span data-stu-id="4bd70-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="4bd70-112">Изаберите **Прикажи још** и потражите **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="4bd70-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="4bd70-113">Изаберите **Повежи се**.</span><span class="sxs-lookup"><span data-stu-id="4bd70-113">Select **Connect**.</span></span>

1. <span data-ttu-id="4bd70-114">**Пријавите се** са истим организационим налогом који користите за Customer Insights и изаберите **Повежи се**.</span><span class="sxs-lookup"><span data-stu-id="4bd70-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="4bd70-115">Пословни контакт који наведете у овом кораку користи се за преузимање података из услуге Customer Insights и не мора бити исти са којим сте пријављени на Power BI.</span><span class="sxs-lookup"><span data-stu-id="4bd70-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="4bd70-116">Да бисте ресетовали налог који се користи за преузимање података, отворите Power BI и идите на **Датотека** > **Опције** > **Подешавања** > **Подешавања извора података**.</span><span class="sxs-lookup"><span data-stu-id="4bd70-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="4bd70-117">На листи извора података изаберите **Пријава на Dynamics 365 Customer Insights** и изаберите **Обриши дозволе**.</span><span class="sxs-lookup"><span data-stu-id="4bd70-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="4bd70-118">У дијалогу **Навигатор**.</span><span class="sxs-lookup"><span data-stu-id="4bd70-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="4bd70-119">видите листу свих окружења којима имате приступ.</span><span class="sxs-lookup"><span data-stu-id="4bd70-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="4bd70-120">Проширите окружење и отворите било коју фасциклу (ентитети, мере, сегменти, обогаћивања).</span><span class="sxs-lookup"><span data-stu-id="4bd70-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="4bd70-121">На пример, отворите фасциклу **Ентитети** да видите све ентитете које можете да увезете.</span><span class="sxs-lookup"><span data-stu-id="4bd70-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="4bd70-122">![Навигатор Power BI конектора](media/power-bi-navigator.png "Навигатор Power BI конектора")</span><span class="sxs-lookup"><span data-stu-id="4bd70-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="4bd70-123">Означите поља за потврду поред ентитета које треба да укључите и **Учитај**.</span><span class="sxs-lookup"><span data-stu-id="4bd70-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="4bd70-124">Можете да изаберете више ентитета, чак и из више окружења.</span><span class="sxs-lookup"><span data-stu-id="4bd70-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="4bd70-125">Видећете дијалог за учитавање док се ентитети учитавају.</span><span class="sxs-lookup"><span data-stu-id="4bd70-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="4bd70-126">Након што се учитају сви изабрани ентитети, можете да користите могућности услуге Power BI за визуализацију података.</span><span class="sxs-lookup"><span data-stu-id="4bd70-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="4bd70-127">Велики скупови података</span><span class="sxs-lookup"><span data-stu-id="4bd70-127">Large data sets</span></span>

<span data-ttu-id="4bd70-128">Customer Insights конектор за Power BI је дизајниран да ради за скупове података који садрже до 1 милион корисничких профила.</span><span class="sxs-lookup"><span data-stu-id="4bd70-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="4bd70-129">Увоз већих скупова података може да функционише, али то траје дуго.</span><span class="sxs-lookup"><span data-stu-id="4bd70-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="4bd70-130">Поред тога, процес би могао наићи на временско ограничење због Power BI ограничења.</span><span class="sxs-lookup"><span data-stu-id="4bd70-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="4bd70-131">За више информација, погледајте [Power BI: Препоруке за велике скупове података](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="4bd70-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="4bd70-132">Рад са подскупом података</span><span class="sxs-lookup"><span data-stu-id="4bd70-132">Work with a subset of data</span></span>

<span data-ttu-id="4bd70-133">Размислите о раду са подскупом података.</span><span class="sxs-lookup"><span data-stu-id="4bd70-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="4bd70-134">На пример, можете да креирате[ сегменте](segments.md) уместо да извезе све евиденције клијената у Power BI.</span><span class="sxs-lookup"><span data-stu-id="4bd70-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="4bd70-135">Решавање проблема</span><span class="sxs-lookup"><span data-stu-id="4bd70-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="4bd70-136">Customer Insights окружење се не приказује у услузи Power BI</span><span class="sxs-lookup"><span data-stu-id="4bd70-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="4bd70-137">Окружења која имају више од једне [релације](relationships.md) дефинисане између два идентична ентитета у увидима о корисницима неће бити доступна у Power BI конектору.</span><span class="sxs-lookup"><span data-stu-id="4bd70-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="4bd70-138">Можете идентификовати и уклонити дупликате релација.</span><span class="sxs-lookup"><span data-stu-id="4bd70-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="4bd70-139">У увидима о корисницима, идите на **Подаци** > **Релације** на окружење које вам недостаје у услузи Power BI.</span><span class="sxs-lookup"><span data-stu-id="4bd70-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="4bd70-140">Идентификујте дупликате релација:</span><span class="sxs-lookup"><span data-stu-id="4bd70-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="4bd70-141">Проверите да ли постоји више релација дефинисаних између иста два ентитета.</span><span class="sxs-lookup"><span data-stu-id="4bd70-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="4bd70-142">Проверите да ли постоји релација креирана између два ентитета која су оба укључена у процес обједињавања.</span><span class="sxs-lookup"><span data-stu-id="4bd70-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="4bd70-143">Дефинисана је имплицитна релација између свих ентитета укључених у процес уједињења.</span><span class="sxs-lookup"><span data-stu-id="4bd70-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="4bd70-144">Уклоните све препознате дупликате релација.</span><span class="sxs-lookup"><span data-stu-id="4bd70-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="4bd70-145">Када уклоните дупликате релација, покушајте да поново конфигуришете Power BI конектор.</span><span class="sxs-lookup"><span data-stu-id="4bd70-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="4bd70-146">Окружење би требало да буде доступно већ сада.</span><span class="sxs-lookup"><span data-stu-id="4bd70-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

