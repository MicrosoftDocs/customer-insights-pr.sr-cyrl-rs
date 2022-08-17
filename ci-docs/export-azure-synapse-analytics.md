---
title: Извоз података у Azure Synapse Analytics (преглед)
description: Сазнајте како да конфигуришете везу са програмом Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 0e953cfff12df433d033717d58b28c2834468916
ms.sourcegitcommit: 086f75136132d561cd78a4c2cb1e1933e2301f32
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 08/11/2022
ms.locfileid: "9259862"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Извоз података у Azure Synapse Analytics (преглед)

Azure Synapse је аналитичка услуга која убрзава време за увид у складишта података и системе великих података. Можете да унесете и користите Customer Insights податке у услузи [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Предуслови

> [!NOTE]
> Обавезно подесите све **доделе улога** као што је описано.

- У фасцикли "Увиди клијената", Azure Active Directory ваш (АД) кориснички налог мора да има улогу [администратора](permissions.md#add-users).

У услузи Azure:

- Активна претплата на услугу Azure.

- Ако користите нови Azure Data Lake Storage Gen2 налог, главни сервис [за увиде клијената има](connect-service-principal.md) дозволе **за складиштење блоб сарадник** података. Data Lake Storage Gen2 **мора да има** омогућен [хијерархијски простор имена](/azure/storage/blobs/data-lake-storage-namespace).

- У групи ресурса у којој Azure Synapse се радни простор налази, *директору услуге* *Azure AD и кориснику са администраторске дозволе у "Увидима* **корисника" мора бити додељено најмање читалац**[дозвола](/azure/role-based-access-control/role-assignments-portal).

- Корисник *Azure AD са администраторским дозволама у програму Цустомер Инсигхтс* има **дозволе за складиштење блоб података сарадник** Azure Data Lake Storage на Gen2 налогу где се подаци налазе и који су повезани са радним Azure Synapse простором. Сазнајте више о [коришћењу Azure портала за додељивање Azure улоге за приступ блоб објекту и подацима у реду](/azure/storage/common/storage-auth-aad-rbac-portal) и [дозволама сарадника за податке складишта блоб објекта](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Управљани *[Azure Synapse идентитет радног простора](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* има **податке о складиштењу** сарадник за Azure Data Lake Storage информације на Gen2 налогу где се подаци налазе и који су повезани са радним Azure Synapse простором. Сазнајте више о [коришћењу Azure портала за додељивање Azure улоге за приступ блоб објекту и подацима у реду](/azure/storage/common/storage-auth-aad-rbac-portal) и [дозволама сарадника за податке складишта блоб објекта](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- На радном Azure Synapse простору, главнина *услуге за увиде клијената* **има додељену улогу администратора**[синапсе](/azure/synapse-analytics/security/how-to-set-up-access-control).

- Ако ваше окружење"Увид у купце" складишти [податке у сопственом Azure Data Lake Storage](own-data-lake-storage.md), кориснику који подешавање Azure Synapse Analytics везе треба барем уграђену **читалац улогу** на Дата Лаке Стораге налогу. За више информација, погледајте [Додељивање Azure улога помоћу Azure портала](/azure/role-based-access-control/role-assignments-portal).

## <a name="set-up-connection-to-azure-synapse"></a>Подеси везу са Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Идите на **Администратор** > **Везе**.

1. Изаберите **Додај везу и** одаберите **Azure Synapse Analytics**.

1. Дајте вези препознатљиво име у пољу **Име за приказ**. Име за приказ и врста везе описују ову везу. Препоручујемо да одаберете назив који објашњава сврху и циљ везе.

1. Одаберите ко може да користи ову везу. Подразумевано су то само администратори. За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Изаберите или потражите претплату у којој желите да користите Customer Insights податке. Чим изаберете претплату, можете и да изаберете **Радни простор**, **Налог складишта** и **Контејнер**.

1. Прегледајте приватност [и усаглашеност података и](connections.md#data-privacy-and-compliance) изаберите И **слажем се**.

1. Изаберите **Сачувај** да бисте креирали везу.

## <a name="configure-an-export"></a>Конфигурисање извоза

[!INCLUDE [export-permission-include](includes/export-permission.md)] Да бисте конфигурисали извоз са дељеном везом, потребно вам је најмање **сарадник** у фасцикли "Увиди купаца".

1. Идите на **Подаци** > **Извози**.

1. Изаберите **Додај извоз**.

1. У пољу **Веза за извоз** одаберите везу из одељка Azure Synapse Analytics. Ако веза није доступна, обратите се администратору.

1. Обезбедите препознатљиво **Име за приказ** за ваш извоз и **Назив базе података**. Извоз ће створити нову базу података [Azure Synapse језера](/azure/synapse-analytics/database-designer/concepts-lake-database) у радном простору дефинисаном у вези.

1. Изаберите ентитете у које желите да извезете Azure Synapse Analytics.
   > [!NOTE]
   > Извори података на основу [Common Data Model фасцикле](connect-common-data-model.md) нису подржани.

1. Изаберите **Сачувај**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Да бисте испитали податке који су извезени у аналитику синапсе, **потребни су вам подаци о складиштењу читалац да бисте** имали приступ одредишном складишту на радном простору извоза.

## <a name="update-an-export"></a>Ажурирање извоза

1. Идите на **Подаци** > **Извози**.

1. Изаберите **Уреди** на извозу који желите да промените.

   - **Додајте** или **уклоните** ентитете из избора. Ако се ентитети уклоне из избора, неће се избрисати из Synapse Analytics базе података. Међутим, будућа освежавања података неће ажурирати уклоњене ентитете у тој бази података.

   - **Промена назива базе података** креира нову Synapse Analytics базу података. База података са именом које је претходно било конфигурисано неће добијати ажурирања у будућим освежавањима.

[!INCLUDE [footer-include](includes/footer-banner.md)]
