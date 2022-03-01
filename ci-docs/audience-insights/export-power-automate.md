---
title: Power Automate конектор | Microsoft Docs
description: Креирајте токове у услузи Microsoft Power Automate из услуге Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406833"
---
# <a name="power-automate-connector-preview"></a>Power Automate конектор (преглед)

Покрените одређене догађаје који се појављују аутоматски када се промене подаци и управљајте сложенијим токовима директно у услузи [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Power Automate окидачи

Можете користити разне окидаче који вам омогућавају да креирате токове за аутоматизацију задатака који се понављају, попут обавештења или напреднијих радњи. 

- Покрените када не успе освежавање извора података. 
- Покрените када успе освежавање извора података.
- Покрените када се пређе гранична вредност за сегмент. Окидач је ограничен на прекорачење граничне вредности.
- Покрените када се пређе гранична вредност за пословну меру. Окидач је ограничен на прекорачење граничне вредности.
- Активира се када се заврши потпуно освежавање (извора података, сегмената, мера...).
- Покрените када се заврши освежавање процеса обједињавања (мапирање, подударање, спајање).

[Конфигурисање окидача у услузи Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Power Automate радње
Power Automate конектор пружа друге радње осим доступних окидача. За више информација погледајте [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Креирајте Power Automate ток у увидима о корисницима

1. У увидима о корисницима идите на **Администратор** > **Систем**.

1. На страници **Систем** изаберите картицу **Статус**.

1. У одељку **Извори података** изаберите **Токови** и изаберите **Креирање тока** из падајуће листе.
   > [!div class="mx-imgBorder"]
   > ![Power Automate конектор који приказује радњу „Креирај ток“](media/power-automate-connector-create-flow.png "Power Automate конектор који приказује радњу „Креирај ток“")

1. У услузи Power Automate, изаберите један од доступних окидача да бисте креирали жељени ток. Ако креирате први ток, прво ћете морати да потврдите идентитет помоћу Power Automate конектора.
