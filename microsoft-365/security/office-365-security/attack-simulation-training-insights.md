---
title: Obtenga información a través de la formación de simulación de ataques
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Los administradores pueden aprender cómo el aprendizaje de simulación de ataques en el centro de seguridad de Microsoft 365 afecta a los empleados y puede obtener información sobre los resultados de simulación y aprendizaje.
ms.technology: mdo
ms.openlocfilehash: 0fcb88406558f73b587d8452375c33dbbec1c78b
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2021
ms.locfileid: "51600012"
---
# <a name="gain-insights-through-attack-simulation-training"></a>Obtenga información a través de la formación de simulación de ataques

Dentro del aprendizaje de simulación de ataque, Microsoft le proporciona información basada en los resultados de simulaciones y aprendizajes que los empleados han pasado. Estas conclusiones le ayudarán a mantenerse informado sobre el progreso de preparación de amenazas de sus empleados, así como a recomendar los siguientes pasos para preparar mejor a los empleados y su entorno para los ataques.

Estamos trabajando continuamente en la expansión de los conocimientos que están disponibles para usted. El impacto del comportamiento y las acciones recomendadas están disponibles actualmente. Para empezar, dirígete a Formación de simulación de ataques en el Centro de seguridad [de Microsoft 365](https://security.microsoft.com/attacksimulator?viewid=overview).

## <a name="behavior-impact-on-compromise-rate"></a>Impacto del comportamiento en la tasa de compromiso

En la **pestaña Información general** del aprendizaje de simulación de ataque, encontrarás el impacto del comportamiento en la tarjeta de tasa **de** compromiso. Esta tarjeta muestra cómo los empleados trataron las simulaciones que ejecutó en contraste con la tasa **de compromiso predicho.** Puede usar estas perspectivas para realizar un seguimiento del progreso en la preparación de amenazas de los empleados mediante la ejecución de varias simulaciones en los mismos grupos de empleados.

En el gráfico puede ver:

- **Tasa de compromiso** predicho que refleja la tasa de compromiso promedio para las simulaciones que usan el mismo tipo de carga en otros inquilinos de Microsoft 365 que usan el aprendizaje de simulación de ataques.
- **La tasa de compromiso real** refleja el porcentaje de empleados que han caído en la simulación.

Además, refleja la diferencia entre el número real de empleados comprometidos por el ataque y la tasa de compromiso `<number> less susceptible to phishing` predicho. Es menos probable que este número de empleados se vea comprometido por ataques similares en el futuro, mientras que indica cómo lo hacían los empleados en general en contraste con la tasa de `<percent%> better than predicted rate` compromiso predicho.

> [!div class="mx-imgBorder"]
> ![Información general sobre la tarjeta de impacto de comportamiento en el aprendizaje de simulación de ataque](../../media/attack-sim-preview-behavior-impact-card.png)

Para ver un informe más detallado, haga clic **en Ver simulaciones y informe de eficacia de aprendizaje.** Este informe proporciona la misma información con contexto adicional de la propia simulación (por ejemplo, la técnica de simulación y el total de usuarios dirigidos).

## <a name="recommended-actions"></a>Acciones recomendadas

En la [ **pestaña Simulaciones,**](https://security.microsoft.com/attacksimulator?viewid=simulations)la selección de una simulación le llevará a los detalles de la simulación, donde encontrará la **sección Acciones recomendadas.**

En la sección acciones recomendadas se detallan las recomendaciones disponibles en [Puntuación segura de Microsoft](../defender/microsoft-secure-score.md). Estas recomendaciones se basan en la carga usada en la simulación y le ayudarán a proteger a sus empleados y su entorno. Hacer clic en cada acción de mejora le llevará a sus detalles.

> [!div class="mx-imgBorder"]
> ![Sección Acciones de recomendación sobre el aprendizaje de simulación de ataques](../../media/attack-sim-preview-recommended-actions.png)

## <a name="related-links"></a>Vínculos relacionados

[Introducción al uso de aprendizaje de simulación de ataques](attack-simulation-training-get-started.md)

[Crear una simulación de ataque de suplantación de identidad](attack-simulation-training.md)

[crear una carga para entrenar a sus personas](attack-simulation-training-payloads.md)
