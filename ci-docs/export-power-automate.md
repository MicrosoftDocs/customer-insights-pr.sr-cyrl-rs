---
title: Power Automate конектор | Microsoft Docs
description: Креирајте токове у услузи Microsoft Power Automate из услуге Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d22c4c785695b23a257a89f1ffa519fdc18b443e
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741197"
---
# <a name="power-automate-connector-preview"></a>Power Automate конектор (преглед)

Покрените одређене догађаје који се појављују аутоматски када се промене подаци и управљајте сложенијим токовима директно у услузи [Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Позната ограничења

- Можете да урадите највише 100 позива на 60 секунди. АПИ можете да позовете крајња тачка више пута помоћу параметра $ скип уређаја. [Сазнајте више о $ скип параметру](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Power Automate окидачи

Користите окидаче да креирате токове у облаку и аутоматизујете понављајуће задатке, као што су обавештења или напредније радње.

- Покрените када не успе освежавање извора података.
- Покрените када успе освежавање извора података.
- Покрените када се пређе гранична вредност за сегмент. Окидач је ограничен на прекорачење граничне вредности.
- Покрените када се пређе гранична вредност за пословну меру. Подржане су само пословне мере без димензије. Окидач је ограничен на прекорачење граничне вредности.
- Активира се када се заврши потпуно освежавање (извора података, сегмената, мера, ...).
- Активирај када се доврши освежавање процеса уједињења.

[Конфигуришите окидаче у услузи Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate радње

Power Automate конектор пружа друге радње осим доступних окидача. За више информација погледајте [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Креирање Power Automate тока

1. Идите на **Администратор** > **Одредишта за извоз**.

1. На плочици **Power Automate** изаберите **Подеси**.

1. Отвара се Customer Insights конектор (преглед) у услузи Power Automate. **Пријавите се** у Power Automate.

1. Изаберите један од доступних окидача и додајте још корака свом новом току. За више информација погледајте [Креирање тока у облаку у услузи Power Automate](/power-automate/get-started-logic-flow).

Примери како се користе токови: 
- Пошаљите поруку на Microsoft Teams канал ако освежавање извора података не успе. 
- Пошаљите е-поруку власницима података када се пређе праг на сегменту.



[!INCLUDE [footer-include](includes/footer-banner.md)]