---
title: Извоз сегмената у Constant Contact (верзија за преглед)
description: Сазнајте како да конфигуришете везу и извезете садржај у Constant Contact.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4d2ec29c194dc481ee40048b8ecbed813291b4d2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196504"
---
# <a name="export-segments-to-constant-contact-preview"></a>Извоз сегмената у Constant Contact (верзија за преглед)

Извезите сегменте обједињених профила клијената у Constant Contact и користите их за маркетиншке активности.

## <a name="prerequisites"></a>Предуслови

- Налог [сталног контакта](https://www.constantcontact.com/account-home) и одговарајући администраторски акредитиви.
- [ИД листе сталних контаката](https://app.constantcontact.com/pages/contacts/ui#lists). Отворите листу у услузи Constant Contact да бисте пронашли ID листе у URL адреси.
- [Конфигурисани сегменти у увидима](segments.md) купаца.
- Обједињени кориснички профили у извезеним сегментима садрже поље које представља адресу е-поште.

## <a name="known-limitations"></a>Позната ограничења

- До милион профила клијената по извозу у Стални контакт, што може да потраје и до сат времена. Број профила купаца које можете извести у "Стални контакт" зависи од уговора са сталним контактом.
- Само сегменти.

## <a name="set-up-connection-to-constant-contact"></a>Подешавање везе са услугом Constant Contact

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Идите на **Администратор** > **Везе**.

1. Изаберите **додај везу и** одаберите ставку **Стални контакт**.

1. Дајте вези препознатљиво име у пољу **Име за приказ**. Име за приказ и врста везе описују ову везу. Препоручујемо да одаберете назив који објашњава сврху и циљ везе.

1. Одаберите ко може да користи ову везу. Подразумевано су то само администратори. За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Прегледајте приватност [и усаглашеност података и](connections.md#data-privacy-and-compliance) изаберите И **слажем се**.

1. Кликните **на дугме** "Повежи" да бисте повезали везу.

1. Изаберите **Потврдите аутентичност са услугом Constant Contact** и наведите администраторске акредитиве за Constant Contact.

1. Изаберите **Додајте себе као корисника за извоз** и обезбедите своје акредитиве за Customer Insights.

1. Изаберите **Сачувај** да бисте креирали везу.

## <a name="configure-an-export"></a>Конфигурисање извоза

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Идите на **Подаци** > **Извози**.

1. Изаберите **Додај извоз**.

1. У пољу **Веза за извоз**, одаберите везу из одељка Constant Contact. Ако веза није доступна, обратите се администратору.

1. Унесите име за извоз.

1. Унесите ИД **листе сталних контаката**.

1. У одељку **Подударање података**, у пољу **Е-пошта**, изаберите поље које представља е-адресу клијента.

1. Опционално, извезите **име** и **презиме као додатна** поља да бисте креирали персонализованије е-поруке. Изаберите **Додај атрибут** за мапирање ових поља.

1. Изаберите сегменте које желите да извезете.

1. Изаберите **Сачувај**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
