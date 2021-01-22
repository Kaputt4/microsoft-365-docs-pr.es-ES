---
title: Realizar un seguimiento del historial de puntuaciones seguras de Microsoft y cumplir los objetivos
description: Obtenga información sobre la actividad que ha afectado a su puntuación de seguridad de Microsoft. Descubrir tendencias y establecer objetivos.
keywords: puntuación de seguridad de microsoft, puntuación de seguridad, puntuación de seguridad de Office 365, puntuación de seguridad de Microsoft, centro de seguridad de Microsoft 365, acciones de mejora
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: c9af6a3ae6f461acfd2968897223446641d5cf09
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925677"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a>Realizar un seguimiento del historial de puntuaciones de seguridad de Microsoft y cumplir los objetivos

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[Puntuación de seguridad de Microsoft](microsoft-secure-score.md) es una medida de la posición de seguridad de una organización, con un número mayor que indica más acciones de mejora tomadas. Puede encontrarse en el Centro de seguridad https://security.microsoft.com/securescore [de Microsoft 365.](overview-security-center.md)

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a>Obtener información sobre la actividad que ha afectado a la puntuación

Vea un gráfico de la puntuación de su organización con el tiempo en la **pestaña** Historial.

Debajo del gráfico hay una lista de todas las acciones realizadas en el intervalo de tiempo seleccionado y sus atributos, como los puntos y la categoría resultantes. Puede personalizar un intervalo de fechas y filtrar por categoría.

![Historial de actividades](../../media/secure-score/secure-score-history-activity.png)

Si seleccionas la acción de mejora asociada a una actividad, aparecerá el control desplegable de acción de mejora completa.

Para ver todo el historial de esa acción de mejora específica, seleccione el vínculo de historial en el menú desplegable.

![Historial de acciones de mejora](../../media/secure-score/secure-score-history-flyout.png)

## <a name="discover-trends-and-set-goals"></a>Descubrir tendencias y establecer objetivos

En la **pestaña &** de tendencias, hay varios gráficos y gráficos para darle más visibilidad a las tendencias y establecer objetivos. Puede establecer el intervalo de fechas para toda la página de visualizaciones. Las visualizaciones incluyen:

* **Zona de puntuación segura:** personalizada en función de los objetivos y las definiciones de rangos de puntuación correctos, correctos y no válidos de su organización.
* **Tendencia de regresión:** una escala de tiempo de puntos que han retrocedido debido a cambios en la configuración, el usuario o el dispositivo.  
* **Tendencia de comparación:** cómo la puntuación de seguridad de su organización se compara con la de otros usuarios a lo largo del tiempo. Esta vista puede incluir líneas que representan el promedio de puntuación de las organizaciones con un recuento de puestos similar y una vista de comparación personalizada que puede establecer.
* **Tendencia de aceptación de riesgos:** escala de tiempo de las acciones de mejora marcadas como "riesgo aceptado".
* **Cambios de** puntuación: número de puntos logrados, puntos en retroceso y cambios en la puntuación en el intervalo de fechas especificado.

### <a name="compare-your-score-to-organizations-like-yours"></a>Comparar tu puntuación con organizaciones como la tuyo

Hay dos lugares para ver cómo se compara su puntuación con las organizaciones que son similares a usted. En ambos gráficos, puede seleccionar Administrar **comparaciones** para ver y editar la información de su organización. También puede crear una comparación personalizada basada en la industria, el tamaño de la organización, las licencias y las regiones.

#### <a name="comparison-bar-chart"></a>Gráfico de barras de comparación

El gráfico de barras de comparación es la **pestaña** Información general. Mantenga el puntero sobre el gráfico para ver la puntuación y la oportunidad de puntuación. Los datos de comparación se anonimizan, por lo que no sabemos exactamente qué otros inquilinos están en la combinación.

![Gráfico de barras de puntuaciones de una organización similar](../../media/secure-score/secure-score-comparison-bar.png)

- **Organizaciones como la de usted:** una puntuación promedio de otros inquilinos (siempre que disponen de al menos cinco o más inquilinos para comparar) que cumplen los criterios siguientes:
    1. Misma industria
    2. Mismo tamaño de organización
    3. Todas las regiones
    4. Los productos de Microsoft usados son 80 % similares
    5. Oportunidad (puntuación máxima que se puede lograr con la licencia actual) dentro de un intervalo del 20 % del espacio empresarial

- **Comparación personalizada:** debe configurarse seleccionando **Administrar** comparación según los criterios siguientes:
    1. Sectores seleccionados
    2. Tamaño o tamaños de organización seleccionados
    3. Regiones seleccionadas
    4. Licencias seleccionadas
    5. Los productos de Microsoft usados son 80 % similares
    6. Oportunidad (puntuación máxima que se puede lograr con la licencia actual) dentro de un intervalo del 20 % del espacio empresarial

Si ha realizado una selección personalizada pero los resultados tienen menos de cinco inquilinos más con los que podemos comparar, verá "No disponible debido a datos limitados".

#### <a name="comparison-trend"></a>Tendencia de comparación

En la **pestaña Métricas & tendencias,** vea cómo la puntuación de seguridad de su organización se compara con la de otros usuarios a lo largo del tiempo.

![Gráfico de líneas de puntuaciones de una organización similar a lo largo del tiempo](../../media/secure-score/secure-score-comparison-trend.png)

## <a name="we-want-to-hear-from-you"></a>Queremos escuchar sus comentarios

Si tiene algún problema, háganoslo saber publicando en la comunidad [seguridad, privacidad & cumplimiento.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) Estamos supervisando la comunidad y le proporcionaremos ayuda.

## <a name="related-resources"></a>Recursos relacionados

- [Información general sobre puntuación de seguridad de Microsoft](microsoft-secure-score.md)
- [Evaluar su postura de seguridad](microsoft-secure-score-improvement-actions.md)
- [Próximas novedades](microsoft-secure-score-whats-coming.md)
- [Novedades](microsoft-secure-score-whats-new.md)
