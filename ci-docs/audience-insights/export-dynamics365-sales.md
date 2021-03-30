---
title: Извезите Customer Insights податке у Dynamics 365 Sales
description: Сазнајте како да конфигуришете везу са услугом Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598127"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="9233c-103">Конектор за Dynamics 365 Sales (преглед)</span><span class="sxs-lookup"><span data-stu-id="9233c-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="9233c-104">Користите податке о клијентима да бисте креирали маркетиншке спискове, пратили токове посла и слали промоције са услугом Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="9233c-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="9233c-105">Предуслов</span><span class="sxs-lookup"><span data-stu-id="9233c-105">Prerequisite</span></span>

1. <span data-ttu-id="9233c-106">Записи контаката морају бити присутни у услузи Dynamics 365 Sales да бисте могли да извезете сегмент из услуге Customer Insights у Sales.</span><span class="sxs-lookup"><span data-stu-id="9233c-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="9233c-107">Прочитајте више о томе како се уносе контакти у [Dynamics 365 Sales помоћу услуге Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="9233c-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="9233c-108">Извоз сегмената из увида о корисницима у Sales неће креирати нове записе контаката у инстанцама услуге Sales.</span><span class="sxs-lookup"><span data-stu-id="9233c-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="9233c-109">Евиденција контаката из услуге Sales мора се унети у увид о корисницима и користити као извор података.</span><span class="sxs-lookup"><span data-stu-id="9233c-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="9233c-110">Такође их треба укључити у јединствени ентитет клијента да би се ID-ови клијената мапирали у ID-ове контаката да би сегменти могли да се извезу.</span><span class="sxs-lookup"><span data-stu-id="9233c-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="9233c-111">Конфигуришите конектор за Sales</span><span class="sxs-lookup"><span data-stu-id="9233c-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="9233c-112">У увидима о корисницима идите на **Администратор** > **Одредишта за извоз**.</span><span class="sxs-lookup"><span data-stu-id="9233c-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="9233c-113">У одељку **Dynamics 365 Sales** изаберите **Подеси**.</span><span class="sxs-lookup"><span data-stu-id="9233c-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="9233c-114">Дајте одредишту за извоз препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="9233c-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="9233c-115">Унесите URL организације за Sales у поље **Адреса сервера**.</span><span class="sxs-lookup"><span data-stu-id="9233c-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="9233c-116">У одељку **Администраторски налог на серверу**, изаберите **Пријавите се** и изаберите Dynamics 365 Sales налог.</span><span class="sxs-lookup"><span data-stu-id="9233c-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="9233c-117">Мапирајте поље корисничког ID-а са Dynamics 365 ID-ом контакта.</span><span class="sxs-lookup"><span data-stu-id="9233c-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="9233c-118">Изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="9233c-118">Select **Next**.</span></span>

1. <span data-ttu-id="9233c-119">Изаберите један или више сегмената.</span><span class="sxs-lookup"><span data-stu-id="9233c-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="9233c-120">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="9233c-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="9233c-121">Извоз података</span><span class="sxs-lookup"><span data-stu-id="9233c-121">Export the data</span></span>

<span data-ttu-id="9233c-122">Можете да [извезете податке на захтев](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="9233c-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="9233c-123">Извоз ће се такође покренути са сваким [планираним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9233c-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]