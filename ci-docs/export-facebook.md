---
title: Извоз сегмената у Facebook Адс Манагер (преглед) (садржи видео)
description: Сазнајте како да конфигуришете везу и извезете у Facebook Ads Manager.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c7a4b1be1c959d70fad929b56452169b40e5b592
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724634"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Извоз сегмената у Facebook Менаџер за огласе (преглед)

Извезите сегменте обједињених корисничких профила у Facebook менаџер огласа за креирање кампања на Facebook и Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>Предуслови

- Налог [Facebook огласа](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) који укључује пословни [Facebook налог](https://business.facebook.com/).
- Администраторске привилегије на Налогу [Facebook огласа](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).
- Прилагођене корисници потребно је прихватити од стране корисника који подешава везу у "Увидима купаца".

## <a name="known-limitations"></a>Позната ограничења

- До 10 милиона профила клијената по извозу у Facebook Адс Манагер, што може да потраје и до 90 минута.
- Само сегменти.
- Facebook Интеграција огласа не подржава кориснике са више од 25 огласних налога.
- Facebook *тип листе купаца* само у [прилагођеним корисницима](https://www.facebook.com/business/help/744354708981227?id=2469097953376494) локације.
  > [!NOTE]
  > У неким случајевима можете видети прилагођене групе различитих типова на падајуће листе. Ако изаберете неки други тип осим листе *купаца*, извоз неће успети.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Подешавање везе са услугом Facebook Ads Manager

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Идите на **Администратор** > **Везе**.

1. Изаберите **додај везу и** одаберите Менаџер **Facebook за огласе**.

1. Дајте вези препознатљиво име у пољу **Име за приказ**. Име за приказ и врста везе описују ову везу. Препоручујемо да одаберете назив који објашњава сврху и циљ везе.

1. [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Потврдите веродостојност помоћу услуге Facebook Ads:

   1. Изаберите **Настави са Facebook-ом** да бисте се пријавили на свој Facebook Ads налог.

   1. Дајте дозволу **ads_management** након потврде идентитета са услугом Facebook.

   1. Изаберите **Facebook налог за оглашавање** са којим желите да радите.

   1. Изаберите **Постојећа прилагођена циљна група** са падајуће листе или креирајте **нову прилагођену циљну групу**.

1. Прегледајте приватност [и усаглашеност података и](connections.md#data-privacy-and-compliance) изаберите И **слажем се**.

1. Изаберите **Сачувај** да бисте креирали везу.

## <a name="configure-an-export"></a>Конфигурисање извоза

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Идите на **Подаци** > **Извози**.

1. Изаберите **Додај извоз**.

1. У пољу **Веза за извоз** одаберите везу из одељка Менаџер Facebook за огласе. Ако веза није доступна, обратите се администратору.

1. Унесите име за извоз.

1. У пољу Повезивање **података** изаберите е-пошту **·**, име **и адресу** или телефон који **ћете** послати менаџеру Facebook огласа.

1. Мапирајте одговарајуће атрибуте вашег обједињеног ентитета клијента за изабрани идентификатор кључа.
   > [!TIP]
   > Најбоље шансе за подударање настају ако одаберете опцију **Е-пошта** као кључни идентификатор. Додавање додатних идентификатора може побољшати подударање.

1. Изаберите **Додај атрибут** да бисте мапирали више атрибута за слање у Facebook Ads Manager. Атрибути из услуге Facebook Ads Manager се пресликавају на следећа имена прилагођена кориснику: **FN** = **Име**, **LN** = **Презиме**, **FI** = **Прво слово имена**, **PHONE** = **Телефон**, **GEN** = **Пол**, **DOB** = **Датум рођења**, **ST** = **Држава**, **CT** = **Град**, **ZIP** = **Поштански број**, **COUNTRY** = **Земља**

1. Изаберите сегменте које желите да извезете.

1. Изаберите **Сачувај**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
