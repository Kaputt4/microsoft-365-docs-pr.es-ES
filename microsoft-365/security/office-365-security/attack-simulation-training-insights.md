---
title: Obtenga información a través de la formación de simulación de ataques
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Obtenga información sobre cómo la formación de simulación de ataques en el centro de seguridad 365 de Microsoft afecta a los empleados y información sobre los resultados de simulación y formación.
ms.openlocfilehash: 6a8ee15f14475a1cebb169ab49bdb0f490c81345
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357356"
---
# <a name="gain-insights-through-attack-simulation-training"></a>Obtenga información a través de la formación de simulación de ataques

En el curso de la simulación de ataques, Microsoft le proporciona información sobre la base de los resultados de las simulaciones y los empleados de formación que han pasado. Esta información le ayudará en el progreso de los empleados en cuanto a la disponibilidad de amenazas, así como recomendar pasos a seguir para preparar mejor a sus empleados y su entorno para los ataques.

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Estamos trabajando continuamente en la información de expansión que tiene a su disposición, con el impacto del comportamiento y las acciones recomendadas actualmente disponibles.
Para empezar, vaya a [formación para la simulación de ataques en el centro de seguridad de Microsoft 365](https://security.microsoft.com/attacksimulator?viewid=overview).

## <a name="behavior-impact-on-compromise-rate"></a>Impacto en el comportamiento de la tasa de exposición

En la ficha **información general** sobre la simulación de ataques, encontrará el **impacto del comportamiento en la tarjeta de tasa de riesgos** . Esta tarjeta muestra cómo los empleados se ocupan de la simulación que ejecutó en contraste con la **tasa de compromiso pronosticada**. Puede usar estos conocimientos para realizar un seguimiento del progreso de la disponibilidad de las amenazas de los empleados mediante la ejecución de varias simulaciones en los mismos grupos de empleados.

En el gráfico, puede ver:

- **Tasa de compromiso pronosticada** que refleja el índice de compromiso medio de las simulaciones usando el mismo tipo de carga entre los inquilinos mediante la simulación de ataques.
- **Tasa de compromiso real** refleja el porcentaje de empleados que se descendión para la simulación.

Además, `<number> less susceptible to phishing` refleja la diferencia entre el número real de empleados que corre el ataque y la tasa de compromiso pronosticada. Es menos probable que este número de empleados se vea comprometido por ataques similares en el futuro, a la vez que `<percent%> better than predicted rate` indica el modo en que los empleados en general se comparan con la tasa de compromiso pronosticada.

> [!div class="mx-imgBorder"]
> ![Tarjeta de impacto del comportamiento en información general de formación sobre simulación de ataques](../../media/attack-sim-preview-behavior-impact-card.png)

Para ver un informe más detallado, haga clic en **Ver simulaciones y entrenar la eficacia del informe** , que proporciona la misma información con contexto adicional de la propia simulación, como la técnica de simulación y el total de usuarios a los que se destina.

## <a name="recommended-actions"></a>Acciones recomendadas

En la [pestaña **simulaciones**](https://security.microsoft.com/attacksimulator?viewid=simulations), al seleccionar cualquiera de las simulaciones, se mostrarán detalles de simulación. A continuación, encontrará la sección **acciones recomendadas** .

En la sección acciones recomendadas se detallan las recomendaciones disponibles en [calificación segura de Microsoft](../mtp/microsoft-secure-score.md). Estas recomendaciones se basan en la carga que se usa en la simulación y le ayudarán a proteger a sus empleados y su entorno. Al hacer clic en cada acción de mejora irá a sus detalles.

> [!div class="mx-imgBorder"]
> ![Sección acciones de recomendación en el aprendizaje de simulación de ataques](../../media/attack-sim-preview-recommended-actions.png)

## <a name="related-links"></a>Vínculos relacionados

**Simulador de ataque** [cree una simulación de ataque de suplantación de identidad](attack-simulation-training.md) y [cree una carga para entrenar a sus usuarios](attack-simulation-training-payloads.md)
