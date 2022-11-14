---
title: Повезивање извор података Azure Synapse (преглед)
description: Користите базу података Azure Synapse као извор података у програму Dynamics 365 Customer Insights.
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 675fd03c44a7a7a492b111895d79c2e77f93a5b5
ms.sourcegitcommit: 4ba74816ebfa46412c64c40a61e1f31c4ccc40f2
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 11/03/2022
ms.locfileid: "9738174"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Повезивање извор података Azure Synapse Analytics (преглед)

Azure Synapse Analytics је услуга аналитике предузећа која убрзава време на увиде у складиштима података и великим системима података. Azure Synapse Analytics окупља најбоље од СQЛ технологија које се користе у складишту података предузећа, Спарк технологије које се користе за велике податке, Дата Еxплорер за аналитику евиденције и временских серија, цевоводе за интеграцију података и ЕТЛ/ЕЛТ и дубоку интеграцију са другим Азуре услугама Power BI као што су, Cosmos DB и АзуреМЛ.

Више информација потражите у чланку [Azure Synapse Преглед](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Предуслови

> [!NOTE]
> Синапса радних простора којима [је омогућен заштитни](/azure/synapse-analytics/security/synapse-workspace-ip-firewall) зид тренутно није подржана.
> [!IMPORTANT]
> Обавезно подесите све **доделе улога** као што је описано.  

**У увидима купаца**:

* Имате улогу администратора **у** "Увидима клијената". Сазнајте више о корисничким [дозволама у фасцикли "Увиди клијената"](permissions.md#add-users).

**У Азуре:**

- Активна претплата на услугу Azure.

- Ако користите нови Azure Data Lake Storage Gen2 налог, *главници услуге за увиде клијената* који је "Дyнамицс 365 АИ за увиде клијената" потребне **су дозволе за складиштење блоб сарадник** података. Сазнајте више о [повезивању са главним Azure Data Lake Storage сервисом за увиде клијената](connect-service-principal.md). Data Lake Storage Gen2 **мора да има** омогућен [хијерархијски простор имена](/azure/storage/blobs/data-lake-storage-namespace).

- У групи ресурса радни Azure Synapse простор се налази, *главницу услуге* која је "Дyнамицс 365 АИ за увиде клијената" *и кориснику за увиде клијената* **потребно је доделити најмање читалац** дозволе. За више информација, погледајте [Додељивање Azure улога помоћу Azure портала](/azure/role-based-access-control/role-assignments-portal).

- *Кориснику* су потребне дозволе **сарадника за податке складишта блоб објекта** на Azure Data Lake Storage Gen2 налогу на којем се подаци налазе и повезани су са Azure Synapse радним простором. Сазнајте више о [коришћењу Azure портала за додељивање Azure улоге за приступ блоб објекту и подацима у реду](/azure/storage/common/storage-auth-aad-rbac-portal) и [дозволама сарадника за податке складишта блоб објекта](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Управљаном идентитету Azure Synapse радног простора](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* су потребне дозволе **сарадника за податке складишта блоб објекта** на Azure Data Lake Storage Gen2 налогу на којем се подаци налазе и повезани су са Azure Synapse радним простором. Сазнајте више о [коришћењу Azure портала за додељивање Azure улоге за приступ блоб објекту и подацима у реду](/azure/storage/common/storage-auth-aad-rbac-portal) и [дозволама сарадника за податке складишта блоб објекта](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- На радном Azure Synapse простору, директору *услуге за увиде клијената* који је "Дyнамицс 365 АИ за увиде клијената" **потребна је улога администратора** синапсе. Кориснику **је** потребна најмање **синапса сарадник** додељена за радни простор. За више информација, погледајте [Како се поставља контрола приступа за ваш Synapse радни простор](/azure/synapse-analytics/security/how-to-set-up-access-control).

- Ако ваше окружење"Увид у купце" складишти [податке у сопственом Azure Data Lake Storage](own-data-lake-storage.md), кориснику који подешавање Azure Synapse Analytics везе треба барем уграђену **читалац улогу** на Дата Лаке Стораге налогу. За више информација, погледајте [Додељивање Azure улога помоћу Azure портала](/azure/role-based-access-control/role-assignments-portal).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Повежи се са базом података језера у Azure Synapse Analytics

1. Идите на **Подаци** > **Извори података**.

1. Изаберите **Додај извор података**.

1. Одаберите **Azure Synapse Analytics метод (Преглед**).

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Дијалог за повезивање са подацима синапсе Аналитика":::
  
1. Унесите **име** за извор података и опционални **опис**.

1. Одаберите [доступну везу](connections.md) са Azure Synapse Analytics или [креирајте нову](export-azure-synapse-analytics.md#set-up-connection-to-azure-synapse).

1. Одаберите базу **података** са радног простора повезаног у изабраној вези и Azure Synapse Analytics кликните на дугме" **Даље"**. Тренутно подржавамо само базу података типа Лаке *база података*.

1. Изаберите ентитете које желите да унестите из повезане базе података и кликните на дугме" **Даље"**.

1. Опционално, одаберите ентитете података да бисте дозволили профилисање података.

1. Кликните **на** дугме "Сачувај" да бисте применили селекцију и започели уношење података из новокреираног извор података са табелама базе података на језеру у програму Azure Synapse Analytics. Отвориће **се страница"Извори података" која приказује нову извор података статусу "Освежавање** **·** ".

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Учитавање података може потрајати. Након успешног освежавања, унети подаци се могу редиговање са странице [**"Ентитети**](entities.md) ".

[!INCLUDE [footer-include](includes/footer-banner.md)]
