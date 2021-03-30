---
title: Извезите Customer Insights податке у Adobe Campaign Standard
description: Сазнајте како се користе сегменти увида у кориснике у услузи Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596333"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="915d1-103">Коришћење Customer Insights сегмената у услузи Adobe Campaign Standard (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="915d1-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="915d1-104">Као корисник увида о корисницима за Dynamics 365 Customer Insights, можда сте креирали сегменте да бисте маркетиншке кампање учинили ефикаснијим тако што ћете циљати релевантне циљне групе.</span><span class="sxs-lookup"><span data-stu-id="915d1-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="915d1-105">Да бисте користили сегмент из увида о корисницима у Adobe платформи искуства и апликацијама попут Adobe Campaign Standard, потребно је да следите неколико корака наведених у овом чланку.</span><span class="sxs-lookup"><span data-stu-id="915d1-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Дијаграм процеса корака описаних у овом чланку.":::

## <a name="prerequisites"></a><span data-ttu-id="915d1-107">Предуслови</span><span class="sxs-lookup"><span data-stu-id="915d1-107">Prerequisites</span></span>

-   <span data-ttu-id="915d1-108">Dynamics 365 Customer Insights лиценца</span><span class="sxs-lookup"><span data-stu-id="915d1-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="915d1-109">Лиценца за Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="915d1-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="915d1-110">Налог Azure складишта блоб објекта</span><span class="sxs-lookup"><span data-stu-id="915d1-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="915d1-111">Преглед кампање</span><span class="sxs-lookup"><span data-stu-id="915d1-111">Campaign Overview</span></span>

<span data-ttu-id="915d1-112">Да бисте боље разумели како можете да користите сегменте из увида о корисницима у Adobe платформи искуства, погледајмо фиктивни пример кампање.</span><span class="sxs-lookup"><span data-stu-id="915d1-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="915d1-113">Претпоставимо да ваше предузеће нуди месечну услугу засновану на претплати за клијенте у Сједињеним Државама.</span><span class="sxs-lookup"><span data-stu-id="915d1-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="915d1-114">Желите да идентификујете клијенте који треба да обнове претплате у наредних осам дана, али још увек нису обновили претплату.</span><span class="sxs-lookup"><span data-stu-id="915d1-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="915d1-115">Да бисте задржали ове клијенте, треба да им пошаљете промотивну понуду путем е-поште, користећи Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="915d1-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="915d1-116">У овом примеру желимо да једном покренемо промотивну кампању е-поште.</span><span class="sxs-lookup"><span data-stu-id="915d1-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="915d1-117">Овај чланак не покрива случај коришћења са више покретања кампање.</span><span class="sxs-lookup"><span data-stu-id="915d1-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="915d1-118">Међутим, увиди у кориснике и Adobe Campaign Standard могу се конфигурисати да раде и за понављајући сценарио кампање.</span><span class="sxs-lookup"><span data-stu-id="915d1-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="915d1-119">Идентификујте своју циљну групу</span><span class="sxs-lookup"><span data-stu-id="915d1-119">Identify your target audience</span></span>

<span data-ttu-id="915d1-120">У нашем сценариј,у претпостављамо да су адресе е-поште клијената доступне у увидима о корисницима и да су анализиране њихове промотивне жељене опције како би се идентификовали чланови сегмента.</span><span class="sxs-lookup"><span data-stu-id="915d1-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="915d1-121">[Сегмент који сте дефинисали увидом о корисницима](segments.md) се зове **ChurnProneCustomers** и планирате да овим клијентима пошаљете е-поруку са промоцијом.</span><span class="sxs-lookup"><span data-stu-id="915d1-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Снимак екрана странице сегмената са креираним сегментом ChurnProneCustomers.":::

<span data-ttu-id="915d1-123">Е-порука са понудом коју желите да пошаљете садржи име, презиме и датум завршетка претплате клијента.</span><span class="sxs-lookup"><span data-stu-id="915d1-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="915d1-124">Порука обавештава клијенте о попусту који ће добити ако обнове претплату пре него што се заврши.</span><span class="sxs-lookup"><span data-stu-id="915d1-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="915d1-125">Извезите своју циљну групу</span><span class="sxs-lookup"><span data-stu-id="915d1-125">Export your target audience</span></span>

<span data-ttu-id="915d1-126">Када је идентификована циљна група, можемо да конфигуришемо извоз из увида о корисницима на налог Azure складишта блоб објекта.</span><span class="sxs-lookup"><span data-stu-id="915d1-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="915d1-127">У увидима о корисницима идите на **Администратор** > **Одредишта за извоз**.</span><span class="sxs-lookup"><span data-stu-id="915d1-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="915d1-128">На плочици **Adobe Campaign** изаберите **Подеси**.</span><span class="sxs-lookup"><span data-stu-id="915d1-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Плочица за конфигурацију за Adobe Campaign Standard.":::

1. <span data-ttu-id="915d1-130">Наведите **име за приказ** за ово ново одредиште за извоз, а затим унесите **Назив налога**, **Кључ налога** и **Контејнер** налога Azure складишта блоб објекта у који желите да извезете сегмент.</span><span class="sxs-lookup"><span data-stu-id="915d1-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Снимак екрана конфигурације налога складишта. "::: 

   - <span data-ttu-id="915d1-132">Да бисте сазнали више о проналажењу имена и кључа налога за Azure складиште блоб објекта, погледајте [Управљајте подешавањима налога за складиштење на Azure порталу](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="915d1-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="915d1-133">Да бисте сазнали како да креирате контејнер, погледајте чланак [Креирање контејнера](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="915d1-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="915d1-134">Изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="915d1-134">Select **Next**.</span></span>

1. <span data-ttu-id="915d1-135">Одаберите сегмент које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="915d1-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="915d1-136">У овом примеру, то је **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="915d1-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Снимак екрана корисничког интерфејса за одабир сегмента са изабраним сегментом ChurnProneCustomers.":::

1. <span data-ttu-id="915d1-138">Изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="915d1-138">Select **Next**.</span></span>

1. <span data-ttu-id="915d1-139">Сада мапирамо поља **Извор** од сегмента увида у кориснике до имена поља **Циљ** у шеми Adobe Campaign Standard профила.</span><span class="sxs-lookup"><span data-stu-id="915d1-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Мапирање поља за Adobe Campaign Standard конектор.":::

   <span data-ttu-id="915d1-141">Ако желите да додате још атрибута, изаберите **Додај атрибут**.</span><span class="sxs-lookup"><span data-stu-id="915d1-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="915d1-142">Назив циља може се разликовати од имена изворног поља, тако да и даље можете мапирати излаз сегмента из увида у кориснике у услугу Adobe Campaign Standard ако поља немају исти назив у два система.</span><span class="sxs-lookup"><span data-stu-id="915d1-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="915d1-143">Адреса е-поште се користи као поље идентитета, али можете користити било који други идентификатор из вашег корисничког профила за увиде у кориснике да бисте мапирали податке у Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="915d1-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="915d1-144">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="915d1-144">Select **Save**.</span></span>

<span data-ttu-id="915d1-145">Када сачувате одредиште за извоз, пронаћи ћете га на листи **Администратор** > **Извози** > **Моја одредишта за извоз**.</span><span class="sxs-lookup"><span data-stu-id="915d1-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Снимак екрана са истакнутом листом извоза и узорком сегмента.":::

<span data-ttu-id="915d1-147">Сада можете да [извозите сегмент на захтев](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="915d1-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="915d1-148">Извоз ће се такође покренути са сваким [планираним освежавањем](system.md).</span><span class="sxs-lookup"><span data-stu-id="915d1-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="915d1-149">Уверите се да је број записа у извезеном сегменту унутар дозвољеног ограничења ваше Adobe Campaign Standard лиценце.</span><span class="sxs-lookup"><span data-stu-id="915d1-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="915d1-150">Извезени подаци се чувају у контејнеру Azure складишта блоб објекта који сте раније конфигурисали.</span><span class="sxs-lookup"><span data-stu-id="915d1-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="915d1-151">Следећа путања до фасцикле се аутоматски креира у вашем контејнеру:</span><span class="sxs-lookup"><span data-stu-id="915d1-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="915d1-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="915d1-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="915d1-153">Пример: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="915d1-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="915d1-154">Конфигурисање услуге Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="915d1-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="915d1-155">Када се извезе сегмент из увида у кориснике, он садржи колоне које сте изабрали приликом дефинисања одредишта извоза у претходном кораку.</span><span class="sxs-lookup"><span data-stu-id="915d1-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="915d1-156">Ови подаци се могу користити за [креирање профила у услузи Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="915d1-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="915d1-157">Да бисмо користили сегмент у услузи Adobe Campaign Standard, треба да проширимо шему профила у услузи Adobe Campaign Standard тако да укључује два додатна поља.</span><span class="sxs-lookup"><span data-stu-id="915d1-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="915d1-158">Сазнајте како да [продужите ресурс профила](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) са новим пољима у услузи Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="915d1-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="915d1-159">У нашем примеру, ова поља су *Назив сегмента и Датум сегмента (опционално).*</span><span class="sxs-lookup"><span data-stu-id="915d1-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="915d1-160">Ова поља ћемо користити за идентификацију профила у програму Adobe Campaign Standard које желимо да циљамо за ову кампању.</span><span class="sxs-lookup"><span data-stu-id="915d1-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="915d1-161">Ако у програму Adobe Campaign Standard не постоје други записи осим оних које ћете увозити, можете прескочити овај корак.</span><span class="sxs-lookup"><span data-stu-id="915d1-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="915d1-162">Увоз података у Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="915d1-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="915d1-163">Сада када је све на свом месту, морамо припремити податке о корисницима из увида у кориснике у услузи Adobe Campaign Standard да бисмо креирали профиле.</span><span class="sxs-lookup"><span data-stu-id="915d1-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="915d1-164">Сазнајте [како да увезете профиле у Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) користећи ток посла.</span><span class="sxs-lookup"><span data-stu-id="915d1-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="915d1-165">Ток посла увоза на доњој слици конфигурисан је за покретање сваких 8 сати и тражи извезене сегменте увида у кориснике (.csv датотека у Azure складишту блоб објекта).</span><span class="sxs-lookup"><span data-stu-id="915d1-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="915d1-166">Ток посла издваја садржај .csv датотеке у наведеном редоследу колона.</span><span class="sxs-lookup"><span data-stu-id="915d1-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="915d1-167">Овај ток посла направљен је да обави основно руковање грешкама и осигура да сваки запис има адресу е-поште пре попуне подацима у услузи Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="915d1-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="915d1-168">Ток посла такође издваја име сегмента из имена датотеке пре додавања у податке ACS профила.</span><span class="sxs-lookup"><span data-stu-id="915d1-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Снимак екрана тока посла увоза у корисничком интерфејсу услуге Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="915d1-170">Преузимање корисника у услузи Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="915d1-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="915d1-171">Када се подаци увезу у Adobe Campaign Standard, ви [можете да креирате ток посла](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) и [упит](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) да би клијенти засновани на *Називу сегмента* и *Датуму сегмента* изабрали профиле који су идентификовани за наш пример кампање.</span><span class="sxs-lookup"><span data-stu-id="915d1-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="915d1-172">Креирајте и пошаљите е-поруку користећи Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="915d1-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="915d1-173">Креирајте садржај е-поруке, а затим [тестирајте и пошаљите](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) е-поруку.</span><span class="sxs-lookup"><span data-stu-id="915d1-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Пример е-поруке са понудом обнове претплате из услуге Adobe Campaign Standard.":::