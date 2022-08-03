---
title: Извоз података у Азуре складиште блоба (преглед)
description: Сазнајте како да конфигуришете везу и извезете садржај у складиште блоб објекта.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195722"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Извоз података у Азуре складиште блоба (преглед)

Складиштите Customer Insights податке у складиште блоб објекта или их користите за пренос података у друге апликације.

## <a name="prerequisites"></a>Предуслови

- Име [Азуре Блоб Стораге налога](/azure/storage/blobs/create-data-lake-storage-account) и кључ налога. Да бисте пронашли име и кључ, погледајте чланак Управљање [поставкама налога за складиштење на Азуре порталу](/azure/storage/common/storage-account-manage).
- Азуре [Блоб складишни контејнер](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Позната ограничења

- За Азуре Блоб Стораге одаберите између стандардних [перформанси и премиум перформанси](/azure/storage/blobs/storage-blob-performance-tiers). Ако одаберете ниво премијум перформанси, изаберите [премијум ове блоб објеката тип пословног контакта](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>Подешавање везе са складиштем блоба

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Идите на **Администратор** > **Везе**.

1. Изаберите **Додај везу** и одаберите **Азуре складиште блоба**.

1. Дајте вези препознатљиво име у пољу **Име за приказ**. Име за приказ и врста везе описују ову везу. Препоручујемо да одаберете назив који објашњава сврху и циљ везе.

1. Одаберите ко може да користи ову везу. Подразумевано су то само администратори. За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Унесите **Назив налога**, **Кључ налога** и **Контејнер** за свој налог складишта блоб објекта.

1. Прегледајте приватност [и усаглашеност података и](connections.md#data-privacy-and-compliance) изаберите И **слажем се**.

1. Изаберите **Сачувај** да бисте креирали везу.

## <a name="configure-an-export"></a>Конфигурисање извоза

Да бисте конфигурисали овај извоз, морате имати [дозволу](export-destinations.md#set-up-a-new-export) за овај тип везе.

> [!IMPORTANT]
> Ако сте укључили поставку [меког брисања](/azure/storage/blobs/soft-delete-blob-enable) за Азуре Блоб Стораге налог, извоз неће успети. Искључите меко брисање за извоз података у блоб објекте.

1. Идите на **Подаци** > **Извози**.

1. Изаберите **Додај извоз**.

1. У пољу **Веза за извоз**, одаберите везу из одељка Azure складишта блоб објекта. Ако веза није доступна, обратите се администратору.

1. Унесите име за извоз.

1. Унесите име фасцикле за складиште блоба.

1. Изаберите поље поред сваког ентитета који желите да извезете на ово одредиште.

1. Изаберите **Сачувај**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Извезени подаци се чувају у контејнеру складишта блоб објекта који сте конфигурисали. Следеће путање фасциклу се аутоматски креирају у вашем контејнеру:

- За изворне ентитете и ентитете које генерише систем:   
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Пример : Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5 /BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.цсв
  
  > [!TIP]
  > Извоз ентитета који садрже велику количину података може довести до више ЦСВ датотека у истој фасцикли за сваки извоз. Дељење извоза се дешава из разлога перформанси да би се умањило време потребно за довршавање извоза.

- Модел .јсон за извезене ентитете се налази на нивоу *%ExportDestinationName%*.  
  
  Пример : Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5 /БлобЕxпорт/модел.јсон

[!INCLUDE [footer-include](includes/footer-banner.md)]
