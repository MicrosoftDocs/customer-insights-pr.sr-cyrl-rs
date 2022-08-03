---
title: Повежите се са подацима у Microsoft Dataverse управљаном језеру података
description: Увоз података из Microsoft Dataverse управљаног језера података.
ms.date: 07/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: b21150a1c51bdad35250cae7fde7f38a014ec876
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206971"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Повежите се са подацима у Microsoft Dataverse управљаном језеру података

Microsoft Dataverse корисници могу брзо да се повежу са аналитичким ентитетима у управљаном Microsoft Dataverse језеру. Само један извор података окружења може истовремено да користи исто Dataverse надгледано језеро.

> [!NOTE]
> Морате бити администратор организације да бисте Dataverse наставили и прегледали листу ентитета доступних у контролисаном језеру.

## <a name="prerequisites"></a>Предуслови

- Подаци ускладиштени у мрежним услугама, као што је Azure Data Lake Storage, могу се складиштити на локацији различитој од оне на којој се подаци обрађују или складиште у услузи Dynamics 365 Customer Insights.Увозом или повезивањем са подацима ускладиштеним у услугама на мрежи слажете се да се подаци могу преносити и складиштити са програмом Dynamics 365 Customer Insights .  [Сазнајте више у Мицрософт центру за поузданост](https://www.microsoft.com/trust-center).

- Видљиви Dataverse су само ентитети [са омогућеним](/power-platform/admin/enable-change-tracking-control-data-synchronization) праћењем промена. Ови ентитети се могу извести у језеро са подацима Dataverse којим се управља и користити у увидима купаца. Табеле без оквира Dataverse подразумевано имају омогућено праћење промена. Потребно је да укључите праћење промена за прилагођене табеле. Да бисте проверили да Dataverse ли је табела омогућена за праћење промена, идите на табеле [Power Apps](https://make.powerapps.com) > **података** > **·**. Пронађите табелу која вас интересује и изаберите је. Идите на **опције** > **"Више опција поставки"** и прегледајте поставку **праћења** промена.

## <a name="connect-to-a-dataverse-managed-lake"></a>Повежите се са Dataverse управљаним језером

1. Идите на **Подаци** > **Извори података**.

1. Изаберите **Додај извор података**.

1. Изаберите **Microsoft Dataverse**.

1. Унесите **име** за извор података и опционални **опис**.

1. Наведите **Адресу сервера** за Dataverse организацију и изаберите **Пријавите се**.

1. Изаберите табеле које желите да унестите као ентитете у увид купца са доступне листе.

   > [!NOTE]
   > Ако су неке табеле већ изабране, могу их користити друге Dynamics 365 апликације (попут Dynamics 365 Sales Insights или Customer Service Insights). Не можете променити избор. Ове табеле ће бити доступне као ентитети када се креира извор података.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Дијалог који приказује листу ентитета у Dataverse окружењу.":::

1. Сачувајте свој избор да бисте започели синхронизацију изабраних табела из услуге Dataverse. Новододату везу ћете пронаћи на страници **Извори података**. Биће стављено у ред за освежавање и приказаће број ентитета као 0 док се све изабране табеле не синхронизују.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Учитавање података може потрајати. Након успешног освежавања, унети подаци се могу редиговање са странице [**"Ентитети**](entities.md) ".

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Уредите извор података за Dataverse управљано језеро

Избор ентитета уређујете тек након што креирате извор података. На пример, ако су додати додатни ентитети у услугу Dataverse, а желите и да их увозите.
Да бисте се повезали са другим Dataverse језером података, [креирајте нови извор података](#connect-to-a-dataverse-managed-lake).

1. Идите на **Подаци** > **Извори података**.

1. Поред извор података желите да ажурирате, изаберите ставку **Уреди**.

1. Изаберите додатне ентитете са доступне листе ентитета.

1. Кликните **на дугме** "Сачувај" да бисте применили промене и вратили се на **страницу "Извори података** ".

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
