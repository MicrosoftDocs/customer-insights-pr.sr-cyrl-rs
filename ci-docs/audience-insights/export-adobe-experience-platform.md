---
title: Извоз Customer Insights података у Adobe платформу искуства
description: Сазнајте како се користе сегменти увида о корисницима у Adobe платформи искуства.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 884f4d30f354bed29909d57be84dce4c8e46965a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760119"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="be8cf-103">Коришћење Customer Insights сегмената у Adobe платформи искуства (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="be8cf-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="be8cf-104">Као корисник увида о корисницима за Dynamics 365 Customer Insights, можда сте креирали сегменте да бисте маркетиншке кампање учинили ефикаснијим тако што ћете циљати релевантне циљне групе.</span><span class="sxs-lookup"><span data-stu-id="be8cf-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="be8cf-105">Да бисте користили сегмент из увида о корисницима у Adobe платформи искуства и апликацијама попут Adobe Campaign Standard, потребно је да следите неколико корака наведених у овом чланку.</span><span class="sxs-lookup"><span data-stu-id="be8cf-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Дијаграм процеса корака описаних у овом чланку.":::

## <a name="prerequisites"></a><span data-ttu-id="be8cf-107">Предуслови</span><span class="sxs-lookup"><span data-stu-id="be8cf-107">Prerequisites</span></span>

-   <span data-ttu-id="be8cf-108">Dynamics 365 Customer Insights лиценца</span><span class="sxs-lookup"><span data-stu-id="be8cf-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="be8cf-109">Лиценца за Adobe платформу искуства</span><span class="sxs-lookup"><span data-stu-id="be8cf-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="be8cf-110">Лиценца за Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="be8cf-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="be8cf-111">Налог Azure складишта блоб објекта</span><span class="sxs-lookup"><span data-stu-id="be8cf-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="be8cf-112">Преглед кампање</span><span class="sxs-lookup"><span data-stu-id="be8cf-112">Campaign Overview</span></span>

<span data-ttu-id="be8cf-113">Да бисте боље разумели како можете да користите сегменте из увида о корисницима у Adobe платформи искуства, погледајмо фиктивни пример кампање.</span><span class="sxs-lookup"><span data-stu-id="be8cf-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="be8cf-114">Претпоставимо да ваше предузеће нуди месечну услугу засновану на претплати за клијенте у Сједињеним Државама.</span><span class="sxs-lookup"><span data-stu-id="be8cf-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="be8cf-115">Желите да идентификујете клијенте који треба да обнове претплате у наредних осам дана, али још увек нису обновили претплату.</span><span class="sxs-lookup"><span data-stu-id="be8cf-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="be8cf-116">Да бисте задржали ове клијенте, треба да им пошаљете промотивну понуду путем е-поште, користећи Adobe платформу искуства.</span><span class="sxs-lookup"><span data-stu-id="be8cf-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="be8cf-117">У овом примеру желимо да једном покренемо промотивну кампању е-поште.</span><span class="sxs-lookup"><span data-stu-id="be8cf-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="be8cf-118">Овај чланак не покрива случај коришћења са више покретања кампање.</span><span class="sxs-lookup"><span data-stu-id="be8cf-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="be8cf-119">Идентификујте своју циљну групу</span><span class="sxs-lookup"><span data-stu-id="be8cf-119">Identify your target audience</span></span>

<span data-ttu-id="be8cf-120">У нашем сценариј,у претпостављамо да су адресе е-поште клијената доступне у увидима о корисницима и да су анализиране њихове промотивне жељене опције како би се идентификовали чланови сегмента.</span><span class="sxs-lookup"><span data-stu-id="be8cf-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="be8cf-121">[Сегмент који сте дефинисали увидом о корисницима](segments.md) се зове **ChurnProneCustomers** и планирате да овим клијентима пошаљете е-поруку са промоцијом.</span><span class="sxs-lookup"><span data-stu-id="be8cf-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Снимак екрана странице сегмената са креираним сегментом ChurnProneCustomers.":::

<span data-ttu-id="be8cf-123">Е-порука са понудом коју желите да пошаљете садржи име, презиме и датум завршетка претплате клијента.</span><span class="sxs-lookup"><span data-stu-id="be8cf-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="be8cf-124">Порука обавештава клијенте о попусту који ће добити ако обнове претплату пре него што се заврши.</span><span class="sxs-lookup"><span data-stu-id="be8cf-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="be8cf-125">Извезите своју циљну групу</span><span class="sxs-lookup"><span data-stu-id="be8cf-125">Export your target audience</span></span>

<span data-ttu-id="be8cf-126">Када је идентификована циљна група, можемо да конфигуришемо извоз из увида о корисницима на налог Azure складишта блоб објекта.</span><span class="sxs-lookup"><span data-stu-id="be8cf-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="be8cf-127">Конфигурисање везе</span><span class="sxs-lookup"><span data-stu-id="be8cf-127">Configure a connection</span></span>

1. <span data-ttu-id="be8cf-128">Идите на **Администратор** > **Везе**.</span><span class="sxs-lookup"><span data-stu-id="be8cf-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="be8cf-129">Изаберите **Додај везу** и одаберите **Azure складиште блоб објекта** или изаберите **Подеси** на плочици **Azure складиште блоб објекта**:</span><span class="sxs-lookup"><span data-stu-id="be8cf-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile:</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Плочица за конфигурацију за Azure складиште блоб објекта."::: <span data-ttu-id="be8cf-131">да бисте конфигурисали везу.</span><span class="sxs-lookup"><span data-stu-id="be8cf-131">to configure the connection.</span></span>

1. <span data-ttu-id="be8cf-132">Дајте вези препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="be8cf-132">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="be8cf-133">Име за приказ и врста везе описују ову везу.</span><span class="sxs-lookup"><span data-stu-id="be8cf-133">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="be8cf-134">Препоручујемо да одаберете назив који објашњава сврху и циљ везе.</span><span class="sxs-lookup"><span data-stu-id="be8cf-134">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="be8cf-135">Одаберите ко може да користи ову везу.</span><span class="sxs-lookup"><span data-stu-id="be8cf-135">Choose who can use this connection.</span></span> <span data-ttu-id="be8cf-136">Ако ништа не предузмете, подразумевани ће бити Администратори.</span><span class="sxs-lookup"><span data-stu-id="be8cf-136">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="be8cf-137">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="be8cf-137">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="be8cf-138">Унесите **Назив налога**, **Кључ налога** и **Контејнер** за ваш налог за складиште блоб објекта у који желите да извезете сегмент.</span><span class="sxs-lookup"><span data-stu-id="be8cf-138">Enter **Account name**, **Account key**, and **Container** for your Blob storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Снимак екрана конфигурације налога складишта. "::: 
   
    - <span data-ttu-id="be8cf-140">Да бисте сазнали више о томе како да пронађете назив налога складишта блоб објекта и кључ налога, погледајте [Управљање подешавањима налога за складиштење на Azure порталу](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="be8cf-140">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="be8cf-141">Да бисте сазнали како да креирате контејнер, погледајте чланак [Креирање контејнера](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="be8cf-141">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="be8cf-142">Изаберите **Сачувај** да бисте креирали везу.</span><span class="sxs-lookup"><span data-stu-id="be8cf-142">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="be8cf-143">Конфигурисање извоза</span><span class="sxs-lookup"><span data-stu-id="be8cf-143">Configure an export</span></span>

<span data-ttu-id="be8cf-144">Овај извоз можете да конфигуришете ако имате приступ вези ове врсте.</span><span class="sxs-lookup"><span data-stu-id="be8cf-144">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="be8cf-145">За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="be8cf-145">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="be8cf-146">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="be8cf-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="be8cf-147">Да бисте креирали нови извоз, изаберите **Додај извоз**.</span><span class="sxs-lookup"><span data-stu-id="be8cf-147">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="be8cf-148">У пољу **Веза за извоз**, одаберите везу из одељка Azure складишта блоб објекта.</span><span class="sxs-lookup"><span data-stu-id="be8cf-148">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="be8cf-149">Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.</span><span class="sxs-lookup"><span data-stu-id="be8cf-149">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="be8cf-150">Одаберите сегмент које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="be8cf-150">Choose the segment that you want to export.</span></span> <span data-ttu-id="be8cf-151">У овом примеру, то је **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="be8cf-151">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Снимак екрана корисничког интерфејса за одабир сегмента са изабраним сегментом ChurnProneCustomers.":::

1. <span data-ttu-id="be8cf-153">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="be8cf-153">Select **Save**.</span></span>

<span data-ttu-id="be8cf-154">Када сачувате одредиште за извоз, пронаћи ћете га у дијалогу **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="be8cf-154">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="be8cf-155">Сада можете да [извозите сегмент на захтев](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="be8cf-155">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="be8cf-156">Извоз ће се такође покренути са сваким [планираним освежавањем](system.md).</span><span class="sxs-lookup"><span data-stu-id="be8cf-156">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="be8cf-157">Уверите се да је број записа у извезеном сегменту унутар дозвољеног ограничења ваше Adobe Campaign Standard лиценце.</span><span class="sxs-lookup"><span data-stu-id="be8cf-157">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="be8cf-158">Извезени подаци се чувају у контејнеру Azure складишта блоб објекта који сте раније конфигурисали.</span><span class="sxs-lookup"><span data-stu-id="be8cf-158">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="be8cf-159">Следећа путања до фасцикле се аутоматски креира у вашем контејнеру:</span><span class="sxs-lookup"><span data-stu-id="be8cf-159">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="be8cf-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="be8cf-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="be8cf-161">Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="be8cf-161">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="be8cf-162">Датотека *model.json* за извезене ентитете налази се на нивоу *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="be8cf-162">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="be8cf-163">Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="be8cf-163">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="be8cf-164">Дефинишите модел података о искуству (XDM) на Adobe платформи искуства</span><span class="sxs-lookup"><span data-stu-id="be8cf-164">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="be8cf-165">Пре него што будемо могли да користимо извезене податке из увида о корисницима на Adobe платформи искуства, морамо да дефинишемо шему модела података искуства и [конфигуришемо податке за профил клијента у реалном времену](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="be8cf-165">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="be8cf-166">Сазнајте [шта је то XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) и разјасните [основе састављања шеме](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="be8cf-166">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="be8cf-167">Увезите податке у Adobe платформу искуства</span><span class="sxs-lookup"><span data-stu-id="be8cf-167">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="be8cf-168">Сада када је све на свом месту, треба да увеземо податке о циљној групи из увида о корисницима у Adobe платформи искуства.</span><span class="sxs-lookup"><span data-stu-id="be8cf-168">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="be8cf-169">Прво [креирајте изворну везу са Azure складиштем блоб објекта](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="be8cf-169">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="be8cf-170">Када дефинишете изворну везу, [конфигуришите ток података](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) за групно повезивање са складиштем у облаку ради увоза излаза сегмента из увида о корисницима у Adobe платформу искуства.</span><span class="sxs-lookup"><span data-stu-id="be8cf-170">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="be8cf-171">Креирање корисника у услузи Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="be8cf-171">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="be8cf-172">Да бисмо послали е-поруку за ову кампању, користићемо Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="be8cf-172">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="be8cf-173">Након увоза података у Adobe платформу искуства, треба да [креирамо циљну групу](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) у услузи Adobe Campaign Standard користећи податке на Adobe платформи искуства.</span><span class="sxs-lookup"><span data-stu-id="be8cf-173">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="be8cf-174">Сазнајте како да [користите алатку за прављење сегмената](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) у услузи Adobe Campaign Standard да бисте дефинисали циљну групу на основу података у Adobe платформи искуства.</span><span class="sxs-lookup"><span data-stu-id="be8cf-174">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="be8cf-175">Креирајте и пошаљите е-поруку користећи Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="be8cf-175">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="be8cf-176">Креирајте садржај е-поруке, а затим [тестирајте и пошаљите](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) е-поруку.</span><span class="sxs-lookup"><span data-stu-id="be8cf-176">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Пример е-поруке са понудом обнове претплате из услуге Adobe Campaign Standard.":::
