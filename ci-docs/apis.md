---
title: Радите са Customer Insights API-јем
description: Користите API-је и схватите ограничења.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387358"
---
# <a name="work-with-customer-insights-apis"></a>Радите са Customer Insights API-јем

Dynamics 365 Customer Insights пружа API-је за изградњу властитих апликација на основу ваших података у услузи Customer Insights.

> [!IMPORTANT]
> Детаљи ових API-ја наведени су у чланку [Референца за Customer Insights API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Садрже додатне информације о операцијама, параметрима и одговорима.

Испробајте АПИ-је за корисничке увиде, креирајте Азуре регистрацију апликација и први кораци у библиотекама клијената.

## <a name="get-started-trying-the-customer-insights-apis"></a>Започните уз испробавање Customer Insights API-ја

Омогућите АПИ-је корисничких увида и испробајте их. Администратор "Увиди клијената" мора да омогући АПИ приступ увидима клијената. Када се омогући приступ, сваки корисник може да користи АПИ са кључем за претплату.

1. [Пријавите се](https://home.ci.ai.dynamics.com) у Customer Insights. Ако још увек немате претплату, [пријавите се за пробну верзију услуге Customer Insights](https://aka.ms/tryci).

1. Идите на **администраторске** > **мере безбедности** и изаберите **картицу АПИ.**

1. Ако АПИ приступ окружењу није подешен, изаберите опцију **Омогући** .

   Омогућавање API-ја креира примарни и секундарни кључ претплате за вашу инстанцу који се користи у API захтевима. Да бисте поново генерисали кључеве, на **картици "АПИС" изаберите** **ставку"Регенериши примарну** **или регенериши секундарну"**.

1. Изаберите [**ставку Истражите наше АПИ-је**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) да бисте испробали АПИ-је.

1. Потражите и изаберите АПИ операцију и изаберите **покушајте**.

   :::image type="content" source="media/try-api.png" alt-text="Како да тестирате API-је.":::

1. У бочном окну, подесите вредност у падајућем менију **Овлашћење** на **имплицитно**. Заглавље `Authorization` се додаје са токеном носиоца. Кључ за претплату се аутоматски попуњава.
  
1. По жељи додајте све потребне параметре упита.

1. Померите се до дна бочног окна и изаберите **Пошаљи**.

   ХТТП одговор се приказује на дну окна.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Направите нову регистрацију апликације на Azure порталу

Креирајте нову регистрацију [апликација](/graph/auth-register-app-v2) да бисте користили АПИ-је корисничких увида у Азуре апликацији користећи делегиране дозволе.

1. Довршите одељак [Први кораци](#get-started-trying-the-customer-insights-apis).

1. Пријавите се на [Azure портал](https://portal.azure.com) помоћу налога који може приступити Customer Insights подацима.

1. Потражите, а затим изаберите **ставке Регистрације апликација**.

1. Изаберите **Нова регистрација**, наведите назив апликације и одаберите тип налога.

   Опционално додајте URL преусмеравања. http://localhost је довољан за развој апликације на вашем локалном рачунару.

1. Изаберите **Регистрација**:

1. На новој регистрацији апликације идите на **Дозволе за API-је**.

1. У **бочном окну изаберите** ставку **Додај дозволу и изаберите Дyнамицс 365 АИ за увиде** клијената.

1. За **Тип дозволе**, изаберите **Делегиране дозволе**, а затим изаберите дозволу **user_impersonation**.

1. Изаберите ставку **Додајте дозволе**.

1. Изаберите **Дајте сагласност администратора за...** да бисте довршили регистрацију апликације.

1. Да бисте приступили АПИ-у без пријављивања корисника, идите на [дозволе апликације "Сервер-то-сервер"](#server-to-server-application-permissions).

ИД апликације/клијента можете користити за [регистрацију ове апликације у Мицрософт библиотеци за потврду идентитета (МСАЛ)](/azure/active-directory/develop/msal-overview) да бисте добили ознаку носиоца коју ћете послати АПИ-у.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

За информације о коришћењу API-ја у нашим клијентским библиотекама, погледајте [Customer Insights клијентске библиотеке](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Дозволе за апликације са сервера на сервер

Креирајте регистрацију апликације за коју није потребна интеракција корисника и може се покренути на серверу.

1. При регистрацији апликације на Azure порталу идите на **Дозволе за API-је**.

1. Изаберите **Додај дозволу**.

1. Изаберите картицу **API-ји које користи моја организација** картицу и са листе изаберите **Dynamics 365 AI за Customer Insights**.

1. За **Тип дозволе**, изаберите **Дозволе за апликацију**, а затим изаберите дозволу **CustomerInsights.Api.All**.

1. Изаберите ставку **Додајте дозволе**.

1. На новој регистрацији апликације вратите се на **Дозволе за API-је**.

1. Изаберите **Дајте сагласност администратора за...** да бисте довршили регистрацију апликације.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Додајте име регистрације апликације као корисника у увид купца.

   1. Отворите опцију "Увиди клијената", идите у **администратор безбедност** > **и** изаберите ставку **Додај кориснике**.

   1. Потражите име регистрације апликације, изаберите је из резултата претраге и изаберите **Сачувај**.

## <a name="sample-queries"></a>Пробни упити

Да би кратка листа пробних упита ОДата радила са АПИ-јем, погледајте [примере упита ОДата](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Customer Insights клијентске библиотеке

Први кораци у коришћењу библиотека клијената доступних за АПИ-је корисничких увида. Сав изворни кôд библиотеке и примери апликација могу се наћи на [Customer Insights GitHub страници](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).

### <a name="c-nuget"></a>C# NuGet

Користите библиотеке Ц# клијената из NuGet .орг. Тренутно је на мети пакета нетстандард 2.0 и нетцореапп 2.0 фрамеwоркс. Више информација о пакету потражите NuGet у чланку [Мицрософт.Дyнамицс.ЦустомерИнсигхтс.Апи](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).

#### <a name="add-the-c-client-library-to-a-c-project"></a>Додајте C# клијентску библиотеку у C# пројекат

1. У програму Visual Studio, отворите **NuGet менаџер пакета** за пројекат.

1. Потражите **Microsoft.Dynamics.CustomerInsights.Api**.

1. Изаберите **Инсталирај** за додавање пакета у пројекат.

   Алтернативно, покрените ову команду у **NuGet конзоли менаџера пакета**:`Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Користите C# клијентску библиотеку

1. Користите [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) да бисте добили `AccessToken` користећи своје постојећу [регистрацију Azure апликације](#create-a-new-app-registration-in-the-azure-portal).

1. Након успешне потврде идентитета и прибављања симбола, `HttpClient` направите нови или користите постојећи са "Овлашћењем" подразумеваних главе постављеним на "Овлашћење" носиоца "токен за приступ" и **Оцп**-Апим-Претплатнички кључ **постављен** на кључ за претплату из **окружења "Увиди купаца** " [**·** .](#get-started-trying-the-customer-insights-apis)   

   Ресетујте заглавље **Овлашћење** по потреби. На пример, када је токен истекао.

1. Проследите `HttpClient` у конструкцију `CustomerInsights` клијента.

   <!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Позивајте са клијентом за „методе продужења“, на пример, `GetAllInstancesAsync`. Ако је жељени приступ основној `Microsoft.Rest.HttpOperationResponse`, користите"хттп методе поруке", на пример. `GetAllInstancesWithHttpMessagesAsync`

1. Одговор је вероватно тип јер `object` метод може да врати више типова (на пример, `IList<InstanceInfo>` и `ApiErrorResult`). Да бисте проверили тип повраћаја, користите објекте у типовима одговора наведеним на страници [АПИ детаља за](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) ту операцију.

   Ако су потребне додатне информације о захтеву, користите **http методе порука** за приступ необрађеном објекту одговора.

### <a name="nodejs-package"></a>NodeJS пакет

Користите NodeJS клијентске библиотеке доступне преко NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Python пакет

Користите Python клијентске библиотеке доступне преко PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
