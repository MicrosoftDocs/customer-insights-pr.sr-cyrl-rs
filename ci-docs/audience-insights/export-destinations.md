---
title: Одредишта за извоз
description: Извезите податке и управљајте одредиштима за извоз.
ms.date: 07/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5557442983f8c48cd46387009e0060beb6e764bb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596104"
---
# <a name="export-destinations-preview-overview"></a>Преглед одредишта за извоз (преглед)

Страница **Одредишта за извоз** приказује све локације на које сте поставили извоз података. Такође можете додати нова одредишта за извоз. Поред тога, приказује извоз тренутно доступних опција. Преузмите брзи преглед, опис и сазнајте шта можете урадити са сваком опцијом проширивости. Извезите обједињене профиле, мере и сегменте у подржане апликације релевантне за ваше пословање.

Идите на **Администратор** > **Извоз одредишта** да бисте пронашли следеће опције проширења:

- [Adobe Campaign Standard](export-adobe-campaign-standard.md)
- [Adobe платформа искуства](export-adobe-experience-platform.md)
- [AdRoll](export-adroll.md)
- [Autopilot](export-autopilot.md)
- [Azure складиште блоб објекта](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [Робот за Microsoft Teams](export-teams-bot.md)
- [Customer Insights API](apis.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Customer Service (програмски додатак за картицу клијента)](customer-card-add-in.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 чвориште за продају (програмски додатак за картицу клијента)](customer-card-add-in.md)
- [Facebook менаџер огласа](export-facebook.md)
- [Google огласи](export-google-ads.md)
- [LiveRamp&reg;](export-liveramp.md)
- [Mailchimp](export-mailchimp.md)
- [Marketo](export-marketo.md)
- [Power Automate](export-power-automate.md)
- [Power Apps](export-power-apps.md)
- [Power BI](export-power-bi.md)
- [SendGrid](export-sendgrid.md)
- [SFTP](export-sftp.md)

## <a name="add-a-new-export-destination"></a>Додавање новог одредишта за извоз

Да бисте додали одредишта за извоз, имате [администраторске дозволе](permissions.md). Ако извозите у Microsoft услуге, претпостављамо да су обе услуге у истој организацији.

1. Идите на **Администратор** > **Одредишта за извоз**.

1. Пребаците се на картицу **Моја одредишта за извоз**.

1. Изаберите **Додавање одредишта** да бисте креирали ново одредиште за извоз.

1. У окну **Додавање одредишта**, изаберите **Тип** одредишта за извоз у падајућој листи.

1. Наведите потребне детаље и изаберите **Следеће** да креирате одредиште за извоз.

Такође можете да изаберете **Подешавање** на плочици на картици **Откривање**.

## <a name="view-export-destinations"></a>Приказ одредишта за извоз

Када креирате одредишта за извоз, наћи ћете их у табели на картици **Моја одредишта за извоз**. Ова табела има три колоне:

- **Име за приказ**: Име које сте унели приликом креирања одредишта.
- **Тип**: Врста одредишта за извоз коју сте поставили приликом креирања одредишта.
- **Креирано**: Датум кад сте креирали одредиште.

## <a name="edit-an-export-destination"></a>Уређивање одредишта за извоз

1. Изаберите вертикалне три тачке за одредиште за извоз које желите да уређујете.

   > [!div class="mx-imgBorder"]
   > ![Вертикалне три тачке](media/export-destinations-page-ellipsis.png "Вертикалне три тачке")

1. Изаберите **Уређуј** из падајућег менија.

1. Промените вредности за које је потребно ажурирање и изаберите **Сачувај**.

## <a name="export-data-on-demand"></a>Извоз података на захтев

Након конфигурисања конектора за одредиште за извоз, извози ће се покренути са сваким [заказаним освежавањем](system.md#schedule-tab).

Да бисте извезли податке без чекања на заказано освежавање, идите на картицу **Моја одредишта за извоз** у дијалогу **Администратор** > **Одредишта за извоз**.

> [!div class="mx-imgBorder"]
> ![Вертикалне три тачке](media/export-destinations-page-ellipsis.png "Вертикалне три тачке")

- Изаберите **Извези** изнад листе да бисте истовремено покренули извоз у сва одредишта за извоз.
- Изаберите три тачке (...) након ставке листе, а затим одаберите опцију **Извези** за покретање извоза за једно одредиште за извоз.

## <a name="remove-an-export-destination"></a>Уклањање одредиште за извоз

Да бисте уклонили одредиште за извоз, почните из главне странице **Одредишта за извоз**.

1. Одаберите вертикалне три тачке за одредиште за извоз које желите да уклоните.

   > [!div class="mx-imgBorder"]
   > ![Вертикалне три тачке](media/export-destinations-page-ellipsis.png "Вертикалне три тачке")

2. Изаберите **Уклони** из падајућег менија.

3. Потврдите уклањање одабиром **Уклони** на екрану за потврду.


[!INCLUDE[footer-include](../includes/footer-banner.md)]