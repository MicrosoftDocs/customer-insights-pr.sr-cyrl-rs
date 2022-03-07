---
title: Управљање колачићима и пристанком корисника за складиштење корисничких података у систему Dynamics 365 Customer Insights
description: Разумите како се колачићи и сагласност корисника користе за идентификацију посетилаца веб-странице.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 018263220d4628690e9f0beb8453e58b0356d099
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229003"
---
# <a name="manage-cookies-and-user-consent"></a>Управљајте колачићима и пристанком корисника

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dynamics 365 Customer Insights могућност увида у ангажовање користи колачиће и (`localStorage`) кључеве за идентификацију посетилаца веб-локације.

Колачићи су мале датотеке у којима се чувају комадићи информација о интеракцији корисника са веб-локацијом. Чувају се у веб-прегледачима. Када корисници посете веб-локацију за коју су ваши корисници сачували колачиће, прегледач шаље те информације серверу, који враћа информације које су јединствене за корисника. Ово је технологија која омогућава, на пример, корпу за куповину на мрежи да чува изабране артикле чак и ако корисник напусти веб-локацију.

## <a name="user-consent"></a>Пристанак корисника

[Општа уредба о заштити података (GDPR)](/dynamics365/get-started/gdpr/) је уредба Европске уније (ЕУ) која налаже како организације треба да поступају са приватношћу и безбедношћу својих корисника. Колачићи често чувају или прикупљају „личне податке“, као што је идентификатор присуства на мрежи, који је покривен GDPR-ом. Ако ваше предузеће запошљава и/или продаје субјектима података из ЕУ, GDPR утиче на вас. [Сазнајте више о томе како вам Microsoft може помоћи да се придржавате GDPR-а](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Да бисте омогућили SDK-у за увиде у ангажовање да чува колачића или друге осетљиве податке, морате да наведете да ли су ваши корисници дали пристанак. То се дешава приликом иницијализације SDK постављањем поља `userConsent` у конфигурацији.

Ако назначите да не постоји сагласност корисника, SDK неће чувати никакве податке и неће слати догађаје који се могу користити за праћење понашања корисника. Сви претходно сачувани подаци биће избрисани из прегледача.

Ако није наведена вредност сагласности корисника, SDK ће претпоставити да је корисник дао сагласност. То значи да ће се, ако ви (као наш клијент) не наведете вредност за сагласност корисника у SDK-у, подаци прикупљати. Међутим, ако наведете да вредност за сагласност корисника мора да буде „тачно“, подаци се неће прикупљати ако корисник одбије или не пружи изричиту сагласност.

Испод је фрагмент кода за покретање веб SDK-а са пристанком корисника:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Чување података о посетиоцима у могућности увида у ангажовање

### <a name="cookies"></a>Колачићи

- _msei
    - Складишти анонимни ID корисника. Овај колачић је постављен на домену клијента и истиче за 365 дана.

### <a name="local-storage"></a>Локално складиште

Могућност увида у ангажовање такође користи (`localStorage`) кључеве за праћење неосетљивих података. Ови подаци се у потпуности складиште у самом прегледачу, без саобраћаја који се шаље на ваше сервере или са њих.

- *EISession.Id*
    - Складишти информације о текућој сесији корисника, као што је ID сесије, када је започела и када истиче.
- *EISession.Previous*
    - Складишти URL адресу претходно посећене странице у тренутној сесији.

Кључеви у локалној меморији не истичу аутоматски и успоставиће почетне вредности се током следеће сесије SDK-а.

## <a name="deleting-cookies"></a>Брисање колачића

Ваши клијенти могу у било ком тренутку ручно да избришу колачиће и кључеве локалног складишта кроз подешавања свог прегледача.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
