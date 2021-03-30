---
title: Рад са API-јима
description: Користите API-је и схватите ограничења.
ms.date: 03/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 011fa700563c53534554a6b73e87c2391bfdf714
ms.sourcegitcommit: a872f59e6febe4d4bd678ddd0b60a1660acca0f3
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/24/2021
ms.locfileid: "5710478"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="f76ae-103">Радите са Customer Insights API-јем</span><span class="sxs-lookup"><span data-stu-id="f76ae-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="f76ae-104">Dynamics 365 Customer Insights пружа API-је за изградњу властитих апликација заснованих на подацима у услузи Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f76ae-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f76ae-105">Детаљи ових API-ја наведени су у чланку [Референца Customer Insights API-ја](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="f76ae-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="f76ae-106">Садрже додатне информације о операцијама, параметрима и одговорима.</span><span class="sxs-lookup"><span data-stu-id="f76ae-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="f76ae-107">Овај чланак вас води кроз приступ Customer Insights API-јима, креирање регистрације Azure апликације и помаже вам да започнете са доступним клијентским библиотекама.</span><span class="sxs-lookup"><span data-stu-id="f76ae-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="f76ae-108">Започните уз испробавање Customer Insights API-ја</span><span class="sxs-lookup"><span data-stu-id="f76ae-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="f76ae-109">[Пријавите се](https://home.ci.ai.dynamics.com) у Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f76ae-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="f76ae-110">Ако још увек немате претплату, [пријавите се за пробну верзију услуге Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="f76ae-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="f76ae-111">Да бисте омогућили API-је у вашем Customer Insights окружењу, идите на **Администратор** > **Дозволе**.</span><span class="sxs-lookup"><span data-stu-id="f76ae-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="f76ae-112">За то ће вам требати дозволе администратора.</span><span class="sxs-lookup"><span data-stu-id="f76ae-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="f76ae-113">Иди на картицу **API-ји** и изаберите дугме **Омогући**.</span><span class="sxs-lookup"><span data-stu-id="f76ae-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="f76ae-114">Омогућавање API-ја креира примарни и секундарни кључ претплате за вашу инстанцу који се користи у API захтевима.</span><span class="sxs-lookup"><span data-stu-id="f76ae-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="f76ae-115">Кључеве можете да поново генеришете тако што ћете изабрати **Поново генериши примарни** или **Поново генериши секундарни** на **Администратор** > **Дозволе** > **API-ји**.</span><span class="sxs-lookup"><span data-stu-id="f76ae-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Омогућавање Customer Insights API-ја":::

1. <span data-ttu-id="f76ae-117">Изаберите **Истражите наше API-је** да [испробате API-је](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="f76ae-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="f76ae-118">Изаберите операцију API-ја и изаберите **Испробајте**.</span><span class="sxs-lookup"><span data-stu-id="f76ae-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="f76ae-119">У бочном окну поставите вредност у падајућем менију **Овлашћење** на **имплицитно**.</span><span class="sxs-lookup"><span data-stu-id="f76ae-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="f76ae-120">Заглавље `Authorization` се добија с додатим токеном носиоца.</span><span class="sxs-lookup"><span data-stu-id="f76ae-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="f76ae-121">Кључ претплате ће се аутоматски попунити.</span><span class="sxs-lookup"><span data-stu-id="f76ae-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="f76ae-122">По жељи додајте све потребне параметре упита.</span><span class="sxs-lookup"><span data-stu-id="f76ae-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="f76ae-123">Померите се до дна бочног окна и изаберите **Пошаљи**.</span><span class="sxs-lookup"><span data-stu-id="f76ae-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="f76ae-124">HTTP одговор ће се ускоро појавити испод.</span><span class="sxs-lookup"><span data-stu-id="f76ae-124">The HTTP response will soon appear below.</span></span>


   :::image type="content" source="media/try-apis.gif" alt-text="Анимирани GIF који показује како да изаберете тест API-ја.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="f76ae-126">Направите нову регистрацију апликације на Azure порталу</span><span class="sxs-lookup"><span data-stu-id="f76ae-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="f76ae-127">Ови кораци помажу вам да започнете са коришћењем Customer Insights API-ја у Azure апликацији користећи делегиране дозволе.</span><span class="sxs-lookup"><span data-stu-id="f76ae-127">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="f76ae-128">Обавезно прво завршите [одељак Започните](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="f76ae-128">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="f76ae-129">Пријавите се на [Azure портал](https://portal.azure.com) помоћу налога који може приступити Customer Insights подацима.</span><span class="sxs-lookup"><span data-stu-id="f76ae-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="f76ae-130">С леве стране изаберите **Регистрације апликација**.</span><span class="sxs-lookup"><span data-stu-id="f76ae-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="f76ae-131">Изаберите **Нова регистрација**, наведите име апликације и одаберите тип налога.</span><span class="sxs-lookup"><span data-stu-id="f76ae-131">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="f76ae-132">Опционално додајте URL преусмеравања.</span><span class="sxs-lookup"><span data-stu-id="f76ae-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="f76ae-133">http://localhost је довољан за развој апликације на вашем локалном рачунару.</span><span class="sxs-lookup"><span data-stu-id="f76ae-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="f76ae-134">На новој регистрацији апликације идите на **Дозволе за API-је**.</span><span class="sxs-lookup"><span data-stu-id="f76ae-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="Анимирани GIF за подешавање дозволе за API у регистрацији апликације.":::

1. <span data-ttu-id="f76ae-136">Изаберите **Додајте дозволу** и изаберите **Customer Insights** у бочном окну.</span><span class="sxs-lookup"><span data-stu-id="f76ae-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="f76ae-137">За **Тип дозволе**, изаберите **Делегиране дозволе** и изаберите дозволу **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="f76ae-137">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="f76ae-138">Изаберите ставку **Додајте дозволе**.</span><span class="sxs-lookup"><span data-stu-id="f76ae-138">Select **Add permissions**.</span></span> <span data-ttu-id="f76ae-139">Ако вам је потребан приступ API-ју без пријављивања корисника, прегледајте одељак [Дозволе за апликације од сервера до сервера](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="f76ae-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="f76ae-140">Изаберите **Дајте сагласност администратора за...** да бисте довршили регистрацију апликације.</span><span class="sxs-lookup"><span data-stu-id="f76ae-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="f76ae-141">Можете да користите ID апликације/клијента за регистрацију ове апликације у Microsoft Authentication Library (MSAL) да бисте добили токен носиоца који ћете са захтевом послати у API.</span><span class="sxs-lookup"><span data-stu-id="f76ae-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Анимирани GIF за давање сагласности администратора.":::

<span data-ttu-id="f76ae-143">За више информација о MSAL-у, погледајте [Преглед Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="f76ae-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="f76ae-144">За више информација о регистрацији апликација у услузи Azure погледајте [Ново искуство регистрације апликација за Azure портал](/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="f76ae-144">For more information about app registration in Azure, see [The new Azure portal app registration experience](/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="f76ae-145">За информације о коришћењу API-ја и наших клијентских библиотека, погледајте [Customer Insights клијентске библиотеке](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="f76ae-145">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="f76ae-146">Дозволе за апликације са сервера на сервер</span><span class="sxs-lookup"><span data-stu-id="f76ae-146">Server-to-server application permissions</span></span>

<span data-ttu-id="f76ae-147">[Одељак за регистрацију апликација](#create-a-new-app-registration-in-the-azure-portal) описује како се региструје апликација која захтева да се корисник пријави ради потврде идентитета.</span><span class="sxs-lookup"><span data-stu-id="f76ae-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="f76ae-148">Сазнајте како да креирате регистрацију апликације која не захтева интеракцију корисника и која се може покренути на серверу.</span><span class="sxs-lookup"><span data-stu-id="f76ae-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="f76ae-149">При регистрацији апликације на Azure порталу идите на **Дозволе за API-је**.</span><span class="sxs-lookup"><span data-stu-id="f76ae-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="f76ae-150">Изаберите **Додајте дозволу** и изаберите **Customer Insights** у бочном окну.</span><span class="sxs-lookup"><span data-stu-id="f76ae-150">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="f76ae-151">За **Тип дозволе**, изаберите **Дозволе за апликације** и изаберите дозволу **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="f76ae-151">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="f76ae-152">Изаберите ставку **Додајте дозволе**.</span><span class="sxs-lookup"><span data-stu-id="f76ae-152">Select **Add permissions**.</span></span>

1. <span data-ttu-id="f76ae-153">Да бисте дали сагласност администратора за ову дозволу за апликацију, морате да додате принципал услуге.</span><span class="sxs-lookup"><span data-stu-id="f76ae-153">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="f76ae-154">Инсталирајте Azure Active Directory (AD) PowerShell модул: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="f76ae-154">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="f76ae-155">Повежите се на AD налог: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="f76ae-155">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="f76ae-156">Можете пронаћи свој ID закупца **Преглед** > **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="f76ae-156">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="f76ae-157">Покрените следећу команду да бисте додали Azure AD принципал услуге: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` Параметар AppId односи се на апликацију Customer Insights API.</span><span class="sxs-lookup"><span data-stu-id="f76ae-157">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Узорак принципала услуге":::

1. <span data-ttu-id="f76ae-159">На новој регистрацији апликације вратите се на **Дозволе за API-је**.</span><span class="sxs-lookup"><span data-stu-id="f76ae-159">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="f76ae-160">Изаберите **Дајте сагласност администратора за...** да бисте довршили регистрацију апликације.</span><span class="sxs-lookup"><span data-stu-id="f76ae-160">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Анимирани GIF за давање сагласности администратора.":::

1. <span data-ttu-id="f76ae-162">Да закључимо, морамо да додамо име регистрације апликације као корисника у Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f76ae-162">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="f76ae-163">Отворите Customer Insights, идите на **Администратор** > **Дозволе** и изаберите **Додај корисника**.</span><span class="sxs-lookup"><span data-stu-id="f76ae-163">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="f76ae-164">Потражите име регистрације апликације, изаберите је из резултата претраге и изаберите **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="f76ae-164">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="f76ae-165">Customer Insights клијентске библиотеке</span><span class="sxs-lookup"><span data-stu-id="f76ae-165">Customer Insights client libraries</span></span>

<span data-ttu-id="f76ae-166">Овај одељак вам помаже да започнете коришћење клијентских библиотека доступних за Customer Insights API-је.</span><span class="sxs-lookup"><span data-stu-id="f76ae-166">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="f76ae-167">Сав изворни кôд библиотеке и примери апликација могу се наћи на [Customer Insights GitHub страници](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="f76ae-167">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="f76ae-168">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="f76ae-168">C# NuGet</span></span>

<span data-ttu-id="f76ae-169">Сазнајте како да започнете коришћење C# клијентских библиотека са NuGet.org. За више информација о NuGet пакету, видите [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="f76ae-169">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="f76ae-170">Тренутно овај пакет циља оквире netstandard2.0 и netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="f76ae-170">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="f76ae-171">Додајте C# клијентску библиотеку у C# пројекат</span><span class="sxs-lookup"><span data-stu-id="f76ae-171">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="f76ae-172">У програму Visual Studio, отворите **NuGet менаџер пакета** за пројекат.</span><span class="sxs-lookup"><span data-stu-id="f76ae-172">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="f76ae-173">Потражите **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="f76ae-173">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="f76ae-174">Изаберите **Инсталирај** за додавање пакета у пројекат.</span><span class="sxs-lookup"><span data-stu-id="f76ae-174">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="f76ae-175">Алтернативно, покрените ову команду у **NuGet конзоли менаџера пакета**:`Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="f76ae-175">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Додајте NuGet пакет у Visual Studio пројекат":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="f76ae-177">Користите C# клијентску библиотеку</span><span class="sxs-lookup"><span data-stu-id="f76ae-177">Use the C# client library</span></span>

1. <span data-ttu-id="f76ae-178">Користите [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) да бисте добили `AccessToken` користећи своје постојећу [регистрацију Azure апликације](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="f76ae-178">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="f76ae-179">Након успешне потврде идентитета и прибављања токена, направите нови или користите постојећи `HttpClient` са додатним **DefaultRequestHeaders "Authorization"** подешеним на **Носилац<access token>** и **Ocp-Apim-Subscription-Key** подешеним на [**кључ претплате** из вашег Customer Insights окружења](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="f76ae-179">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="f76ae-180">Ресетујте заглавље **Овлашћење** по потреби.</span><span class="sxs-lookup"><span data-stu-id="f76ae-180">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="f76ae-181">На пример, када је токен истекао.</span><span class="sxs-lookup"><span data-stu-id="f76ae-181">For example, when the token expired.</span></span>

1. <span data-ttu-id="f76ae-182">Проследите `HttpClient` у конструкцију `CustomerInsights` клијента.</span><span class="sxs-lookup"><span data-stu-id="f76ae-182">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Узорак httpclient-а":::

1. <span data-ttu-id="f76ae-184">Позивајте са клијентом за „методе продужења“, на пример, `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="f76ae-184">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="f76ae-185">Ако је потребан приступ основном `Microsoft.Rest.HttpOperationResponse`, користите „http методе порука“, на пример, `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="f76ae-185">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="f76ae-186">Одговор ће вероватно бити типа `object` јер метод може да врати више типова (на пример, `IList<InstanceInfo>` и `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="f76ae-186">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="f76ae-187">Да бисте проверили тип повратка, можете експлицитно конвертовати објекте у типове одговора наведене на [страници са детаљима API-ја](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) за ту операцију.</span><span class="sxs-lookup"><span data-stu-id="f76ae-187">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="f76ae-188">Ако су потребне додатне информације о захтеву, користите **http методе порука** за приступ необрађеном објекту одговора.</span><span class="sxs-lookup"><span data-stu-id="f76ae-188">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="f76ae-189">NodeJS пакет</span><span class="sxs-lookup"><span data-stu-id="f76ae-189">NodeJS package</span></span>

<span data-ttu-id="f76ae-190">Користите NodeJS клијентске библиотеке доступне преко NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="f76ae-190">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="f76ae-191">Python пакет</span><span class="sxs-lookup"><span data-stu-id="f76ae-191">Python package</span></span>

<span data-ttu-id="f76ae-192">Користите Python клијентске библиотеке доступне преко PyPi: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="f76ae-192">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
