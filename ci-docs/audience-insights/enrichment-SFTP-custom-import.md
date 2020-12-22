---
title: Обогаћивање уз SFTP прилагођени увоз
description: Опште информације о обогаћивању SFTP прилагођеног увоза.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 59f7f05ca0825ba147e9e93f10fa3508ec3a16dd
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568498"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="a25e2-103">Обогатите профиле клијената уз прилагођене податке (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="a25e2-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="a25e2-104">Secure File Transfer Protocol (SFTP) прилагођени увоз вам омогућава да увезете податке који не морају да пролазе кроз процес обједињавања података.</span><span class="sxs-lookup"><span data-stu-id="a25e2-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="a25e2-105">То је флексибилан, сигуран и лак начин уноса података.</span><span class="sxs-lookup"><span data-stu-id="a25e2-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="a25e2-106">SFTP прилагођени увоз се може користити у комбинацији са [SFTP извозом](export-sftp.md) који вам омогућава извоз података о профилу клијената потребних за обогаћивање.</span><span class="sxs-lookup"><span data-stu-id="a25e2-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="a25e2-107">Подаци се затим могу обрадити, обогатити и SFTP прилагођени увоз може се користити за враћање обогаћених података у могућност увида о корисницима услуге Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a25e2-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a25e2-108">Предуслови</span><span class="sxs-lookup"><span data-stu-id="a25e2-108">Prerequisites</span></span>

<span data-ttu-id="a25e2-109">Да бисте конфигурисали SFTP прилагођени увоз, морају бити испуњени следећи предуслови:</span><span class="sxs-lookup"><span data-stu-id="a25e2-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="a25e2-110">Имате корисничке акредитиве (корисничко име и лозинку) за SFTP локацију одакле ће се подаци увозити.</span><span class="sxs-lookup"><span data-stu-id="a25e2-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="a25e2-111">Имате URL и број порта (обично 22) за STFP хост.</span><span class="sxs-lookup"><span data-stu-id="a25e2-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="a25e2-112">Имате име датотеке и локацију датотеке коју треба увести на SFTP хост.</span><span class="sxs-lookup"><span data-stu-id="a25e2-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="a25e2-113">Постоји *model.json* датотека која наводи шему за податке који се увозе.</span><span class="sxs-lookup"><span data-stu-id="a25e2-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="a25e2-114">Ова датотека мора бити у истом директоријуму као и датотека коју треба увести.</span><span class="sxs-lookup"><span data-stu-id="a25e2-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="a25e2-115">Имате [администраторску](permissions.md#administrator) дозволу.</span><span class="sxs-lookup"><span data-stu-id="a25e2-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="a25e2-116">Конфигурисање</span><span class="sxs-lookup"><span data-stu-id="a25e2-116">Configuration</span></span>

1. <span data-ttu-id="a25e2-117">Идите до картице **Подаци** > **Обогаћивање** и изаберите картицу **Откриј**.</span><span class="sxs-lookup"><span data-stu-id="a25e2-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="a25e2-118">На **плочици SFTP прилагођеног увоза**, изаберите **Обогати моје податке**.</span><span class="sxs-lookup"><span data-stu-id="a25e2-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a25e2-119">![Плочица SFTP прилагођеног увоза](media/SFTP_Custom_Import_tile.png "Плочица SFTP прилагођеног увоза")</span><span class="sxs-lookup"><span data-stu-id="a25e2-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="a25e2-120">Изаберите **Започните** и наведите акредитиве и адресу за SFTP сервер.</span><span class="sxs-lookup"><span data-stu-id="a25e2-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="a25e2-121">На пример, sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="a25e2-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="a25e2-122">Унесите име датотеке која садржи податке и путању до датотеке на SFTP серверу ако није у основној фасцикли.</span><span class="sxs-lookup"><span data-stu-id="a25e2-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="a25e2-123">Потврдите све уносе избором опције **Повежите се са прилагођеним увозом**.</span><span class="sxs-lookup"><span data-stu-id="a25e2-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a25e2-124">![Потпалета конфигурације SFTP прилагођеног увоза](media/SFTP_Custom_Import_Configuration_flyout.png "Потпалета конфигурације SFTP прилагођеног увоза")</span><span class="sxs-lookup"><span data-stu-id="a25e2-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="a25e2-125">Дефинисање мапирања поља</span><span class="sxs-lookup"><span data-stu-id="a25e2-125">Defining field mappings</span></span> 

<span data-ttu-id="a25e2-126">Директоријум који садржи датотеку за увоз на SFTP сервер такође мора садржати *model.json* датотеку.</span><span class="sxs-lookup"><span data-stu-id="a25e2-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="a25e2-127">Ова датотека дефинише шему која ће се користити за увоз података.</span><span class="sxs-lookup"><span data-stu-id="a25e2-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="a25e2-128">Шема мора да користи [Common Data Model](https://docs.microsoft.com/common-data-model/) за одређивање мапирања поља.</span><span class="sxs-lookup"><span data-stu-id="a25e2-128">The schema has to use [the Common Data Model](https://docs.microsoft.com/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="a25e2-129">Једноставан пример датотеке model.json изгледа овако:</span><span class="sxs-lookup"><span data-stu-id="a25e2-129">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="a25e2-130">Резултати обогаћивања</span><span class="sxs-lookup"><span data-stu-id="a25e2-130">Enrichment results</span></span>

<span data-ttu-id="a25e2-131">Да бисте започели процес обогаћивања, изаберите **Покрени** са командне траке.</span><span class="sxs-lookup"><span data-stu-id="a25e2-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="a25e2-132">Такође можете пустити да систем аутоматски покреће обогаћивање као део [планираног освежавања](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a25e2-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a25e2-133">Време обраде зависиће од величине података који се увозе и везе са SFTP сервером.</span><span class="sxs-lookup"><span data-stu-id="a25e2-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="a25e2-134">По завршетку процеса обогаћивања, можете прегледати своје новоувезене прилагођене податке обогаћивања под **Моја обогаћења**.</span><span class="sxs-lookup"><span data-stu-id="a25e2-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="a25e2-135">Осим тога, пронаћи ћете време последњег ажурирања и број обогаћених профила.</span><span class="sxs-lookup"><span data-stu-id="a25e2-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="a25e2-136">Детаљном приказу сваког обогаћеног профила можете приступити ако изаберете **Прикажи обогаћене податке**.</span><span class="sxs-lookup"><span data-stu-id="a25e2-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a25e2-137">Следећи кораци</span><span class="sxs-lookup"><span data-stu-id="a25e2-137">Next steps</span></span>

<span data-ttu-id="a25e2-138">Надоградите на обогаћеним подацима о клијентима.</span><span class="sxs-lookup"><span data-stu-id="a25e2-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="a25e2-139">Креирајте [сегменте](segments.md), [мере](measures.md) и [извезите податке](export-destinations.md) да бисте клијентима пружили персонализована искуства.</span><span class="sxs-lookup"><span data-stu-id="a25e2-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


