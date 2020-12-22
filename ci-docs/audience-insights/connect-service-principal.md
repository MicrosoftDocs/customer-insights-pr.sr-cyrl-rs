---
title: Повежите се са Azure Data Lake Storage Gen2 налог помоћу принципала услуге
description: користите принципал Azure услуге за увиде у кориснике да бисте се повезали са сопственим језером података када га приложите увидима у кориснике.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644106"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>Повежите се са Azure Data Lake Storage Gen2 налогом помоћу принципала Azure услуге за увиде у циљну групу

Аутоматизовани алати који користе Azure услуге увек би требало да имају ограничене дозволе. Уместо да се апликације пријављују као потпуно привилеговани корисник, Azure нуди принципале услуга. Читајте даље да бисте сазнали како да повежете увиде у кориснике са Azure Data Lake Storage Gen2 налогом који користи Azure принципал услуге уместо кључева налога за складиштење. 

Принципал услуге можете користити за сигурно [додавање или уређивање Common Data Model фасцикле као извора података](connect-common-data-model.md) или [креирајте ново или ажурирајте постојеће окружење](manage-environments.md#create-an-environment-in-an-existing-organization).

Потребне су вам администраторске дозволе за Azure претплату да бисте креирали принципал услуге.

## <a name="create-azure-service-principal-for-audience-insights"></a>Направите принципал Azure услуге за увиде у кориснике

Пре него што направите нов принципал услуге за увиде у кориснике, проверите да ли већ постоји у вашој организацији.

### <a name="look-for-an-existing-service-principal"></a>Потражите постојећи принципал услуге

1. Идите на [Azure портал за администрацију](https://portal.azure.com) и пријавите се у своју организацију.

2. Изаберите **Azure Active Directory** из Azure услуга.

3. У одељку **Управљање**, изаберите **Пословне апликације**.

4. Потражите ID директне апликације увида у кориснике `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` или име `Dynamics 365 AI for Customer Insights`.

5. Ако пронађете одговарајући запис, то значи да постоји принципал услуге за увиде у кориснике. Не морате да га поново креирате.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Снимак екрана који приказује постојећи принципал услуге.":::
   
6. Ако се не прикажу резултати, креирајте нов принципал услуге.

### <a name="create-a-new-service-principal"></a>Креирај нов принципал услуге

1. Инсталирајте најновију верзију **Azure Active Directory PowerShell за Graph**. За више информација погледајте [Инсталирајте Azure Active Directory PowerShell за Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).
   - На рачунару изаберите Windows тастер на тастатури и потражите **Windows PowerShell** и **Покрени као администратор**.
   
   - У PowerShell прозору који се отвори унесите `Install-Module AzureAD`.

2. Направите принципал услуге за увиде у кориснике помоћу Azure AD PowerShell модула.
   - У PowerShell прозор унесите `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Замените „свој ID закупца“ стварним ID-ом вашег закупца тамо где желите да направите принципал услуге. Параметар назива окружења `AzureEnvironmentName` је опционалан.
  
   - Унесите `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Ова наредба креира принципал услуге за увиде о корисницима на изабраном закупцу.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Доделите дозволе принципалу услуге за приступ налогу за складиштење

Идите на Azure портал да бисте доделили дозволе принципалу услуге за налог за складиштење који желите да користите у увидима о корисницима.

1. Идите на [Azure портал за администрацију](https://portal.azure.com) и пријавите се у своју организацију.

1. Отворите налог за складиштење којем желите да принципал услуге за увиде о корисницима има приступ.

1. Изаберите **Контрола приступа (IAM)** у окну за навигацију и изаберите **Додај** > **Додајте доделу улога**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Снимак екрана који приказује Azure портал током додавања улога.":::
   
1. У окну **Додајте доделу улога** поставите следећа својства:
   - Улога: *Сарадник за податке складишта блоб објекта*
   - Доделите приступ: *Корисник, група или принципал услуге*
   - Изаберите: *Dynamics 365 AI for Customer Insights* ([принципал услуге који сте креирали](#create-a-new-service-principal))

1.  Изаберите ставку **Сачувај**.

Пренос промена може трајати до 15 минута.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Унесите ID Azure ресурса или детаље о Azure претплати у прилогу налога за складиштење у увидима о корисницима.

Приложите Azure Data Lake налог за складиштење у увиде о корисницима ради [чувања излазних података](manage-environments.md) или [га користите као извор података](connect-common-data-service-lake.md). Избор опције Azure Data Lake омогућава вам да одаберете између приступа заснованог на ресурсима или претплати.

Следите кораке у наставку да бисте пружили потребне информације о одабраном приступу.

### <a name="resounce-based-storage-account-connection"></a>Повезивање налога за складиштење заснованог на ресурсима

1. Идите на [Azure портал за администрацију](https://portal.azure.com), пријавите се на своју претплату и отворите налог за складиштење.

1. Идите у **Подешавања** > **Својства** у окну за навигацију.

1. Копирајте вредност ID-а ресурса налога за складиштење.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Копирајте ID ресурса налога за складиштење.":::

1. У увидима о корисницима уметните ID ресурса у поље ресурса приказано на екрану за повезивање са налогом за складиштење.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Унесите информације о ID-у ресурса налога за складиштење.":::   
   
1. Наставите са преосталим корацима у увидима о корисницима да бисте приложили налог за складиштење.

### <a name="subscription-based-storage-account-connection"></a>Повезивање налога за складиштење заснованог на претплатама

1. Идите на [Azure портал за администрацију](https://portal.azure.com), пријавите се на своју претплату и отворите налог за складиштење.

1. Идите у **Подешавања** > **Својства** у окну за навигацију.

1. Прегледајте **Претплата**,**Група ресурса** и **Име** налога за складиштење како бисте били сигурни да сте изабрали праве вредности у увидима о корисницима.

1. У увиду о корисницима одаберите вредности или одговарајућа поља приликом прилагања налога за складиштење.

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Унесите информације о ID-у ресурса налога за складиштење.":::
   
1. Наставите са преосталим корацима у увидима о корисницима да бисте приложили налог за складиштење.
