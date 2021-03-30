---
title: Извезите Customer Insights податке у SendGrid
description: Сазнајте како да конфигуришете везу са услугом SendGrid.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597299"
---
# <a name="connector-for-sendgrid-preview"></a>Конектор за SendGrid (преглед)

Извезите сегменте обједињених профила клијената у SendGrid листе контаката и користите их за кампање и маркетинг у услузи SendGrid. 

## <a name="prerequisites"></a>Предуслови

-   Имате [SendGrid налог](https://sendgrid.com/) и одговарајуће акредитиве администратора.
-   Постоје постојеће листе контаката у услузи SendGrid и одговарајући ID-ови. За више информација погледајте [SendGrid – Управљање контактима](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   [Конфигурисали сте сегменте](segments.md) у увидима о корисницима.
-   Обједињени профили клијената у извезеним сегментима садрже поље које представља адресу е-поште.

## <a name="connect-to-sendgrid"></a>Повежите се са услугом SendGrid

1. Идите на **Администратор** > **Одредишта за извоз**.

1. У делу **SendGrid** изаберите **Подеси**.

1. Дајте одредишту за извоз препознатљиво име у пољу **Име за приказ**.

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Окно за конфигурацију извоза у услузи SendGrid.":::

1. Унесите свој **SendGrid API кључ** [SendGrid API кључ](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Унесите **[ID SendGrid листе](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. Изаберите **Прихватам** да бисте потврдили **Приватност података и усаглашеност**.

1. Изаберите **Повежи се** за иницијализацију везе са услугом SendGrid.

1. Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.

1. Изаберите **Следеће** да бисте конфигурисали извоз.

## <a name="configure-the-connector"></a>Конфигурисање конектора

1. У одељку **Подударање података**, у пољу **Адреса е-поште** изаберите поље у обједињеном профилу клијента које представља е-адресу клијента. Поновите исте кораке за друга опционална поља као што су **Име**, **Презиме**, **Земља/Регион**, **Држава**, **Град** и **Поштански број**.

1. Изаберите сегменте које желите да извезете. Изричито **препоручујемо да не извозите укупно више од 100.000 профила клијената** у SendGrid. 

1. Изаберите ставку **Сачувај**.

## <a name="export-the-data"></a>Извоз података

Можете да [извезете податке на захтев](export-destinations.md). Извоз ће се такође покренути са сваким [планираним освежавањем](system.md#schedule-tab).

## <a name="known-limitations"></a>Позната ограничења

- Укупно до 100.000 профила у SendGrid.
- Извоз у SendGrid је ограничен на сегменте.
- Извоз до 100.000 профила у SendGrid може да потраје до неколико сати. 
- Број профила које можете да извезете у SendGrid зависи од вашег уговора са компанијом SendGrid и ограничен је њиме.

## <a name="data-privacy-and-compliance"></a>Приватност података и усаглашеност

Када омогућите да Dynamics 365 Customer Insights преноси податке у SendGrid, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци. Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да SendGrid испуњава све обавезе приватности или безбедности које имате. За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.


[!INCLUDE[footer-include](../includes/footer-banner.md)]