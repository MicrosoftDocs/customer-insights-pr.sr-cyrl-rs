---
title: Рад са API-јима
description: Користите API-је и схватите ограничења.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: b1e022f8afb8b7dbb707636009b6a25ee242a4e0
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354803"
---
# <a name="work-with-customer-insights-apis"></a>Радите са Customer Insights API-јем

Dynamics 365 Customer Insights пружа API-је за изградњу властитих апликација на основу ваших података у услузи Customer Insights.

> [!IMPORTANT]
> Детаљи ових API-ја наведени су у чланку [Референца за Customer Insights API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Садрже додатне информације о операцијама, параметрима и одговорима.

Овај чланак описује како да приступите Customer Insights API-јима, креирате регистрацију Azure апликације и започнете са доступним библиотекама клијената.

## <a name="get-started-trying-the-customer-insights-apis"></a>Започните уз испробавање Customer Insights API-ја

1. [Пријавите се](https://home.ci.ai.dynamics.com) у Customer Insights. Ако још увек немате претплату, [пријавите се за пробну верзију услуге Customer Insights](https://aka.ms/tryci).

1. Да бисте омогућили API-је у вашем Customer Insights окружењу, идите на **Администратор** > **Дозволе**. За то ће вам требати дозволе администратора.

1. Иди на картицу **API-ји** и изаберите дугме **Омогући**.    
 
   Омогућавање API-ја креира примарни и секундарни кључ претплате за вашу инстанцу који се користи у API захтевима. Кључеве можете да поново генеришете тако што ћете изабрати **Поново генериши примарни** или **Поново генериши секундарни** на **Администратор** > **Дозволе** > **API-ји**.

<!--  :::image type="content" source="media/enable-apis.gif" alt-text="Enable Customer Insights APIs."::: -->

1. Изаберите **Истражите наше API-је** да [испробате API-је](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Изаберите операцију API-ја и изаберите **Испробајте**.

1. У бочном окну, подесите вредност у падајућем менију **Овлашћење** на **имплицитно**. Заглавље `Authorization` се додаје са токеном носиоца. Кључ претплате ће се аутоматски попунити.
  
1. По жељи додајте све потребне параметре упита.

1. Померите се до дна бочног окна и изаберите **Пошаљи**.

HTTP одговор ће се ускоро појавити испод.

<!--   :::image type="content" source="media/try-apis.gif" alt-text="How to test the APIs."::: -->

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Направите нову регистрацију апликације на Azure порталу

Ови кораци вам помажу да започнете са коришћењем Customer Insights API-ја у Azure апликацији помоћу делегираних дозвола. Обавезно прво попуните [одељак „Први кораци“](#get-started-trying-the-customer-insights-apis).

1. Пријавите се на [Azure портал](https://portal.azure.com) помоћу налога који може приступити Customer Insights подацима.

1. С леве стране изаберите **Регистрације апликација**.

1. Изаберите **Нова регистрација**, наведите назив апликације и одаберите тип налога.
 
   Опционално додајте URL преусмеравања. http://localhost је довољан за развој апликације на вашем локалном рачунару.

1. На новој регистрацији апликације идите на **Дозволе за API-је**.

<!--   :::image type="content" source="media/app-registration-1.gif" alt-text="How to set API permissions in App registration."::: -->

1. Изаберите **Додајте дозволу** и изаберите **Customer Insights** у бочном окну.

1. За **Тип дозволе**, изаберите **Делегиране дозволе**, а затим изаберите дозволу **user_impersonation**.

1. Изаберите ставку **Додајте дозволе**. Ако вам је потребан приступ API-ју без пријављивања корисника, прегледајте одељак [Дозволе за апликације од сервера до сервера](#server-to-server-application-permissions).

1. Изаберите **Дајте сагласност администратора за...** да бисте довршили регистрацију апликације.

Можете да користите ID апликације/клијента за регистрацију ове апликације у Microsoft Authentication Library (MSAL) да бисте добили токен носиоца који ћете са захтевом послати у API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

За више информација о MSAL-у, погледајте [Преглед Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).

За више информација о регистрацији апликација у услузи Azure, погледајте [Регистровање апликације](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).

За информације о коришћењу API-ја у нашим клијентским библиотекама, погледајте [Customer Insights клијентске библиотеке](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Дозволе за апликације са сервера на сервер

[Одељак за регистрацију апликација](#create-a-new-app-registration-in-the-azure-portal) описује како се региструје апликација која захтева да се корисник пријави ради потврде идентитета. Сазнајте како да креирате регистрацију апликације која не захтева интеракцију корисника и која се може покренути на серверу.

1. При регистрацији апликације на Azure порталу идите на **Дозволе за API-је**.

1. Изаберите **Додај дозволу**. 

1. Изаберите картицу **API-ји које користи моја организација** картицу и са листе изаберите **Dynamics 365 AI за Customer Insights**. 

1. За **Тип дозволе**, изаберите **Дозволе за апликацију**, а затим изаберите дозволу **CustomerInsights.Api.All**.

1. Изаберите ставку **Додајте дозволе**.

1. На новој регистрацији апликације вратите се на **Дозволе за API-је**.

1. Изаберите **Дајте сагласност администратора за...** да бисте довршили регистрацију апликације.

 <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

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

 <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Користите C# клијентску библиотеку

1. Користите [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) да бисте добили `AccessToken` користећи своје постојећу [регистрацију Azure апликације](#create-a-new-app-registration-in-the-azure-portal).

1. Након успешног потврде идентитета и прибављања симбола, направите нови или користите постојећи са додатним ДефаултРеqуестХеадерс "Ауторизатион" постављеним `HttpClient` на Беарер "токен за приступ" **и** Оцп-Апим-Субсцриптион-Кеy **постављен** на претплатнички кључ из **окружења"Увиди купаца"**[**.**](#get-started-trying-the-customer-insights-apis)   
 
   Ресетујте заглавље **Овлашћење** по потреби. На пример, када је токен истекао.

1. Проследите `HttpClient` у конструкцију `CustomerInsights` клијента.

<!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Упућујте позиве клијенту за „методе проширења“, на пример, `GetAllInstancesAsync`. Ако је потребан приступ основном `Microsoft.Rest.HttpOperationResponse`, користите „методе http порука“ – на пример, `GetAllInstancesWithHttpMessagesAsync`.

1. Одговор ће вероватно бити типа `object` јер метод може да врати више типова (на пример, `IList<InstanceInfo>` и `ApiErrorResult`). Да бисте проверили тип повратка, можете експлицитно конвертовати објекте у типове одговора наведене на [страници са детаљима API-ја](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) за ту операцију.    
   
   Ако су потребне додатне информације о захтеву, користите **http методе порука** за приступ необрађеном објекту одговора.

### <a name="nodejs-package"></a>NodeJS пакет

Користите NodeJS клијентске библиотеке доступне преко NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Python пакет

Користите Python клијентске библиотеке доступне преко PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE[footer-include](../includes/footer-banner.md)]
