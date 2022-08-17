---
title: Обогатите профиле клијената СФТП прилагођеним увозом (преглед)
description: Опште информације о обогаћивању SFTP прилагођеног увоза.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 831d1d3d3045379bbc5bcdcd4b05b8a147221f31
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237784"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>Обогатите профиле клијената СФТП прилагођеним увозом (преглед)

Secure File Transfer Protocol (SFTP) прилагођени увоз вам омогућава да увезете податке који не морају да пролазе кроз процес обједињавања података. То је флексибилан, сигуран и лак начин уноса података. SFTP прилагођени увоз се може користити у комбинацији са [SFTP извозом](export-sftp.md) који вам омогућава извоз података о профилу клијената потребних за обогаћивање. Подаци се затим могу обрадити и обогатити, а СФТП прилагођени увоз може да се користи за повратак обогаћених података на Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Предуслови

- Познато је име датотеке и локација (путања) датотеке која треба да се увезе на СФТП домаћину.

- Доступна *је датотека модел.јсон* која наводи шему "Уобичајени модел података" за увоз података. Ова датотека мора бити у истом директоријуму као и датотека коју треба увести.

- СФТП [веза](connections.md) је [конфигурисана](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Пример шеме датотека

Директоријум који садржи датотеку за увоз на SFTP сервер такође мора садржати *model.json* датотеку. Ова датотека дефинише шему која ће се користити за увоз података. Шема треба да користи [Common Data Model](/common-data-model/) да одреди мапирање поља. Једноставан пример датотеке model.json изгледа овако:

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
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
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

## <a name="configure-the-connection-for-sftp-custom-import"></a>Конфигурисање везе за SFTP прилагођеним увозом

Морате бити администратор у програму [Цустомер](permissions.md#admin) Инсигхтс и имати корисничке акредитиве, УРЛ адресу и број порта за СФТП локацију са које желите да увезете податке.

1. Изаберите **опцију Додај** везу приликом конфигурисања обогаћења или идите на **административне** > **везе и** изаберите **ставку Подешавање** на плочици "Прилагођени увоз".

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Прилагођена страница за конфигурацију везе увоза.":::

1. Унесите име за везу.

1. Унесите важеће корисничко име, лозинку и URL хоста за SFTP сервер на којем се налазе подаци које треба увести.

1. Прегледајте приватност [и усаглашеност података и](connections.md#data-privacy-and-compliance) изаберите И **слажем се**.

1. Изаберите **опцију** Провери да бисте проверили ваљаност конфигурације, а затим кликните на дугме **Сачувај**.

## <a name="configure-the-import"></a>Конфигурисање увоза

1. Идите до картице **Подаци** > **Обогаћивање** и изаберите картицу **Откриј**.

1. Изаберите **ставку Обогати моје податке** на **СФТП прилагођеној плочици** за увоз.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Плочица SFTP прилагођеног увоза.":::

1. Прегледајте преглед, а затим кликните на дугме **Даље**.

1. Изаберите везу. Ако веза није доступна, обратите се администратору.

1. Изаберите опцију **скуп података и** одаберите профил или сегмент који желите да обогатите. Ентитет *купца* обогаћује све профиле купаца, док сегмент обогаћује само профиле купаца садржане у том сегменту.

1. Изаберите **Следеће**.

1. Унесите путању **и** име **датотеке** датотеке са подацима коју желите да увезете.

1. Изаберите **Следеће**.

1. Наведите **име** за богаћење и име **ентитета излаза**.

1. Изаберите **Сачувај обогаћивање** након прегледа ваших избора.

1. Кликните **на дугме** "Покрени" да бисте започели процес обогаћивања или близу да бисте се вратили на страницу **"Обогаћивање** ".

## <a name="view-enrichment-results"></a>Прикажи резултате обогаћивања

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Следећи кораци

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
