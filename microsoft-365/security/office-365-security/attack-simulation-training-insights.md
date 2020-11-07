---
title: Obtener información mediante el entrenamiento de la simulación de ataques
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
description: Obtenga información sobre cómo el curso de simulación de ataques de los empleados del efecto centro de seguridad de Microsoft 365 y obtenga información de los resultados de la simulación y el entrenamiento.
ms.openlocfilehash: 180ddc773b5a299692e40ddc558d3b3a89f4093b
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944533"
---
# <a name="gain-insights-through-attack-simulation-training"></a>Obtener información mediante el entrenamiento de la simulación de ataques

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

![Tarjeta de impacto del comportamiento en información general de formación sobre simulación de ataques](../../media/attack-sim-preview-behavior-impact-card.png)

Para ver un informe más detallado, haga clic en **Ver simulaciones y entrenar la eficacia del informe** , que proporciona la misma información con contexto adicional de la propia simulación, como la técnica de simulación y el total de usuarios a los que se destina.

## <a name="recommended-actions"></a>Acciones recomendadas

En la [pestaña **simulaciones**](https://security.microsoft.com/attacksimulator?viewid=simulations) , la selección de una de las simulaciones le llevará a los detalles de la simulación. A continuación, encontrará la sección **acciones recomendadas** .

En la sección acciones recomendadas se detallan las recomendaciones disponibles en [calificación segura de Microsoft](../mtp/microsoft-secure-score.md). Estas recomendaciones se basan en la carga que se usa en la simulación y le ayudarán a proteger a sus empleados y su entorno. Al hacer clic en cada acción de mejora irá a sus detalles.

![Sección acciones de recomendación en el aprendizaje de simulación de ataques](../../media/attack-sim-preview-recommended-actions.png)