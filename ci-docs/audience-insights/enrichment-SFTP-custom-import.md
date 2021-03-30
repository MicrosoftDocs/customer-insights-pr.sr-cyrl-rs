---
title: Обогаћивање уз SFTP прилагођени увоз
description: Опште информације о обогаћивању SFTP прилагођеног увоза.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d9e095ef793cbd25415864f76a541dce68fafe47
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595873"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Обогатите профиле клијената уз прилагођене податке (верзија за преглед)

Secure File Transfer Protocol (SFTP) прилагођени увоз вам омогућава да увезете податке који не морају да пролазе кроз процес обједињавања података. То је флексибилан, сигуран и лак начин уноса података. SFTP прилагођени увоз се може користити у комбинацији са [SFTP извозом](export-sftp.md) који вам омогућава извоз података о профилу клијената потребних за обогаћивање. Подаци се затим могу обрадити, обогатити и SFTP прилагођени увоз може се користити за враћање обогаћених података у могућност увида о корисницима услуге Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Предуслови

Да бисте конфигурисали SFTP прилагођени увоз, морају бити испуњени следећи предуслови:

- Имате корисничке акредитиве (корисничко име и лозинку) за SFTP локацију одакле ће се подаци увозити.
- Имате URL и број порта (обично 22) за STFP хост.
- Имате име датотеке и локацију датотеке коју треба увести на SFTP хост.
- Постоји *model.json* датотека која наводи шему за податке који се увозе. Ова датотека мора бити у истом директоријуму као и датотека коју треба увести.
- Имате [администраторску](permissions.md#administrator) дозволу.

## <a name="configuration"></a>Конфигурисање

1. Идите до картице **Подаци** > **Обогаћивање** и изаберите картицу **Откриј**.

1. На **плочици SFTP прилагођеног увоза**, изаберите **Обогати моје податке**.

   > [!div class="mx-imgBorder"]
   > ![Плочица SFTP прилагођеног увоза](media/SFTP_Custom_Import_tile.png "Плочица SFTP прилагођеног увоза")

1. Изаберите **Започните** и наведите акредитиве и адресу за SFTP сервер. На пример, sftp://mysftpserver.com:22.

1. Унесите име датотеке која садржи податке и путању до датотеке на SFTP серверу ако није у основној фасцикли.

1. Потврдите све уносе избором опције **Повежите се са прилагођеним увозом**.

   > [!div class="mx-imgBorder"]
   > ![Потпалета конфигурације SFTP прилагођеног увоза](media/SFTP_Custom_Import_Configuration_flyout.png "Потпалета конфигурације SFTP прилагођеног увоза")

## <a name="defining-field-mappings"></a>Дефинисање мапирања поља 

Директоријум који садржи датотеку за увоз на SFTP сервер такође мора садржати *model.json* датотеку. Ова датотека дефинише шему која ће се користити за увоз података. Шема мора да користи [Common Data Model](/common-data-model/) за одређивање мапирања поља. Једноставан пример датотеке model.json изгледа овако:

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

## <a name="enrichment-results"></a>Резултати обогаћивања

Да бисте започели процес обогаћивања, изаберите **Покрени** са командне траке. Такође можете пустити да систем аутоматски покреће обогаћивање као део [планираног освежавања](system.md#schedule-tab). Време обраде зависиће од величине података који се увозе и везе са SFTP сервером.

По завршетку процеса обогаћивања, можете прегледати своје новоувезене прилагођене податке обогаћивања под **Моја обогаћења**. Осим тога, пронаћи ћете време последњег ажурирања и број обогаћених профила.

Детаљном приказу сваког обогаћеног профила можете приступити ако изаберете **Прикажи обогаћене податке**.

## <a name="next-steps"></a>Следећи кораци

Надоградите на обогаћеним подацима о клијентима. Креирајте [сегменте](segments.md), [мере](measures.md) и [извезите податке](export-destinations.md) да бисте клијентима пружили персонализована искуства.




[!INCLUDE[footer-include](../includes/footer-banner.md)]