---
title: Донесите свој властити Azure Key Vault (верзија за преглед)
description: Сазнајте како да конфигуришете увиде клијената да користе сопствени Азуре кључни трезор за управљање тајнама.
ms.date: 08/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 229fb5698a02d1d73c30442f61c7b1b5fce918bf
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246173"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Донесите свој властити Azure Key Vault (верзија за преглед)

Повезивање наменског Азуре [кључа трезора са окружењем](/azure/key-vault/general/basic-concepts) увида клијената помаже организацијама да испуне услове усаглашености.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Повезивање кључног трезора са окружењем увида купаца

Подесите наменски кључни трезор да организује и користи тајне на граници усаглашености организације.

### <a name="prerequisites"></a>Предуслови

- Активна претплата на услугу Azure.

- Улога [администратора](permissions.md#admin) додељена [у увидима](permissions.md#add-users) клијената.

- [сарадник администратора](/azure/role-based-access-control/built-in-roles#contributor)[и администратора](/azure/role-based-access-control/built-in-roles#user-access-administrator) корисничког приступа на кључном трезору или групи ресурса којој припада трезор кључа. За још информација идите на [Додавање или уклањање Azure додела улога користећи Azure портал](/azure/role-based-access-control/role-assignments-portal). Ако немате улогу администратора корисничког приступа у трезору кључа, посебно подесите дозволе за контролу приступа засноване на улози за директора Азуре Dynamics 365 Customer Insights услуге. Пратите кораке да бисте [користили принципала услуге Azure](connect-service-principal.md) за безбедносно складиште које треба повезати.

- Кључ мора да има онемогућен заштитни зид кључног **трезора**.

- Кључни трезор је на истој [Азуре локацији као](https://azure.microsoft.com/global-infrastructure/geographies/#overview) и окружење "Увиди купаца". У опцији"Увиди клијената" идите на картицу **"Админ** > **систем** " и на **картицу** "Основни подаци" да бисте приказали регион окружења.

### <a name="recommendations"></a>Препоруке

- [Користите посебан или наменски трезор кључа](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults) који садржи само тајне потребне за увиде клијената.

- Пратите [најбоље праксе за коришћење безбедносних складишта](/azure/key-vault/general/best-practices#turn-on-logging) за опције контроле приступа, прављења резервних копија, ревизије и опоравка.

### <a name="link-a-key-vault-to-the-environment"></a>Повезивање безбедносног складишта са окружењем

1. Идите на **администраторско** > **обезбеђење**, а затим изаберите картицу **"Трезор кључа** ".
1. На плочици **Безбедносно складиште**, изаберите **Подешавање**.
1. Одаберите **претплату**.
1. Одаберите безбедносно складиште са падајуће листе **Безбедносно складиште**. Ако је доступно превише кључних трезора, изаберите групу ресурса да бисте ограничили резултате претраге.
1. Прегледајте [Приватност података и усклађеност](connections.md#data-privacy-and-compliance) и изаберите **Слажем се**.
1. Изаберите **Сачувај**.

Плочица **"Кључни** трезор" приказује име повезаног кључа трезора, претплату и групу ресурса. Спреман је за коришћење у подешавању везе.
За детаље о томе које дозволе за кључни трезор се додељују увидима клијената погледајте [дозволе додељене у кључном трезору](#permissions-granted-on-the-key-vault).

## <a name="use-the-key-vault-in-the-connection-setup"></a>Коришћење безбедносног складишта у подешавању везе

Када [подешавате везе](connections.md) са [подржаним системима независних произвођача](#supported-connection-types), користите тајне из повезаног трезора кључа да бисте конфигурисали везе.

1. Идите на **Администратор** > **Везе**.
1. Изаберите **Додај везу**.
1. За подржане типове веза, прекидач за **Користите безбедносно складиште** је доступан ако сте повезали безбедносно складиште.
1. Уместо ручног уношења тајне, одаберите тајно име које указује на тајну вредност у кључном трезору.

   :::image type="content" source="media/use-key-vault-secret.png" alt-text="Окно за повезивање са SFTP везом која користи тајну безбедносног складишта.":::

1. Кликните на **дугме** Сачувај да бисте креирали везу.

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

Кључна [улога читалац и кључних трезора](/azure/key-vault/general/rbac-guide?tabs=azure-cli) тајни биће додата за увиде клијената.

## <a name="frequently-asked-questions"></a>Најчешћа питања

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Да ли "Увиди купаца" могу да напишу тајне или да преправе тајне у кључни трезор?

Не. Само дозволе за читање и листе наведене у одобреним [дозволама додељује](#permissions-granted-on-the-key-vault) се увидима клијената. Систем не може да додаје, брише или замењује тајне у безбедносном складишту. То је и разлог зашто не можете да унесете акредитиве када веза користи Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Могу ли да променим везу са коришћења тајни за Key Vault на подразумевану потврду идентитета?

Не. Не можете се вратити на подразумевану везу након што сте је конфигурисали помоћу тајне из повезаног безбедносног складишта. Креирајте засебну везу и избришите стару ако вам више не треба.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Како могу да опозовем приступ кључном трезору за увиде клијената?

Ако су [омогућене смернице за приступ](/azure/key-vault/general/assign-access-policy?tabs=azure-portal)[кључу трезора или Азуре контроле приступа засноване](/azure/key-vault/general/rbac-guide?tabs=azure-cli) на улози, уклоните дозволе за главницу услуге `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` са именом `Dynamics 365 AI for Customer Insights`. Све везе које користе безбедносно складиште ће престати да раде.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Тајна која се користи у вези уклоњена је из безбедносног складишта. Шта могу да урадим?

Обавештење се појављује у "Увидима купаца" када конфигурисана тајна из трезора кључа више није доступна. Омогућите [меко брисање](/azure/key-vault/general/soft-delete-overview) у безбедносном складишту за враћање тајни ако су случајно уклоњене.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Веза не функционише, али моја тајна је у безбедносном складишту. Шта би могао бити узрок?

Обавештење се појављује у увидима клијената када не може да приступи трезору кључа. Узрок би могао бити:

- Дозволе за директора услуге"Увид у кориснике" су уклоњене. Потребно их је ручно вратити.

- Заштитни зид на безбедносном складишту је омогућен. Заштитни зид мора бити онемогућен да би кључни трезор поново био доступан за увиде клијената.
