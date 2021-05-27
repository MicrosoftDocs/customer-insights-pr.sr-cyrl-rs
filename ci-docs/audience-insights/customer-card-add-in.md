---
title: Програмски додатак за картицу клијента за Dynamics 365 апликације
description: Прикажите податке из увида у циљну групу у Dynamics 365 апликацијама са овим програмским додатком.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059606"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="bee59-103">Додатак за картицу клијента (преглед)</span><span class="sxs-lookup"><span data-stu-id="bee59-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="bee59-104">Стекните преглед својих клијената од 360 степени директно у Dynamics 365 апликацијама.</span><span class="sxs-lookup"><span data-stu-id="bee59-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="bee59-105">Када је програмски додатак за клијентску картицу инсталиран у подржаној Dynamics 365 апликацији, можете одабрати да приказујете демографске податке, увиде и временске осе активности.</span><span class="sxs-lookup"><span data-stu-id="bee59-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="bee59-106">Програмски додатак ће преузети податке из услуге Customer Insights без утицаја на податке у повезаној Dynamics 365 апликацији.</span><span class="sxs-lookup"><span data-stu-id="bee59-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="bee59-107">Предуслови</span><span class="sxs-lookup"><span data-stu-id="bee59-107">Prerequisites</span></span>

- <span data-ttu-id="bee59-108">Програмски додатак ради само са Dynamics 365 апликацијама заснованим на моделу, као што су Sales или Customer Service, верзије 9.0 и новије.</span><span class="sxs-lookup"><span data-stu-id="bee59-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="bee59-109">Да би се ваши Dynamics 365 подаци мапирали у корисничке профиле увида у циљну групу, они треба да буду [унети из Dynamics 365 апликације помоћу Common Data Service конектора](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="bee59-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="bee59-110">Сви Dynamics 365 корисници програмског додатка за картице клијента морају бити [додати као корисници](permissions.md) у увидима у циљну групу да бисте видели податке.</span><span class="sxs-lookup"><span data-stu-id="bee59-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="bee59-111">[Конфигурисане могућности претраге и филтрирања](search-filter-index.md) у увидима у циљну групу су потребне да би проналажење података функционисало.</span><span class="sxs-lookup"><span data-stu-id="bee59-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="bee59-112">Свака контрола програмског додатка ослања се на одређене податке у увидима у циљну групу:</span><span class="sxs-lookup"><span data-stu-id="bee59-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="bee59-113">Контрола мере: Захтева [конфигурисане мере](measures.md).</span><span class="sxs-lookup"><span data-stu-id="bee59-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="bee59-114">Контрола обавештавања: Захтева податке генерисане коришћењем [предвиђања](predictions.md) или [прилагођених модела](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="bee59-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="bee59-115">Демографска контрола: Демографска поља (као што су старост или пол) доступна су у обједињеном корисничком профилу.</span><span class="sxs-lookup"><span data-stu-id="bee59-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="bee59-116">Контрола обогаћивања: Захтева да се активна [обогаћивања](enrichment-hub.md) примене се на корисничке профиле.</span><span class="sxs-lookup"><span data-stu-id="bee59-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="bee59-117">Контрола временске линије: Захтева[ конфигурисане активности](activities.md).</span><span class="sxs-lookup"><span data-stu-id="bee59-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="bee59-118">Инсталирајте и користите додатак за картицу клијента</span><span class="sxs-lookup"><span data-stu-id="bee59-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="bee59-119">Програмски додатак за картицу клијента је решење за Customer Engagement апликације у систему Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="bee59-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="bee59-120">Да бисте инсталирали решење, идите на AppSource и потражите **Dynamics картицу клијента**.</span><span class="sxs-lookup"><span data-stu-id="bee59-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="bee59-121">Изаберите [додатак за картицу клијента у услузи AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) и изаберите **Преузми одмах**.</span><span class="sxs-lookup"><span data-stu-id="bee59-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="bee59-122">Можда ћете морати да се пријавите помоћу акредитива администратора за апликацију Dynamics 365 да бисте инсталирали решење.</span><span class="sxs-lookup"><span data-stu-id="bee59-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="bee59-123">Можда ће бити потребно неко време да се решење инсталира у ваше окружење.</span><span class="sxs-lookup"><span data-stu-id="bee59-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="bee59-124">Конфигурисање додатка клијентске картице</span><span class="sxs-lookup"><span data-stu-id="bee59-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="bee59-125">Као администратор, идите у одељак **Подешавања** у систему Dynamics 365 и изаберите **Решења**.</span><span class="sxs-lookup"><span data-stu-id="bee59-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="bee59-126">Изаберите везу **Име за приказ** за решење **Dynamics 365 Customer Insights додатак клијентске картице (преглед)**.</span><span class="sxs-lookup"><span data-stu-id="bee59-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bee59-127">![Изаберите име за приказ](media/select-display-name.png "Изаберите име за приказ")</span><span class="sxs-lookup"><span data-stu-id="bee59-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="bee59-128">Изаберите **Пријављивање** и унесите акредитиве за налог администратора који користите за конфигурисање услуге Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="bee59-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bee59-129">Проверите да ли блокатор искачућих прозора прегледача не блокира прозор за потврду идентитета када изаберете дугме **Пријављивање**.</span><span class="sxs-lookup"><span data-stu-id="bee59-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="bee59-130">Изаберите инстанцу Customer Insights окружења из којег желите да преузмете податке.</span><span class="sxs-lookup"><span data-stu-id="bee59-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="bee59-131">Дефинишите мапирање поља на записе у Dynamics 365 апликацији.</span><span class="sxs-lookup"><span data-stu-id="bee59-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="bee59-132">У зависности од ваших података у услузи Customer Insights, можете одабрати да мапирате следеће опције:</span><span class="sxs-lookup"><span data-stu-id="bee59-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="bee59-133">Да бисте мапирали контакт, одаберите поље у ентитету клијента које се подудара са ID-ом вашег ентитета контакта.</span><span class="sxs-lookup"><span data-stu-id="bee59-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="bee59-134">Да бисте мапирали пословни контакт, одаберите поље у ентитету клијента које се подудара са ID-ом вашег ентитета пословног контакта.</span><span class="sxs-lookup"><span data-stu-id="bee59-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bee59-135">![Поље ID контакта](media/contact-id-field.png "Поље ID контакта")</span><span class="sxs-lookup"><span data-stu-id="bee59-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="bee59-136">Изаберите **Сачувај конфигурацију** да бисте сачували подешавања.</span><span class="sxs-lookup"><span data-stu-id="bee59-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="bee59-137">Затим треба да доделите безбедносне улоге у систему Dynamics 365 како би корисници могли да прилагођавају и виде корисничку картицу.</span><span class="sxs-lookup"><span data-stu-id="bee59-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="bee59-138">У систему Dynamics 365, идите на **Подешавања** > **Безбедност** > **Корисници**.</span><span class="sxs-lookup"><span data-stu-id="bee59-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="bee59-139">Изаберите кориснике да бисте изменили корисничке улоге и изаберите **Управљај улогама**.</span><span class="sxs-lookup"><span data-stu-id="bee59-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="bee59-140">Доделите улогу **Стручњак за прилагођавање Customer Insights картица** корисницима који ће з целу организацију прилагођавати садржај приказан на картици.</span><span class="sxs-lookup"><span data-stu-id="bee59-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="bee59-141">Додајте контроле картице клијента у обрасце</span><span class="sxs-lookup"><span data-stu-id="bee59-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="bee59-142">Да бисте додали контроле картице клијента у образац за контакт, идите на **Подешавања** > **Прилагођавања** у Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="bee59-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="bee59-143">Изаберите **Прилагоди систем**.</span><span class="sxs-lookup"><span data-stu-id="bee59-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="bee59-144">Дођите до ентитета **Контакт**, проширите га, а затим изаберите **Обрасци**.</span><span class="sxs-lookup"><span data-stu-id="bee59-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="bee59-145">Изаберите образац контакта на који желите да додате контроле картице клијента.</span><span class="sxs-lookup"><span data-stu-id="bee59-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="bee59-146">![Избор обрасца Контакта](media/contact-active-forms.png "Избор обрасца Контакта")</span><span class="sxs-lookup"><span data-stu-id="bee59-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="bee59-147">Да бисте додали контролу, у уређивачу образаца превуците било које поље из **Истраживача поља** тамо где желите да се контрола приказује.</span><span class="sxs-lookup"><span data-stu-id="bee59-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="bee59-148">Изаберите поље на обрасцу које сте управо додали, а затим изаберите **Промени својства**.</span><span class="sxs-lookup"><span data-stu-id="bee59-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="bee59-149">Идите до картице **Контроле** и изаберите **Додај контролу**.</span><span class="sxs-lookup"><span data-stu-id="bee59-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="bee59-150">Изаберите неку од доступних прилагођених контрола и изаберите **Додај**.</span><span class="sxs-lookup"><span data-stu-id="bee59-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="bee59-151">У дијалогу **Својства поља**, обришите поље за потврду **Прикажите ознаку на обрасцу**.</span><span class="sxs-lookup"><span data-stu-id="bee59-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="bee59-152">Изаберите опцију **Веб** за контролу.</span><span class="sxs-lookup"><span data-stu-id="bee59-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="bee59-153">За контролу обогаћивања изаберите тип обогаћивања који желите да прикажете конфигурисањем поља **Тип обогаћивања**.</span><span class="sxs-lookup"><span data-stu-id="bee59-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="bee59-154">Додајте засебну контролу обогаћивања за сваку врсту обогаћивања.</span><span class="sxs-lookup"><span data-stu-id="bee59-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="bee59-155">Изаберите **Сачувај** и **Објави** да бисте објавили ажурирани образац за контакт.</span><span class="sxs-lookup"><span data-stu-id="bee59-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="bee59-156">Идите на објављени образац контакта.</span><span class="sxs-lookup"><span data-stu-id="bee59-156">Go to the published contact form.</span></span> <span data-ttu-id="bee59-157">Видећете новододату контролу.</span><span class="sxs-lookup"><span data-stu-id="bee59-157">You'll see the newly added control.</span></span> <span data-ttu-id="bee59-158">Можда ћете морати да се пријавите приликом првог коришћења.</span><span class="sxs-lookup"><span data-stu-id="bee59-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="bee59-159">Да бисте прилагодили шта желите да прикажете на прилагођеној контроли, изаберите дугме за уређивање у горњем десном углу.</span><span class="sxs-lookup"><span data-stu-id="bee59-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="bee59-160">Надоградња програмског додатка за картицу клијента</span><span class="sxs-lookup"><span data-stu-id="bee59-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="bee59-161">Програмски додатак за корисничку картицу се не надограђује аутоматски.</span><span class="sxs-lookup"><span data-stu-id="bee59-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="bee59-162">Да бисте надоградили на најновију верзију, следите овај поступак у Dynamics 365 апликацији у којој је инсталиран програмски додатак.</span><span class="sxs-lookup"><span data-stu-id="bee59-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="bee59-163">У Dynamics 365 апликацији идите на **Подешавања** > **Прилагођавање** и изаберите **Решења**.</span><span class="sxs-lookup"><span data-stu-id="bee59-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="bee59-164">У табели додатака потражите **CustomerInsightsCustomerCard** и изаберите ред.</span><span class="sxs-lookup"><span data-stu-id="bee59-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="bee59-165">Изаберите **Примени надоградњу решења** у траци са радњама.</span><span class="sxs-lookup"><span data-stu-id="bee59-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Надоградите решење у области Прилагођавање Dynamics 365 апликација":::

1. <span data-ttu-id="bee59-167">Када започнете процес надоградње, видећете индикатор учитавања док се надоградња не заврши.</span><span class="sxs-lookup"><span data-stu-id="bee59-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="bee59-168">Ако нема новије верзије, надоградња ће приказати поруку о грешци.</span><span class="sxs-lookup"><span data-stu-id="bee59-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
