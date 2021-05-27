---
title: Извезите Customer Insights податке у SFTP хостове
description: Сазнајте како да конфигуришете везу и извезете на SFTP локацију.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3663a48955f0b1db8a96e25403e5f8947bc6a220
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976957"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a><span data-ttu-id="16c0c-103">Извоз листа сегмената и осталих података у SFTP (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="16c0c-103">Export segment lists and other data to SFTP (preview)</span></span>

<span data-ttu-id="16c0c-104">Користите податке о клијентима у независним апликацијама тако што ћете их извести на локацију протокола за безбедни пренос датотека (SFTP).</span><span class="sxs-lookup"><span data-stu-id="16c0c-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="16c0c-105">Предуслови за везу</span><span class="sxs-lookup"><span data-stu-id="16c0c-105">Prerequisites for connection</span></span>

- <span data-ttu-id="16c0c-106">Доступност SFTP хоста и одговарајућих акредитива.</span><span class="sxs-lookup"><span data-stu-id="16c0c-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="16c0c-107">Позната ограничења</span><span class="sxs-lookup"><span data-stu-id="16c0c-107">Known limitations</span></span>

- <span data-ttu-id="16c0c-108">Време извожења зависи од перформанси вашег система.</span><span class="sxs-lookup"><span data-stu-id="16c0c-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="16c0c-109">Препоручујемо два језгра процесора и 1 GB меморије као минималну конфигурацију вашег сервера.</span><span class="sxs-lookup"><span data-stu-id="16c0c-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="16c0c-110">Извоз ентитета са до 100 милиона корисничких профила може потрајати 90 минута када се користи препоручена минимална конфигурација са два језгра процесора и 1 GB меморије.</span><span class="sxs-lookup"><span data-stu-id="16c0c-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="16c0c-111">Подешавање везе са SFTP</span><span class="sxs-lookup"><span data-stu-id="16c0c-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="16c0c-112">Идите на **Администратор** > **Везе**.</span><span class="sxs-lookup"><span data-stu-id="16c0c-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="16c0c-113">Изаберите **Додај везу** и бирајте **SFTP** да бисте конфигурисали везу.</span><span class="sxs-lookup"><span data-stu-id="16c0c-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="16c0c-114">Дајте вези препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="16c0c-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="16c0c-115">Име за приказ и врста везе описују ову везу.</span><span class="sxs-lookup"><span data-stu-id="16c0c-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="16c0c-116">Препоручујемо да одаберете назив који објашњава сврху и циљ везе.</span><span class="sxs-lookup"><span data-stu-id="16c0c-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="16c0c-117">Одаберите ко може да користи ову везу.</span><span class="sxs-lookup"><span data-stu-id="16c0c-117">Choose who can use this connection.</span></span> <span data-ttu-id="16c0c-118">Ако ништа не предузмете, подразумевани ће бити Администратори.</span><span class="sxs-lookup"><span data-stu-id="16c0c-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="16c0c-119">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="16c0c-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="16c0c-120">Наведите **корисничко име**, **лозинку**, **име хоста** и **фасциклу за извоз** за SFTP налог.</span><span class="sxs-lookup"><span data-stu-id="16c0c-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="16c0c-121">Изаберите **Верификуј** да тестирате везу.</span><span class="sxs-lookup"><span data-stu-id="16c0c-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="16c0c-122">Одаберите да ли желите да извезете податке **спаковано** или **распаковано** и **сепаратор поља** за извезене датотеке.</span><span class="sxs-lookup"><span data-stu-id="16c0c-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="16c0c-123">Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.</span><span class="sxs-lookup"><span data-stu-id="16c0c-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="16c0c-124">Изаберите **Сачувај** да бисте креирали везу.</span><span class="sxs-lookup"><span data-stu-id="16c0c-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="16c0c-125">Конфигурисање извоза</span><span class="sxs-lookup"><span data-stu-id="16c0c-125">Configure an export</span></span>

<span data-ttu-id="16c0c-126">Овај извоз можете да конфигуришете ако имате приступ вези ове врсте.</span><span class="sxs-lookup"><span data-stu-id="16c0c-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="16c0c-127">За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="16c0c-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="16c0c-128">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="16c0c-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="16c0c-129">Да бисте креирали нови извоз, изаберите **Додај одредиште**.</span><span class="sxs-lookup"><span data-stu-id="16c0c-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="16c0c-130">У пољу **Веза за извоз**, одаберите везу из одељка SFTP.</span><span class="sxs-lookup"><span data-stu-id="16c0c-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="16c0c-131">Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.</span><span class="sxs-lookup"><span data-stu-id="16c0c-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="16c0c-132">Изаберите ентитете, на пример сегменте које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="16c0c-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="16c0c-133">Сваки изабрани ентитет биће подељен на до пет излазних датотека приликом извоза.</span><span class="sxs-lookup"><span data-stu-id="16c0c-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="16c0c-134">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="16c0c-134">Select **Save**.</span></span>

<span data-ttu-id="16c0c-135">Чување извоза не покреће извоз одмах.</span><span class="sxs-lookup"><span data-stu-id="16c0c-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="16c0c-136">Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="16c0c-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="16c0c-137">Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="16c0c-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="16c0c-138">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="16c0c-138">Data privacy and compliance</span></span>

<span data-ttu-id="16c0c-139">Када омогућите да Dynamics 365 Customer Insights преноси податке путем SFTP-а, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="16c0c-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="16c0c-140">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да одредиште за извоз испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="16c0c-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="16c0c-141">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="16c0c-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="16c0c-142">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="16c0c-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
