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
# <a name="work-with-customer-insights-apis"></a>Радите са Customer Insights API-јем

Dynamics 365 Customer Insights пружа API-је за изградњу властитих апликација заснованих на подацима у услузи Customer Insights.

> [!IMPORTANT]
> Детаљи ових API-ја наведени су у чланку [Референца Customer Insights API-ја](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Садрже додатне информације о операцијама, параметрима и одговорима.

Овај чланак вас води кроз приступ Customer Insights API-јима, креирање регистрације Azure апликације и помаже вам да започнете са доступним клијентским библиотекама.

## <a name="get-started-trying-the-customer-insights-apis"></a>Започните уз испробавање Customer Insights API-ја

1. [Пријавите се](https://home.ci.ai.dynamics.com) у Customer Insights. Ако још увек немате претплату, [пријавите се за пробну верзију услуге Customer Insights](https://aka.ms/tryci).

1. Да бисте омогућили API-је у вашем Customer Insights окружењу, идите на **Администратор** > **Дозволе**. За то ће вам требати дозволе администратора.

1. Иди на картицу **API-ји** и изаберите дугме **Омогући**.    
   Омогућавање API-ја креира примарни и секундарни кључ претплате за вашу инстанцу који се користи у API захтевима. Кључеве можете да поново генеришете тако што ћете изабрати **Поново генериши примарни** или **Поново генериши секундарни** на **Администратор** > **Дозволе** > **API-ји**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Омогућавање Customer Insights API-ја":::

1. Изаберите **Истражите наше API-је** да [испробате API-је](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Изаберите операцију API-ја и изаберите **Испробајте**.

1. У бочном окну поставите вредност у падајућем менију **Овлашћење** на **имплицитно**. Заглавље `Authorization` се добија с додатим токеном носиоца. Кључ претплате ће се аутоматски попунити.
  
1. По жељи додајте све потребне параметре упита.

1. Померите се до дна бочног окна и изаберите **Пошаљи**.

HTTP одговор ће се ускоро појавити испод.


   :::image type="content" source="media/try-apis.gif" alt-text="Анимирани GIF који показује како да изаберете тест API-ја.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Направите нову регистрацију апликације на Azure порталу

Ови кораци помажу вам да започнете са коришћењем Customer Insights API-ја у Azure апликацији користећи делегиране дозволе. Обавезно прво завршите [одељак Започните](#get-started-trying-the-customer-insights-apis).

1. Пријавите се на [Azure портал](https://portal.azure.com) помоћу налога који може приступити Customer Insights подацима.

1. С леве стране изаберите **Регистрације апликација**.

1. Изаберите **Нова регистрација**, наведите име апликације и одаберите тип налога.
   Опционално додајте URL преусмеравања. http://localhost је довољан за развој апликације на вашем локалном рачунару.

1. На новој регистрацији апликације идите на **Дозволе за API-је**.

   :::image type="content" source="media/app-registration-1.gif" alt-text="Анимирани GIF за подешавање дозволе за API у регистрацији апликације.":::

1. Изаберите **Додајте дозволу** и изаберите **Customer Insights** у бочном окну.

1. За **Тип дозволе**, изаберите **Делегиране дозволе** и изаберите дозволу **user_impersonation**.

1. Изаберите ставку **Додајте дозволе**. Ако вам је потребан приступ API-ју без пријављивања корисника, прегледајте одељак [Дозволе за апликације од сервера до сервера](#server-to-server-application-permissions).

1. Изаберите **Дајте сагласност администратора за...** да бисте довршили регистрацију апликације.

Можете да користите ID апликације/клијента за регистрацију ове апликације у Microsoft Authentication Library (MSAL) да бисте добили токен носиоца који ћете са захтевом послати у API.

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Анимирани GIF за давање сагласности администратора.":::

За више информација о MSAL-у, погледајте [Преглед Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).

За више информација о регистрацији апликација у услузи Azure погледајте [Ново искуство регистрације апликација за Azure портал](/azure/active-directory/develop/app-registration-portal-training-guide).

За информације о коришћењу API-ја и наших клијентских библиотека, погледајте [Customer Insights клијентске библиотеке](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Дозволе за апликације са сервера на сервер

[Одељак за регистрацију апликација](#create-a-new-app-registration-in-the-azure-portal) описује како се региструје апликација која захтева да се корисник пријави ради потврде идентитета. Сазнајте како да креирате регистрацију апликације која не захтева интеракцију корисника и која се може покренути на серверу.

1. При регистрацији апликације на Azure порталу идите на **Дозволе за API-је**.

1. Изаберите **Додајте дозволу** и изаберите **Customer Insights** у бочном окну.

1. За **Тип дозволе**, изаберите **Дозволе за апликације** и изаберите дозволу **CustomerInsights.Api.All**.

1. Изаберите ставку **Додајте дозволе**.

1. Да бисте дали сагласност администратора за ову дозволу за апликацију, морате да додате принципал услуге.

   1. Инсталирајте Azure Active Directory (AD) PowerShell модул: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`
   1. Повежите се на AD налог: `Connect-AzureAD -TenantId <your tenant id>`. Можете пронаћи свој ID закупца **Преглед** > **Azure Active Directory**.
   1. Покрените следећу команду да бисте додали Azure AD принципал услуге: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` Параметар AppId односи се на апликацију Customer Insights API.

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Узорак принципала услуге":::

1. На новој регистрацији апликације вратите се на **Дозволе за API-је**.

1. Изаберите **Дајте сагласност администратора за...** да бисте довршили регистрацију апликације.

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Анимирани GIF за давање сагласности администратора.":::

1. Да закључимо, морамо да додамо име регистрације апликације као корисника у Customer Insights.    
   Отворите Customer Insights, идите на **Администратор** > **Дозволе** и изаберите **Додај корисника**.

1. Потражите име регистрације апликације, изаберите је из резултата претраге и изаберите **Сачувај**.

## <a name="customer-insights-client-libraries"></a>Customer Insights клијентске библиотеке

Овај одељак вам помаже да започнете коришћење клијентских библиотека доступних за Customer Insights API-је. Сав изворни кôд библиотеке и примери апликација могу се наћи на [Customer Insights GitHub страници](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Сазнајте како да започнете коришћење C# клијентских библиотека са NuGet.org. За више информација о NuGet пакету, видите [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Тренутно овај пакет циља оквире netstandard2.0 и netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Додајте C# клијентску библиотеку у C# пројекат

1. У програму Visual Studio, отворите **NuGet менаџер пакета** за пројекат.

1. Потражите **Microsoft.Dynamics.CustomerInsights.Api**.

1. Изаберите **Инсталирај** за додавање пакета у пројекат.
   Алтернативно, покрените ову команду у **NuGet конзоли менаџера пакета**:`Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Додајте NuGet пакет у Visual Studio пројекат":::

#### <a name="use-the-c-client-library"></a>Користите C# клијентску библиотеку

1. Користите [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) да бисте добили `AccessToken` користећи своје постојећу [регистрацију Azure апликације](#create-a-new-app-registration-in-the-azure-portal).

1. Након успешне потврде идентитета и прибављања токена, направите нови или користите постојећи `HttpClient` са додатним **DefaultRequestHeaders "Authorization"** подешеним на **Носилац<access token>** и **Ocp-Apim-Subscription-Key** подешеним на [**кључ претплате** из вашег Customer Insights окружења](#get-started-trying-the-customer-insights-apis).    
   Ресетујте заглавље **Овлашћење** по потреби. На пример, када је токен истекао.

1. Проследите `HttpClient` у конструкцију `CustomerInsights` клијента.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Узорак httpclient-а":::

1. Позивајте са клијентом за „методе продужења“, на пример, `GetAllInstancesAsync`. Ако је потребан приступ основном `Microsoft.Rest.HttpOperationResponse`, користите „http методе порука“, на пример, `GetAllInstancesWithHttpMessagesAsync`.

1. Одговор ће вероватно бити типа `object` јер метод може да врати више типова (на пример, `IList<InstanceInfo>` и `ApiErrorResult`). Да бисте проверили тип повратка, можете експлицитно конвертовати објекте у типове одговора наведене на [страници са детаљима API-ја](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) за ту операцију.    
   Ако су потребне додатне информације о захтеву, користите **http методе порука** за приступ необрађеном објекту одговора.

### <a name="nodejs-package"></a>NodeJS пакет

Користите NodeJS клијентске библиотеке доступне преко NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Python пакет

Користите Python клијентске библиотеке доступне преко PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE[footer-include](../includes/footer-banner.md)]
