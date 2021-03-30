---
title: Извезите Customer Insights податке у SFTP хостове
description: Научите како да конфигуришете везу на SFTP хостом.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598403"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="08af9-103">Конектор за SFTP (преглед)</span><span class="sxs-lookup"><span data-stu-id="08af9-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="08af9-104">Користите податке о клијентима у независним апликацијама тако што ћете их извести на Secure File Transfer Protocol (SFTP) хост.</span><span class="sxs-lookup"><span data-stu-id="08af9-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="08af9-105">Предуслови</span><span class="sxs-lookup"><span data-stu-id="08af9-105">Prerequisites</span></span>

- <span data-ttu-id="08af9-106">Доступност SFTP хоста и одговарајућих акредитива.</span><span class="sxs-lookup"><span data-stu-id="08af9-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="08af9-107">Повезивање са SFTP</span><span class="sxs-lookup"><span data-stu-id="08af9-107">Connect to SFTP</span></span>

1. <span data-ttu-id="08af9-108">Идите на **Администратор** > **Одредишта за извоз**.</span><span class="sxs-lookup"><span data-stu-id="08af9-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="08af9-109">Под **SFTP**, изаберите **Постави**.</span><span class="sxs-lookup"><span data-stu-id="08af9-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="08af9-110">Дајте одредишту препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="08af9-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="08af9-111">Наведите **корисничко име**, **лозинку**, **име хоста** и **фасциклу за извоз** за SFTP налог.</span><span class="sxs-lookup"><span data-stu-id="08af9-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="08af9-112">Изаберите **Верификуј** да тестирате везу.</span><span class="sxs-lookup"><span data-stu-id="08af9-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="08af9-113">Након успешне верификације, изаберите да ли желите да извезете податке у облику **Gzipped** или **Распаковано** и изаберите **граничник поља** за извезене датотеке.</span><span class="sxs-lookup"><span data-stu-id="08af9-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="08af9-114">Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.</span><span class="sxs-lookup"><span data-stu-id="08af9-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="08af9-115">Изаберите **Следеће** да бисте започели конфигурисање извоза.</span><span class="sxs-lookup"><span data-stu-id="08af9-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="08af9-116">Конфигурисање извоза</span><span class="sxs-lookup"><span data-stu-id="08af9-116">Configure the export</span></span>

1. <span data-ttu-id="08af9-117">Изаберите ентитете, на пример сегменте које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="08af9-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="08af9-118">Сваки изабрани ентитет ће имати до пет излазних датотека приликом извоза.</span><span class="sxs-lookup"><span data-stu-id="08af9-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="08af9-119">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="08af9-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="08af9-120">Извоз података</span><span class="sxs-lookup"><span data-stu-id="08af9-120">Export the data</span></span>

<span data-ttu-id="08af9-121">Можете да [извезете податке на захтев](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="08af9-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="08af9-122">Извоз ће се такође покренути са сваким [планираним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="08af9-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="08af9-123">Позната ограничења</span><span class="sxs-lookup"><span data-stu-id="08af9-123">Known limitations</span></span>

- <span data-ttu-id="08af9-124">Време извожења зависи од перформанси вашег система.</span><span class="sxs-lookup"><span data-stu-id="08af9-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="08af9-125">Препоручујемо два језгра процесора и 1 GB меморије као минималну конфигурацију вашег сервера.</span><span class="sxs-lookup"><span data-stu-id="08af9-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="08af9-126">Извоз ентитета са до 100 милиона корисничких профила може потрајати 90 минута када се користи препоручена минимална конфигурација са два језгра процесора и 1 GB меморије.</span><span class="sxs-lookup"><span data-stu-id="08af9-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="08af9-127">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="08af9-127">Data privacy and compliance</span></span>

<span data-ttu-id="08af9-128">Када омогућите да Dynamics 365 Customer Insights преноси податке путем SFTP-а, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="08af9-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="08af9-129">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да одредиште за извоз испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="08af9-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="08af9-130">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="08af9-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="08af9-131">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="08af9-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]