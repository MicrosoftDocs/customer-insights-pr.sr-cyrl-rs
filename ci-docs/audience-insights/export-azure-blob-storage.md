---
title: Извоз Customer Insights података у Azure складиште блоб објекта
description: Сазнајте како да конфигуришете везу и извезете садржај у складиште блоб објекта.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 294feff2f77c3756fbadb36c90aab430454f5967
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760253"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="fbbcc-103">Извоз листе сегмената и других података у Azure складиште блоб објекта (преглед)</span><span class="sxs-lookup"><span data-stu-id="fbbcc-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="fbbcc-104">Складиштите Customer Insights податке у складиште блоб објекта или их користите за пренос података у друге апликације.</span><span class="sxs-lookup"><span data-stu-id="fbbcc-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="fbbcc-105">Подесите везу са складиштем блоб објекта</span><span class="sxs-lookup"><span data-stu-id="fbbcc-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="fbbcc-106">Идите на **Администратор** > **Везе**.</span><span class="sxs-lookup"><span data-stu-id="fbbcc-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="fbbcc-107">Изаберите **Додај везу** и бирајте **Azure складиште блоб објекта** да бисте конфигурисали везу.</span><span class="sxs-lookup"><span data-stu-id="fbbcc-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="fbbcc-108">Дајте вези препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="fbbcc-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="fbbcc-109">Име за приказ и врста везе описују ову везу.</span><span class="sxs-lookup"><span data-stu-id="fbbcc-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="fbbcc-110">Препоручујемо да одаберете назив који објашњава сврху и циљ везе.</span><span class="sxs-lookup"><span data-stu-id="fbbcc-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="fbbcc-111">Одаберите ко може да користи ову везу.</span><span class="sxs-lookup"><span data-stu-id="fbbcc-111">Choose who can use this connection.</span></span> <span data-ttu-id="fbbcc-112">Ако ништа не предузмете, подразумевани ће бити Администратори.</span><span class="sxs-lookup"><span data-stu-id="fbbcc-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="fbbcc-113">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="fbbcc-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="fbbcc-114">Унесите **Назив налога**, **Кључ налога** и **Контејнер** за свој налог складишта блоб објекта.</span><span class="sxs-lookup"><span data-stu-id="fbbcc-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="fbbcc-115">Да бисте сазнали више о томе како да пронађете назив налога складишта блоб објекта и кључ налога, погледајте [Управљање подешавањима налога за складиштење на Azure порталу](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="fbbcc-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="fbbcc-116">Да бисте сазнали како да креирате контејнер, погледајте чланак [Креирање контејнера](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="fbbcc-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="fbbcc-117">Изаберите **Сачувај** да бисте креирали везу.</span><span class="sxs-lookup"><span data-stu-id="fbbcc-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="fbbcc-118">Конфигурисање извоза</span><span class="sxs-lookup"><span data-stu-id="fbbcc-118">Configure an export</span></span>

<span data-ttu-id="fbbcc-119">Овај извоз можете да конфигуришете ако имате приступ вези ове врсте.</span><span class="sxs-lookup"><span data-stu-id="fbbcc-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="fbbcc-120">За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="fbbcc-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="fbbcc-121">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="fbbcc-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="fbbcc-122">Да бисте креирали нови извоз, изаберите **Додај одредиште**.</span><span class="sxs-lookup"><span data-stu-id="fbbcc-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="fbbcc-123">У пољу **Веза за извоз**, одаберите везу из одељка Azure складишта блоб објекта.</span><span class="sxs-lookup"><span data-stu-id="fbbcc-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="fbbcc-124">Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.</span><span class="sxs-lookup"><span data-stu-id="fbbcc-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="fbbcc-125">Изаберите поље поред сваког ентитета који желите да извезете на ово одредиште.</span><span class="sxs-lookup"><span data-stu-id="fbbcc-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="fbbcc-126">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="fbbcc-126">Select **Save**.</span></span>

<span data-ttu-id="fbbcc-127">Чување извоза не покреће извоз одмах.</span><span class="sxs-lookup"><span data-stu-id="fbbcc-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="fbbcc-128">Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fbbcc-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="fbbcc-129">Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="fbbcc-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="fbbcc-130">Извезени подаци се чувају у контејнеру складишта блоб објекта који сте конфигурисали.</span><span class="sxs-lookup"><span data-stu-id="fbbcc-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="fbbcc-131">Следеће путање фасциклу се аутоматски креирају у вашем контејнеру:</span><span class="sxs-lookup"><span data-stu-id="fbbcc-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="fbbcc-132">За изворне ентитете и ентитете које генерише систем: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="fbbcc-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="fbbcc-133">Пример: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="fbbcc-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="fbbcc-134">Датотека model.json за извезене ентитете биће на нивоу %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="fbbcc-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="fbbcc-135">Пример: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="fbbcc-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
