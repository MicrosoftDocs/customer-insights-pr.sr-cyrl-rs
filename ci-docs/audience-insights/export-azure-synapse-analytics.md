---
title: Извоз Customer Insights података у услугу Azure Synapse Analytics
description: Сазнајте како да конфигуришете везу са услугом Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977395"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="85092-103">Извоз података у услугу Azure Synapse Analytics (преглед)</span><span class="sxs-lookup"><span data-stu-id="85092-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="85092-104">Azure Synapse је аналитичка услуга која убрзава време за увид у складишта података и системе великих података.</span><span class="sxs-lookup"><span data-stu-id="85092-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="85092-105">Можете да унесете и користите Customer Insights податке у услузи [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="85092-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="85092-106">Предуслови</span><span class="sxs-lookup"><span data-stu-id="85092-106">Prerequisites</span></span>

<span data-ttu-id="85092-107">Следећи предуслови морају бити испуњени за конфигурисање везе из услуге Customer Insights у услугу Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="85092-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="85092-108">Обавезно подесите све **доделе улога** као што је описано.</span><span class="sxs-lookup"><span data-stu-id="85092-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="85092-109">Предуслови у услузи Customer Insights</span><span class="sxs-lookup"><span data-stu-id="85092-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="85092-110">Имате улогу **администратора** у увидима у циљну групу.</span><span class="sxs-lookup"><span data-stu-id="85092-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="85092-111">Сазнајте више о [постављању корисничких дозвола у увидима у циљну групу](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="85092-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="85092-112">У услузи Azure:</span><span class="sxs-lookup"><span data-stu-id="85092-112">In Azure:</span></span> 

- <span data-ttu-id="85092-113">Активна претплата на услугу Azure.</span><span class="sxs-lookup"><span data-stu-id="85092-113">An active Azure subscription.</span></span>

- <span data-ttu-id="85092-114">Ако користите нови Azure Data Lake Storage Gen2 налог, *принципалу услуге за увиде у циљну групу* су потребне дозволе **сарадника за податке складишта блоб објекта**.</span><span class="sxs-lookup"><span data-stu-id="85092-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="85092-115">Сазнајте више о [повезивању са Azure Data Lake Storage Gen2 налогом са Azure принципалом услуге за увиде у циљну групу](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="85092-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="85092-116">Data Lake Storage Gen2 **мора да има** омогућен [хијерархијски простор имена](/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="85092-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="85092-117">У групи ресурса у којој се налази Azure Synapse радни простор, *принципалу услуге* и *кориснику за увиде у циљну групу* треба доделити барем дозволе **читаоца**.</span><span class="sxs-lookup"><span data-stu-id="85092-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="85092-118">За више информација, погледајте [Додељивање Azure улога помоћу Azure портала](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="85092-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="85092-119">*Кориснику* су потребне дозволе **сарадника за податке складишта блоб објекта** на Azure Data Lake Storage Gen2 налогу на којем се подаци налазе и повезани су са Azure Synapse радним простором.</span><span class="sxs-lookup"><span data-stu-id="85092-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="85092-120">Сазнајте више о [коришћењу Azure портала за додељивање Azure улоге за приступ блоб објекту и подацима у реду](/azure/storage/common/storage-auth-aad-rbac-portal) и [дозволама сарадника за податке складишта блоб објекта](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="85092-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="85092-121">*[Управљаном идентитету Azure Synapse радног простора](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* су потребне дозволе **сарадника за податке складишта блоб објекта** на Azure Data Lake Storage Gen2 налогу на којем се подаци налазе и повезани су са Azure Synapse радним простором.</span><span class="sxs-lookup"><span data-stu-id="85092-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="85092-122">Сазнајте више о [коришћењу Azure портала за додељивање Azure улоге за приступ блоб објекту и подацима у реду](/azure/storage/common/storage-auth-aad-rbac-portal) и [дозволама сарадника за податке складишта блоб објекта](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="85092-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="85092-123">У Azure Synapse радном простору, *принципалу услуге за увиде у циљну групу* је потребна додељена улога **Synapse администратора**.</span><span class="sxs-lookup"><span data-stu-id="85092-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="85092-124">За више информација, погледајте [Како се поставља контрола приступа за ваш Synapse радни простор](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="85092-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="85092-125">Подесите везу и извоз у Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="85092-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="85092-126">Конфигурисање везе</span><span class="sxs-lookup"><span data-stu-id="85092-126">Configure a connection</span></span>

1. <span data-ttu-id="85092-127">Идите на **Администратор** > **Везе**.</span><span class="sxs-lookup"><span data-stu-id="85092-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="85092-128">Изаберите **Додај везу** и бирајте **Azure Synapse Analytics** или изаберите **Подешавање** на плочици **Azure Synapse Analytics** да бисте конфигурисали везу.</span><span class="sxs-lookup"><span data-stu-id="85092-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="85092-129">Дајте вези препознатљиво име у пољу Име за приказ.</span><span class="sxs-lookup"><span data-stu-id="85092-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="85092-130">Име за приказ и врста везе описују ову везу.</span><span class="sxs-lookup"><span data-stu-id="85092-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="85092-131">Препоручујемо да одаберете назив који објашњава сврху и циљ везе.</span><span class="sxs-lookup"><span data-stu-id="85092-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="85092-132">Одаберите ко може да користи ову везу.</span><span class="sxs-lookup"><span data-stu-id="85092-132">Choose who can use this connection.</span></span> <span data-ttu-id="85092-133">Ако ништа не предузмете, подразумевани ће бити Администратори.</span><span class="sxs-lookup"><span data-stu-id="85092-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="85092-134">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="85092-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="85092-135">Изаберите или потражите претплату у којој желите да користите Customer Insights податке.</span><span class="sxs-lookup"><span data-stu-id="85092-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="85092-136">Чим изаберете претплату, можете и да изаберете **Радни простор**, **Налог складишта** и **Контејнер**.</span><span class="sxs-lookup"><span data-stu-id="85092-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="85092-137">Изаберите **Сачувај** да бисте сачували везу.</span><span class="sxs-lookup"><span data-stu-id="85092-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="85092-138">Конфигурисање извоза</span><span class="sxs-lookup"><span data-stu-id="85092-138">Configure an export</span></span>

<span data-ttu-id="85092-139">Овај извоз можете да конфигуришете ако имате приступ вези ове врсте.</span><span class="sxs-lookup"><span data-stu-id="85092-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="85092-140">За више информација, погледајте [дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="85092-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="85092-141">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="85092-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="85092-142">Да бисте креирали нови извоз, изаберите **Додај извоз**.</span><span class="sxs-lookup"><span data-stu-id="85092-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="85092-143">У пољу **Веза за извоз** одаберите везу из одељка **Azure Synapse Analytics**.</span><span class="sxs-lookup"><span data-stu-id="85092-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="85092-144">Ако не видите назив овог одељка, не постоје [везе](connections.md) овог типа које су вам доступне.</span><span class="sxs-lookup"><span data-stu-id="85092-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="85092-145">Обезбедите препознатљиво **Име за приказ** за ваш извоз и **Назив базе података**.</span><span class="sxs-lookup"><span data-stu-id="85092-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="85092-146">Изаберите које ентитете желите да извезете у услугу Azure Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="85092-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="85092-147">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="85092-147">Select **Save**.</span></span>

<span data-ttu-id="85092-148">Чување извоза не покреће извоз одмах.</span><span class="sxs-lookup"><span data-stu-id="85092-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="85092-149">Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="85092-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="85092-150">Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="85092-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="85092-151">Ажурирање извоза</span><span class="sxs-lookup"><span data-stu-id="85092-151">Update an export</span></span>

1. <span data-ttu-id="85092-152">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="85092-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="85092-153">Изаберите **Уреди** на извозу који желите да промените.</span><span class="sxs-lookup"><span data-stu-id="85092-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="85092-154">**Додајте** или **уклоните** ентитете из избора.</span><span class="sxs-lookup"><span data-stu-id="85092-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="85092-155">Ако се ентитети уклоне из избора, неће се избрисати из Synapse Analytics базе података.</span><span class="sxs-lookup"><span data-stu-id="85092-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="85092-156">Међутим, будућа освежавања података неће ажурирати уклоњене ентитете у тој бази података.</span><span class="sxs-lookup"><span data-stu-id="85092-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="85092-157">**Промена назива базе података** креира нову Synapse Analytics базу података.</span><span class="sxs-lookup"><span data-stu-id="85092-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="85092-158">База података са именом које је претходно било конфигурисано неће добијати ажурирања у будућим освежавањима.</span><span class="sxs-lookup"><span data-stu-id="85092-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
