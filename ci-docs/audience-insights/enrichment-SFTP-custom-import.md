---
title: Обогаћивање уз SFTP прилагођени увоз
description: Опште информације о обогаћивању SFTP прилагођеног увоза.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896299"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="a96c1-103">Обогатите профиле клијената уз прилагођене податке (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="a96c1-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="a96c1-104">Прилагођени увоз протокола безбедног преноса датотека (SFTP) омогућава вам увоз података који не морају да пролазе кроз процес обједињавања података.</span><span class="sxs-lookup"><span data-stu-id="a96c1-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that does not have to go through the process of data unification.</span></span> <span data-ttu-id="a96c1-105">То је флексибилан, сигуран и лак начин уноса података.</span><span class="sxs-lookup"><span data-stu-id="a96c1-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="a96c1-106">SFTP прилагођени увоз се може користити у комбинацији са [SFTP извозом](export-sftp.md) који вам омогућава извоз података о профилу клијената потребних за обогаћивање.</span><span class="sxs-lookup"><span data-stu-id="a96c1-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="a96c1-107">Подаци се затим могу обрадити, обогатити и SFTP прилагођени увоз може се користити за враћање обогаћених података у могућност увида о корисницима услуге Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a96c1-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a96c1-108">Предуслови</span><span class="sxs-lookup"><span data-stu-id="a96c1-108">Prerequisites</span></span>

<span data-ttu-id="a96c1-109">Да бисте конфигурисали SFTP прилагођени увоз, морају бити испуњени следећи предуслови:</span><span class="sxs-lookup"><span data-stu-id="a96c1-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="a96c1-110">Имате име датотеке и локацију (путању) до датотеке коју треба увести на SFTP хост.</span><span class="sxs-lookup"><span data-stu-id="a96c1-110">You have the filename and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="a96c1-111">Постоји датотека *model.json* која наводи [шему заједничког модела података](/common-data-model/) за увоз података.</span><span class="sxs-lookup"><span data-stu-id="a96c1-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="a96c1-112">Ова датотека мора бити у истом директоријуму као и датотека коју треба увести.</span><span class="sxs-lookup"><span data-stu-id="a96c1-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="a96c1-113">Администратор је већ конфигурисао SFTP везу *или* имате дозволе [администратора](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="a96c1-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="a96c1-114">Требаће вам кориснички акредитиви, URL адреса и број порта за SFTP локацију одакле желите да увезете податке.</span><span class="sxs-lookup"><span data-stu-id="a96c1-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="a96c1-115">Конфигурисање увоза</span><span class="sxs-lookup"><span data-stu-id="a96c1-115">Configure the import</span></span>

1. <span data-ttu-id="a96c1-116">Идите до картице **Подаци** > **Обогаћивање** и изаберите картицу **Откриј**.</span><span class="sxs-lookup"><span data-stu-id="a96c1-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="a96c1-117">На **плочици за SFTP прилагођени увоз** изаберите **Обогати моје податке**, а затим изаберите **Започни**.</span><span class="sxs-lookup"><span data-stu-id="a96c1-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Плочица SFTP прилагођеног увоза.":::

1. <span data-ttu-id="a96c1-119">Изаберите [везу](connections.md) из падајуће листе.</span><span class="sxs-lookup"><span data-stu-id="a96c1-119">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="a96c1-120">Ако веза није доступна, обратите се администратору.</span><span class="sxs-lookup"><span data-stu-id="a96c1-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="a96c1-121">Ако сте администратор, везу можете да направите ако изаберете **Додај везу** и бирате **SFTP прилагођени увоз** из падајућег менија.</span><span class="sxs-lookup"><span data-stu-id="a96c1-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the drop-down.</span></span>

1. <span data-ttu-id="a96c1-122">Изаберите **Повежите са прилагођеним увозом** да бисте потврдили изабрану везу.</span><span class="sxs-lookup"><span data-stu-id="a96c1-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="a96c1-123">Изаберите **Следеће** и унесите **Назив документа** и **Путању** датотеке података коју желите да увезете.</span><span class="sxs-lookup"><span data-stu-id="a96c1-123">Select **Next** and enter the **Filename** and **Path** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Снимак екрана приликом уноса локације података.":::

1. <span data-ttu-id="a96c1-125">Изаберите **Следеће** и обезбедите назив за обогаћивање и назив за излазни ентитет.</span><span class="sxs-lookup"><span data-stu-id="a96c1-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="a96c1-126">Изаберите **Сачувај обогаћивање** након прегледа ваших избора.</span><span class="sxs-lookup"><span data-stu-id="a96c1-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="a96c1-127">Конфигурисање везе за SFTP прилагођеним увозом</span><span class="sxs-lookup"><span data-stu-id="a96c1-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="a96c1-128">Морате бити администратор да бисте конфигурисали везе.</span><span class="sxs-lookup"><span data-stu-id="a96c1-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="a96c1-129">Изаберите **Додај везу** приликом конфигурисања обогаћивања *или* идите на **Администратор** > **Везе** и изаберите **Подешавање** на плочици Custom Import.</span><span class="sxs-lookup"><span data-stu-id="a96c1-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="a96c1-130">Унесите назив везе у поље **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="a96c1-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="a96c1-131">Унесите важеће корисничко име, лозинку и URL адресу хоста за SFTP сервер на којем се налазе подаци за увоз.</span><span class="sxs-lookup"><span data-stu-id="a96c1-131">Enter valid user name, password, and host URL for the STFP server the data to be imported resides on.</span></span>

1. <span data-ttu-id="a96c1-132">Прегледајте и дајте свој пристанак за **Приватност података и усаглашеност** тако што ћете изабрати поље за потврду **Слажем се**.</span><span class="sxs-lookup"><span data-stu-id="a96c1-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="a96c1-133">Изаберите **Верификуј** да бисте проверили ваљаност конфигурације.</span><span class="sxs-lookup"><span data-stu-id="a96c1-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="a96c1-134">Када се верификација заврши, везу можете сачувати кликом на **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="a96c1-134">Once the verification has completed, the connection can be saved by clicking **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="a96c1-135">![Страница за конфигурацију везе за Experian](media/enrichment-SFTP-connection.png "Страница за конфигурацију везе за Experian")</span><span class="sxs-lookup"><span data-stu-id="a96c1-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="a96c1-136">Дефинисање мапирања поља</span><span class="sxs-lookup"><span data-stu-id="a96c1-136">Defining field mappings</span></span> 

<span data-ttu-id="a96c1-137">Директоријум који садржи датотеку за увоз на SFTP сервер такође мора садржати *model.json* датотеку.</span><span class="sxs-lookup"><span data-stu-id="a96c1-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="a96c1-138">Ова датотека дефинише шему која ће се користити за увоз података.</span><span class="sxs-lookup"><span data-stu-id="a96c1-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="a96c1-139">Шема мора да користи [Common Data Model](/common-data-model/) за одређивање мапирања поља.</span><span class="sxs-lookup"><span data-stu-id="a96c1-139">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="a96c1-140">Једноставан пример датотеке model.json изгледа овако:</span><span class="sxs-lookup"><span data-stu-id="a96c1-140">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="a96c1-141">Резултати обогаћивања</span><span class="sxs-lookup"><span data-stu-id="a96c1-141">Enrichment results</span></span>

<span data-ttu-id="a96c1-142">Да бисте започели процес обогаћивања, изаберите **Покрени** са командне траке.</span><span class="sxs-lookup"><span data-stu-id="a96c1-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="a96c1-143">Такође можете пустити да систем аутоматски покреће обогаћивање као део [планираног освежавања](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a96c1-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a96c1-144">Време обраде зависиће од величине података који се увозе и везе са SFTP сервером.</span><span class="sxs-lookup"><span data-stu-id="a96c1-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="a96c1-145">По завршетку процеса обогаћивања, можете прегледати своје новоувезене прилагођене податке обогаћивања под **Моја обогаћења**.</span><span class="sxs-lookup"><span data-stu-id="a96c1-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="a96c1-146">Осим тога, пронаћи ћете време последњег ажурирања и број обогаћених профила.</span><span class="sxs-lookup"><span data-stu-id="a96c1-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="a96c1-147">Детаљном приказу сваког обогаћеног профила можете приступити ако изаберете **Прикажи обогаћене податке**.</span><span class="sxs-lookup"><span data-stu-id="a96c1-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a96c1-148">Следећи кораци</span><span class="sxs-lookup"><span data-stu-id="a96c1-148">Next steps</span></span>

<span data-ttu-id="a96c1-149">Надоградите на обогаћеним подацима о клијентима.</span><span class="sxs-lookup"><span data-stu-id="a96c1-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="a96c1-150">Креирајте [сегменте](segments.md), [мере](measures.md) и [извезите податке](export-destinations.md) да бисте клијентима пружили персонализована искуства.</span><span class="sxs-lookup"><span data-stu-id="a96c1-150">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
