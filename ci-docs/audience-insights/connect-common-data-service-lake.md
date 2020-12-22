---
title: Повежите се са ентитетима у Common Data Service надгледаном језеру
description: Увоз података из Common Data Service управљаног језера података.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643416"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Повежите се са подацима у Common Data Service управљаном језеру података

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Овај чланак пружа информације о томе како постојећи Dynamics 365 корисници могу брзо да се повежу са својим аналитичким ентитетима у Common Data Service управљаном језеру. Морате бити администратор Common Data Service организације како бисте наставили и видели списак ентитета доступних у управљаном језеру.

## <a name="important-considerations"></a>Важна разматрања

Подаци ускладиштени у мрежним услугама, као што је Azure Data Lake Storage, могу се складиштити на локацији различитој од оне на којој се подаци обрађују или складиште у услузи Dynamics 365 Customer Insights. Увозом или повезивањем података ускладиштених у мрежној услузи, слажете се да се подаци могу пренети и складиштити у услузи Dynamics 365 Customer Insights. [Сазнајте више у Microsoft центру за поузданост.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Повежите се са Common Data Service управљаним језером

1. У увидима о корисницима идите на **Подаци** > **Извори података**.

2. Изаберите **Додај извор података**.

3. Изаберите **Повезивање са услугом Common Data Service** и изаберите **Следеће**.

4. Унесите **Назив** извора података и изаберите **Следеће**.

5. Наведите **Адресу сервера** за вашу Common Data Service организацију и изаберите **Пријавите се**.

   > [!div class="mx-imgBorder"]
   > ![Дијалог за унос Common Data Service адресе сервера](media/enter-CDS-org-details.png)

6. Изаберите ентитете које желите да унесете са доступне листе.    

   > [!NOTE]
   > Ако су неки ентитети већ изабрани, могу их користити друге Dynamics 365 апликације (као што су Dynamics 365 Sales Insights или Customer Service Insights). Не можете променити избор. Ови ентитети ће бити доступни након креирања извора података.

   > [!div class="mx-imgBorder"]
   > ![Дијалог који приказује листу ентитета у Common Data Service организацији](media/select-analytical-entities.png)

7. Сачувајте свој избор да бисте започели синхронизацију изабраних ентитета са Common Data Service управљаним језером. Новододату везу ћете пронаћи на страници **Извори података**. Биће постављена у ред за освежавање и приказаће бројеве ентитета као 0 док се сви ентитети не синхронизују.

Само један извор података окружења може истовремено да користи исто Common Data Service надгледано језеро.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Уредите извор података за Common Data Service управљано језеро

Избор ентитета уређујете тек након што креирате извор података. На пример, ако су додати додатни ентитети у услугу Common Data Service, а желите и да их увозите.    
Да бисте се повезали са другом услугом Common Data Service, [креирајте нови извор података](#connect-to-a-common-data-service-managed-lake).

1. У увидима о корисницима идите на **Подаци** > **Извори података**.

2. Поред извора података који желите да ажурирате, изаберите три тачке.

3. Изаберите опцију **Уреди** са листе.

4. Изаберите додатне ентитете с доступне листе ентитета и изаберите **Сачувај**.
