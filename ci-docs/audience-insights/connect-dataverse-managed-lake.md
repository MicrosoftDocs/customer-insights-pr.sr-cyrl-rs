---
title: Повезивање са табелама у услузи Microsoft Dataverse
description: Увоз података из Microsoft Dataverse управљаног језера података.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: f92d64723e6a4d2fcebdbb3758519d4bfd4aeaf4
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692592"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Повежите се са подацима у Microsoft Dataverse управљаном језеру података

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Овај чланак пружа информације о томе како Dataverse корисници могу брзо да сае повежу са својим аналитичким ентитетима у Dataverse управљаном језеру. Морате бити администратор Dataverse организације како бисте наставили и видели списак ентитета доступних у управљаном језеру.

## <a name="important-considerations"></a>Важна разматрања

Подаци ускладиштени у мрежним услугама, као што је Azure Data Lake Storage, могу се складиштити на локацији различитој од оне на којој се подаци обрађују или складиште у услузи Dynamics 365 Customer Insights. Увозом или повезивањем података ускладиштених у мрежној услузи, слажете се да се подаци могу пренети и складиштити у услузи Dynamics 365 Customer Insights. [Сазнајте више у Microsoft центру за поузданост.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-dataverse-managed-lake"></a>Повежите се са Dataverse управљаним језером

1. У увидима о корисницима идите на **Подаци** > **Извори података**.

2. Изаберите **Додај извор података**.

3. Изаберите **Повезивање са Microsoft Dataverse управљаним језером** и изаберите **Даље**.

4. Унесите **Назив** извора података и изаберите **Следеће**. Смернице за називе: 
   - Започните словом.
   - Користите само слова и бројеве. Посебни знакови и размаци нису дозвољени.
   - Користите између 3 и 64 знака.

5. Наведите **Адресу сервера** за Dataverse организацију и изаберите **Пријавите се**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Екран у кораку уноса података где корисник може да унесе URL Dataverse окружења.":::

6. Изаберите табеле које желите да унесете као ентитете у увиде у циљну групу са доступне листе.    

   > [!NOTE]
   > Ако су неке табеле већ изабране, могу их користити друге Dynamics 365 апликације (попут Dynamics 365 Sales Insights или Customer Service Insights). Не можете променити избор. Ове табеле ће бити доступне као ентитети када се креира извор података.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Дијалог који приказује листу ентитета у Dataverse окружењу.":::

7. Сачувајте свој избор да бисте започели синхронизацију изабраних табела из услуге Dataverse. Новододату везу ћете пронаћи на страници **Извори података**. Биће стављено у ред за освежавање и приказаће број ентитета као 0 док се све изабране табеле не синхронизују.

Само један извор података окружења може истовремено да користи исто Dataverse надгледано језеро.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Уредите извор података за Dataverse управљано језеро

Избор ентитета уређујете тек након што креирате извор података. На пример, ако су додати додатни ентитети у услугу Dataverse, а желите и да их увозите.    
Да бисте се повезали са другим Dataverse језером података, [креирајте нови извор података](#connect-to-a-dataverse-managed-lake).

1. У увидима о корисницима идите на **Подаци** > **Извори података**.

2. Поред извора података који желите да ажурирате, изаберите три тачке.

3. Изаберите опцију **Уреди** са листе.

4. Изаберите додатне ентитете с доступне листе ентитета и изаберите **Сачувај**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]