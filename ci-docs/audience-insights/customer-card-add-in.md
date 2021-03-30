---
title: Инсталирајте и конфигуришите Додатак за картицу клијента
description: Инсталирајте и конфигуришите додатак за картицу клијента за Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f3c4a01f9ce7749eeee72f7901620dae7cb9b8d3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597345"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="ba1a1-103">Додатак за картицу клијента (преглед)</span><span class="sxs-lookup"><span data-stu-id="ba1a1-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ba1a1-104">Стекните преглед својих клијената од 360 степени директно у Dynamics 365 апликацијама.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="ba1a1-105">Прикажите демографске податке, увиде и временске рокове активности помоћу додатка картице клијента.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ba1a1-106">Предуслови</span><span class="sxs-lookup"><span data-stu-id="ba1a1-106">Prerequisites</span></span>

- <span data-ttu-id="ba1a1-107">Апликација Dynamics 365 (као што је чвориште продаје или чвориште корисничке службе), верзије 9.0 и новије са омогућеним обједињеним интерфејсом.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="ba1a1-108">Профили клијената [унети из апликације Dynamics 365 помоћу услуге Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="ba1a1-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="ba1a1-109">Корисници Додатка за картицу клијента морају бити [додати као корисници](permissions.md) у увидима о корисницима.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="ba1a1-110">[Конфигурисане могућности претраживања и филтрирања](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="ba1a1-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="ba1a1-111">Демографска контрола: Демографска поља (као што су старост или пол) доступна су у обједињеном профилу клијента.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="ba1a1-112">Контрола обогаћивања: Захтева да се активна [обогаћивања](enrichment-hub.md) примене се на профиле клијената.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="ba1a1-113">Контрола обавештавања: Захтева податке генерисане помоћу Azure машинског учења ([предвиђања](predictions.md) или [прилагођени модели](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="ba1a1-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="ba1a1-114">Контрола мере: Захтева [конфигурисане мере](measures.md).</span><span class="sxs-lookup"><span data-stu-id="ba1a1-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="ba1a1-115">Контрола временске линије: Захтева[ конфигурисане активности](activities.md).</span><span class="sxs-lookup"><span data-stu-id="ba1a1-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="ba1a1-116">Инсталирајте и користите додатак за картицу клијента</span><span class="sxs-lookup"><span data-stu-id="ba1a1-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="ba1a1-117">Програмски додатак за картицу клијента је решење за Customer Engagement апликације у систему Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="ba1a1-118">Да бисте инсталирали решење, идите на AppSource и потражите **Dynamics картицу клијента**.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="ba1a1-119">Изаберите [додатак за картицу клијента у услузи AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) и изаберите **Преузми одмах**.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="ba1a1-120">Можда ћете морати да се пријавите помоћу акредитива администратора за апликацију Dynamics 365 да бисте инсталирали решење.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="ba1a1-121">Можда ће бити потребно неко време да се решење инсталира у ваше окружење.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="ba1a1-122">Конфигурисање додатка клијентске картице</span><span class="sxs-lookup"><span data-stu-id="ba1a1-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="ba1a1-123">Као администратор, идите у одељак **Подешавања** у систему Dynamics 365 и изаберите **Решења**.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="ba1a1-124">Изаберите везу **Име за приказ** за решење **Dynamics 365 Customer Insights додатак клијентске картице (преглед)**.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ba1a1-125">![Изаберите име за приказ](media/select-display-name.png "Изаберите име за приказ")</span><span class="sxs-lookup"><span data-stu-id="ba1a1-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="ba1a1-126">Изаберите **Пријављивање** и унесите акредитиве за налог администратора који користите за конфигурисање услуге Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ba1a1-127">Проверите да ли блокатор искачућих прозора прегледача не блокира прозор за потврду идентитета када изаберете дугме **Пријављивање**.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="ba1a1-128">Изаберите окружење из којег желите да преузмете податке.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="ba1a1-129">Дефинишите које се мапирање поља снима у апликацији Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="ba1a1-130">Да бисте мапирали контакт, одаберите поље у ентитету клијента које се подудара са ID-ом вашег ентитета контакта.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="ba1a1-131">Да бисте мапирали пословни контакт, одаберите поље у ентитету клијента које се подудара са ID-ом вашег ентитета пословног контакта.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ba1a1-132">![Поље ID контакта](media/contact-id-field.png "Поље ID контакта")</span><span class="sxs-lookup"><span data-stu-id="ba1a1-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="ba1a1-133">Изаберите **Сачувај конфигурацију** да бисте сачували подешавања.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="ba1a1-134">Затим треба да доделите безбедносне улоге у систему Dynamics 365 како би корисници могли да прилагођавају и виде корисничку картицу.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="ba1a1-135">У систему Dynamics 365, идите на **Подешавања** > **Безбедност** > **Корисници**.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="ba1a1-136">Изаберите кориснике да бисте изменили корисничке улоге и изаберите **Управљај улогама**.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="ba1a1-137">Доделите улогу **Стручњак за прилагођавање Customer Insights картица** корисницима који ће з целу организацију прилагођавати садржај приказан на картици.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="ba1a1-138">Додајте контроле картице клијента у обрасце</span><span class="sxs-lookup"><span data-stu-id="ba1a1-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="ba1a1-139">Да бисте додали контроле картице клијента у образац за контакт, идите на **Подешавања** > **Прилагођавања** у Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="ba1a1-140">Изаберите **Прилагоди систем**.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="ba1a1-141">Дођите до ентитета **Контакт**, проширите га, а затим изаберите **Обрасци**.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="ba1a1-142">Изаберите образац контакта на који желите да додате контроле картице клијента.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ba1a1-143">![Избор обрасца Контакта](media/contact-active-forms.png "Избор обрасца Контакта")</span><span class="sxs-lookup"><span data-stu-id="ba1a1-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="ba1a1-144">Да бисте додали контролу, у уређивачу образаца превуците било које поље из **Истраживача поља** тамо где желите да се контрола приказује.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="ba1a1-145">Изаберите поље на обрасцу које сте управо додали, а затим изаберите **Промени својства**.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="ba1a1-146">Идите до картице **Контроле** и изаберите **Додај контролу**.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="ba1a1-147">Изаберите неку од доступних прилагођених контрола и изаберите **Додај**.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="ba1a1-148">У дијалогу **Својства поља**, обришите поље за потврду **Прикажите ознаку на обрасцу**.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="ba1a1-149">Изаберите опцију **Веб** за контролу.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="ba1a1-150">За контролу обогаћивања изаберите тип обогаћивања који желите да прикажете конфигурисањем поља **Тип обогаћивања**.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="ba1a1-151">Додајте засебну контролу обогаћивања за сваку врсту обогаћивања.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="ba1a1-152">Изаберите **Сачувај** и **Објави** да бисте објавили ажурирани образац за контакт.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="ba1a1-153">Идите на објављени образац контакта.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-153">Go to the published contact form.</span></span> <span data-ttu-id="ba1a1-154">Видећете новододату контролу.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-154">You'll see the newly added control.</span></span> <span data-ttu-id="ba1a1-155">Можда ћете морати да се пријавите приликом првог коришћења.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="ba1a1-156">Да бисте прилагодили шта желите да прикажете на прилагођеној контроли, изаберите дугме за уређивање у горњем десном углу.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="ba1a1-157">Надоградња програмског додатка за картицу клијента</span><span class="sxs-lookup"><span data-stu-id="ba1a1-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="ba1a1-158">Програмски додатак за корисничку картицу се не надограђује аутоматски.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="ba1a1-159">Да бисте надоградили на најновију верзију, следите овај поступак у Dynamics 365 апликацији у којој је инсталиран програмски додатак.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="ba1a1-160">У Dynamics 365 апликацији идите на **Подешавања** > **Прилагођавање** и изаберите **Решења**.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="ba1a1-161">У табели додатака потражите **CustomerInsightsCustomerCard** и изаберите ред.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="ba1a1-162">Изаберите **Примени надоградњу решења** у траци са радњама.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Надоградите решење у области Прилагођавање Dynamics 365 апликација":::

1. <span data-ttu-id="ba1a1-164">Када започнете процес надоградње, видећете индикатор учитавања док се надоградња не заврши.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="ba1a1-165">Ако нема новије верзије, надоградња ће приказати поруку о грешци.</span><span class="sxs-lookup"><span data-stu-id="ba1a1-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]