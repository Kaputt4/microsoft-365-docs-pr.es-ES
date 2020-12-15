---
title: Obtenga información a través de la formación de simulación de ataques
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Los administradores pueden obtener información sobre cómo afecta la simulación de ataques en el centro de seguridad de Microsoft 365 y pueden obtener información de los resultados de la simulación y la formación.
ms.openlocfilehash: 6fc109469f8a9a3cf6aa87e9b8f9e3a024fed6e3
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667608"
---
# <a name="gain-insights-through-attack-simulation-training"></a>Obtenga información a través de la formación de simulación de ataques

En el curso de la simulación de ataques, Microsoft le proporciona información sobre la base de los resultados de las simulaciones y los entrenamientos que los empleados pasaron. Esta información le ayudará a mantenerse informado sobre el progreso de la preparación contra amenazas de sus empleados, así como a recomendar pasos a seguir para preparar mejor a sus empleados y su entorno para los ataques.

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Estamos trabajando continuamente en la ampliación de la información que tiene a su disposición. El impacto del comportamiento y las acciones recomendadas están actualmente disponibles. Para empezar, vaya a [formación para la simulación de ataques en el centro de seguridad de Microsoft 365](https://security.microsoft.com/attacksimulator?viewid=overview).

## <a name="behavior-impact-on-compromise-rate"></a>Impacto en el comportamiento de la tasa de exposición

En la ficha **información general** de formación sobre la simulación de ataques, observará el **impacto del comportamiento en** la tarjeta de tasa de riesgos. Esta tarjeta muestra cómo los empleados se ocupan de las simulaciones que ejecutó en contraste con la **tasa de compromiso pronosticada**. Puede usar estos conocimientos para realizar un seguimiento del progreso de la disponibilidad de las amenazas de los empleados mediante la ejecución de varias simulaciones en los mismos grupos de empleados.

En el gráfico, puede ver:

- **Tasa de compromiso pronosticada** que refleja la tasa de compromiso media de las simulaciones que usan el mismo tipo de carga en otros inquilinos de Microsoft 365 que usan la simulación de ataques.
- **Tasa de compromiso real** refleja el porcentaje de empleados que se descendión para la simulación.

Además, `<number> less susceptible to phishing` refleja la diferencia entre el número real de empleados que corre el ataque y la tasa de compromiso pronosticada. Es menos probable que este número de empleados se vea comprometido por ataques similares en el futuro, a la vez que `<percent%> better than predicted rate` indica el modo en que los empleados en general se comparan con la tasa de compromiso pronosticada.

> [!div class="mx-imgBorder"]
> ![Tarjeta de impacto del comportamiento en información general de formación sobre simulación de ataques](../../media/attack-sim-preview-behavior-impact-card.png)

Para ver un informe más detallado, haga clic en **Ver simulaciones y entrenar el informe de eficacia**. Este informe proporciona la misma información con contexto adicional de la propia simulación (por ejemplo, técnica de simulación y total de usuarios de destino).

## <a name="recommended-actions"></a>Acciones recomendadas

En la [pestaña **simulaciones**](https://security.microsoft.com/attacksimulator?viewid=simulations), al seleccionar una simulación, irá a los detalles de la simulación, donde encontrará la sección **acciones recomendadas** .

En la sección acciones recomendadas se detallan las recomendaciones disponibles en [calificación segura de Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score). Estas recomendaciones se basan en la carga que se usa en la simulación y le ayudarán a proteger a sus empleados y su entorno. Al hacer clic en cada acción de mejora irá a sus detalles.

> [!div class="mx-imgBorder"]
> ![Sección acciones de recomendación en el aprendizaje de simulación de ataques](../../media/attack-sim-preview-recommended-actions.png)

## <a name="related-links"></a>Vínculos relacionados

**Simulador de ataque** [cree una simulación de ataque de suplantación de identidad](attack-simulation-training.md) y [cree una carga para entrenar a sus usuarios](attack-simulation-training-payloads.md)
