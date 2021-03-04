---
title: Извезите Customer Insights податке у Azure Data Lake Storage Gen2
description: Сазнајте како да конфигуришете везу са услугом Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477197"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="4d88c-103">Конектор за Azure Data Lake Storage Gen2 (преглед)</span><span class="sxs-lookup"><span data-stu-id="4d88c-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="4d88c-104">Складиштите податке Customer Insights података у услугу Azure Data Lake Storage Gen2 или их користите за пренос података у друге апликације.</span><span class="sxs-lookup"><span data-stu-id="4d88c-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="4d88c-105">Конфигуришите конектор за Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="4d88c-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="4d88c-106">У увидима о корисницима идите на **Администратор** > **Одредишта за извоз**.</span><span class="sxs-lookup"><span data-stu-id="4d88c-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="4d88c-107">Уз одељку **Azure Data Lake Storage Gen2** изаберите **Подеси**.</span><span class="sxs-lookup"><span data-stu-id="4d88c-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="4d88c-108">Дајте одредишту препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="4d88c-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="4d88c-109">Унесите **Назив пословног контакта**, **Кључ пословног контакта** и **Контејнер** за ваш Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="4d88c-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="4d88c-110">Да бисте сазнали како да направите налог за складиштење са којим ћете користити Azure Data Lake Storage Gen2, погледајте чланак [Креирање налога за складиштење](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="4d88c-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="4d88c-111">Да бисте сазнали више о томе како да пронађете име пословног контакта за Azure Data Lake Gen2 складиште, погледајте чланак [Управљање подешавањима налога за складиштење на Azure порталу](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="4d88c-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="4d88c-112">Изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="4d88c-112">Select **Next**.</span></span>

1. <span data-ttu-id="4d88c-113">Изаберите поље поред сваког ентитета који желите да извезете на ово одредиште.</span><span class="sxs-lookup"><span data-stu-id="4d88c-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="4d88c-114">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="4d88c-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="4d88c-115">Извоз података</span><span class="sxs-lookup"><span data-stu-id="4d88c-115">Export the data</span></span>

<span data-ttu-id="4d88c-116">Можете да [извезете податке на захтев](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="4d88c-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="4d88c-117">Извоз ће се такође покренути са сваким [планираним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4d88c-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
