---
title: Креирање и конфигурисање плаћене лиценце решења Customer Insights
description: Кораци за добијање лиценциране претплате за Dynamics 365 Customer Insights и његово конфигурисање.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b5f76f4c468b88aaf7037dbd2ee3bed449fbeaa5f645d52278eee05b36b4e328
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034470"
---
# <a name="get-started-with-a-paid-subscription"></a>Први кораци уз плаћену претплату

Овај чланак објашњава како да креирате ново окружење након што је ваша организација купила Dynamics 365 Customer Insights претплату. Ако желите да купите решење Customer Insights, наше опције за контакт су наведене на [Dynamics 365 Customer Insights веб-локацији](https://dynamics.microsoft.com/ai/customer-insights/). 

Ако желите да испробате услугу и функције, погледајте [Конфигурисање пробног окружења](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>Креирајте окружење у постојећој организацији

Након што купите претплатничку лиценцу за Customer Insights, глобални администратор Microsoft 365 закупца прима поруку е-поште која га позива да креира окружење. Идите на [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start) да бисте започели. 

Customer Insights није лиценциран по кориснику, па се неће приказивати у подручју Лиценце. Ако тражите лиценцу у Microsoft 365 центру администрације, идите на **Ваши производи**. 

> [!NOTE]
> Организације могу да креирају *два* окружења за сваку Customer Insights лиценцу. Ако ваша организација више пута купи лиценцу, [контактирајте наш тим за подршку](https://go.microsoft.com/fwlink/?linkid=2079641) да бисте повећали број доступних окружења. За више информација о капацитету и додатном капацитету преузмите [Dynamics 365 водич за лиценцирање](https://go.microsoft.com/fwlink/?LinkId=866544).

Да бисте креирали окружења:

1. У дијалогу **Креирање окружења**, изаберите **Ново окружење**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Дијалог за креирање новог Customer Insights окружења.":::

   Препоручујемо да започнете са конфигурисањем окружења од почетка. Међутим, ако сте администратор или члан пробног окружења, могли бисте [да копирате податке из другог окружења](manage-environments.md#copy-the-environment-configuration), избором опције **Копирај из постојећег окружења**. Видећете листу свих доступних окружења у вашој организацији, одакле можете копирати податке.

1. Наведите следеће детаље:
   - **Назив**: Унесите назив овог окружења. Ово поље је већ попуњено ако сте копирали постојеће окружење, али можете га променити.
   - **Регион**: Регион у којем је услуга примењена и хостована.
   - **Тип**: изаберите да ли желите да креирате производно или Sandbox окружење. Sandbox окружења не дозвољавају заказано освежавање података и намењена су за предимплементацију и тестирање.
   
1. По жељи можете одабрати **Напредна подешавања**:

   - **Сачувај све податке у**: Одређује где желите да сачувате излазне податке генерисане у услузи Customer Insights. Имаћете две могућности: **Customer Insights складиште** (Azure Data Lake којим управља Customer Insights тим) и **Azure Data Lake Storage** (ваш сопствени Azure Data Lake Storage). Подразумевано је одабрана опција Customer Insights складишта.

     > [!NOTE]
     > Чувањем података у услузи Azure Data Lake Storage, слажете се да ће подаци бити пренети и ускладиштени на одговарајућој географској локацији за тај Azure налог за складиштење, која може да се разликује од места складиштења података у услузи Dynamics 365 Customer Insights. [Сазнајте више у Microsoft центру за поузданост.](https://www.microsoft.com/trust-center)
     >
     > Тренутно се унети ентитети из Power BI токова података увек чувају у Microsoft Dataverse управљаној услузи Data Lake. 
     > 
     > Подржавамо само Azure Data Lake Storage налоге из истог Azure региона који сте изабрали приликом креирања окружења. 
     > 
     > Подржавамо само Azure Data Lake Storage налоге који имају омогућен хијерархијски простор имена.


   - За опцију Azure Data Lake Storage, можете одабрати између опције засноване на ресурсима и опције засноване на претплати за потврду идентитета. За више информација погледајте [Повезивање увида о корисницима са Azure Data Lake Storage Gen2 налогом помоћу принципала Azure услуге](connect-service-principal.md). Назив **Контејнер** се не може променити и биће `customerinsights`.
   
   - Ако желите да користите [готове моделе](predictions-overview.md#out-of-box-models), конфигуришите дељење података са услугом Microsoft Dataverse или омогућите унос података из локалних извора података, наведите URL адресу Microsoft Dataverse окружења у оквиру опције **Конфигуришите дељење података са услугом Microsoft Dataverse и омогућите додатне могућности**. Изаберите **Омогући дељење података** да бисте делили Customer Insights излазне податке помоћу платформе Microsoft Dataverse Managed Data Lake.

     > [!NOTE]
     > - Дељење података помоћу услуге Microsoft Dataverse Managed Data Lake тренутно није подржано када све податке чувате у сопственом Azure Data Lake Storage.
     > - [Предвиђање вредности које недостају у ентитету](predictions.md) тренутно није подржано када омогућите дељење података са платформом Microsoft Dataverse Managed Data Lake.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Опције конфигурације за омогућавање дељења података са платформом Microsoft Dataverse.":::

   Када систем обради потпуни унос података, систем креира одговарајуће фасцикле на налогу за складиштење који сте навели. Датотеке са подацима и model.json датотеке се креирају и додају у фасцикле на основу назива процеса.

   Ако креирате више окружења за Customer Insights и одлучите да сачувате излазне ентитете из тих окружења на свом налогу за складиштење, креираће се засебне фасцикле за свако окружење са ci_<environmentid> у контејнеру.

1. Изаберите **Креирај** да бисте конфигурисали окружење. 

## <a name="configure-an-environment"></a>Конфигурисање окружења

Прегледајте следеће чланке који ће вам помоћи да започнете са конфигурисањем решења Customer Insights. 

- [Додајте још корисника и доделите дозволе](permissions.md).
- [Унесите своје изворе података](data-sources.md) и провуците их кроз [процес обједињавања података](data-unification.md) како бисте добили [обједињене профиле клијената](customer-profiles.md).
- [Обогатите обједињене профиле клијената](enrichment-hub.md) или [покрените моделе предвиђања](predictions-overview.md).
- Креирајте [сегменте](segments.md) да бисте груписали клијенте и [мере](measures.md) прегледајте KPI показатеље.
- Подесите [везе](connections.md) и [извозе](export-destinations.md) за обраду подскупова података у другим апликацијама.
