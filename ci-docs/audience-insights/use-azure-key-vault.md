---
title: Донесите свој властити Azure Key Vault за управљање тајнама
description: Научите како да конфигуришете Customer Insights да користите сопствени Azure Key Vault.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 418575f724090628da8bd01e2569a4cb9e646337
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376526"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Донесите свој властити Azure Key Vault (верзија за преглед)

Повезивање наменског [Azure Key Vault-а](/azure/key-vault/general/basic-concepts) у окружење увида у циљну групу помаже организацијама да испуне захтеве усклађености.
Наменско безбедносно складиште може да се користи за постављање и коришћење тајни у границама усклађености организације. Увиди у циљну групу могу користити тајне у Azure Key Vault-у за [успостављање веза](connections.md) са системима трећих страна.

## <a name="link-the-key-vault-to-the-audience-insights-environment"></a>Повезивање безбедносног складишта са окружењем увида у циљну групу

### <a name="prerequisites"></a>Предуслови

Да бисте конфигурисали безбедносно складиште у увидима у циљну групу, морају бити испуњени следећи предуслови:

- Имате активну Azure претплату.

- Имате улогу [администратора](permissions.md#admin) у увидима у циљну групу. Сазнајте више о [корисничким дозволама у увидима у циљну групу](permissions.md#assign-roles-and-permissions).

- Имате улоге [Сарадник](/azure/role-based-access-control/built-in-roles#contributor) и [Администратор корисничког приступа](/azure/role-based-access-control/built-in-roles#user-access-administrator) у безбедносном складишту или групи ресурса којој припада безбедносно складиште. За још информација идите на [Додавање или уклањање Azure додела улога користећи Azure портал](/azure/role-based-access-control/role-assignments-portal). Ако немате улогу администратора корисничког приступа у безбедносном складишту, морате засебно успоставити дозволе контроле приступа засноване на улогама за принципала услуге Azure за Dynamics 365 Customer Insights. Пратите кораке да бисте [користили принципала услуге Azure](connect-service-principal.md) за безбедносно складиште које треба повезати.

- Безбедносно складиште мора имати **онемогућен** заштитни зид услуге Key Vault.

- Безбедносно складиште је на истој [Azure локацији](https://azure.microsoft.com/global-infrastructure/geographies/#overview) као окружење увида у циљну групу. Регион окружења у увидима у циљну групу је наведен у оквиру опције **Администратор** > **Систем** > **О систему** > **Регион**.

### <a name="link-a-key-vault-to-the-environment"></a>Повезивање безбедносног складишта са окружењем

1. Идите у **Администратор** > **Систем**, а затим изаберите картицу **Безбедност**.
1. На плочици **Безбедносно складиште**, изаберите **Подешавање**.
1. Одаберите **претплату**.
1. Одаберите безбедносно складиште са падајуће листе **Безбедносно складиште**. Ако се приказује превише безбедносних складишта, изаберите групу ресурса да бисте ограничили резултате претраге.
1. Прихватите изјаву о **Приватности података и усклађености**.
1. Изаберите ставку **Сачувај**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Кораци за успостављање повезаног безбедносног складишта у увидима у циљну групу.":::

Плочица **Безбедносно складиште** сада приказује назив повезаног безбедносног складишта, групу ресурса и претплату. Спреман је за коришћење у подешавању везе.
За детаље о томе које су дозволе за безбедносно складиште додељене увидима у циљну групу, идите на [Дате дозволе у безбедносном складишту за увиде у циљну групу](#permissions-granted-on-the-key-vault-to-audience-insights), касније у овом чланку.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Коришћење безбедносног складишта у подешавању везе

Када [подешавате везе](connections.md) са системима трећих страна, тајне из повезаног Key Vault-а могу се користити за конфигурисање веза.

1. Идите на **Администратор** > **Везе**.
1. Изаберите **Додај везу**.
1. За подржане типове веза, прекидач за **Користите безбедносно складиште** је доступан ако сте повезали безбедносно складиште.
1. Уместо да ручно уносите тајну, можете изабрати назив тајне који указује на вредност тајне у безбедносном складишту.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Окно за повезивање са SFTP везом која користи тајну безбедносног складишта.":::

## <a name="supported-connection-types"></a>Подржани типови веза

Следеће везе за [извоз](export-destinations.md) су подржане:

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google огласи](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault-to-audience-insights"></a>Дозволе дате у безбедносном складишту за увиде у циљну групу

Следеће дозволе су одобрене увидима у циљну групу на повезаном безбедносном складишту ако су омогућени или [Политика приступа за Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) или [Azure контрола приступа заснована на улогама](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

### <a name="key-vault-access-policy"></a>Политика приступа за Key Vault

| Тип        | Дозволе          |
| ----------- | -------------------- |
| Тастер         | [Прибавите кључеве](/rest/api/keyvault/get-keys), [Прибавите кључ](/rest/api/keyvault/get-key)                                 |
| Тајни      | [Прибавите тајне](/rest/api/keyvault/get-secrets), [Прибавите тајну](/rest/api/keyvault/get-secret)                     |
| Цертификат | [Прибавите цертификате](/rest/api/keyvault/get-certificates), [Прибавите цертификат](/rest/api/keyvault/get-certificate) |

Претходне вредности су минимум за навођење и читање током извршавања.

### <a name="azure-role-based-access-control"></a>Azure контрола приступа заснована на улогама

Корисничке улоге Читач безбедносног складишта и Тајне безбедносног складишта биће додате за увиде у циљну групу. За детаље о овим улогама идите на [Уграђене Azure улоге за операције равни података у Key Vault-у](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Препоруке

- Користите засебно или наменско безбедносно складиште које садржи само тајне потребне за увиде у циљну групу. Прочитајте више о томе зашто [се препоручују засебна безбедносна складишта](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Пратите [најбоље праксе за коришћење безбедносних складишта](/azure/key-vault/general/best-practices#turn-on-logging) за опције контроле приступа, прављења резервних копија, ревизије и опоравка.

## <a name="frequently-asked-questions"></a>Најчешћа питања

### <a name="can-audience-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Могу ли увиди у циљну групу уписати тајне или заменити их у безбедносном складишту?

Не. Само дозволе за читање и навођење на листи наведене у одељку [одобрене дозволе](#permissions-granted-on-the-key-vault-to-audience-insights) раније у овом чланку имају дозволу за приступ увидима у циљну групу. Систем не може да додаје, брише или замењује тајне у безбедносном складишту. То је и разлог зашто не можете да унесете акредитиве када веза користи Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Могу ли да променим везу са коришћења тајни за Key Vault на подразумевану потврду идентитета?

Не. Не можете се вратити на подразумевану везу након што сте је конфигурисали помоћу тајне из повезаног безбедносног складишта. Креирајте засебну везу и избришите стару ако вам више не треба.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-audience-insights"></a>Како могу опозвати приступ безбедносном складишту за увиде у циљну групу?

У зависности од тога да ли је омогућено [Политика приступа за Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) или [Azure контрола приступа заснована на улогама](/azure/key-vault/general/rbac-guide?tabs=azure-cli), морате уклонити дозволе за принципала услуге `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` са именом `Dynamics 365 AI for Customer Insights`. Све везе које користе безбедносно складиште ће престати да раде.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Тајна која се користи у вези уклоњена је из безбедносног складишта. Шта могу да урадим?

Обавештење се појављује у увидима о циљној групи када конфигурисана тајна из безбедносног складишта више није доступна. Омогућите [меко брисање](/azure/key-vault/general/soft-delete-overview) у безбедносном складишту за враћање тајни ако су случајно уклоњене.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Веза не функционише, али моја тајна је у безбедносном складишту. Шта би могао бити узрок?

Обавештење се појављује у увидима о циљној групи када не може да приступи безбедносном складишту. Узрок би могао бити:

- Уклоњене су дозволе за принципала услуге увида у циљну групу. Потребно их је ручно вратити.

- Заштитни зид на безбедносном складишту је омогућен. Заштитни зид мора бити онемогућен како би безбедносно складиште поново било доступно за увиде у циљну групу.
