---
title: Уношење података у реалном времену и ограничења
description: Опште информације о могућностима у реалном времену у увидима о корисницима.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7421ed9d2cb399d546815b2d1b0ea5ec51ca6b6d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270298"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="23259-103">Унос података у реалном времену (преглед)</span><span class="sxs-lookup"><span data-stu-id="23259-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="23259-104">Функционалност која је скоро сасвим у стварном времену омогућава вам да у року од неколико секунди видите најновије интеракције које су извршили ваши клијенти са вашим производима или услугама.</span><span class="sxs-lookup"><span data-stu-id="23259-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="23259-105">[Заказана освежавања](system.md#schedule-tab) укључују велики број записа и неколико сложених операција.</span><span class="sxs-lookup"><span data-stu-id="23259-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="23259-106">Прво се подаци узимају из извора података.</span><span class="sxs-lookup"><span data-stu-id="23259-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="23259-107">Затим се подаци обједињују, а затим обогаћују додатним информацијама.</span><span class="sxs-lookup"><span data-stu-id="23259-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="23259-108">Свако покретање овог поступка може трајати од неколико минута до неколико сати.</span><span class="sxs-lookup"><span data-stu-id="23259-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="23259-109">Функционалност у реалном времену пружа податке који се одмах могу користити, све док накнадно планирано освежавање не повуче ове податке из извора података.</span><span class="sxs-lookup"><span data-stu-id="23259-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="23259-110">Ажурирања у реалном времену имају време истека након чега више не мењају вредност из извора података:</span><span class="sxs-lookup"><span data-stu-id="23259-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="23259-111">Ажурирања профила чуваће се 4 сата</span><span class="sxs-lookup"><span data-stu-id="23259-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="23259-112">Активности ће се чувати 30 дана</span><span class="sxs-lookup"><span data-stu-id="23259-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="23259-113">Те вредности су параметри API позива које можете променити.</span><span class="sxs-lookup"><span data-stu-id="23259-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="23259-114">Они имају за циљ да осигурају да ваши изворни подаци остану ваш извор истине.</span><span class="sxs-lookup"><span data-stu-id="23259-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="23259-115">Ако желите да ажурирања у реалном времену буду дуже укључена, морате их додати у извор података како би се повукла током следећег заказаног освежавања.</span><span class="sxs-lookup"><span data-stu-id="23259-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="23259-116">Ажурирање поља обједињеног профила клијента у реалном времену</span><span class="sxs-lookup"><span data-stu-id="23259-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="23259-117">Ажурирани профили ће се приказати у приказу картице клијента или било којој другој визуелизацији у року од неколико секунди.</span><span class="sxs-lookup"><span data-stu-id="23259-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="23259-118">Пошто се операције у реалном времену одвијају након што се десило обједињавање података, оне се примењују само на обједињене профиле корисника.</span><span class="sxs-lookup"><span data-stu-id="23259-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="23259-119">Стога промене профила у реалном времену неће ажурирати мере, чланство у сегментима или обогаћивања.</span><span class="sxs-lookup"><span data-stu-id="23259-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="23259-120">Ограничења</span><span class="sxs-lookup"><span data-stu-id="23259-120">Limitations</span></span>

- <span data-ttu-id="23259-121">Профили корисника се могу ажурирати, али не и креирати или брисати.</span><span class="sxs-lookup"><span data-stu-id="23259-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="23259-122">Извоз ажурирања у реалном времену у спољне системе, као што је Power BI, тренутно није могуће.</span><span class="sxs-lookup"><span data-stu-id="23259-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="23259-123">Креирање активности у реалном времену</span><span class="sxs-lookup"><span data-stu-id="23259-123">Real-time creation of activities</span></span>

<span data-ttu-id="23259-124">API у реалном времену омогућава вам објављивање нове активности из вашег изворног система (појединачни изворни запис) на обједињеном профилу клијента.</span><span class="sxs-lookup"><span data-stu-id="23259-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="23259-125">Нова активност ће бити доступна као обједињена активност на временској оси тог обједињеног клијента у року од неколико секунди.</span><span class="sxs-lookup"><span data-stu-id="23259-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="23259-126">Временску линију можете видети у приказу картице клијента или било којој другој интеграцији временске линије коју сте конфигурисали.</span><span class="sxs-lookup"><span data-stu-id="23259-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="23259-127">Активности су непроменљиве.</span><span class="sxs-lookup"><span data-stu-id="23259-127">Activities are immutable.</span></span> <span data-ttu-id="23259-128">Не мењају се једном када их креирате.</span><span class="sxs-lookup"><span data-stu-id="23259-128">They don't change once created.</span></span>
> - <span data-ttu-id="23259-129">Тренутно се сегменти и мере неће ажурирати на основу нове активности.</span><span class="sxs-lookup"><span data-stu-id="23259-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="23259-130">Активности додате само путем API-ја у реалном времену нису део извоза и неће се приказати у услузи PowerBI.</span><span class="sxs-lookup"><span data-stu-id="23259-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="23259-131">Постоје два начина за повезивање са API-јем у реалном времену:</span><span class="sxs-lookup"><span data-stu-id="23259-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="23259-132">[индиректно](#connect-via-the-dynamics-365-customer-insights-connector), помоћу [Dynamics 365 Customer Insights конектора](https://docs.microsoft.com/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="23259-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/)</span></span>
- <span data-ttu-id="23259-133">[директно](#connect-directly-to-the-real-time-api), са кодом</span><span class="sxs-lookup"><span data-stu-id="23259-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="23259-134">Оба начина деле следеће предуслове:</span><span class="sxs-lookup"><span data-stu-id="23259-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="23259-135">Customer Insights окружење</span><span class="sxs-lookup"><span data-stu-id="23259-135">A Customer Insights environment</span></span>
- <span data-ttu-id="23259-136">Обједињени профил клијента</span><span class="sxs-lookup"><span data-stu-id="23259-136">Unified customer profiles</span></span>
- <span data-ttu-id="23259-137">Активности се конфигуришу и покрећу</span><span class="sxs-lookup"><span data-stu-id="23259-137">Activities configured and run</span></span>
- <span data-ttu-id="23259-138">Дозволе сарадника или администратора за потврду идентитета налога</span><span class="sxs-lookup"><span data-stu-id="23259-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="23259-139">Повежите се путем Dynamics 365 Customer Insights конектора</span><span class="sxs-lookup"><span data-stu-id="23259-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="23259-140">API у реалном времену може да уноси податке са наменског Power Platform конектора, по имену [Dynamics 365 Customer Insights конектор](https://docs.microsoft.com/connectors/customerinsights/), без потребе за писањем и применом било каквог кода.</span><span class="sxs-lookup"><span data-stu-id="23259-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="23259-141">Конектор може да обавља исте радње у реалном времену као и API.</span><span class="sxs-lookup"><span data-stu-id="23259-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="23259-142">Потребна вам је важећа лиценца за премијум конекторе.</span><span class="sxs-lookup"><span data-stu-id="23259-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="23259-143">За више информација, погледајте чланак [Најчешћа питања о Power Apps и Power Automate лиценцирању](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="23259-143">For more information, see [Power Apps and Power Automate licensing FAQs](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="23259-144">Power Platform [Power Apps и/или Power Automate](https://docs.microsoft.com/connectors/)</span><span class="sxs-lookup"><span data-stu-id="23259-144">Power Platform [Power Apps and/or Power Automate](https://docs.microsoft.com/connectors/)</span></span>
- <span data-ttu-id="23259-145">Azure [логичке апликације](https://docs.microsoft.com/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="23259-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span></span>

<span data-ttu-id="23259-146">За детаље о креирању токова, погледајте [Power Automate документацију](https://docs.microsoft.com/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="23259-146">For details about creating flows, see the [Power Automate documentation](https://docs.microsoft.com/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="23259-147">Повежите се директно са API-јем у реалном времену</span><span class="sxs-lookup"><span data-stu-id="23259-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="23259-148">Могућности у реалном времену можете да користите изградњом сопственог канала и директним повезивањем са API-јем у реалном времену.</span><span class="sxs-lookup"><span data-stu-id="23259-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="23259-149">Активност можете објавити у формату вашег изворног система или у формату UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="23259-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="23259-150">Преузмите формат упућивањем API позива у /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="23259-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="23259-151">Детаљи овог API-ја, укључујући параметре и одговоре, могу се наћи у одељку **Подаци о ентитетима** у [Референци Customer Insights API-ја](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="23259-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="23259-152">За више информација погледајте [Радите са Customer Insights API-јима](apis.md).</span><span class="sxs-lookup"><span data-stu-id="23259-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="23259-153">Објашњење употребе у реалном времену помоћу телеметрије</span><span class="sxs-lookup"><span data-stu-id="23259-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="23259-154">Добијте преглед обима захтева за API у реалном времену и информације о проблемима са којима се систем може сусрести.</span><span class="sxs-lookup"><span data-stu-id="23259-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="23259-155">Можете [приступати телеметрији у реалном времену](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="23259-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]