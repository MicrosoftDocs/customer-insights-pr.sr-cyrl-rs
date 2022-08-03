---
title: Power Automate линија спајања (преглед) | Мицрософт документи
description: Креирајте токове у услузи Microsoft Power Automate из услуге Dynamics 365 Customer Insights.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sr-Cyrl-RS
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196136"
---
# <a name="power-automate-connector-preview"></a>Power Automate конектор (преглед)

Покрените одређене догађаје који се појављују аутоматски када се промене подаци и управљајте сложенијим токовима директно у услузи [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Позната ограничења

- Највише 100 позива на 60 секунди. Користите [параметар $ скип да](/connectors/customerinsights/#get-items-from-an-entity) бисте позвали АПИ крајња тачка више пута.

## <a name="power-automate-triggers"></a>Power Automate окидачи

Користите окидаче да креирате токове у облаку и аутоматизујете понављајуће задатке, као што су обавештења или напредније радње. Користи окидаче када:

- Освежавање извор података не успе.
- Освежавање извор података успе.
- Праг се прелази на сегменту. Окидач је ограничен на прекорачење граничне вредности.
- Праг се прелази на пословној мери. Подржане су само пословне мере без димензије. Окидач је ограничен на прекорачење граничне вредности.
- Комплетно планирано освежавање је довршено. Овај окидач не ради за ручно започето освежавање.
- Освежавање процеса уједињења је довршено.

[Конфигуришите окидаче у услузи Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate радње

Power Automate конектор пружа друге радње осим доступних окидача. За више информација погледајте [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Креирање Power Automate тока

1. Идите на **Администратор** > **Везе**.

1. На плочици **Power Automate** изаберите **Подеси**.

1. Отвара се Customer Insights конектор (преглед) у услузи Power Automate. **Пријавите се** у Power Automate.

1. Изаберите један од доступних окидача и додајте још корака свом новом току. За више информација погледајте [Креирање тока у облаку у услузи Power Automate](/power-automate/get-started-logic-flow).

Примери како се користе токови: 
- Пошаљите поруку на Microsoft Teams канал ако освежавање извора података не успе. 
- Пошаљите е-поруку власницима података када се пређе праг на сегменту.

[!INCLUDE [footer-include](includes/footer-banner.md)]
