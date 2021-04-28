---
title: LiveRamp конектор
description: Сазнајте како да конфигуришете везу и извезете у LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760345"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="777b4-103">Извоз сегмената у LiveRamp&reg; (верзија за преглед)</span><span class="sxs-lookup"><span data-stu-id="777b4-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="777b4-104">Активирајте своје податке у услузи LiveRamp да бисте се повезали са преко 500 платформи на дигиталним, друштвеним и телевизијским системима.</span><span class="sxs-lookup"><span data-stu-id="777b4-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="777b4-105">Радите са својим подацима у услузи LiveRamp да бисте циљали, потиснули и персонализовали огласне кампање.</span><span class="sxs-lookup"><span data-stu-id="777b4-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="777b4-106">Предуслови за везу</span><span class="sxs-lookup"><span data-stu-id="777b4-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="777b4-107">За употребу овог конектора потребна вам је претплата на LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="777b4-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="777b4-108">Да бисте добили претплату, [контактирајте LiveRamp](https://liveramp.com/contact/) директно.</span><span class="sxs-lookup"><span data-stu-id="777b4-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="777b4-109">[Сазнајте више о услузи LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="777b4-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="777b4-110">Подешавање везе у услузи LiveRamp</span><span class="sxs-lookup"><span data-stu-id="777b4-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="777b4-111">Идите на **Администратор** > **Везе**.</span><span class="sxs-lookup"><span data-stu-id="777b4-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="777b4-112">Изаберите **Додај везу** и бирајте **LiveRamp** да бисте конфигурисали везу.</span><span class="sxs-lookup"><span data-stu-id="777b4-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="777b4-113">Дајте вези препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="777b4-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="777b4-114">Име за приказ и врста везе описују ову везу.</span><span class="sxs-lookup"><span data-stu-id="777b4-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="777b4-115">Препоручујемо да одаберете назив који објашњава сврху и циљ везе.</span><span class="sxs-lookup"><span data-stu-id="777b4-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="777b4-116">Одаберите ко може да користи ову везу.</span><span class="sxs-lookup"><span data-stu-id="777b4-116">Choose who can use this connection.</span></span> <span data-ttu-id="777b4-117">Ако ништа не предузмете, подразумевани ће бити Администратори.</span><span class="sxs-lookup"><span data-stu-id="777b4-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="777b4-118">За више информација, погледајте [Дозволите сарадницима да користе везу за извоз](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="777b4-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="777b4-119">Обезбедите **Корисничко име** и **Лозинку** за свој LiveRamp Secure FTP (SFTP) налог.</span><span class="sxs-lookup"><span data-stu-id="777b4-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="777b4-120">Ови акредитиви могу бити различити од ваших акредитива за LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="777b4-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="777b4-121">Изаберите **Верификуј** да тестирате везу са услугом LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="777b4-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="777b4-122">Након успешне верификације, дајте свој пристанак за **Приватност података и усаглашеност** тако што ћете изабрати поље за потврду **Слажем се**.</span><span class="sxs-lookup"><span data-stu-id="777b4-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="777b4-123">Изаберите **Сачувај** да бисте креирали везу.</span><span class="sxs-lookup"><span data-stu-id="777b4-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="777b4-124">Конфигурисање извоза</span><span class="sxs-lookup"><span data-stu-id="777b4-124">Configure an export</span></span>

<span data-ttu-id="777b4-125">Овај извоз можете да конфигуришете ако имате приступ вези ове врсте.</span><span class="sxs-lookup"><span data-stu-id="777b4-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="777b4-126">За више информација погледајте [Дозволе потребне за конфигурисање извоза](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="777b4-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="777b4-127">Идите на **Подаци** > **Извози**.</span><span class="sxs-lookup"><span data-stu-id="777b4-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="777b4-128">Да бисте креирали нови извоз, изаберите **Додај одредиште**.</span><span class="sxs-lookup"><span data-stu-id="777b4-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="777b4-129">У пољу **Веза за извоз**, одаберите везу из одељка LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="777b4-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="777b4-130">Ако не видите назив овог одељка, не постоје вам доступне везе овог типа.</span><span class="sxs-lookup"><span data-stu-id="777b4-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="777b4-131">У пољу **Одаберите свој идентификатор кључа**, изаберите **Е-пошта**, **Име и адреса** или **Телефон** за слање у LiveRamp ради решавања идентитета.</span><span class="sxs-lookup"><span data-stu-id="777b4-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="777b4-132">![LiveRamp конектор са мапирањем атрибута](media/export-liveramp-segments.png "LiveRamp конектор са мапирањем атрибута")</span><span class="sxs-lookup"><span data-stu-id="777b4-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="777b4-133">Мапирајте одговарајуће атрибуте вашег обједињеног ентитета клијента за изабрани идентификатор кључа.</span><span class="sxs-lookup"><span data-stu-id="777b4-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="777b4-134">Изаберите **Додај атрибут** да бисте мапирали више атрибута за слање у LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="777b4-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="777b4-135">Ако пошаљете више кључних атрибута идентификатора у LiveRamp, вероватно ће добити вишу стопу подударања.</span><span class="sxs-lookup"><span data-stu-id="777b4-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="777b4-136">Изаберите сегменте које желите да извезете у LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="777b4-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="777b4-137">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="777b4-137">Select **Save**.</span></span>

<span data-ttu-id="777b4-138">Чување извоза не покреће извоз одмах.</span><span class="sxs-lookup"><span data-stu-id="777b4-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="777b4-139">Извоз се покреће са сваким [заказаним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="777b4-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="777b4-140">Такође можете да [извезете податке на захтев](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="777b4-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="777b4-141">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="777b4-141">Data privacy and compliance</span></span>

<span data-ttu-id="777b4-142">Када омогућите да Dynamics 365 Customer Insights преноси податке у Liveramp, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="777b4-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="777b4-143">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Liveramp испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="777b4-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="777b4-144">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="777b4-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="777b4-145">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="777b4-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
