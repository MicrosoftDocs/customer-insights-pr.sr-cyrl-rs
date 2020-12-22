---
title: LiveRamp конектор
description: Сазнајте како да извезете податке у LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 86aa8c66a47ee61741082c95f05d2e5ce3f06f35
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667202"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="27611-103">LiveRamp&reg; конектор (преглед)</span><span class="sxs-lookup"><span data-stu-id="27611-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="27611-104">Активирајте своје податке у услузи LiveRamp да бисте се повезали са преко 500 платформи у дигиталним, друштвеним и ТВ екосистемима.</span><span class="sxs-lookup"><span data-stu-id="27611-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="27611-105">Радите са својим подацима у услузи LiveRamp да бисте циљали, потиснули и персонализовали огласне кампање.</span><span class="sxs-lookup"><span data-stu-id="27611-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="27611-106">Предуслови</span><span class="sxs-lookup"><span data-stu-id="27611-106">Prerequisites</span></span>

- <span data-ttu-id="27611-107">За употребу овог конектора потребна вам је претплата на LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="27611-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="27611-108">Да бисте добили претплату, [контактирајте LiveRamp](https://liveramp.com/contact/) директно.</span><span class="sxs-lookup"><span data-stu-id="27611-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="27611-109">[Сазнајте више о услузи LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="27611-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="27611-110">Повезивање на LiveRamp</span><span class="sxs-lookup"><span data-stu-id="27611-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="27611-111">У увидима о корисницима идите на **Администратор** > **Одредишта за извоз**.</span><span class="sxs-lookup"><span data-stu-id="27611-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="27611-112">На плочици **LiveRamp** изаберите **Подеси**.</span><span class="sxs-lookup"><span data-stu-id="27611-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="27611-113">Дајте одредишту препознатљиво име у пољу **Име за приказ**.</span><span class="sxs-lookup"><span data-stu-id="27611-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="27611-114">Обезбедите **Корисничко име** и **Лозинку** за свој LiveRamp Secure FTP (SFTP) налог.</span><span class="sxs-lookup"><span data-stu-id="27611-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="27611-115">Ови акредитиви могу бити различити од ваших акредитива за LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="27611-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="27611-116">Изаберите **Верификуј** да тестирате везу са услугом LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="27611-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="27611-117">Након успешне верификације, дајте свој пристанак за **Приватност података и усаглашеност** тако што ћете изабрати поље за потврду **Слажем се**.</span><span class="sxs-lookup"><span data-stu-id="27611-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="27611-118">Изаберите **Следеће** да подесите LiveRamp конектор.</span><span class="sxs-lookup"><span data-stu-id="27611-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="27611-119">Конфигурисање конектора</span><span class="sxs-lookup"><span data-stu-id="27611-119">Configure the connector</span></span>

1. <span data-ttu-id="27611-120">У пољу **Одаберите свој идентификатор кључа**, изаберите **Е-пошта**, **Име и адреса** или **Телефон** за слање у LiveRamp ради решавања идентитета.</span><span class="sxs-lookup"><span data-stu-id="27611-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="27611-121">Мапирајте одговарајуће атрибуте вашег обједињеног ентитета клијента за изабрани идентификатор кључа.</span><span class="sxs-lookup"><span data-stu-id="27611-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="27611-122">Изаберите **Додај атрибут** да бисте мапирали додатне атрибуте које треба послати у LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="27611-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="27611-123">Ако пошаљете више кључних атрибута идентификатора у LiveRamp, вероватно ће добити вишу стопу подударања.</span><span class="sxs-lookup"><span data-stu-id="27611-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="27611-124">Изаберите сегменте које желите да извезете у LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="27611-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="27611-125">Изаберите ставку **Сачувај**.</span><span class="sxs-lookup"><span data-stu-id="27611-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="27611-126">![LiveRamp конектор са мапирањем атрибута](media/export-liveramp-segments.png "LiveRamp конектор са мапирањем атрибута")</span><span class="sxs-lookup"><span data-stu-id="27611-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="27611-127">Извоз података</span><span class="sxs-lookup"><span data-stu-id="27611-127">Export the data</span></span>

<span data-ttu-id="27611-128">Извоз ће почети ускоро ако су испуњени сви предуслови за извоз.</span><span class="sxs-lookup"><span data-stu-id="27611-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="27611-129">Извоз ће се такође покренути са сваким [планираним освежавањем](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="27611-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="27611-130">Након што је извоз успешно завршен, можете се пријавити у LiveRamp Onboarding да бисте активирали и дистрибуирали своје податке.</span><span class="sxs-lookup"><span data-stu-id="27611-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="27611-131">Приватност података и усаглашеност</span><span class="sxs-lookup"><span data-stu-id="27611-131">Data privacy and compliance</span></span>

<span data-ttu-id="27611-132">Када омогућите да Dynamics 365 Customer Insights преноси податке у Liveramp, дозвољавате пренос података изван границе усклађености за Dynamics 365 Customer Insights, укључујући потенцијално осетљиве податке као што су лични подаци.</span><span class="sxs-lookup"><span data-stu-id="27611-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="27611-133">Microsoft ће преносити такве податке по вашем упутству, али ви сте одговорни за то да Liveramp испуњава све обавезе приватности или безбедности које имате.</span><span class="sxs-lookup"><span data-stu-id="27611-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="27611-134">За више информација погледајте [Изјаву о приватности компаније Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="27611-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="27611-135">Dynamics 365 Customer Insights администратор може у сваком тренутку да уклони одредиште за извоз како бисте престали са коришћењем ове функционалности.</span><span class="sxs-lookup"><span data-stu-id="27611-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>