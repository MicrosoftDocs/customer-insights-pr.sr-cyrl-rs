---
title: Повезивање са Azure Data Lake Storage налогом коришћењем принципала услуге
description: За повезивање са сопственим језером података, користите принципала услуге Azure.
ms.date: 09/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b901d799dbd73841a6ddbae754c4e4275f61146a
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645190"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Повезивање са Azure Data Lake Storage налогом коришћењем Azure принципала услуге

Аутоматизовани алати који користе Azure услуге увек би требало да имају ограничене дозволе. Уместо да се апликације пријављују као потпуно привилеговани корисник, Azure нуди принципале услуга. Читајте даље да бисте сазнали како да повежете услугу Dynamics 365 Customer Insights са Azure Data Lake Storage налогом користећи принципала услуге Azure уместо кључева налога за складиштење. 

Можете користити принципала услуге да безбедно [додате или уредите Common Data Service фасциклу као извор података](connect-common-data-model.md) или да [креирате или ажурирате окружење](create-environment.md).

> [!IMPORTANT]
> - Data Lake Storage налог који ће користити принципала услуге мора имати [омогућен хијерархијски простор за име](/azure/storage/blobs/data-lake-storage-namespace).
> - Потребне су вам администраторске дозволе за Azure претплату да бисте креирали принципал услуге.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Креирање принципала услуге Azure за Customer Insights

Пре него што креирате новог принципала услуге за увиде у циљну групу или увиде у ангажовање, проверите да ли већ постоји у вашој организацији.

### <a name="look-for-an-existing-service-principal"></a>Потражите постојећи принципал услуге

1. Идите на [Azure портал за администрацију](https://portal.azure.com) и пријавите се у своју организацију.

2. На страници **Azure услуге** изаберите **Azure Active Directory**.

3. У одељку **Управљање**, изаберите **Пословне апликације**.

4. Потражите ID Microsoft апликације:
   - Увиди у циљну групу: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` под називом `Dynamics 365 AI for Customer Insights`
   - Увиди у ангажовање: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` под називом `Dynamics 365 AI for Customer Insights engagement insights`

5. Ако пронађете одговарајући запис, то значи да принципал услуге већ постоји. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Снимак екрана који приказује постојећег принципала услуге.":::
   
6. Ако се не прикажу резултати, креирајте нов принципал услуге.

>[!NOTE]
>Да бисте искористили сву моћ услуге Dynamics 365 Customer Insights, предлажемо да обе апликације додате принципалу услуге.

### <a name="create-a-new-service-principal"></a>Креирај нов принципал услуге

1. Инсталирајте најновију верзију услуге Azure Active Directory PowerShell for Graph. За више информација погледајте чланак [Инсталирање услуге Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. На рачунару изаберите тастер Windows на тастатури и потражите **Windows PowerShell** и изаберите **Покрени као администратор**.
   
   1. У PowerShell прозору који се отвори унесите `Install-Module AzureAD`.

2. Креирајте принципала услуге за Customer Insights помоћу Azure AD PowerShell модула.

   1. У PowerShell прозор унесите `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Замените *[свој ID закупца]* стварним ID-ом вашег закупца тамо где желите да направите принципал услуге. Параметар назива окружења `AzureEnvironmentName` је опционалан.
  
   1. Унесите `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Ова наредба креира принципал услуге за увиде о корисницима на изабраном закупцу. 

   1. Унесите `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Ова команда креира принципала за увиде у ангажовање на изабраном закупцу.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Доделите дозволе принципалу услуге за приступ налогу за складиштење

Идите на Azure портал да бисте доделили дозволе принципалу услуге за налог за складиштење који желите да користите у увидима о корисницима.

1. Идите на [Azure портал за администрацију](https://portal.azure.com) и пријавите се у своју организацију.

1. Отворите налог за складиштење којем желите да принципал услуге за увиде о корисницима има приступ.

1. У левом окну изаберите **Контрола приступа (IAM)**, а затим изаберите **Додавање** > **Додај доделу улоге**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Снимак екрана који приказује Azure портал док додајете доделу улоге.":::

1. У окну **Додај доделу улоге** подесите следећа својства:
   - Улога: **Сарадник за податке складишта блоб објекта**
   - Доделите приступ: **Корисник, група или принципал услуге**
   - Изаберите: **Dynamics 365 AI for Customer Insights** и **Увиди у ангажовање у услузи Dynamics 365 AI for Customer Insights** (два [принципала услуга](#create-a-new-service-principal) која сте креирали раније у овој процедури)

1.  Изаберите ставку **Сачувај**.

Пренос промена може трајати до 15 минута.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Унесите ID Azure ресурса или детаље о Azure претплати у прилогу налога за складиштење у увидима о циљној групи

Можете да приложите Data Lake Storage налог у увиде о циљној групи у [излазне податке за складиштење](manage-environments.md) или их [користите као извор података](connect-common-data-service-lake.md). Ова опција вам омогућава да бирате између приступа заснованог на ресурсима или приступа заснованог на претплати. У зависности од приступа који изаберете, следите поступак у једном од следећих одељака.

### <a name="resource-based-storage-account-connection"></a>Повезивање налога за складиштење засновано на ресурсима

1. Идите на [Azure портал за администрацију](https://portal.azure.com), пријавите се на своју претплату и отворите налог за складиштење.

1. У левом окну идите на **Подешавања** > **Својства**.

1. Копирајте вредност ID-а ресурса налога за складиштење.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Копирајте ID ресурса налога за складиштење.":::

1. У увидима о циљној групи, уметните ID ресурса у поље ресурса приказано на екрану за повезивање налога за складиштење.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Унесите информације о ID-у ресурса налога за складиштење.":::   

1. Наставите са преосталим корацима у увидима о корисницима да бисте приложили налог за складиштење.

### <a name="subscription-based-storage-account-connection"></a>Повезивање налога за складиштење заснованог на претплатама

1. Идите на [Azure портал за администрацију](https://portal.azure.com), пријавите се на своју претплату и отворите налог за складиштење.

1. У левом окну идите на **Подешавања** > **Својства**.

1. Прегледајте **Претплата**,**Група ресурса** и **Име** налога за складиштење како бисте били сигурни да сте изабрали праве вредности у увидима о корисницима.

1. У увидима о циљној групи, одаберите вредности за одговарајућа поља приликом прилагања налога за складиштење.

1. Наставите са преосталим корацима у увидима о корисницима да бисте приложили налог за складиштење.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
