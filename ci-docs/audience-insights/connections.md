---
title: Везе са осталим услугама из услуге Customer Insights.
description: Поделите податке са другим услугама.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 106dbc26f95b309821d738e1484b1eaa79dd225b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896115"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="db870-103">Преглед веза (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="db870-103">Connections (preview) overview</span></span>

<span data-ttu-id="db870-104">Везе су кључ за омогућавање дељења података у услугу Customer Insights и из ње.</span><span class="sxs-lookup"><span data-stu-id="db870-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="db870-105">Свака веза успоставља дељење података са одређеном услугом.</span><span class="sxs-lookup"><span data-stu-id="db870-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="db870-106">Везе су темељ да [конфигуришете обогаћивања трећих страна](enrichment-hub.md) и [конфигурисање извоза](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="db870-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="db870-107">Иста веза се може користити више пута.</span><span class="sxs-lookup"><span data-stu-id="db870-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="db870-108">На пример, једна веза са услугом Dynamics 365 Marketing функционише за више извоза, а једна Leadspace веза може се користити за неколико обогаћивања.</span><span class="sxs-lookup"><span data-stu-id="db870-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="db870-109">Идите на **Администратор** > **Везе** да бисте креирали и приказали везе.</span><span class="sxs-lookup"><span data-stu-id="db870-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="db870-110">На картици **Везе** приказују се све активне везе.</span><span class="sxs-lookup"><span data-stu-id="db870-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="db870-111">Листа приказује ред за сваку везу.</span><span class="sxs-lookup"><span data-stu-id="db870-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="db870-112">Преузмите брзи преглед, опис и сазнајте шта можете учинити са сваком опцијом проширивости на картици **Откривање**.</span><span class="sxs-lookup"><span data-stu-id="db870-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="db870-113">Извоз</span><span class="sxs-lookup"><span data-stu-id="db870-113">Exports</span></span>

<span data-ttu-id="db870-114">Само администратори могу да конфигуришу нове везе, али могу да дају приступ сарадницима да користе постојеће везе.</span><span class="sxs-lookup"><span data-stu-id="db870-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="db870-115">Администратори контролишу куда подаци могу да иду, сарадници дефинишу корисне податке и учесталост у складу са својим потребама.</span><span class="sxs-lookup"><span data-stu-id="db870-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="db870-116">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="db870-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="db870-117">Обогаћивања</span><span class="sxs-lookup"><span data-stu-id="db870-117">Enrichments</span></span>

<span data-ttu-id="db870-118">Само администратори могу да конфигуришу нове везе, али креиране везе су увек доступне и администраторима и сарадницима.</span><span class="sxs-lookup"><span data-stu-id="db870-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="db870-119">Администратори управљају акредитивима и дају сагласност за пренос података.</span><span class="sxs-lookup"><span data-stu-id="db870-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="db870-120">Везе тада могу да користе администратори и сарадници за обогаћивања.</span><span class="sxs-lookup"><span data-stu-id="db870-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="db870-121">Додавање нове везе</span><span class="sxs-lookup"><span data-stu-id="db870-121">Add a new connection</span></span>

<span data-ttu-id="db870-122">Да бисте додали везе, морате да имате [администраторске дозволе](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="db870-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="db870-123">Ако се повежете са другим Microsoft услугама, претпостављамо да су обе услуге у истој организацији.</span><span class="sxs-lookup"><span data-stu-id="db870-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="db870-124">Идите на **Администратор** > **Везе (преглед)**.</span><span class="sxs-lookup"><span data-stu-id="db870-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="db870-125">Идите на картицу **Везе**.</span><span class="sxs-lookup"><span data-stu-id="db870-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="db870-126">Изаберите **Додај везу** да бисте креирали нову везу.</span><span class="sxs-lookup"><span data-stu-id="db870-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="db870-127">Одаберите из падајућег менија коју врсту везе желите да креирате.</span><span class="sxs-lookup"><span data-stu-id="db870-127">Choose from the drop-down menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="db870-128">У окну **Подешавање везе**, наведите потребне детаље.</span><span class="sxs-lookup"><span data-stu-id="db870-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="db870-129">**Име за приказ** и врста везе описују везу.</span><span class="sxs-lookup"><span data-stu-id="db870-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="db870-130">Препоручујемо да одаберете назив који објашњава сврху и циљ ове везе.</span><span class="sxs-lookup"><span data-stu-id="db870-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="db870-131">Тачна поља зависе од услуге на коју се повезујете.</span><span class="sxs-lookup"><span data-stu-id="db870-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="db870-132">Више о детаљима одређеног типа везе можете сазнати у чланку о циљној услузи.</span><span class="sxs-lookup"><span data-stu-id="db870-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="db870-133">Да бисте креирали везу, изаберите **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="db870-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="db870-134">Такође можете да изаберете **Подешавање** на плочици на картици **Откривање**.</span><span class="sxs-lookup"><span data-stu-id="db870-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="db870-135">Дозволите сарадницима да користе везу за извоз</span><span class="sxs-lookup"><span data-stu-id="db870-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="db870-136">Када подешавате или уређујете везу за извоз, ви бирате који корисници смеју да користе ову одређену везу за дефинисање [извоза](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="db870-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="db870-137">Подразумевано је веза доступна корисницима са администраторском улогом.</span><span class="sxs-lookup"><span data-stu-id="db870-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="db870-138">Ово подешавање можете променити у делу **Изаберите ко може да користи ову везу** и дозволите корисницима са улогом сарадника да користе ову везу.</span><span class="sxs-lookup"><span data-stu-id="db870-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="db870-139">Сарадници неће моћи да виде или измене везу.</span><span class="sxs-lookup"><span data-stu-id="db870-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="db870-140">Видеће само име за приказ и тип везе приликом креирања извоза.</span><span class="sxs-lookup"><span data-stu-id="db870-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="db870-141">Дељењем везе омогућавате сарадницима да је користе.</span><span class="sxs-lookup"><span data-stu-id="db870-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="db870-142">Сарадници ће видети заједничке везе када успоставе извоз.</span><span class="sxs-lookup"><span data-stu-id="db870-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="db870-143">Они могу управљати сваким извозом који користи ову специфичну везу.</span><span class="sxs-lookup"><span data-stu-id="db870-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="db870-144">Можете да промените ово подешавање, а да задржите извоз који су већ дефинисали сарадници.</span><span class="sxs-lookup"><span data-stu-id="db870-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="db870-145">Уређивање везе</span><span class="sxs-lookup"><span data-stu-id="db870-145">Edit a connection</span></span>

1. <span data-ttu-id="db870-146">Идите на **Администратор** > **Везе (преглед)**.</span><span class="sxs-lookup"><span data-stu-id="db870-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="db870-147">Идите на картицу **Везе**.</span><span class="sxs-lookup"><span data-stu-id="db870-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="db870-148">Изаберите вертикалне три тачке за везу коју желите да уредите.</span><span class="sxs-lookup"><span data-stu-id="db870-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="db870-149">Изаберите **Уреди**.</span><span class="sxs-lookup"><span data-stu-id="db870-149">Select **Edit**.</span></span>

1. <span data-ttu-id="db870-150">Промените вредности које желите да ажурирате и изаберите **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="db870-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="db870-151">Уклањање везе</span><span class="sxs-lookup"><span data-stu-id="db870-151">Remove a connection</span></span>

<span data-ttu-id="db870-152">Ако се веза коју уклањате користи за обогаћивање или извоз, прво их морате одвојити или уклонити.</span><span class="sxs-lookup"><span data-stu-id="db870-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="db870-153">Дијалог за уклањање водиће вас до релевантних обогаћивања или извоза.</span><span class="sxs-lookup"><span data-stu-id="db870-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> <span data-ttu-id="db870-154">Одвојена обогаћивања и извози постају неактивни.</span><span class="sxs-lookup"><span data-stu-id="db870-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="db870-155">Поново их активирате додавањем друге везе са њима на страници [Обогаћивања](enrichment-hub.md) или [Извози](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="db870-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="db870-156">Идите на **Администратор** > **Везе (преглед)**.</span><span class="sxs-lookup"><span data-stu-id="db870-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="db870-157">Идите на картицу **Везе**.</span><span class="sxs-lookup"><span data-stu-id="db870-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="db870-158">Изаберите вертикалне три тачке за везу коју желите да уклоните.</span><span class="sxs-lookup"><span data-stu-id="db870-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="db870-159">Изаберите **Уклони** из падајућег менија.</span><span class="sxs-lookup"><span data-stu-id="db870-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="db870-160">Приказује се дијалог за потврду.</span><span class="sxs-lookup"><span data-stu-id="db870-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="db870-161">Ако постоје обогаћивања или извози који користе ову везу, изаберите дугме да бисте видели шта користи везу.</span><span class="sxs-lookup"><span data-stu-id="db870-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="db870-162">**Извози:** Можете да уклоните или прекинете извоз како бисте могли да уклоните везу.</span><span class="sxs-lookup"><span data-stu-id="db870-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="db870-163">Да би прекинули извоз, администратори могу да користе радњу **Прекини везу**.</span><span class="sxs-lookup"><span data-stu-id="db870-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="db870-164">Ова радња је доступна за појединачне и вишеструко изабране извозе.</span><span class="sxs-lookup"><span data-stu-id="db870-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="db870-165">Прекидом везе задржавате конфигурацију извоза, али она се неће покренути док јој се не дода друга веза.</span><span class="sxs-lookup"><span data-stu-id="db870-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="db870-166">**Обогаћивања:** Можете да уклоните или деактивирате обогаћивања како бисте могли да уклоните везу.</span><span class="sxs-lookup"><span data-stu-id="db870-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="db870-167">Када веза нема више зависности, вратите се на **Администратор** > **Везе** и покушајте поново да уклоните везу.</span><span class="sxs-lookup"><span data-stu-id="db870-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="db870-168">Да бисте потврдили брисање, изаберите **Уклони**.</span><span class="sxs-lookup"><span data-stu-id="db870-168">To confirm the deletion select **Remove**.</span></span>

