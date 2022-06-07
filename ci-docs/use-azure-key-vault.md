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
ms.openlocfilehash: d4f2d5ebc828053c40e22065f4915c4d0f84153f
ms.sourcegitcommit: 6ec4626a185892dfb781d3c7af4384f9c13f3723
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 05/17/2022
ms.locfileid: "8763597"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Донесите свој властити Azure Key Vault (верзија за преглед)

Повезивање наменског Азуре [кључа трезора са окружењем](/azure/key-vault/general/basic-concepts) увида клијената помаже организацијама да испуне услове усаглашености.
Наменско безбедносно складиште може да се користи за постављање и коришћење тајни у границама усклађености организације. Увиди клијената могу да користе тајне у Азуре кључ трезору за [подешавање веза са системима](connections.md) независних произвођача.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Повезивање кључног трезора са окружењем увида купаца

### <a name="prerequisites"></a>Предуслови

Да бисте конфигурисали кључни трезор у увидима клијената, морају бити испуњени следећи предуслови:

- Имате активну Azure претплату.

- Имате улогу администратора [у](permissions.md#admin) "Увидима клијената". Сазнајте више о корисничким [дозволама у фасцикли "Увиди клијената"](permissions.md#assign-roles-and-permissions).

- Имате улоге [Сарадник](/azure/role-based-access-control/built-in-roles#contributor) и [Администратор корисничког приступа](/azure/role-based-access-control/built-in-roles#user-access-administrator) у безбедносном складишту или групи ресурса којој припада безбедносно складиште. За још информација идите на [Додавање или уклањање Azure додела улога користећи Azure портал](/azure/role-based-access-control/role-assignments-portal). Ако немате улогу администратора корисничког приступа у безбедносном складишту, морате засебно успоставити дозволе контроле приступа засноване на улогама за принципала услуге Azure за Dynamics 365 Customer Insights. Пратите кораке да бисте [користили принципала услуге Azure](connect-service-principal.md) за безбедносно складиште које треба повезати.

- Безбедносно складиште мора имати **онемогућен** заштитни зид услуге Key Vault.

- Кључни трезор је на истој Азуре [локацији као](https://azure.microsoft.com/global-infrastructure/geographies/#overview) и окружење "Увиди купаца". Регион окружења у увидима клијената наведен је у оквиру ставке **Админ** > **Сyстем** > **Абоут** > **Регион**.

### <a name="link-a-key-vault-to-the-environment"></a>Повезивање безбедносног складишта са окружењем

1. Идите на **администраторско** > **обезбеђење**, а затим изаберите картицу **"Трезор кључа** ".
1. На плочици **Безбедносно складиште**, изаберите **Подешавање**.
1. Одаберите **претплату**.
1. Одаберите безбедносно складиште са падајуће листе **Безбедносно складиште**. Ако се приказује превише безбедносних складишта, изаберите групу ресурса да бисте ограничили резултате претраге.
1. Прихватите изјаву о **Приватности података и усклађености**.
1. Изаберите **Сачувај**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Кораци за подешавање повезаног трезора кључа у увидима купаца.":::

Плочица **Безбедносно складиште** сада приказује назив повезаног безбедносног складишта, групу ресурса и претплату. Спреман је за коришћење у подешавању везе.
За детаље о томе које дозволе на кључном трезору се доделе увидима клијената, идите на [дозволе одобрене у кључном трезору](#permissions-granted-on-the-key-vault), касније у овом чланку.

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

## <a name="permissions-granted-on-the-key-vault"></a>Одобрене дозволе за кључни трезор

Следеће дозволе се додељују програму Цустомер Инсигхтс у повезаном трезору ако је омогућена [смерница за приступ](/azure/key-vault/general/assign-access-policy?tabs=azure-portal)[кључном трезору или Азуре контроле](/azure/key-vault/general/rbac-guide?tabs=azure-cli) приступа засноване на улози.

### <a name="key-vault-access-policy"></a>Политика приступа за Key Vault

| Тип        | Дозволе          |
| ----------- | -------------------- |
| Тастер         | [Прибавите кључеве](/rest/api/keyvault/keys/get-keys/get-keys), [Прибавите кључ](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Тајни      | [Прибавите тајне](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Прибавите тајну](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Цертификат | [Прибавите цертификате](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Прибавите цертификат](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Претходне вредности су минимум за навођење и читање током извршавања.

### <a name="azure-role-based-access-control"></a>Azure контрола приступа заснована на улогама

Кључна улога читалац и кључних трезора тајни биће додата за увиде клијената. За детаље о овим улогама идите на [Уграђене Azure улоге за операције равни података у Key Vault-у](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Препоруке

- Користите посебан или наменски трезор кључа који садржи само тајне потребне за увиде клијената. Прочитајте више о томе зашто [се препоручују засебна безбедносна складишта](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Пратите [најбоље праксе за коришћење безбедносних складишта](/azure/key-vault/general/best-practices#turn-on-logging) за опције контроле приступа, прављења резервних копија, ревизије и опоравка.

## <a name="frequently-asked-questions"></a>Најчешћа питања

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Да ли "Увиди купаца" могу да напишу тајне или да преправе тајне у кључни трезор?

Не. Само дозволе за читање и листе наведене у одељку [са одобреним дозволама](#permissions-granted-on-the-key-vault) раније у овом чланку додељивање су увидима корисника. Систем не може да додаје, брише или замењује тајне у безбедносном складишту. То је и разлог зашто не можете да унесете акредитиве када веза користи Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Могу ли да променим везу са коришћења тајни за Key Vault на подразумевану потврду идентитета?

Не. Не можете се вратити на подразумевану везу након што сте је конфигурисали помоћу тајне из повезаног безбедносног складишта. Креирајте засебну везу и избришите стару ако вам више не треба.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Како могу да опозовем приступ кључном трезору за увиде клијената?

У зависности од тога да ли је омогућено [Политика приступа за Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) или [Azure контрола приступа заснована на улогама](/azure/key-vault/general/rbac-guide?tabs=azure-cli), морате уклонити дозволе за принципала услуге `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` са именом `Dynamics 365 AI for Customer Insights`. Све везе које користе безбедносно складиште ће престати да раде.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Тајна која се користи у вези уклоњена је из безбедносног складишта. Шта могу да урадим?

Обавештење се појављује у "Увидима купаца" када конфигурисана тајна из трезора кључа више није доступна. Омогућите [меко брисање](/azure/key-vault/general/soft-delete-overview) у безбедносном складишту за враћање тајни ако су случајно уклоњене.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Веза не функционише, али моја тајна је у безбедносном складишту. Шта би могао бити узрок?

Обавештење се појављује у увидима клијената када не може да приступи трезору кључа. Узрок би могао бити:

- Дозволе за директора услуге"Увид у кориснике" су уклоњене. Потребно их је ручно вратити.

- Заштитни зид на безбедносном складишту је омогућен. Заштитни зид мора бити онемогућен да би кључни трезор поново био доступан за увиде клијената.
