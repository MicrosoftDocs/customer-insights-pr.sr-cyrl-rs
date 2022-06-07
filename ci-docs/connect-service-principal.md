---
title: Повезивање са Azure Data Lake Storage налогом коришћењем принципала услуге
description: За повезивање са сопственим језером података, користите принципала услуге Azure.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: b18d1f42b9510ebf23f0666322819865d132173b
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833415"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Повезивање са Azure Data Lake Storage налогом коришћењем Azure принципала услуге

Овај чланак говори о томе како да се повежете Dynamics 365 Customer Insights са налогом Azure Data Lake Storage помоћу директора Азуре услуге уместо кључева налога за складиштење.

Аутоматизовани алати који користе Azure услуге увек би требало да имају ограничене дозволе. Уместо да се апликације пријављују као потпуно привилеговани корисник, Azure нуди принципале услуга. Принципалне услуге можете да користите за безбедно додавање [или уређивање фасцикле "Уобичајени модел података" као извор података](connect-common-data-model.md) или [креирање или ажурирање окружења](create-environment.md).

> [!IMPORTANT]
>
> - Дата Лаке Стораге налог који ће користити главницу услуге мора бити Gen2 и имати [омогућен хијерархијски простор за име](/azure/storage/blobs/data-lake-storage-namespace). Азуре Дата Лаке Gen1 налози за складиштење нису подржани.
> - Потребне су вам администраторске дозволе за Азуре закупац да бисте креирали директора услуге.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Креирање принципала услуге Azure за Customer Insights

Пре него што креирате новог директора сервиса за увиде клијената, проверите да ли он већ постоји у вашој организацији.

### <a name="look-for-an-existing-service-principal"></a>Потражите постојећи принципал услуге

1. Идите на [Azure портал за администрацију](https://portal.azure.com) и пријавите се у своју организацију.

2. На страници **Azure услуге** изаберите **Azure Active Directory**.

3. У оквиру Управљање изаберите **Мицрософт апликацију** . **·**

4. Додајте филтер за **ИД апликације започните**`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` са или потражите име `Dynamics 365 AI for Customer Insights`.

5. Ако пронађете одговарајући запис, то значи да принципал услуге већ постоји.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Снимак екрана који приказује постојећег принципала услуге.":::

6. Ако резултати не буду враћени, можете креирати [новог директора услуге](#create-a-new-service-principal). У већини случајева већ постоји и потребно је само да доделите дозволе за приступ главном налогу услуге.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Доделите дозволе принципалу услуге за приступ налогу за складиштење

Идите на портал Азуре да бисте доделили дозволе директору услуге за налог за складиштење који желите да користите у увидима клијената.

1. Идите на [Azure портал за администрацију](https://portal.azure.com) и пријавите се у своју организацију.

1. Отворите налог за складиште којем желите да главница услуге за увиде клијената има приступ.

1. У левом окну изаберите **Контрола приступа (IAM)**, а затим изаберите **Додавање** > **Додај доделу улоге**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Снимак екрана који приказује Azure портал док додајете доделу улоге.":::

1. У окну **Додај доделу улоге** подесите следећа својства:
   - Улога: **Сарадник за податке складишта блоб објекта**
   - Доделите приступ: **Корисник, група или принципал услуге**
   - Изаберите чланове: **Дyнамицс 365 АИ за увиде клијената** ([главница услуге](#create-a-new-service-principal) коју сте тражили раније у овој процедури)

1. Изаберите **Редиговање + додели**.

Пренос промена може трајати до 15 минута.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Унесите ИД Азуре ресурса или детаље Азуре претплате у прилог налога за складиштење у фасцикли "Увиди купаца"

Налог складишта "Дата Лаке" можете приложити у увидима купаца да бисте [ускладиштили излазне](manage-environments.md) податке [или их користили као извор података](connect-dataverse-managed-lake.md). Ова опција вам омогућава да бирате између приступа заснованог на ресурсима или приступа заснованог на претплати. У зависности од приступа који изаберете, следите поступак у једном од следећих одељака.

### <a name="resource-based-storage-account-connection"></a>Повезивање налога за складиштење засновано на ресурсима

1. Идите на [Azure портал за администрацију](https://portal.azure.com), пријавите се на своју претплату и отворите налог за складиштење.

1. У левом окну идите на крајње **тачке** > **поставки**.

1. Копирајте вредност ID-а ресурса налога за складиштење.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Копирајте ID ресурса налога за складиштење.":::

1. У оквиру "Увиди купаца" уметните ИД ресурса у поље ресурса приказано на екрану за повезивање налога за складиштење.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Унесите информације о ID-у ресурса налога за складиштење.":::   

1. Наставите са преосталим корацима у увидима клијената да бисте приложили налог за складиштење.

### <a name="subscription-based-storage-account-connection"></a>Повезивање налога за складиштење заснованог на претплатама

1. Идите на [Azure портал за администрацију](https://portal.azure.com), пријавите се на своју претплату и отворите налог за складиштење.

1. У левом окну идите на **Подешавања** > **Својства**.

1. Прегледајте **претплату**, групу **ресурса** и име **налога** за складиштење да бисте се уверили да сте изабрали праве вредности у увидима клијената.

1. У прозору Увиди купаца одаберите вредности за одговарајућа поља приликом прилагања налога за складиштење.

1. Наставите са преосталим корацима у увидима клијената да бисте приложили налог за складиштење.

### <a name="create-a-new-service-principal"></a>Креирај нов принципал услуге

1. Инсталирајте најновију верзију услуге Azure Active Directory PowerShell for Graph. За више информација погледајте чланак [Инсталирање услуге Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. На рачунару притисните тастер Wиндоwс на тастатури и потражите **Wиндоwс ПоwерСхелл и изаберите** Покрени **као администратор**.

   1. У PowerShell прозору који се отвори унесите `Install-Module AzureAD`.

2. Креирајте принципала услуге за Customer Insights помоћу Azure AD PowerShell модула.

   1. У PowerShell прозор унесите `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Замените *[ИД каталога] правим* ИД-ом директоријума Азуре претплате где желите да креирате главницу услуге. Параметар назива окружења `AzureEnvironmentName` је опционалан.
  
   1. Унесите `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Ова команда креира главницу услуге за увиде клијената у изабраној Азуре претплати.

[!INCLUDE [footer-include](includes/footer-banner.md)]