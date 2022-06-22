---
title: Ингест подаци из Azure Synapse Analytics
description: Користите базу података Azure Synapse као извор података у програму Dynamics 365 Customer Insights.
ms.date: 03/25/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 6f94cdbcc203fc4518544f7a945bd80e871b36c1
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011445"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Повезивање извор података Azure Synapse Analytics (преглед)

Azure Synapse Analytics је услуга аналитике предузећа која убрзава време на увиде у складиштима података и великим системима података. Azure Synapse Analytics окупља најбоље од СQЛ технологија које се користе у складишту података предузећа, Спарк технологије које се користе за велике податке, Дата Еxплорер за аналитику евиденције и временских серија, цевоводе за интеграцију података и ЕТЛ/ЕЛТ и дубоку интеграцију са другим Азуре услугама Power BI као што су, Cosmos DB и АзуреМЛ.

Више информација потражите у чланку [Azure Synapse Преглед](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Предуслови

> [!IMPORTANT]
> Обавезно подесите све **доделе улога** као што је описано.  

**У увидима купаца**:

* Имате улогу администратора **у** "Увидима клијената". Сазнајте више о корисничким [дозволама у фасцикли "Увиди клијената"](permissions.md#assign-roles-and-permissions).

**У Азуре:**

- Активна претплата на услугу Azure.

- Ако користите нови Azure Data Lake Storage Gen2 налог, главној услузи *за увиде клијената потребни* су **подаци о складиштењу сарадник** дозволе. Сазнајте више о [повезивању са главним Azure Data Lake Storage сервисом за увиде клијената](connect-service-principal.md). Data Lake Storage Gen2 **мора да има** омогућен [хијерархијски простор имена](/azure/storage/blobs/data-lake-storage-namespace).

- У групи ресурса радни Azure Synapse простор се налази, *директору услуге и* *кориснику за увиде клијената* потребно је доделити **најмање читалац** дозволе. За више информација, погледајте [Додељивање Azure улога помоћу Azure портала](/azure/role-based-access-control/role-assignments-portal).

- *Кориснику* су потребне дозволе **сарадника за податке складишта блоб објекта** на Azure Data Lake Storage Gen2 налогу на којем се подаци налазе и повезани су са Azure Synapse радним простором. Сазнајте више о [коришћењу Azure портала за додељивање Azure улоге за приступ блоб објекту и подацима у реду](/azure/storage/common/storage-auth-aad-rbac-portal) и [дозволама сарадника за податке складишта блоб објекта](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Управљаном идентитету Azure Synapse радног простора](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* су потребне дозволе **сарадника за податке складишта блоб објекта** на Azure Data Lake Storage Gen2 налогу на којем се подаци налазе и повезани су са Azure Synapse радним простором. Сазнајте више о [коришћењу Azure портала за додељивање Azure улоге за приступ блоб објекту и подацима у реду](/azure/storage/common/storage-auth-aad-rbac-portal) и [дозволама сарадника за податке складишта блоб објекта](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- На радном Azure Synapse простору, директору *услуге за увиде клијената* потребна **је додељена улога администратора** синапсе. За више информација, погледајте [Како се поставља контрола приступа за ваш Synapse радни простор](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Повежи се са базом података језера у Azure Synapse Analytics

1. Идите на **Подаци** > **Извори података**.

1. Изаберите **Додај извор података**.

1. Одаберите **Azure Synapse Analytics метод (Преглед**).

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Дијалог за повезивање са подацима синапсе Аналитика":::
  
1. Унесите **име** за извор података и опционални **опис**.

1. Одаберите [доступну везу](connections.md) са Azure Synapse Analytics или креирајте нову.

1. Одаберите базу **података** са радног простора повезаног у изабраној вези и Azure Synapse Analytics кликните на дугме" **Даље"**.

1. Изаберите ентитете које желите да унестите из повезане базе података и кликните на дугме" **Даље"**.

1. Опционално, одаберите ентитете података да бисте дозволили профилисање података.

1. Кликните **на** дугме "Сачувај" да бисте применили селекцију и започели уношење података из новокреираног извор података са табелама базе података језера у програму Azure Synapse Analytics. Отвориће **се страница"Извори података" која приказује нову извор података статусу "Освежавање** **·** ".
