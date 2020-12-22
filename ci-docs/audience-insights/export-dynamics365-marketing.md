---
title: Извезите Customer Insights податке у Dynamics 365 Marketing
description: Сазнајте како да конфигуришете везу са услугом Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643791"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="80493-103">Конектор за Dynamics 365 Marketing (преглед)</span><span class="sxs-lookup"><span data-stu-id="80493-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="80493-104">Користите [сегменте](segments.md) да бисте генерисали кампање и контактирали одређене групе клијената помоћу услуге Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="80493-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="80493-105">Више информација потражите у чланку [Коришћење сегмената из услуга Dynamics 365 Customer Insights уз Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="80493-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="80493-106">Предуслов</span><span class="sxs-lookup"><span data-stu-id="80493-106">Prerequisite</span></span>

<span data-ttu-id="80493-107">Записи контаката [из Dynamics 365 Marketing унети помоћу услуге Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="80493-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="80493-108">Конфигуришите конектор за Marketing</span><span class="sxs-lookup"><span data-stu-id="80493-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="80493-109">У увидима о корисницима идите на **Администратор** > **Одредишта за извоз**.</span><span class="sxs-lookup"><span data-stu-id="80493-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="80493-110">У одељку **Dynamics 365 Marketing** изаберите **Подеси**.</span><span class="sxs-lookup"><span data-stu-id="80493-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="80493-111">Дајте одредишту за извоз препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="80493-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="80493-112">Унесите URL организације за Marketing у поље **Адреса сервера**.</span><span class="sxs-lookup"><span data-stu-id="80493-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="80493-113">У одељку **Администраторски налог на серверу**, изаберите **Пријавите се** и изаберите Dynamics 365 Marketing налог.</span><span class="sxs-lookup"><span data-stu-id="80493-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="80493-114">Мапирајте поље корисничког ID-а са Dynamics 365 ID-ом контакта.</span><span class="sxs-lookup"><span data-stu-id="80493-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="80493-115">Изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="80493-115">Select **Next**.</span></span>

1. <span data-ttu-id="80493-116">Изаберите један или више сегмената.</span><span class="sxs-lookup"><span data-stu-id="80493-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="80493-117">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="80493-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="80493-118">Извоз података</span><span class="sxs-lookup"><span data-stu-id="80493-118">Export the data</span></span>

<span data-ttu-id="80493-119">Можете да [извезете податке на захтев](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="80493-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="80493-120">Извоз ће се такође покренути са сваким [планираним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="80493-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
