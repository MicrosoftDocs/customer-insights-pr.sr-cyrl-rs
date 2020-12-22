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
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="7f1eb-103">Повежите се са Azure Data Lake Storage Gen2 налогом помоћу принципала Azure услуге за увиде у циљну групу</span><span class="sxs-lookup"><span data-stu-id="7f1eb-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="7f1eb-104">Аутоматизовани алати који користе Azure услуге увек би требало да имају ограничене дозволе.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="7f1eb-105">Уместо да се апликације пријављују као потпуно привилеговани корисник, Azure нуди принципале услуга.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="7f1eb-106">Читајте даље да бисте сазнали како да повежете увиде у кориснике са Azure Data Lake Storage Gen2 налогом који користи Azure принципал услуге уместо кључева налога за складиштење.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="7f1eb-107">Принципал услуге можете користити за сигурно [додавање или уређивање Common Data Model фасцикле као извора података](connect-common-data-model.md) или [креирајте ново или ажурирајте постојеће окружење](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="7f1eb-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

<span data-ttu-id="7f1eb-108">Потребне су вам администраторске дозволе за Azure претплату да бисте креирали принципал услуге.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-108">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="7f1eb-109">Направите принципал Azure услуге за увиде у кориснике</span><span class="sxs-lookup"><span data-stu-id="7f1eb-109">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="7f1eb-110">Пре него што направите нов принципал услуге за увиде у кориснике, проверите да ли већ постоји у вашој организацији.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-110">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="7f1eb-111">Потражите постојећи принципал услуге</span><span class="sxs-lookup"><span data-stu-id="7f1eb-111">Look for an existing service principal</span></span>

1. <span data-ttu-id="7f1eb-112">Идите на [Azure портал за администрацију](https://portal.azure.com) и пријавите се у своју организацију.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-112">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="7f1eb-113">Изаберите **Azure Active Directory** из Azure услуга.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-113">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="7f1eb-114">У одељку **Управљање**, изаберите **Пословне апликације**.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-114">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="7f1eb-115">Потражите ID директне апликације увида у кориснике `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` или име `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-115">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="7f1eb-116">Ако пронађете одговарајући запис, то значи да постоји принципал услуге за увиде у кориснике.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-116">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="7f1eb-117">Не морате да га поново креирате.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-117">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Снимак екрана који приказује постојећи принципал услуге.":::
   
6. <span data-ttu-id="7f1eb-119">Ако се не прикажу резултати, креирајте нов принципал услуге.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-119">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="7f1eb-120">Креирај нов принципал услуге</span><span class="sxs-lookup"><span data-stu-id="7f1eb-120">Create a new service principal</span></span>

1. <span data-ttu-id="7f1eb-121">Инсталирајте најновију верзију **Azure Active Directory PowerShell за Graph**.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-121">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="7f1eb-122">За више информација погледајте [Инсталирајте Azure Active Directory PowerShell за Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="7f1eb-122">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="7f1eb-123">На рачунару изаберите Windows тастер на тастатури и потражите **Windows PowerShell** и **Покрени као администратор**.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-123">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="7f1eb-124">У PowerShell прозору који се отвори унесите `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-124">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="7f1eb-125">Направите принципал услуге за увиде у кориснике помоћу Azure AD PowerShell модула.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-125">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="7f1eb-126">У PowerShell прозор унесите `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-126">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="7f1eb-127">Замените „свој ID закупца“ стварним ID-ом вашег закупца тамо где желите да направите принципал услуге.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-127">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="7f1eb-128">Параметар назива окружења `AzureEnvironmentName` је опционалан.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-128">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="7f1eb-129">Унесите `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-129">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="7f1eb-130">Ова наредба креира принципал услуге за увиде о корисницима на изабраном закупцу.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-130">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="7f1eb-131">Доделите дозволе принципалу услуге за приступ налогу за складиштење</span><span class="sxs-lookup"><span data-stu-id="7f1eb-131">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="7f1eb-132">Идите на Azure портал да бисте доделили дозволе принципалу услуге за налог за складиштење који желите да користите у увидима о корисницима.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-132">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="7f1eb-133">Идите на [Azure портал за администрацију](https://portal.azure.com) и пријавите се у своју организацију.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-133">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="7f1eb-134">Отворите налог за складиштење којем желите да принципал услуге за увиде о корисницима има приступ.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-134">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="7f1eb-135">Изаберите **Контрола приступа (IAM)** у окну за навигацију и изаберите **Додај** > **Додајте доделу улога**.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-135">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Снимак екрана који приказује Azure портал током додавања улога.":::
   
1. <span data-ttu-id="7f1eb-137">У окну **Додајте доделу улога** поставите следећа својства:</span><span class="sxs-lookup"><span data-stu-id="7f1eb-137">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="7f1eb-138">Улога: *Сарадник за податке складишта блоб објекта*</span><span class="sxs-lookup"><span data-stu-id="7f1eb-138">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="7f1eb-139">Доделите приступ: *Корисник, група или принципал услуге*</span><span class="sxs-lookup"><span data-stu-id="7f1eb-139">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="7f1eb-140">Изаберите: *Dynamics 365 AI for Customer Insights* ([принципал услуге који сте креирали](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="7f1eb-140">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="7f1eb-141">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-141">Select **Save**.</span></span>

<span data-ttu-id="7f1eb-142">Пренос промена може трајати до 15 минута.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-142">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="7f1eb-143">Унесите ID Azure ресурса или детаље о Azure претплати у прилогу налога за складиштење у увидима о корисницима.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-143">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="7f1eb-144">Приложите Azure Data Lake налог за складиштење у увиде о корисницима ради [чувања излазних података](manage-environments.md) или [га користите као извор података](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="7f1eb-144">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="7f1eb-145">Избор опције Azure Data Lake омогућава вам да одаберете између приступа заснованог на ресурсима или претплати.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-145">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="7f1eb-146">Следите кораке у наставку да бисте пружили потребне информације о одабраном приступу.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-146">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resounce-based-storage-account-connection"></a><span data-ttu-id="7f1eb-147">Повезивање налога за складиштење заснованог на ресурсима</span><span class="sxs-lookup"><span data-stu-id="7f1eb-147">Resounce-based storage account connection</span></span>

1. <span data-ttu-id="7f1eb-148">Идите на [Azure портал за администрацију](https://portal.azure.com), пријавите се на своју претплату и отворите налог за складиштење.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-148">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="7f1eb-149">Идите у **Подешавања** > **Својства** у окну за навигацију.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-149">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="7f1eb-150">Копирајте вредност ID-а ресурса налога за складиштење.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-150">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Копирајте ID ресурса налога за складиштење.":::

1. <span data-ttu-id="7f1eb-152">У увидима о корисницима уметните ID ресурса у поље ресурса приказано на екрану за повезивање са налогом за складиштење.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-152">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Унесите информације о ID-у ресурса налога за складиштење.":::   
   
1. <span data-ttu-id="7f1eb-154">Наставите са преосталим корацима у увидима о корисницима да бисте приложили налог за складиштење.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-154">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="7f1eb-155">Повезивање налога за складиштење заснованог на претплатама</span><span class="sxs-lookup"><span data-stu-id="7f1eb-155">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="7f1eb-156">Идите на [Azure портал за администрацију](https://portal.azure.com), пријавите се на своју претплату и отворите налог за складиштење.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-156">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="7f1eb-157">Идите у **Подешавања** > **Својства** у окну за навигацију.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-157">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="7f1eb-158">Прегледајте **Претплата**,**Група ресурса** и **Име** налога за складиштење како бисте били сигурни да сте изабрали праве вредности у увидима о корисницима.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-158">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="7f1eb-159">У увиду о корисницима одаберите вредности или одговарајућа поља приликом прилагања налога за складиштење.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-159">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Унесите информације о ID-у ресурса налога за складиштење.":::
   
1. <span data-ttu-id="7f1eb-161">Наставите са преосталим корацима у увидима о корисницима да бисте приложили налог за складиштење.</span><span class="sxs-lookup"><span data-stu-id="7f1eb-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>
