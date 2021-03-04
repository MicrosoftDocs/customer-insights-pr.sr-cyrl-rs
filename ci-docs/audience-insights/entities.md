---
title: Ентитети и скупови података
description: Погледајте податке на страници Ентитети.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e71c69a6207147d8cd65363d51a5fa6bbf896151
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269394"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="f69bc-103">Ентитети у увидима о корисницима</span><span class="sxs-lookup"><span data-stu-id="f69bc-103">Entities in audience insights</span></span>

<span data-ttu-id="f69bc-104">Када [конфигуришете изворе података](data-sources.md), идите на страницу **Ентитети** да процените квалитет унетих података.</span><span class="sxs-lookup"><span data-stu-id="f69bc-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="f69bc-105">Ентитети се сматрају скуповима података.</span><span class="sxs-lookup"><span data-stu-id="f69bc-105">Entities are considered datasets.</span></span> <span data-ttu-id="f69bc-106">Више могућности услуге Dynamics 365 Customer Insights направљено је на основу ових ентитета.</span><span class="sxs-lookup"><span data-stu-id="f69bc-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="f69bc-107">Њихов пажљив преглед може вам помоћи да потврдите ваљаност исхода тих могућности.</span><span class="sxs-lookup"><span data-stu-id="f69bc-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="f69bc-108">Страница **Ентитети** наводи ентитете и садржи неколико колона:</span><span class="sxs-lookup"><span data-stu-id="f69bc-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="f69bc-109">**Назив**: Назив вашег ентитета података.</span><span class="sxs-lookup"><span data-stu-id="f69bc-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="f69bc-110">Ако видите симбол упозорења поред назива ентитета, то значи да се подаци за тај ентитет нису успешно учитали.</span><span class="sxs-lookup"><span data-stu-id="f69bc-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="f69bc-111">**Извор**: Врста извора података који су унети у ентитет</span><span class="sxs-lookup"><span data-stu-id="f69bc-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="f69bc-112">**Аутор**: Име особе која је креирала ентитет</span><span class="sxs-lookup"><span data-stu-id="f69bc-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="f69bc-113">**Креирано**: Датум и време стварања ентитета</span><span class="sxs-lookup"><span data-stu-id="f69bc-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="f69bc-114">**Аутор измене**: Име особе која је ажурирала ентитет</span><span class="sxs-lookup"><span data-stu-id="f69bc-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="f69bc-115">**Време последње измене**: Датум и време последњег ажурирања ентитета</span><span class="sxs-lookup"><span data-stu-id="f69bc-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="f69bc-116">**Последње освежавање**: Датум и време последњег освежавања података</span><span class="sxs-lookup"><span data-stu-id="f69bc-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="f69bc-117">Истраживање података одређеног ентитета</span><span class="sxs-lookup"><span data-stu-id="f69bc-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="f69bc-118">Изаберите ентитет да бисте истражили различита поља и записе који су укључени у тај ентитет.</span><span class="sxs-lookup"><span data-stu-id="f69bc-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f69bc-119">![Изаберите ентитет](media/data-manager-entities-data.png "Изаберите ентитет")</span><span class="sxs-lookup"><span data-stu-id="f69bc-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="f69bc-120">Картица **Подаци** је подразумевано изабрана и приказује табелу у којој су наведени детаљи о појединачним записима ентитета.</span><span class="sxs-lookup"><span data-stu-id="f69bc-120">The **Data** tab is selected by default and shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f69bc-121">![Табела поља](media/data-manager-entities-fields.PNG "Табела поља")</span><span class="sxs-lookup"><span data-stu-id="f69bc-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="f69bc-122">Картица **Поља** приказује табелу за преглед детаља за одабрани ентитет, као што су имена поља, типови података и типови.</span><span class="sxs-lookup"><span data-stu-id="f69bc-122">The **Fields** tab shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="f69bc-123">Колона **Тип** приказује типове повезане са Common Data Model, које систем аутоматски препознаје или их корисници [ручно мапирају](map-entities.md).</span><span class="sxs-lookup"><span data-stu-id="f69bc-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="f69bc-124">Ово су семантички типови који се могу разликовати од типова података атрибута – на пример, поље *Е-пошта* у наставку је типа података *Текст*, али његов (семантички) Common Data Model тип може бити *Е-пошта* или *Адреса е-поште*.</span><span class="sxs-lookup"><span data-stu-id="f69bc-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="f69bc-125">Обе табеле приказују само узорак података вашег ентитета.</span><span class="sxs-lookup"><span data-stu-id="f69bc-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="f69bc-126">Да бисте видели цео скуп података, идите на страницу **Извори података**, изаберите ентитет, изаберите **Уреди**, а затим прегледајте податке овог ентитета помоћу Power Query уређивача, као што је објашњено у чланку [Извори података](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="f69bc-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="f69bc-127">Да бисте сазнали више о подацима који се уносе у ентитет, колона **Резиме** вам пружа неке важне карактеристике података, као што су поља без вредности, недостајуће вредности, јединствене вредности, бројеви и дистрибуције, како је већ примењиво на податке.</span><span class="sxs-lookup"><span data-stu-id="f69bc-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="f69bc-128">Изаберите икону графикона да бисте видели резиме података.</span><span class="sxs-lookup"><span data-stu-id="f69bc-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f69bc-129">![Симбол резимеа](media/data-manager-entities-summary.png "Табела са резимеом података")</span><span class="sxs-lookup"><span data-stu-id="f69bc-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="f69bc-130">Следећи корак</span><span class="sxs-lookup"><span data-stu-id="f69bc-130">Next step</span></span>

<span data-ttu-id="f69bc-131">Погледајте тему [Уједначавање](data-unification.md) да бисте сазнали како да *мапирате*, *подударате* и *спајате* унете податке.</span><span class="sxs-lookup"><span data-stu-id="f69bc-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]