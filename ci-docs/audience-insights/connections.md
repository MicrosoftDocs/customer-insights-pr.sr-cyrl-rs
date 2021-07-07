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
ms.openlocfilehash: 17e04b243e9b3d4375c86f5a890a18be35956835
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304990"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="3b70e-103">Преглед веза (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="3b70e-103">Connections (preview) overview</span></span>

<span data-ttu-id="3b70e-104">Везе су кључ за омогућавање дељења података у услугу Customer Insights и из ње.</span><span class="sxs-lookup"><span data-stu-id="3b70e-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="3b70e-105">Свака веза успоставља дељење података са одређеном услугом.</span><span class="sxs-lookup"><span data-stu-id="3b70e-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="3b70e-106">Везе су темељ да [конфигуришете обогаћивања трећих страна](enrichment-hub.md) и [конфигурисање извоза](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="3b70e-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="3b70e-107">Иста веза се може користити више пута.</span><span class="sxs-lookup"><span data-stu-id="3b70e-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="3b70e-108">На пример, једна веза са услугом Dynamics 365 Marketing функционише за више извоза, а једна Leadspace веза може се користити за неколико обогаћивања.</span><span class="sxs-lookup"><span data-stu-id="3b70e-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="3b70e-109">Идите на **Администратор** > **Везе** да бисте креирали и приказали везе.</span><span class="sxs-lookup"><span data-stu-id="3b70e-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="3b70e-110">На картици **Везе** приказују се све активне везе.</span><span class="sxs-lookup"><span data-stu-id="3b70e-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="3b70e-111">Листа приказује ред за сваку везу.</span><span class="sxs-lookup"><span data-stu-id="3b70e-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="3b70e-112">Преузмите брзи преглед, опис и сазнајте шта можете учинити са сваком опцијом проширивости на картици **Откривање**.</span><span class="sxs-lookup"><span data-stu-id="3b70e-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="3b70e-113">Извоз</span><span class="sxs-lookup"><span data-stu-id="3b70e-113">Exports</span></span>

<span data-ttu-id="3b70e-114">Само администратори могу да конфигуришу нове везе, али могу да дају приступ сарадницима да користе постојеће везе.</span><span class="sxs-lookup"><span data-stu-id="3b70e-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="3b70e-115">Администратори контролишу куда подаци могу да иду, сарадници дефинишу корисне податке и учесталост у складу са својим потребама.</span><span class="sxs-lookup"><span data-stu-id="3b70e-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="3b70e-116">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="3b70e-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="3b70e-117">Обогаћивања</span><span class="sxs-lookup"><span data-stu-id="3b70e-117">Enrichments</span></span>

<span data-ttu-id="3b70e-118">Само администратори могу да конфигуришу нове везе, али креиране везе су увек доступне и администраторима и сарадницима.</span><span class="sxs-lookup"><span data-stu-id="3b70e-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="3b70e-119">Администратори управљају акредитивима и дају сагласност за пренос података.</span><span class="sxs-lookup"><span data-stu-id="3b70e-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="3b70e-120">Везе тада могу да користе администратори и сарадници за обогаћивања.</span><span class="sxs-lookup"><span data-stu-id="3b70e-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="3b70e-121">Додавање нове везе</span><span class="sxs-lookup"><span data-stu-id="3b70e-121">Add a new connection</span></span>

<span data-ttu-id="3b70e-122">Да бисте додали везе, морате да имате [администраторске дозволе](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="3b70e-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="3b70e-123">Ако се повежете са другим Microsoft услугама, претпостављамо да су обе услуге у истој организацији.</span><span class="sxs-lookup"><span data-stu-id="3b70e-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="3b70e-124">Идите на **Администратор** > **Везе (преглед)**.</span><span class="sxs-lookup"><span data-stu-id="3b70e-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="3b70e-125">Идите на картицу **Везе**.</span><span class="sxs-lookup"><span data-stu-id="3b70e-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="3b70e-126">Изаберите **Додај везу** да бисте креирали нову везу.</span><span class="sxs-lookup"><span data-stu-id="3b70e-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="3b70e-127">Одаберите из падајућег менија коју врсту везе желите да креирате.</span><span class="sxs-lookup"><span data-stu-id="3b70e-127">Choose from the dropdown menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="3b70e-128">У окну **Подешавање везе**, наведите потребне детаље.</span><span class="sxs-lookup"><span data-stu-id="3b70e-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="3b70e-129">**Име за приказ** и врста везе описују везу.</span><span class="sxs-lookup"><span data-stu-id="3b70e-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="3b70e-130">Препоручујемо да одаберете назив који објашњава сврху и циљ ове везе.</span><span class="sxs-lookup"><span data-stu-id="3b70e-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="3b70e-131">Тачна поља зависе од услуге на коју се повезујете.</span><span class="sxs-lookup"><span data-stu-id="3b70e-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="3b70e-132">Више о детаљима одређеног типа везе можете сазнати у чланку о циљној услузи.</span><span class="sxs-lookup"><span data-stu-id="3b70e-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="3b70e-133">Да бисте креирали везу, изаберите **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="3b70e-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="3b70e-134">Такође можете да изаберете **Подешавање** на плочици на картици **Откривање**.</span><span class="sxs-lookup"><span data-stu-id="3b70e-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="3b70e-135">Дозволите сарадницима да користе везу за извоз</span><span class="sxs-lookup"><span data-stu-id="3b70e-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="3b70e-136">Када подешавате или уређујете везу за извоз, ви бирате који корисници смеју да користе ову одређену везу за дефинисање [извоза](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="3b70e-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="3b70e-137">Подразумевано је веза доступна корисницима са администраторском улогом.</span><span class="sxs-lookup"><span data-stu-id="3b70e-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="3b70e-138">Ово подешавање можете променити у делу **Изаберите ко може да користи ову везу** и дозволите корисницима са улогом сарадника да користе ову везу.</span><span class="sxs-lookup"><span data-stu-id="3b70e-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="3b70e-139">Сарадници неће моћи да виде или измене везу.</span><span class="sxs-lookup"><span data-stu-id="3b70e-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="3b70e-140">Видеће само име за приказ и тип везе приликом креирања извоза.</span><span class="sxs-lookup"><span data-stu-id="3b70e-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="3b70e-141">Дељењем везе омогућавате сарадницима да је користе.</span><span class="sxs-lookup"><span data-stu-id="3b70e-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="3b70e-142">Сарадници ће видети заједничке везе када успоставе извоз.</span><span class="sxs-lookup"><span data-stu-id="3b70e-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="3b70e-143">Они могу управљати сваким извозом који користи ову специфичну везу.</span><span class="sxs-lookup"><span data-stu-id="3b70e-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="3b70e-144">Можете да промените ово подешавање, а да задржите извоз који су већ дефинисали сарадници.</span><span class="sxs-lookup"><span data-stu-id="3b70e-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="3b70e-145">Уређивање везе</span><span class="sxs-lookup"><span data-stu-id="3b70e-145">Edit a connection</span></span>

1. <span data-ttu-id="3b70e-146">Идите на **Администратор** > **Везе (преглед)**.</span><span class="sxs-lookup"><span data-stu-id="3b70e-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="3b70e-147">Идите на картицу **Везе**.</span><span class="sxs-lookup"><span data-stu-id="3b70e-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="3b70e-148">Изаберите вертикалне три тачке за везу коју желите да уредите.</span><span class="sxs-lookup"><span data-stu-id="3b70e-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="3b70e-149">Изаберите **Уреди**.</span><span class="sxs-lookup"><span data-stu-id="3b70e-149">Select **Edit**.</span></span>

1. <span data-ttu-id="3b70e-150">Промените вредности које желите да ажурирате и изаберите **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="3b70e-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="3b70e-151">Уклањање везе</span><span class="sxs-lookup"><span data-stu-id="3b70e-151">Remove a connection</span></span>

<span data-ttu-id="3b70e-152">Ако се веза коју уклањате користи за обогаћивање или извоз, прво их морате одвојити или уклонити.</span><span class="sxs-lookup"><span data-stu-id="3b70e-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="3b70e-153">Дијалог за уклањање водиће вас до релевантних обогаћивања или извоза.</span><span class="sxs-lookup"><span data-stu-id="3b70e-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> 

<span data-ttu-id="3b70e-154">Одвојена обогаћивања и извози постају неактивни.</span><span class="sxs-lookup"><span data-stu-id="3b70e-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="3b70e-155">Поново их активирате додавањем друге везе са њима на страници [Обогаћивања](enrichment-hub.md) или [Извози](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="3b70e-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="3b70e-156">Идите на **Администратор** > **Везе (преглед)**.</span><span class="sxs-lookup"><span data-stu-id="3b70e-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="3b70e-157">Идите на картицу **Везе**.</span><span class="sxs-lookup"><span data-stu-id="3b70e-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="3b70e-158">Изаберите вертикалне три тачке за везу коју желите да уклоните.</span><span class="sxs-lookup"><span data-stu-id="3b70e-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="3b70e-159">Изаберите **Уклони** из падајућег менија.</span><span class="sxs-lookup"><span data-stu-id="3b70e-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="3b70e-160">Приказује се дијалог за потврду.</span><span class="sxs-lookup"><span data-stu-id="3b70e-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="3b70e-161">Ако постоје обогаћивања или извози који користе ову везу, изаберите дугме да бисте видели шта користи везу.</span><span class="sxs-lookup"><span data-stu-id="3b70e-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="3b70e-162">**Извози:** Можете да уклоните или прекинете извоз како бисте могли да уклоните везу.</span><span class="sxs-lookup"><span data-stu-id="3b70e-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="3b70e-163">Да би прекинули извоз, администратори могу да користе радњу **Прекини везу**.</span><span class="sxs-lookup"><span data-stu-id="3b70e-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="3b70e-164">Ова радња је доступна за појединачне и вишеструко изабране извозе.</span><span class="sxs-lookup"><span data-stu-id="3b70e-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="3b70e-165">Прекидом везе задржавате конфигурацију извоза, али она се неће покренути док јој се не дода друга веза.</span><span class="sxs-lookup"><span data-stu-id="3b70e-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="3b70e-166">**Обогаћивања:** Можете да уклоните или деактивирате обогаћивања како бисте могли да уклоните везу.</span><span class="sxs-lookup"><span data-stu-id="3b70e-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="3b70e-167">Када веза нема више зависности, вратите се на **Администратор** > **Везе** и покушајте поново да уклоните везу.</span><span class="sxs-lookup"><span data-stu-id="3b70e-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="3b70e-168">Да бисте потврдили брисање, изаберите **Уклони**.</span><span class="sxs-lookup"><span data-stu-id="3b70e-168">To confirm the deletion, select **Remove**.</span></span>

