---
title: Извоз Customer Insights података у Adobe платформу искуства
description: Сазнајте како се користе сегменти увида о корисницима у Adobe платформи искуства.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596287"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="818f6-103">Коришћење Customer Insights сегмената у Adobe платформи искуства (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="818f6-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="818f6-104">Као корисник увида о корисницима за Dynamics 365 Customer Insights, можда сте креирали сегменте да бисте маркетиншке кампање учинили ефикаснијим тако што ћете циљати релевантне циљне групе.</span><span class="sxs-lookup"><span data-stu-id="818f6-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="818f6-105">Да бисте користили сегмент из увида о корисницима у Adobe платформи искуства и апликацијама попут Adobe Campaign Standard, потребно је да следите неколико корака наведених у овом чланку.</span><span class="sxs-lookup"><span data-stu-id="818f6-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Дијаграм процеса корака описаних у овом чланку.":::

## <a name="prerequisites"></a><span data-ttu-id="818f6-107">Предуслови</span><span class="sxs-lookup"><span data-stu-id="818f6-107">Prerequisites</span></span>

-   <span data-ttu-id="818f6-108">Dynamics 365 Customer Insights лиценца</span><span class="sxs-lookup"><span data-stu-id="818f6-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="818f6-109">Лиценца за Adobe платформу искуства</span><span class="sxs-lookup"><span data-stu-id="818f6-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="818f6-110">Лиценца за Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="818f6-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="818f6-111">Налог Azure складишта блоб објекта</span><span class="sxs-lookup"><span data-stu-id="818f6-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="818f6-112">Преглед кампање</span><span class="sxs-lookup"><span data-stu-id="818f6-112">Campaign Overview</span></span>

<span data-ttu-id="818f6-113">Да бисте боље разумели како можете да користите сегменте из увида о корисницима у Adobe платформи искуства, погледајмо фиктивни пример кампање.</span><span class="sxs-lookup"><span data-stu-id="818f6-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="818f6-114">Претпоставимо да ваше предузеће нуди месечну услугу засновану на претплати за клијенте у Сједињеним Државама.</span><span class="sxs-lookup"><span data-stu-id="818f6-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="818f6-115">Желите да идентификујете клијенте који треба да обнове претплате у наредних осам дана, али још увек нису обновили претплату.</span><span class="sxs-lookup"><span data-stu-id="818f6-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="818f6-116">Да бисте задржали ове клијенте, треба да им пошаљете промотивну понуду путем е-поште, користећи Adobe платформу искуства.</span><span class="sxs-lookup"><span data-stu-id="818f6-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="818f6-117">У овом примеру желимо да једном покренемо промотивну кампању е-поште.</span><span class="sxs-lookup"><span data-stu-id="818f6-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="818f6-118">Овај чланак не покрива случај коришћења са више покретања кампање.</span><span class="sxs-lookup"><span data-stu-id="818f6-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="818f6-119">Идентификујте своју циљну групу</span><span class="sxs-lookup"><span data-stu-id="818f6-119">Identify your target audience</span></span>

<span data-ttu-id="818f6-120">У нашем сценариј,у претпостављамо да су адресе е-поште клијената доступне у увидима о корисницима и да су анализиране њихове промотивне жељене опције како би се идентификовали чланови сегмента.</span><span class="sxs-lookup"><span data-stu-id="818f6-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="818f6-121">[Сегмент који сте дефинисали увидом о корисницима](segments.md) се зове **ChurnProneCustomers** и планирате да овим клијентима пошаљете е-поруку са промоцијом.</span><span class="sxs-lookup"><span data-stu-id="818f6-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Снимак екрана странице сегмената са креираним сегментом ChurnProneCustomers.":::

<span data-ttu-id="818f6-123">Е-порука са понудом коју желите да пошаљете садржи име, презиме и датум завршетка претплате клијента.</span><span class="sxs-lookup"><span data-stu-id="818f6-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="818f6-124">Порука обавештава клијенте о попусту који ће добити ако обнове претплату пре него што се заврши.</span><span class="sxs-lookup"><span data-stu-id="818f6-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="818f6-125">Извезите своју циљну групу</span><span class="sxs-lookup"><span data-stu-id="818f6-125">Export your target audience</span></span>

<span data-ttu-id="818f6-126">Када је идентификована циљна група, можемо да конфигуришемо извоз из увида о корисницима на налог Azure складишта блоб објекта.</span><span class="sxs-lookup"><span data-stu-id="818f6-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="818f6-127">У увидима о корисницима идите на **Администратор** > **Одредишта за извоз**.</span><span class="sxs-lookup"><span data-stu-id="818f6-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="818f6-128">На плочици **Azure складиште блоб објекта** изаберите **Подеси**.</span><span class="sxs-lookup"><span data-stu-id="818f6-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Плочица за конфигурацију за Azure складиште блоб објекта.":::

1. <span data-ttu-id="818f6-130">Наведите **име за приказ** за ово ново одредиште за извоз, а затим унесите **Назив налога**, **Кључ налога** и **Контејнер** налога Azure складишта блоб објекта у који желите да извезете сегмент.</span><span class="sxs-lookup"><span data-stu-id="818f6-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Снимак екрана конфигурације налога складишта. "::: 

   - <span data-ttu-id="818f6-132">Да бисте сазнали више о проналажењу имена и кључа налога за Azure складиште блоб објекта, погледајте [Управљајте подешавањима налога за складиштење на Azure порталу](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="818f6-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="818f6-133">Да бисте сазнали како да креирате контејнер, погледајте чланак [Креирање контејнера](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="818f6-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="818f6-134">Изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="818f6-134">Select **Next**.</span></span>

1. <span data-ttu-id="818f6-135">Одаберите сегмент које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="818f6-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="818f6-136">У овом примеру, то је **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="818f6-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Снимак екрана корисничког интерфејса за одабир сегмента са изабраним сегментом ChurnProneCustomers.":::

1. <span data-ttu-id="818f6-138">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="818f6-138">Select **Save**.</span></span>

<span data-ttu-id="818f6-139">Када сачувате одредиште за извоз, пронаћи ћете га на листи **Администратор** > **Извози** > **Моја одредишта за извоз**.</span><span class="sxs-lookup"><span data-stu-id="818f6-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Снимак екрана са истакнутом листом извоза и узорком сегмента.":::

<span data-ttu-id="818f6-141">Сада можете да [извозите сегмент на захтев](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="818f6-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="818f6-142">Извоз ће се такође покренути са сваким [планираним освежавањем](system.md).</span><span class="sxs-lookup"><span data-stu-id="818f6-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="818f6-143">Уверите се да је број записа у извезеном сегменту унутар дозвољеног ограничења ваше Adobe Campaign Standard лиценце.</span><span class="sxs-lookup"><span data-stu-id="818f6-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="818f6-144">Извезени подаци се чувају у контејнеру Azure складишта блоб објекта који сте раније конфигурисали.</span><span class="sxs-lookup"><span data-stu-id="818f6-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="818f6-145">Следећа путања до фасцикле се аутоматски креира у вашем контејнеру:</span><span class="sxs-lookup"><span data-stu-id="818f6-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="818f6-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="818f6-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="818f6-147">Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="818f6-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="818f6-148">Датотека *model.json* за извезене ентитете налази се на нивоу *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="818f6-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="818f6-149">Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="818f6-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="818f6-150">Дефинишите модел података о искуству (XDM) на Adobe платформи искуства</span><span class="sxs-lookup"><span data-stu-id="818f6-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="818f6-151">Пре него што будемо могли да користимо извезене податке из увида о корисницима на Adobe платформи искуства, морамо да дефинишемо шему модела података искуства и [конфигуришемо податке за профил клијента у реалном времену](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="818f6-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="818f6-152">Сазнајте [шта је то XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) и разјасните [основе састављања шеме](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="818f6-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="818f6-153">Увезите податке у Adobe платформу искуства</span><span class="sxs-lookup"><span data-stu-id="818f6-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="818f6-154">Сада када је све на свом месту, треба да увеземо податке о циљној групи из увида о корисницима у Adobe платформи искуства.</span><span class="sxs-lookup"><span data-stu-id="818f6-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="818f6-155">Прво [креирајте изворну везу са Azure складиштем блоб објекта](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="818f6-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="818f6-156">Када дефинишете изворну везу, [конфигуришите ток података](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) за групно повезивање са складиштем у облаку ради увоза излаза сегмента из увида о корисницима у Adobe платформу искуства.</span><span class="sxs-lookup"><span data-stu-id="818f6-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="818f6-157">Креирање корисника у услузи Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="818f6-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="818f6-158">Да бисмо послали е-поруку за ову кампању, користићемо Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="818f6-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="818f6-159">Након увоза података у Adobe платформу искуства, треба да [креирамо циљну групу](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) у услузи Adobe Campaign Standard користећи податке на Adobe платформи искуства.</span><span class="sxs-lookup"><span data-stu-id="818f6-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="818f6-160">Сазнајте како да [користите алатку за прављење сегмената](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) у услузи Adobe Campaign Standard да бисте дефинисали циљну групу на основу података у Adobe платформи искуства.</span><span class="sxs-lookup"><span data-stu-id="818f6-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="818f6-161">Креирајте и пошаљите е-поруку користећи Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="818f6-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="818f6-162">Креирајте садржај е-поруке, а затим [тестирајте и пошаљите](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) е-поруку.</span><span class="sxs-lookup"><span data-stu-id="818f6-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Пример е-поруке са понудом обнове претплате из услуге Adobe Campaign Standard.":::