---
title: Power Automate конектор | Microsoft Docs
description: Креирајте токове у услузи Microsoft Power Automate из услуге Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268842"
---
# <a name="power-automate-connector-preview"></a>Power Automate конектор (преглед)

Покрените одређене догађаје који се појављују аутоматски када се промене подаци и управљајте сложенијим токовима директно у услузи [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Power Automate окидачи

Користите окидаче да креирате токове у облаку и аутоматизујете понављајуће задатке, као што су обавештења или напредније радње. 

- Покрените када не успе освежавање извора података. 
- Покрените када успе освежавање извора података.
- Покрените када се пређе гранична вредност за сегмент. Окидач је ограничен на прекорачење граничне вредности.
- Покрените када се пређе гранична вредност за пословну меру. Окидач је ограничен на прекорачење граничне вредности.
- Активира се када се заврши потпуно освежавање (извора података, сегмената, мера...).
- Покрените када се заврши освежавање процеса обједињавања (мапирање, подударање, спајање).

[Конфигурисање окидача у услузи Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Power Automate радње
Power Automate конектор пружа друге радње осим доступних окидача. За више информација погледајте [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Креирање Power Automate тока

1. У увидима о корисницима идите на **Администратор** > **Одредишта за извоз**.

1. На плочици **Power Automate** изаберите **Подеси**.

1. Отвара се Customer Insights конектор (преглед) у услузи Power Automate. **Пријавите се** у Power Automate.

1. Изаберите један од доступних окидача и додајте још корака свом новом току. За више информација погледајте [Креирање тока у облаку у услузи Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).

Примери коришћења токова: 
- Пошаљите поруку на Microsoft Teams канал ако освежавање извора података не успе. 
- Пошаљите е-поруку власницима података када се пређе праг на сегменту.



[!INCLUDE[footer-include](../includes/footer-banner.md)]