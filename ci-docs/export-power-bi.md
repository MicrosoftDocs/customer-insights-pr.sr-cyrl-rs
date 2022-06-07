---
title: Power BI конектор
description: Сазнајте како да користите Dynamics 365 Customer Insights конектор у услузи Power BI.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e901114703a43b4b4e751e0a93eb4876d7636c00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643637"
---
# <a name="connector-for-power-bi-preview"></a>Конектор за Power BI (преглед)

Направите визуелизације за своје податке помоћу услуге Power BI Desktop. Генеришите додатне увиде и правите извештаје помоћу обједињених података о клијентима.

## <a name="prerequisites"></a>Предуслови

- Имате обједињене профиле клијената.
- Најновија верзија апликације [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) је инсталирана на вашем рачунару. [Сазнајте више о Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Конфигуришите конектор за Power BI

1. У програму Power BI Desktop, изаберите **Датотека** > **Преузми податке**.

1. Изаберите **Прикажи још** и потражите **Dynamics 365 Customer Insights**

1. Изаберите **Повежи се**.

1. **Пријавите се** са истим организационим налогом који користите за Customer Insights и изаберите **Повежи се**.
   > [!NOTE]
   > Пословни контакт који наведете у овом кораку користи се за преузимање података из услуге Customer Insights и не мора бити исти са којим сте пријављени на Power BI. Да бисте ресетовали налог који се користи за преузимање података, отворите Power BI и идите на **Датотека** > **Опције** > **Подешавања** > **Подешавања извора података**. На листи извора података изаберите **Пријава на Dynamics 365 Customer Insights** и изаберите **Обриши дозволе**.  

1. У дијалогу **Навигатор**. видите листу свих окружења којима имате приступ. Проширите окружење и отворите било коју фасциклу (ентитети, мере, сегменти, обогаћивања). На пример, отворите фасциклу **Ентитети** да видите све ентитете које можете да увезете.

   ![Навигатор Power BI конектора.](media/power-bi-navigator.png "Навигатор Power BI конектора")

1. Означите поља за потврду поред ентитета које треба да укључите и **Учитај**. Можете да изаберете више ентитета, чак и из више окружења.

1. Видећете дијалог за учитавање док се ентитети учитавају. Након што се учитају сви изабрани ентитети, можете да користите могућности услуге Power BI за визуализацију података.

## <a name="large-data-sets"></a>Велики скупови података

Customer Insights конектор за Power BI је дизајниран да ради за скупове података који садрже до 1 милион корисничких профила. Увоз већих скупова података може да функционише, али то траје дуго. Поред тога, процес би могао наићи на временско ограничење због Power BI ограничења. За више информација, погледајте [Power BI: Препоруке за велике скупове података](/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Рад са подскупом података

Размислите о раду са подскупом података. На пример, можете да креирате[ сегменте](segments.md) уместо да извезе све евиденције клијената у Power BI.

## <a name="troubleshooting"></a>Решавање проблема

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Customer Insights окружење се не приказује у услузи Power BI

Окружења која имају више од једне релације [дефинисане](relationships.md) између два идентична ентитета у увидима клијената неће бити доступна у конектору Power BI.

Можете идентификовати и уклонити дупликате релација.

1. Идите на **односи** > **подаци** о окружењу у којем недостајете Power BI.
2. Идентификујте дупликате релација:
   - Проверите да ли постоји више релација дефинисаних између иста два ентитета.
   - Проверите да ли постоји релација креирана између два ентитета која су оба укључена у процес обједињавања. Дефинисана је имплицитна релација између свих ентитета укључених у процес уједињења.
3. Уклоните све препознате дупликате релација.

Када уклоните дупликате релација, покушајте да поново конфигуришете Power BI конектор. Окружење би требало да буде доступно већ сада.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Грешке у пољима датума при учитавању ентитета у услузи Power BI Desktop

Приликом учитавања ентитета који садрже поља са форматом датума попут ММ/ДД/ГГГГ, можете наићи на грешке због неусклађених формата за локални стандард. До овог неподударања се дешава када је Power BI Desktop датотека постављена на други локални стандард од енглеског (САД), јер се поља датума у увидима купаца чувају у америчком формату.

Power BI Desktop датотека има једно подешавање локалног стандарда, која се примењује при преузимању података. Да бисте исправно протумачили ова поља датума, поставите локални стандард .BPI датотеке на енглески (Сједињене Државе). [Сазнајте како да промените локални стандард Power BI Desktop датотеке](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop).

[!INCLUDE [footer-include](includes/footer-banner.md)]