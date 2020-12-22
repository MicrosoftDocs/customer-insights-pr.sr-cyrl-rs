---
title: Извезите Customer Insights податке у SFTP хостове
description: Научите како да конфигуришете везу на SFTP хостом.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643521"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="0539e-103">Конектор за SFTP (преглед)</span><span class="sxs-lookup"><span data-stu-id="0539e-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="0539e-104">Користите податке о клијентима у независним апликацијама тако што ћете их извести на Secure File Transfer Protocol (SFTP) хост.</span><span class="sxs-lookup"><span data-stu-id="0539e-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0539e-105">Предуслови</span><span class="sxs-lookup"><span data-stu-id="0539e-105">Prerequisites</span></span>

- <span data-ttu-id="0539e-106">Доступност SFTP хоста и одговарајућих акредитива.</span><span class="sxs-lookup"><span data-stu-id="0539e-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="0539e-107">Повезивање на SFTP</span><span class="sxs-lookup"><span data-stu-id="0539e-107">Connect to SFTP</span></span>

1. <span data-ttu-id="0539e-108">Идите на **Администратор** > **Одредишта за извоз**.</span><span class="sxs-lookup"><span data-stu-id="0539e-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="0539e-109">Под **SFTP**, изаберите **Постави**.</span><span class="sxs-lookup"><span data-stu-id="0539e-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="0539e-110">Дајте одредишту препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="0539e-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="0539e-111">Наведите **Корисничко име**, **Лозинку** и **Име хоста** за SFTP налог.</span><span class="sxs-lookup"><span data-stu-id="0539e-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="0539e-112">Пример: Ако је основном директоријум вашег SFTP сервера /root/folder, а желите да се подаци извезу у /root/folder/ci_export_destination_folder, хост треба да буде sftp://<server_address>/ci_export_destination_folder".</span><span class="sxs-lookup"><span data-stu-id="0539e-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="0539e-113">Изаберите **Верификуј** да тестирате везу.</span><span class="sxs-lookup"><span data-stu-id="0539e-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="0539e-114">Након успешне верификације, изаберите да ли желите да извезите своје податке као **Компримовану датотеку** или **Распаковати датотеку**, а затим изаберите **знак разграничавања поља** за извезене датотеке.</span><span class="sxs-lookup"><span data-stu-id="0539e-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="0539e-115">Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.</span><span class="sxs-lookup"><span data-stu-id="0539e-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0539e-116">Изаберите **Следеће** да бисте започели конфигурисање извоза.</span><span class="sxs-lookup"><span data-stu-id="0539e-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="0539e-117">Конфигурисање везе</span><span class="sxs-lookup"><span data-stu-id="0539e-117">Configure the connection</span></span>

1. <span data-ttu-id="0539e-118">Изаберите **атрибуте клијента** које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="0539e-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="0539e-119">Можете да извезете један или више атрибута.</span><span class="sxs-lookup"><span data-stu-id="0539e-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="0539e-120">Изаберите **Следеће**.</span><span class="sxs-lookup"><span data-stu-id="0539e-120">Select **Next**.</span></span>

1. <span data-ttu-id="0539e-121">Изаберите сегменте које желите да извезете.</span><span class="sxs-lookup"><span data-stu-id="0539e-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="0539e-122">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="0539e-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="0539e-123">Извоз података</span><span class="sxs-lookup"><span data-stu-id="0539e-123">Export the data</span></span>

<span data-ttu-id="0539e-124">Можете да [извезете податке на захтев](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="0539e-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="0539e-125">Извоз ће се такође покренути са сваким [планираним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0539e-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0539e-126">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="0539e-126">Data privacy and compliance</span></span>

<span data-ttu-id="0539e-127">Када омогућите да Dynamics 365 Customer Insights преноси податке путем SFTP-а, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="0539e-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0539e-128">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да одредиште за извоз испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="0539e-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0539e-129">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0539e-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0539e-130">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="0539e-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
