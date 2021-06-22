---
title: Односи између ентитета и путања ентитета
description: Правите и управљајте односима између ентитета из више извора података.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171182"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="f10a5-103">Релације између ентитета</span><span class="sxs-lookup"><span data-stu-id="f10a5-103">Relationships between entities</span></span>

<span data-ttu-id="f10a5-104">Релације повезују ентитете и дефинишу графикон ваших података када ентитети деле заједнички идентификатор, страни кључ.</span><span class="sxs-lookup"><span data-stu-id="f10a5-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="f10a5-105">Овај страни кључ може се референцирати из једног ентитета на други.</span><span class="sxs-lookup"><span data-stu-id="f10a5-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="f10a5-106">Повезани ентитети омогућавају дефиницију сегмената и мере на основу више извора података.</span><span class="sxs-lookup"><span data-stu-id="f10a5-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="f10a5-107">Постоје три врсте релација:</span><span class="sxs-lookup"><span data-stu-id="f10a5-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="f10a5-108">Системске релације које не могу да се уређују, креира их систем као део процеса уједначавања података</span><span class="sxs-lookup"><span data-stu-id="f10a5-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="f10a5-109">Наслеђене релације без могућности уређивања, које се аутоматски креирају из уноса извора података</span><span class="sxs-lookup"><span data-stu-id="f10a5-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="f10a5-110">Прилагођене релације са могућношћу уређивања, које креирају и конфигуришу корисници</span><span class="sxs-lookup"><span data-stu-id="f10a5-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="f10a5-111">Системске релације које не могу да се уређују</span><span class="sxs-lookup"><span data-stu-id="f10a5-111">Non-editable system relationships</span></span>

<span data-ttu-id="f10a5-112">Током уједначавања података, системске релације се аутоматски креирају на основу интелигентног подударања.</span><span class="sxs-lookup"><span data-stu-id="f10a5-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="f10a5-113">Ове релације помажу да се повежу записи профила клијената са одговарајућим записима.</span><span class="sxs-lookup"><span data-stu-id="f10a5-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="f10a5-114">Следећи дијаграм илуструје креирање три системске релације.</span><span class="sxs-lookup"><span data-stu-id="f10a5-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="f10a5-115">Ентитет клијента се подудара са другим ентитетима како би се направио обједињени ентитет *Клијент*.</span><span class="sxs-lookup"><span data-stu-id="f10a5-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Дијаграм са путањама релација за ентитет клијента са три релације „1-n“.":::

- <span data-ttu-id="f10a5-117">**Релација *CustomerToContact*** је креирана између ентитета *Клијент* и ентитета *Контакт*.</span><span class="sxs-lookup"><span data-stu-id="f10a5-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="f10a5-118">Ентитет *Клијент* добија кључно поље **Contact_contactID** да ступи у релацију са пољем **contactId** кључа ентитета *Контакт*.</span><span class="sxs-lookup"><span data-stu-id="f10a5-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="f10a5-119">**Релација *CustomerToAccount*** је креирана између ентитета *Клијент* и ентитета *Пословни контакт*.</span><span class="sxs-lookup"><span data-stu-id="f10a5-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="f10a5-120">Ентитет *Клијент* добија поље кључа **Account_accountID** да ступи у релацију са пољем **accountID** кључа ентитета *Пословни контакт*.</span><span class="sxs-lookup"><span data-stu-id="f10a5-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="f10a5-121">**Релација *CustomerToWebAccount*** је креирана између ентитета *Клијент* и ентитета *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="f10a5-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="f10a5-122">Ентитет *Клијент* добија поље кључа **WebAccount_webaccountID** да ступи у релацију са пољем **webaccountID** кључа ентитета *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="f10a5-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="f10a5-123">Наслеђене релације које не могу да се уређују</span><span class="sxs-lookup"><span data-stu-id="f10a5-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="f10a5-124">Током процеса уноса података, систем проверава постоје ли релације у изворима података.</span><span class="sxs-lookup"><span data-stu-id="f10a5-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="f10a5-125">Ако не постоје релације, систем их аутоматски креира.</span><span class="sxs-lookup"><span data-stu-id="f10a5-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="f10a5-126">Те релације се такође користе у последичним процесима.</span><span class="sxs-lookup"><span data-stu-id="f10a5-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="f10a5-127">Креирање прилагођене релације</span><span class="sxs-lookup"><span data-stu-id="f10a5-127">Create a custom relationship</span></span>

<span data-ttu-id="f10a5-128">Релација се састоји од *изворног ентитета* који садржи страни кључ и *циљни ентитет* на који указује страни кључ изворног ентитета.</span><span class="sxs-lookup"><span data-stu-id="f10a5-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="f10a5-129">У увидима о корисницима идите на **Подаци** > **Односи**.</span><span class="sxs-lookup"><span data-stu-id="f10a5-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="f10a5-130">Изаберите **Нова релација**.</span><span class="sxs-lookup"><span data-stu-id="f10a5-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="f10a5-131">У окну **Нова релација**, наведите следеће информације:</span><span class="sxs-lookup"><span data-stu-id="f10a5-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Ново бочно окно релације са празним пољима за унос.":::

   - <span data-ttu-id="f10a5-133">**Назив релације**: Назив који одражава сврху везе.</span><span class="sxs-lookup"><span data-stu-id="f10a5-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="f10a5-134">Пример: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="f10a5-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="f10a5-135">**Опис**: Опис релације.</span><span class="sxs-lookup"><span data-stu-id="f10a5-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="f10a5-136">**Изворни ентитет**: Ентитет који се користи као извор у релацији.</span><span class="sxs-lookup"><span data-stu-id="f10a5-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="f10a5-137">Пример: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="f10a5-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="f10a5-138">**Циљни ентитет**: Ентитет који се користи као циљ у релацији.</span><span class="sxs-lookup"><span data-stu-id="f10a5-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="f10a5-139">Пример: Клијент.</span><span class="sxs-lookup"><span data-stu-id="f10a5-139">Example: Customer.</span></span>
   - <span data-ttu-id="f10a5-140">**Изворна кардиналност**: Наведите кардиналност изворног ентитета.</span><span class="sxs-lookup"><span data-stu-id="f10a5-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="f10a5-141">Кардиналност описује број могућих елемената у скупу.</span><span class="sxs-lookup"><span data-stu-id="f10a5-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="f10a5-142">Увек се односи на циљну кардиналност.</span><span class="sxs-lookup"><span data-stu-id="f10a5-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="f10a5-143">Можете бирати између **Један** и **Више**.</span><span class="sxs-lookup"><span data-stu-id="f10a5-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="f10a5-144">Подржани су само релације више-према-један и један-према-један.</span><span class="sxs-lookup"><span data-stu-id="f10a5-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="f10a5-145">Више према један: Више изворних записа може се односити на један циљни запис.</span><span class="sxs-lookup"><span data-stu-id="f10a5-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="f10a5-146">Пример: Више случајева подршке од једног клијента.</span><span class="sxs-lookup"><span data-stu-id="f10a5-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="f10a5-147">Један према један: Један изворни запис односи се на један циљни запис.</span><span class="sxs-lookup"><span data-stu-id="f10a5-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="f10a5-148">Пример: Један ID лојалности за једног клијента.</span><span class="sxs-lookup"><span data-stu-id="f10a5-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="f10a5-149">Релације „Више према више“ могу се креирати помоћу две релације „више према један“ и повезујућег ентитета, који повезује изворни ентитет и циљни ентитет.</span><span class="sxs-lookup"><span data-stu-id="f10a5-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="f10a5-150">**Циљна кардиналност**: Изаберите кардиналност циљних записа ентитета.</span><span class="sxs-lookup"><span data-stu-id="f10a5-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="f10a5-151">**Поље изворног кључа**: Поље страног кључа у изворном ентитету.</span><span class="sxs-lookup"><span data-stu-id="f10a5-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="f10a5-152">Пример: SupportCase може користити CaseID као поље страног кључа.</span><span class="sxs-lookup"><span data-stu-id="f10a5-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="f10a5-153">**Поље циљног кључа**: Поље кључа циљног ентитета.</span><span class="sxs-lookup"><span data-stu-id="f10a5-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="f10a5-154">Пример „Клијент“ би могао да користи поље кључа **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="f10a5-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="f10a5-155">Изаберите **Сачувај** да бисте креирали прилагођену релацију.</span><span class="sxs-lookup"><span data-stu-id="f10a5-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="f10a5-156">Приказ релација</span><span class="sxs-lookup"><span data-stu-id="f10a5-156">View relationships</span></span>

<span data-ttu-id="f10a5-157">На страници Релације наведене су све релације које су креиране.</span><span class="sxs-lookup"><span data-stu-id="f10a5-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="f10a5-158">Сваки ред представља релацију, што такође укључује детаље о изворном ентитету, циљном ентитету и кардиналности.</span><span class="sxs-lookup"><span data-stu-id="f10a5-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Листа релација и опција на траци са радњама на страници Релације.":::

<span data-ttu-id="f10a5-160">Ова страница нуди скуп опција за постојеће и нове релације:</span><span class="sxs-lookup"><span data-stu-id="f10a5-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="f10a5-161">**Нова релација**: [Креирање нове релације](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="f10a5-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="f10a5-162">**Визуелизатор**: [Истражите визуелизатор односа](#explore-the-relationship-visualizer) да бисте видели мрежни дијаграм постојећих релација и њихову кардиналност.</span><span class="sxs-lookup"><span data-stu-id="f10a5-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="f10a5-163">**Филтрирај према**: Изаберите тип релација који ће се приказивати на листи.</span><span class="sxs-lookup"><span data-stu-id="f10a5-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="f10a5-164">**Претрага релација**: Користите текстуалну претрагу својстава релација.</span><span class="sxs-lookup"><span data-stu-id="f10a5-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="f10a5-165">Истражите визуелизатор релација</span><span class="sxs-lookup"><span data-stu-id="f10a5-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="f10a5-166">Визуелизатор релација приказује мрежни дијаграм постојећих релација између повезаних ентитета и њихову кардиналност.</span><span class="sxs-lookup"><span data-stu-id="f10a5-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="f10a5-167">Да бисте прилагодили приказ, можете да промените положај оквира тако што ћете их превући на подлогу.</span><span class="sxs-lookup"><span data-stu-id="f10a5-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Снимак екрана мрежног дијаграма визуелизатора релација са везама између повезаних ентитета.":::

<span data-ttu-id="f10a5-169">Доступне опције:</span><span class="sxs-lookup"><span data-stu-id="f10a5-169">Available options:</span></span> 
- <span data-ttu-id="f10a5-170">**Извези као слику**: Снимите тренутни приказ као датотеку слике.</span><span class="sxs-lookup"><span data-stu-id="f10a5-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="f10a5-171">**Промена на хоризонтални/вертикални распоред**: Промените поравнање ентитета и релација.</span><span class="sxs-lookup"><span data-stu-id="f10a5-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="f10a5-172">**Уреди**: Ажурирајте својства прилагођених релација у окну за уређивање и сачувајте промене.</span><span class="sxs-lookup"><span data-stu-id="f10a5-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="f10a5-173">Управљање постојећим релацијама</span><span class="sxs-lookup"><span data-stu-id="f10a5-173">Manage existing relationships</span></span> 

<span data-ttu-id="f10a5-174">На страници Релације, свака релација је представљена једним редом.</span><span class="sxs-lookup"><span data-stu-id="f10a5-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="f10a5-175">Изаберите релацију и одаберите једну од следећих опција:</span><span class="sxs-lookup"><span data-stu-id="f10a5-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="f10a5-176">**Уреди**: Ажурирајте својства прилагођених релација у окну за уређивање и сачувајте промене.</span><span class="sxs-lookup"><span data-stu-id="f10a5-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="f10a5-177">**Избриши**: Избришите прилагођене релације.</span><span class="sxs-lookup"><span data-stu-id="f10a5-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="f10a5-178">**Приказ**: Прикажите системски креиране и наслеђене релације.</span><span class="sxs-lookup"><span data-stu-id="f10a5-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="f10a5-179">Следећи корак</span><span class="sxs-lookup"><span data-stu-id="f10a5-179">Next step</span></span>

<span data-ttu-id="f10a5-180">Системске и прилагођене релације се користе за [креирање сегмената](segments.md) на основу више извора података који више нису у силосу.</span><span class="sxs-lookup"><span data-stu-id="f10a5-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
