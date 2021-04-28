---
title: Извезите Customer Insights податке у Azure Data Lake Storage Gen2
description: Сазнајте како да конфигуришете везу са услугом Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760069"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="f325c-103">Подешавање везе са апликацијом Azure Data Lake Storage Gen2 (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="f325c-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="f325c-104">Идите на **Администратор** > **Везе**.</span><span class="sxs-lookup"><span data-stu-id="f325c-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f325c-105">Изаберите **Додај везу** и бирајте **Azure Data Lake Gen 2** да бисте конфигурисали везу.</span><span class="sxs-lookup"><span data-stu-id="f325c-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="f325c-106">Дајте вези препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="f325c-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f325c-107">Име за приказ и врста везе описују ову везу.</span><span class="sxs-lookup"><span data-stu-id="f325c-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f325c-108">Препоручујемо да одаберете назив који објашњава сврху и циљ везе.</span><span class="sxs-lookup"><span data-stu-id="f325c-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f325c-109">Одаберите ко може да користи ову везу.</span><span class="sxs-lookup"><span data-stu-id="f325c-109">Choose who can use this connection.</span></span> <span data-ttu-id="f325c-110">Ако ништа не предузмете, подразумевани ће бити Администратори.</span><span class="sxs-lookup"><span data-stu-id="f325c-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f325c-111">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f325c-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f325c-112">Унесите **Назив пословног контакта**, **Кључ пословног контакта** и **Контејнер** за ваш Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="f325c-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="f325c-113">Да бисте сазнали како да направите налог за складиштење са којим ћете користити Azure Data Lake Storage Gen2, погледајте чланак [Креирање налога за складиштење](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="f325c-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="f325c-114">Да бисте сазнали више о називу налога Azure Data Lake Gen2 складишта и кључу складишта, погледајте [Управљање подешавањима налога за складиштење на Azure порталу](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="f325c-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="f325c-115">Изаберите **Сачувај** да бисте креирали везу.</span><span class="sxs-lookup"><span data-stu-id="f325c-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="f325c-116">Конфигурисање извоза</span><span class="sxs-lookup"><span data-stu-id="f325c-116">Configure an export</span></span>

<span data-ttu-id="f325c-117">Овај извоз можете да конфигуришете ако имате приступ вези ове врсте.</span><span class="sxs-lookup"><span data-stu-id="f325c-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f325c-118">За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f325c-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f325c-119">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="f325c-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f325c-120">Да бисте креирали нови извоз, изаберите **Додај извоз**.</span><span class="sxs-lookup"><span data-stu-id="f325c-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="f325c-121">У пољу **Веза за извоз**, одаберите везу из одељка **Azure Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="f325c-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="f325c-122">Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.</span><span class="sxs-lookup"><span data-stu-id="f325c-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f325c-123">Изаберите поље поред сваког ентитета који желите да извезете на ово одредиште.</span><span class="sxs-lookup"><span data-stu-id="f325c-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="f325c-124">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="f325c-124">Select **Save**.</span></span>

<span data-ttu-id="f325c-125">Чување извоза не покреће извоз одмах.</span><span class="sxs-lookup"><span data-stu-id="f325c-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f325c-126">Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f325c-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f325c-127">Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f325c-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="f325c-128">Извезени подаци се чувају у Azure Data Lake Gen 2 контејнеру за складиштење који сте конфигурисали.</span><span class="sxs-lookup"><span data-stu-id="f325c-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
