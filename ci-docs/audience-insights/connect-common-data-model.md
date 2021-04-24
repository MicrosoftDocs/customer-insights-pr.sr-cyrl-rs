---
title: Повежите Common Data Model податке са Azure Data Lake налогом
description: Радите са Common Data Model подацима користећи Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 385406b706890d741fec2694c190c0fada7809d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596563"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Повежите се Common Data Model фасциклом која користи Azure Data Lake налог

Овај чланак пружа информације о томе како уносити податке из Common Data Model фасцикле помоћу Azure Data Lake Storage Gen2 налога.

## <a name="important-considerations"></a>Важна разматрања

- Подаци у вашем Azure Data Lake треба да прате уобичајени стандард Common Data Model. Други формати тренутно нису подржани.

- Унос података подржава само Azure Data Lake *Gen2* налоге за складиштење. Не можете да користите Azure Data Lake Gen1 налоге за складиштење за унос података.

- Да бисте потврдили идентитет помоћу принципала услуге Azure, уверите се да је конфигурисан у вашем закупцу. За више информација погледајте [Повезивање увида о корисницима са Azure Data Lake Storage Gen2 налогом помоћу принципала Azure услуге](connect-service-principal.md).

- Azure Data Lake са којим желите да се повежете и унесете податке мора бити у истом Azure региону као и Dynamics 365 Customer Insights окружење. Не подржавају се везе са Common Data Model фасциклом из језера података у другом Azure региону. Да бисте сазнали Azure регион окружења, посетите **Администратор** > **Систем** > **Основни подаци** у увидима о корисницима.

- Подаци који се чувају у услугама на мрежи могу се чувати на локацији која се разликује од оне на којој се подаци обрађују или чувају у услузи Dynamics 365 Customer Insights. Увозом или повезивањем података ускладиштених у мрежној услузи, слажете се да се подаци могу пренети и складиштити у услузи Dynamics 365 Customer Insights. [Сазнајте више у Microsoft центру за поузданост.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-model-folder"></a>Повежите се у фасциклу Common Data Model

1. У увидима о корисницима идите на **Подаци** > **Извори података**.

1. Изаберите **Додај извор података**.

1. Изаберите **Повежите се са Common Data Model фасциклом**, унесите **Име** за извор података и изаберите **Следеће**. Смернице за називе: 
   - Започните словом.
   - Користите само слова и бројеве. Посебни знакови и размаци нису дозвољени.
   - Користите између 3 и 64 знака.

1. Можете да бирате између коришћења опције засноване на ресурсима и опције засноване на претплати за потврду идентитета. За више информација погледајте [Повезивање увида о корисницима са Azure Data Lake Storage Gen2 налогом помоћу принципала Azure услуге](connect-service-principal.md). Унесите информације о **Контејнеру** и изаберите **Следеће**.
   > [!div class="mx-imgBorder"]
   > ![Дијалог за унос нових детаља везе за Azure Data Lake](media/enter-new-storage-details.png)
   > [!NOTE]
   > Потребна вам је једна од следећих улога у контејнеру или налогу за складиштење поменутом горе да бисте могли да се повежете и креирате извор података:
   >  - Читач података складишта блоб објекта
   >  - Власник података складишта блоб објекта
   >  - Сарадник за податке складишта блоб објекта

1. У дијалогу **Изаберите Common Data Model фасциклу**, изаберите датотеку model.json или manifest.json из које желите да увезете податке, па изаберите **Следеће**.
   > [!NOTE]
   > Ниједна датотека model.json или manifest.json повезана са другим извором података у окружењу неће се приказати на листи.

1. Листу доступних ентитета добићете у изабраној датотеци model.json или manifest.json. Можете да прегледате ентитете и изаберете их са листе доступних ентитета, па изаберите **Сачувај**. Сви изабрани ентитети биће унети из новог извора података.
   > [!div class="mx-imgBorder"]
   > ![Дијалог који приказује листу ентитета из датотеке model.json](media/review-entities.png)

8. Наведите ентитете података за које желите да омогућите профилисање података и изаберите **Сачувај**. Профилисање података омогућава аналитику и друге могућности. Можете одабрати читав ентитет који бира све атрибуте из ентитета или одабрати одређене атрибуте по свом избору. Подразумевано ниједан ентитет није омогућен за профилисање података.
   > [!div class="mx-imgBorder"]
   > ![Дијалог који приказује профилисање података](media/dataprofiling-entities.png)

9. Када сачувате изабране опције, отвориће се страница **Извори података**. Сада би требало да видите везу Common Data Model фасцикле као извор података.

> [!NOTE]
> Датотека model.json или manifest.json може се повезати само са једним извором података у истом окружењу. Међутим, иста датотека model.json или manifest.json може се користити за изворе података у више окружења.

## <a name="edit-a-common-data-model-folder-data-source"></a>Уредите извор података Common Data Model фасцикле

Можете да ажурирате приступни кључ за налог за складиштење који садржи Common Data Model фасциклу. Такође можете променити датотеку model.json или manifest.json. Да бисте се повезали на други контејнер са налога за складиштење или да промените име налога, [креирајте нову везу са извором података](#connect-to-a-common-data-model-folder).

1. У увидима о корисницима идите на **Подаци** > **Извори података**.

2. Поред извора података који желите да ажурирате, изаберите три тачке.

3. Изаберите опцију **Уреди** са листе.

4. Опционално, ажурирајте **Кључ за приступ** и изаберите **Следеће**.

   ![Дијалог за уређивање и ажурирање кључа за приступ за постојећи извор података](media/edit-access-key.png)

5. По жељи можете да ажурирате са везе кључа налога на везу засновану на ресурсима или претплати. За више информација погледајте [Повезивање увида о корисницима са Azure Data Lake Storage Gen2 налогом помоћу принципала Azure услуге](connect-service-principal.md). Не можете променити информације о **контејнеру** приликом ажурирања везе.
   > [!div class="mx-imgBorder"]

   > ![Дијалог за унос детаља везе услуге Azure Data Lake са постојећим налогом за складиштење](media/enter-existing-storage-details.png)

   > [!NOTE]
   > Потребна вам је једна од следећих улога у контејнеру или налогу за складиштење поменутом горе да бисте могли да се повежете и креирате извор података:
   >  - Читач података складишта блоб објекта
   >  - Власник података складишта блоб објекта
   >  - Сарадник за податке складишта блоб објекта


6. Опционално, одаберите другу датотеку model.json или manifest.json са различитим скупом ентитета из контејнера.

7. По жељи можете одабрати додатне ентитете за унос. Такође можете уклонити све већ одабране ентитете ако нема зависних елемената.

   > [!IMPORTANT]
   > Ако постоје зависности од постојеће датотеке model.json или manifest.json и скупа ентитета, видећете поруку о грешци и не можете да изаберете другу датотеку model.json или manifest.json. Уклоните те зависности пре промене датотеке model.json или manifest.json или креирајте нови извор података са датотеком model.json или manifest.json коју желите да користите да бисте избегли уклањање зависности.

8. По жељи можете одабрати додатне атрибуте или ентитете како бисте омогућили профилисање података или онемогућили већ одабране.   


[!INCLUDE[footer-include](../includes/footer-banner.md)]