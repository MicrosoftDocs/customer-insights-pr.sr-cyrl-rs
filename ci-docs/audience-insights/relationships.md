---
title: Односи између ентитета и путања ентитета
description: Правите и управљајте односима између ентитета из више извора података.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 295c372bb452e7c40aa950506dc494d4a2de1108
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406879"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="7652d-103">Релације између ентитета</span><span class="sxs-lookup"><span data-stu-id="7652d-103">Relationships between entities</span></span>

<span data-ttu-id="7652d-104">Релације вам помажу да повежете ентитете и генеришете графикон ваших података када ентитети деле заједнички идентификатор (страни кључ) који се може референцирати из једног ентитета у други.</span><span class="sxs-lookup"><span data-stu-id="7652d-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="7652d-105">Повезани ентитети вам омогућавају да дефинишете сегменте и мере на основу више извора података.</span><span class="sxs-lookup"><span data-stu-id="7652d-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="7652d-106">Постоје два типа релација.</span><span class="sxs-lookup"><span data-stu-id="7652d-106">There are two types of relationships.</span></span> <span data-ttu-id="7652d-107">Системске релације које се не могу уређивати, које се креирају аутоматски, и прилагођене релације, које креирају и конфигуришу корисници.</span><span class="sxs-lookup"><span data-stu-id="7652d-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="7652d-108">Током процеса подударања и спајања, системске релације се креирају се иза сцене на основу интелигентног подударања.</span><span class="sxs-lookup"><span data-stu-id="7652d-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="7652d-109">Ове релације помажу да се повежу евиденције профила клијената са подацима других ентитета.</span><span class="sxs-lookup"><span data-stu-id="7652d-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="7652d-110">Следећи дијаграм илуструје креирање три системске релације када се ентитет клијента подудари са додатним ентитетима како би се произвео коначни ентитет Профил клијента.</span><span class="sxs-lookup"><span data-stu-id="7652d-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7652d-111">![Креирање релације](media/relationships-entities-merge.png "Креирање релације")</span><span class="sxs-lookup"><span data-stu-id="7652d-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="7652d-112">**Релација *CustomerToContact*** је креирана између ентитета Клијент и контактног ентитета.</span><span class="sxs-lookup"><span data-stu-id="7652d-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="7652d-113">Ентитет Клијент добија кључно поље **Contact_contactId** да ступи у релацију са пољем кључа ентитета Контакт **contactId**.</span><span class="sxs-lookup"><span data-stu-id="7652d-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="7652d-114">**Релација _CustomerToContact_** је креирана између ентитета Клијент и ентитета Пословни контакт.</span><span class="sxs-lookup"><span data-stu-id="7652d-114">**_CustomerToAccount_ relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="7652d-115">Ентитет Клијент добија поље кључа **Account_accountId** да ступи у релацију са пољем кључа ентитета Пословни контакт **accountId**.</span><span class="sxs-lookup"><span data-stu-id="7652d-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="7652d-116">**Релација _CustomerToWebAccount_** је креирана између ентитета Клијент и ентитета WebAccount.</span><span class="sxs-lookup"><span data-stu-id="7652d-116">**_CustomerToWebAccount_ relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="7652d-117">Ентитет Клијент добија поље кључа **WebAccount_webaccountId** да ступи у релацију са пољем кључа ентитета WebAccount **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="7652d-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="7652d-118">Креирање односа</span><span class="sxs-lookup"><span data-stu-id="7652d-118">Create a relationship</span></span>

<span data-ttu-id="7652d-119">Дефинишите прилагођене релације на страници **Релације**.</span><span class="sxs-lookup"><span data-stu-id="7652d-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="7652d-120">Свака релација се састоји од изворног ентитета (ентитета који држи страни кључ) и циљног ентитета (ентитета на који указује на страни кључ изворног ентитета).</span><span class="sxs-lookup"><span data-stu-id="7652d-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="7652d-121">У увидима о корисницима идите на **Подаци** > **Односи**.</span><span class="sxs-lookup"><span data-stu-id="7652d-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="7652d-122">Изаберите **Нова релација**.</span><span class="sxs-lookup"><span data-stu-id="7652d-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="7652d-123">У окну **Нова релација**, наведите следеће информације:</span><span class="sxs-lookup"><span data-stu-id="7652d-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7652d-124">![Унесите детаље релације](media/relationships-add.png "Унесите детаље релације")</span><span class="sxs-lookup"><span data-stu-id="7652d-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="7652d-125">**Назив релације**: Име које одражава сврху релације (на пример, **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="7652d-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="7652d-126">**Опис**: Опис релације.</span><span class="sxs-lookup"><span data-stu-id="7652d-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="7652d-127">**Изворни ентитет**: Изаберите ентитет који се користи као извор у релацији (на пример, WebLog).</span><span class="sxs-lookup"><span data-stu-id="7652d-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="7652d-128">**Кардиналност**: Изаберите кардиналност изворних записа ентитета.</span><span class="sxs-lookup"><span data-stu-id="7652d-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="7652d-129">На пример, „много“ значи да је више Weblog записа у релацији са једним ентитетом WebAccount.</span><span class="sxs-lookup"><span data-stu-id="7652d-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="7652d-130">**Изворно поље кључа**: Ово представља поље страног кључа у изворном ентитету.</span><span class="sxs-lookup"><span data-stu-id="7652d-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="7652d-131">На пример, WebLog има поље страног кључа **accountId**.</span><span class="sxs-lookup"><span data-stu-id="7652d-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="7652d-132">**Циљни ентитет**: Изаберите ентитет који се користи као циљ у релацији (на пример, WebAccount).</span><span class="sxs-lookup"><span data-stu-id="7652d-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="7652d-133">**Циљна кардиналност**: Изаберите кардиналност циљних записа ентитета.</span><span class="sxs-lookup"><span data-stu-id="7652d-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="7652d-134">На пример, „један“ значи да је више Weblog записа у релацији са једним ентитетом WebAccount.</span><span class="sxs-lookup"><span data-stu-id="7652d-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="7652d-135">**Циљно поље кључа**: Ово поље представља поље кључа циљног ентитета.</span><span class="sxs-lookup"><span data-stu-id="7652d-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="7652d-136">На пример, WebAccount има поље кључа **accountId**.</span><span class="sxs-lookup"><span data-stu-id="7652d-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="7652d-137">Подржани су само релације више-према-један и један-према-један.</span><span class="sxs-lookup"><span data-stu-id="7652d-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="7652d-138">Релације више-према-више могу да се креирају помоћу две релације више-према-један и једног ентитета везе (ентитета који се користи за повезивање изворног ентитета и циљног ентитета).</span><span class="sxs-lookup"><span data-stu-id="7652d-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="7652d-139">Брисање релације</span><span class="sxs-lookup"><span data-stu-id="7652d-139">Delete a relationship</span></span>

1. <span data-ttu-id="7652d-140">У увидима о корисницима идите на **Подаци** > **Односи**.</span><span class="sxs-lookup"><span data-stu-id="7652d-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="7652d-141">Изаберите поља за потврду за релације које желите да избришете.</span><span class="sxs-lookup"><span data-stu-id="7652d-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="7652d-142">Изаберите **Избриши** на врху табеле **Релације**.</span><span class="sxs-lookup"><span data-stu-id="7652d-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="7652d-143">Потврдите брисање.</span><span class="sxs-lookup"><span data-stu-id="7652d-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="7652d-144">Следећи корак</span><span class="sxs-lookup"><span data-stu-id="7652d-144">Next step</span></span>

<span data-ttu-id="7652d-145">Системске и прилагођене релације се користе за креирање сегмената на основу више извора података који се више не бирају.</span><span class="sxs-lookup"><span data-stu-id="7652d-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="7652d-146">За више информација, погледајте чланак [Сегменти](segments.md).</span><span class="sxs-lookup"><span data-stu-id="7652d-146">For more information, see [Segments](segments.md).</span></span>
