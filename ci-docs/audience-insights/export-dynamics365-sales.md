---
title: Извезите Customer Insights податке у Dynamics 365 Sales
description: Сазнајте како да конфигуришете везу са услугом Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643836"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="887d9-103">Конектор за Dynamics 365 Sales (преглед)</span><span class="sxs-lookup"><span data-stu-id="887d9-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="887d9-104">Користите податке о клијентима да бисте креирали маркетиншке спискове, пратили токове посла и слали промоције са услугом Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="887d9-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="887d9-105">Предуслов</span><span class="sxs-lookup"><span data-stu-id="887d9-105">Prerequisite</span></span>

<span data-ttu-id="887d9-106">Записи контаката [из Dynamics 365 Sales унетих помоћу услуге Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="887d9-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="887d9-107">Конфигуришите конектор за Sales</span><span class="sxs-lookup"><span data-stu-id="887d9-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="887d9-108">У увидима о корисницима идите на **Администратор** > **Одредишта за извоз**.</span><span class="sxs-lookup"><span data-stu-id="887d9-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="887d9-109">У одељку **Dynamics 365 Sales** изаберите **Подеси**.</span><span class="sxs-lookup"><span data-stu-id="887d9-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="887d9-110">Дајте одредишту за извоз препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="887d9-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="887d9-111">Унесите URL организације за Sales у поље **Адреса сервера**.</span><span class="sxs-lookup"><span data-stu-id="887d9-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="887d9-112">У одељку **Администраторски налог на серверу**, изаберите **Пријавите се** и изаберите Dynamics 365 Sales налог.</span><span class="sxs-lookup"><span data-stu-id="887d9-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="887d9-113">Мапирајте поље корисничког ID-а са Dynamics 365 ID-ом контакта.</span><span class="sxs-lookup"><span data-stu-id="887d9-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="887d9-114">Изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="887d9-114">Select **Next**.</span></span>

1. <span data-ttu-id="887d9-115">Изаберите један или више сегмената.</span><span class="sxs-lookup"><span data-stu-id="887d9-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="887d9-116">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="887d9-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="887d9-117">Извоз података</span><span class="sxs-lookup"><span data-stu-id="887d9-117">Export the data</span></span>

<span data-ttu-id="887d9-118">Можете да [извезете податке на захтев](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="887d9-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="887d9-119">Извоз ће се такође покренути са сваким [планираним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="887d9-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
