---
title: Ингест подаци из Azure Synapse Analytics
description: Користите базу података Azure Synapse као извор података у програму Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 163bef897880f0497bf00e90fd095621a2d14378
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/25/2022
ms.locfileid: "8356054"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Повезивање извор података Azure Synapse (преглед)

Azure Synapse Analytics је услуга аналитике предузећа која убрзава време на увиде у складиштима података и великим системима података. Azure Synapse Analytics окупља најбоље од СQЛ технологија које се користе у складишту података предузећа, Спарк технологије које се користе за велике податке, Дата Еxплорер за аналитику евиденције и временских серија, цевоводе за интеграцију података и ЕТЛ/ЕЛТ и дубоку интеграцију са другим Азуре услугама Power BI као што су, Cosmos DB и АзуреМЛ.

Више информација потражите у чланку [Azure Synapse Преглед](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Предуслови

Следећи предуслови морају бити испуњени за конфигурисање везе из услуге Customer Insights у услугу Azure Synapse.

> [!IMPORTANT]
> Обавезно подесите све **доделе улога** као што је описано.  

## <a name="prerequisites-in-customer-insights"></a>Предуслови у услузи Customer Insights

* Имате улогу администратора **у** "Увидима клијената". Сазнајте више о [корисничким дозволама у увидима у циљну групу](permissions.md#assign-roles-and-permissions).

У услузи Azure: 

- Активна претплата на услугу Azure.

- Ако користите нови Azure Data Lake Storage Gen2 налог, *принципалу услуге за увиде у циљну групу* су потребне дозволе **сарадника за податке складишта блоб објекта**. Сазнајте више [о повезивању са Azure Data Lake Storage директором услуге за корисници увиде](connect-service-principal.md). Data Lake Storage Gen2 **мора да има** омогућен [хијерархијски простор имена](/azure/storage/blobs/data-lake-storage-namespace).

- У групи ресурса у којој се налази Azure Synapse радни простор, *принципалу услуге* и *кориснику за увиде у циљну групу* треба доделити барем дозволе **читаоца**. За више информација, погледајте [Додељивање Azure улога помоћу Azure портала](/azure/role-based-access-control/role-assignments-portal).

- *Кориснику* су потребне дозволе **сарадника за податке складишта блоб објекта** на Azure Data Lake Storage Gen2 налогу на којем се подаци налазе и повезани су са Azure Synapse радним простором. Сазнајте више о [коришћењу Azure портала за додељивање Azure улоге за приступ блоб објекту и подацима у реду](/azure/storage/common/storage-auth-aad-rbac-portal) и [дозволама сарадника за податке складишта блоб објекта](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Управљаном идентитету Azure Synapse радног простора](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* су потребне дозволе **сарадника за податке складишта блоб објекта** на Azure Data Lake Storage Gen2 налогу на којем се подаци налазе и повезани су са Azure Synapse радним простором. Сазнајте више о [коришћењу Azure портала за додељивање Azure улоге за приступ блоб објекту и подацима у реду](/azure/storage/common/storage-auth-aad-rbac-portal) и [дозволама сарадника за податке складишта блоб објекта](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- У Azure Synapse радном простору, *принципалу услуге за увиде у циљну групу* је потребна додељена улога **Synapse администратора**. За више информација, погледајте [Како се поставља контрола приступа за ваш Synapse радни простор](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Повежи се са базама података језера у Azure Synapse Analytics

1. Идите на **Подаци** > **Извори података**.

1. Изаберите **Додај извор података**.

1. Одаберите **Azure Synapse Analytics метод (Преглед**).

1. Наведите **Назив** за извор података, па изаберите **Следеће** како бисте креирали извор података. 

1. Одаберите [доступну везу](connections.md) са Azure Synapse Analytics или креирајте нову.

1. Одаберите базу **података језера** са радног простора повезаног у изабраној вези и Azure Synapse Analytics кликните на дугме" **Даље"**.

1. Изаберите ентитете које желите да унестите из повезане базе података. 

1. Опционално, одаберите ентитете података да бисте дозволили профилисање података. 

1. Кликните **на** дугме "Сачувај" да бисте применили селекцију и започели уношење података из новокреираног извор података са табелама базе података језера у програму Azure Synapse Analytics.
