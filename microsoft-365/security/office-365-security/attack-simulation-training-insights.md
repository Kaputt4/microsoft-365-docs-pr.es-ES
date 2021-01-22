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
description: Los administradores pueden aprender cómo el aprendizaje de simulación de ataques en el Centro de seguridad de Microsoft 365 afecta a los empleados y puede obtener información a partir de resultados de simulación y aprendizaje.
ms.technology: mdo
ms.openlocfilehash: b7fd414cc355e768077198eb5215720c4d4a9444
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933071"
---
# <a name="gain-insights-through-attack-simulation-training"></a>Obtenga información a través de la formación de simulación de ataques

Dentro del entrenamiento de simulación de ataques, Microsoft proporciona información basada en los resultados de simulaciones y cursos que los empleados han pasado. Estas conclusiones te ayudarán a mantenerte informado sobre el progreso de preparación de amenazas de los empleados, así como a recomendar los siguientes pasos para preparar mejor a los empleados y a tu entorno para los ataques.

Estamos trabajando continuamente en la expansión de las conclusiones que están disponibles para usted. El impacto en el comportamiento y las acciones recomendadas están disponibles actualmente. To start, head over to [Attack simulation training in the Microsoft 365 security center](https://security.microsoft.com/attacksimulator?viewid=overview).

## <a name="behavior-impact-on-compromise-rate"></a>Impacto del comportamiento en la tasa de peligro

En la pestaña **Información general** del aprendizaje de simulación de ataques, encontrarás el impacto del comportamiento en la tarjeta de tasa **de peligro.** Esta tarjeta muestra cómo los empleados trataron las simulaciones que ejecutó en contraste con la tasa **de compromiso prediseada.** Puedes usar estas conclusiones para realizar un seguimiento del progreso de la preparación de amenazas de los empleados mediante la ejecución de varias simulaciones en los mismos grupos de empleados.

En el gráfico puede ver:

- **Tasa de compromiso** previsto que refleja la tasa de compromiso promedio para las simulaciones que usan el mismo tipo de carga en otros inquilinos de Microsoft 365 que usan formación de simulación de ataques.
- **La tasa de compromiso** real refleja el porcentaje de empleados que han caído para la simulación.

Además, refleja la diferencia entre el número real de empleados comprometidos por el ataque y la tasa de `<number> less susceptible to phishing` compromiso previsto. Es menos probable que este número de empleados se vea comprometido por ataques similares en el futuro, mientras que indica cómo lo hacían los empleados en general, en contraste con la tasa de compromiso `<percent%> better than predicted rate` previsto.

> [!div class="mx-imgBorder"]
> ![Información general sobre la tarjeta de impacto del comportamiento en el aprendizaje de simulación de ataques](../../media/attack-sim-preview-behavior-impact-card.png)

Para ver un informe más detallado, haga clic en **Ver simulaciones y el informe de formación.** Este informe proporciona la misma información con contexto adicional de la propia simulación (por ejemplo, la técnica de simulación y el total de usuarios dirigidos).

## <a name="recommended-actions"></a>Acciones recomendadas

En la [ **pestaña Simulaciones,**](https://security.microsoft.com/attacksimulator?viewid=simulations)seleccionar una simulación le llevará a los detalles de la simulación, donde encontrará la **sección Acciones recomendadas.**

En la sección de acciones recomendadas se detallan las recomendaciones según la [puntuación de seguridad de Microsoft.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) Estas recomendaciones se basan en la carga usada en la simulación y le ayudarán a proteger a los empleados y a su entorno. Al hacer clic en cada acción de mejora, se mostrarán sus detalles.

> [!div class="mx-imgBorder"]
> ![Sección de acciones de recomendación sobre el aprendizaje de simulación de ataques](../../media/attack-sim-preview-recommended-actions.png)

## <a name="related-links"></a>Vínculos relacionados

[Introducción al uso de aprendizaje de simulación de ataques](attack-simulation-training-get-started.md)

[Crear una simulación de ataque de suplantación de identidad](attack-simulation-training.md)

[crear una carga útil para formar a los usuarios](attack-simulation-training-payloads.md)
