---
title: Извези податке Azure Data Lake Storage у Gen2 (преглед)
description: Сазнајте како да конфигуришете везу са услугом Azure Data Lake Storage Gen2.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196458"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Извези податке Azure Data Lake Storage у Gen2 (преглед)

Складиштите податке из услуге Customer Insights у Data Lake Storage Gen2 налог или их користите за пренос података у друге апликације.

## <a name="prerequisites"></a>Предуслови

- Налог за [складиштење који ће се користити са Азуре Дата Лаке Gen2](/azure/storage/blobs/create-data-lake-storage-account). Да бисте пронашли име и кључ налога за складиштење, погледајте чланак [Управљање поставкама налога за складиштење на Азуре порталу](/azure/storage/common/storage-account-manage).
- Азуре [Блоб складишни контејнер](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Позната ограничења

- За Azure Data Lake Storage Gen2 одаберите између стандардних [перформанси и премиум перформанси](/azure/storage/blobs/create-data-lake-storage-account). Ако одаберете ниво премијум перформанси, изаберите [премијум ове блоб објеката тип пословног контакта](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Подешавање везе са gen2 Azure Data Lake Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Идите на **Администратор** > **Везе**.

1. Изаберите **Додај везу** и одаберите **Азуре Дата Лаке Ген 2**.

1. Дајте вези препознатљиво име у пољу **Име за приказ**. Име за приказ и врста везе описују ову везу. Препоручујемо да одаберете назив који објашњава сврху и циљ везе.

1. Одаберите ко може да користи ову везу. Подразумевано су то само администратори. За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Унесите **Назив пословног контакта**, **Кључ пословног контакта** и **Контејнер** за ваш Azure Data Lake Storage Gen2.

1. Прегледајте приватност [и усаглашеност података и](connections.md#data-privacy-and-compliance) изаберите И **слажем се**.

1. Изаберите **Сачувај** да бисте креирали везу.

## <a name="configure-an-export"></a>Конфигурисање извоза

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Идите на **Подаци** > **Извози**.

1. Изаберите **Додај извоз**.

1. У пољу **Веза за извоз** одаберите везу из одељка Азуре језеро са подацима. Ако веза није доступна, обратите се администратору.

1. Унесите име за извоз.

1. Унесите име фасцикле за Azure Data Lake Storage Gen2 складиште.

1. Изаберите поље поред сваког ентитета који желите да извезете на ово одредиште.

1. Изаберите **Сачувај**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Извезени подаци се чувају у Azure Data Lake Gen 2 контејнеру за складиштење који сте конфигурисали.

> [!TIP]
> Извоз ентитета који садрже велику количину података може довести до више ЦСВ датотека у истој фасцикли за сваки извоз. Дељење извоза се дешава из разлога перформанси да би се умањило време потребно за довршавање извоза.

[!INCLUDE [footer-include](includes/footer-banner.md)]
