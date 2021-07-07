---
title: Извезите Customer Insights података у Salesforce Marketing Cloud
description: Сазнајте како да конфигуришете везу и извезете је у Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314669"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="1ddc1-103">Извоз сегмената и других података у Salesforce Marketing Cloud (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="1ddc1-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="1ddc1-104">Користите податке о клијентима у услузи Salesforce Marketing Cloud тако што ћете их извести путем локације протокола сигурног преноса датотека (SFTP).</span><span class="sxs-lookup"><span data-stu-id="1ddc1-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="1ddc1-105">Предуслови за везу</span><span class="sxs-lookup"><span data-stu-id="1ddc1-105">Prerequisites for connection</span></span>

- <span data-ttu-id="1ddc1-106">Доступност SFTP хоста и одговарајућих администраторских акредитива.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="1ddc1-107">Како поставити SFTP локације за Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="1ddc1-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="1ddc1-108">Позната ограничења</span><span class="sxs-lookup"><span data-stu-id="1ddc1-108">Known limitations</span></span>

- <span data-ttu-id="1ddc1-109">Време извожења зависи од перформанси вашег система.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="1ddc1-110">Препоручујемо два језгра процесора и 1 GB меморије као минималну конфигурацију вашег сервера.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="1ddc1-111">Извоз ентитета са до 100 милиона корисничких профила може потрајати 90 минута када се користи препоручена минимална конфигурација.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="1ddc1-112">Подешавање везе са услугом Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="1ddc1-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="1ddc1-113">Идите на **Администратор** > **Везе**.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1ddc1-114">Изаберите **Додај везу** и изаберите **Salesforce Marketing Cloud** да бисте конфигурисали везу.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="1ddc1-115">Дајте вези препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1ddc1-116">Име за приказ и врста везе описују ову везу.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1ddc1-117">Препоручујемо да одаберете назив који објашњава сврху и циљ везе.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1ddc1-118">Одаберите ко може да користи ову везу.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-118">Choose who can use this connection.</span></span> <span data-ttu-id="1ddc1-119">Ако ништа не предузмете, подразумевани ће бити Администратори.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1ddc1-120">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1ddc1-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1ddc1-121">Наведите **корисничко име**, **лозинку**, **име хоста** и **фасциклу за извоз** за SFTP налог.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="1ddc1-122">Изаберите **Верификуј** да тестирате везу.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="1ddc1-123">Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1ddc1-124">Изаберите **Сачувај** да бисте креирали везу.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="1ddc1-125">Конфигурисање извоза</span><span class="sxs-lookup"><span data-stu-id="1ddc1-125">Configure an export</span></span>

<span data-ttu-id="1ddc1-126">Овај извоз можете да конфигуришете ако имате приступ вези ове врсте.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1ddc1-127">За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1ddc1-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1ddc1-128">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1ddc1-129">Да бисте креирали нови извоз, изаберите **Додај одредиште**.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1ddc1-130">У пољу **Веза за извоз**, одаберите везу из одељка SFTP.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="1ddc1-131">Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1ddc1-132">Одаберите да ли желите да извезете податке **спаковано** или **распаковано** и **сепаратор поља** за извезене датотеке.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="1ddc1-133">Изаберите ентитете, на пример сегменте које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1ddc1-134">Сваки изабрани ентитет биће подељен на до пет излазних датотека приликом извоза.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="1ddc1-135">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-135">Select **Save**.</span></span>

<span data-ttu-id="1ddc1-136">Чување извоза не покреће извоз одмах.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1ddc1-137">Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1ddc1-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1ddc1-138">Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1ddc1-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="1ddc1-139">Извезите Customer Insights податке у са SFTP локације Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="1ddc1-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="1ddc1-140">Креирајте [проширења података у услузи Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) за увоз Customer Insights датотеке података са SFTP локације.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="1ddc1-141">[Увезите податке са SFTP локације](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) у Salesforce Marketing Cloud проширење података.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="1ddc1-142">Подесите аутоматизацију за увоз података у проширења података.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="1ddc1-143">Сазнајте више о [аутоматизацијама отпуштања датотека и заказаним аутоматизацијама](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="1ddc1-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="1ddc1-144">Дефинишите [аутоматизацију отпуштања датотека](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) или [заказану аутоматизацију](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="1ddc1-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="1ddc1-145">Ево примера [аутоматизације са SFTP-ом](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="1ddc1-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1ddc1-146">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="1ddc1-146">Data privacy and compliance</span></span>

<span data-ttu-id="1ddc1-147">Када омогућите да Dynamics 365 Customer Insights преноси податке путем SFTP-а, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1ddc1-148">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да одредиште за извоз испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1ddc1-149">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1ddc1-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1ddc1-150">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="1ddc1-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
