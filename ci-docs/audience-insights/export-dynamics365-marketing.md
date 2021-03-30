---
title: Извезите Customer Insights податке у Dynamics 365 Marketing
description: Сазнајте како да конфигуришете везу са услугом Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597621"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="93c39-103">Конектор за Dynamics 365 Marketing (преглед)</span><span class="sxs-lookup"><span data-stu-id="93c39-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="93c39-104">Користите [сегменте](segments.md) да бисте генерисали кампање и контактирали одређене групе клијената помоћу услуге Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="93c39-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="93c39-105">Више информација потражите у чланку [Коришћење сегмената из услуга Dynamics 365 Customer Insights уз Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="93c39-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="93c39-106">Предуслов</span><span class="sxs-lookup"><span data-stu-id="93c39-106">Prerequisite</span></span>

- <span data-ttu-id="93c39-107">Записи контаката морају бити присутни у услузи Dynamics 365 Marketing да бисте могли да извезете сегмент из услуге Customer Insights у Marketing.</span><span class="sxs-lookup"><span data-stu-id="93c39-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="93c39-108">Прочитајте више о томе како се уносе контакти у [Dynamics 365 Marketing помоћу услуге Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="93c39-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="93c39-109">Извоз сегмената из увида о корисницима у Marketing неће креирати нове записе контаката у инстанцама услуге Marketing.</span><span class="sxs-lookup"><span data-stu-id="93c39-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="93c39-110">Евиденција контаката из услуге Marketing мора се унети у увид о корисницима и користити као извор података.</span><span class="sxs-lookup"><span data-stu-id="93c39-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="93c39-111">Такође их треба укључити у јединствени ентитет клијента да би се ID-ови клијената мапирали у ID-ове контаката да би сегменти могли да се извезу.</span><span class="sxs-lookup"><span data-stu-id="93c39-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="93c39-112">Конфигуришите конектор за Marketing</span><span class="sxs-lookup"><span data-stu-id="93c39-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="93c39-113">У увидима о корисницима идите на **Администратор** > **Одредишта за извоз**.</span><span class="sxs-lookup"><span data-stu-id="93c39-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="93c39-114">У одељку **Dynamics 365 Marketing** изаберите **Подеси**.</span><span class="sxs-lookup"><span data-stu-id="93c39-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="93c39-115">Дајте одредишту за извоз препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="93c39-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="93c39-116">Унесите URL организације за Marketing у поље **Адреса сервера**.</span><span class="sxs-lookup"><span data-stu-id="93c39-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="93c39-117">У одељку **Администраторски налог на серверу**, изаберите **Пријавите се** и изаберите Dynamics 365 Marketing налог.</span><span class="sxs-lookup"><span data-stu-id="93c39-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="93c39-118">Мапирајте поље корисничког ID-а са Dynamics 365 ID-ом контакта.</span><span class="sxs-lookup"><span data-stu-id="93c39-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="93c39-119">Изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="93c39-119">Select **Next**.</span></span>

1. <span data-ttu-id="93c39-120">Изаберите један или више сегмената.</span><span class="sxs-lookup"><span data-stu-id="93c39-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="93c39-121">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="93c39-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="93c39-122">Извоз података</span><span class="sxs-lookup"><span data-stu-id="93c39-122">Export the data</span></span>

<span data-ttu-id="93c39-123">Можете да [извезете податке на захтев](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="93c39-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="93c39-124">Извоз ће се такође покренути са сваким [планираним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="93c39-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]