---
title: Realizar un seguimiento del historial de puntuación segura de Microsoft y cumplir los objetivos
description: Obtenga información sobre las actividades que han afectado a la puntuación segura de Microsoft. Descubra tendencias y establezca metas.
keywords: puntuación segura de Microsoft, calificación segura, puntuación segura de Office 365, puntuación de seguridad de Microsoft, centro de seguridad de Microsoft 365, acciones de mejora
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: ed937c90bbc6875ee3d72f710d5ac11d4069cbb6
ms.sourcegitcommit: a8f3c633714e934f9ad026c3bc72157ed535dcfc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/29/2020
ms.locfileid: "49738048"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a>Realizar un seguimiento del historial de puntuación segura de Microsoft y cumplir los objetivos

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

La [calificación segura de Microsoft](microsoft-secure-score.md) es una medida de la postura de seguridad de una organización, con un número más alto que indica que se han realizado más acciones de mejora. Puede encontrarse en https://security.microsoft.com/securescore el [centro de seguridad de Microsoft 365](overview-security-center.md).

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a>Obtener información sobre las actividades que han afectado a su calificación

Vea un gráfico de la puntuación de su organización con el tiempo en la ficha **historial** .

Debajo del gráfico hay una lista de todas las acciones realizadas en el intervalo de tiempo seleccionado y sus atributos, como puntos y categorías resultantes. Puede personalizar un intervalo de fechas y filtrar por categoría.

![Historial de actividades](../../media/secure-score/secure-score-history-activity.png)

Si selecciona la acción de mejora asociada a una actividad, aparecerá el flotante de acción de mejora completa.

Para ver todo el historial de esa acción de mejora específica, seleccione el vínculo historial en el control flotante.

![Historial de acciones de mejora](../../media/secure-score/secure-score-history-flyout.png)

## <a name="discover-trends-and-set-goals"></a>Descubrir tendencias y establecer objetivos

En la ficha **métricas & tendencias** , hay varios gráficos y gráficos para proporcionar más visibilidad sobre las tendencias y establecer los objetivos. Puede establecer el intervalo de fechas para toda la página de visualizaciones. Las visualizaciones incluyen:

* **La zona de puntuación segura** -personalizada en función de los objetivos de la organización y las definiciones de los intervalos de puntuación buenos, correctos y no válidos.
* **Tendencia de regresión** : una escala de tiempo de puntos que se han regresivo debido a cambios en la configuración, el usuario o el dispositivo.  
* **Tendencia de comparación** : cómo la puntuación segura de su organización se compara con otras personas a lo largo del tiempo. Esta vista puede incluir líneas que representan la media de puntuación de organizaciones con recuento de asientos similar y una vista de comparación personalizada que puede establecer.
* **Tendencia de aceptación de riesgos** : escala de tiempo de acciones de mejora marcadas como "riesgo aceptado".
* **Cambios de puntuación** : el número de puntos alcanzados, los puntos retrasdos y los cambios en su puntuación en el intervalo de fechas especificado.

### <a name="compare-your-score-to-organizations-like-yours"></a>Comparar su calificación con organizaciones como la suya

Hay dos lugares para ver cómo se compara su puntuación con las organizaciones que son similares. En ambos gráficos, puede seleccionar **administrar comparaciones** para ver y editar la información de la organización. También puede crear una comparación personalizada basada en la industria, el tamaño de la organización, las licencias y las regiones.

#### <a name="comparison-bar-chart"></a>Gráfico de barras de comparación

El gráfico de barras de comparación es la ficha **información general** . Mantenga el mouse sobre el gráfico para ver la puntuación y la oportunidad de puntuación. Los datos de la comparación son anonimizan, por lo que no sabemos exactamente qué otros inquilinos hay en la combinación.

![Gráfico de barras de calificaciones de una organización similar](../../media/secure-score/secure-score-comparison-bar.png)

- **Organizaciones como la suya**: una puntuación media de otros inquilinos (siempre que tenga al menos cinco o más inquilinos para comparar) que cumplan los siguientes criterios:
    1. Misma industria
    2. Mismo tamaño de organización
    3. Todas las regiones
    4. Los productos de Microsoft usados son de un 80% similar
    5. Oportunidad (puntuación máxima que se puede lograr por licencia actual) dentro de un 20% de intervalo desde el espacio empresarial

- **Comparación personalizada**: debe configurarse seleccionando **administrar la comparación** en función de los criterios siguientes:
    1. Industria (es) seleccionada (s)
    2. Tamaño de la organización seleccionada (es)
    3. Región o regiones seleccionadas
    4. Licencias seleccionadas
    5. Los productos de Microsoft usados son de un 80% similar
    6. Oportunidad (puntuación máxima que se puede lograr por licencia actual) dentro de un 20% de intervalo desde el espacio empresarial

Si ha realizado una selección personalizada pero los resultados tienen menos de cinco inquilinos con los que se puede comparar, verá "no disponible debido a datos limitados".

#### <a name="comparison-trend"></a>Tendencia de comparación

En la ficha **métricas & tendencias** , vea cómo la puntuación segura de su organización se compara con otras personas a lo largo del tiempo.

![Gráfico de líneas de calificaciones similares a lo largo del tiempo](../../media/secure-score/secure-score-comparison-trend.png)

## <a name="we-want-to-hear-from-you"></a>Queremos escuchar sus comentarios

Si tiene algún problema, háganoslo saber mediante la publicación de la comunidad de [seguridad, privacidad & cumplimiento](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) . Estamos supervisando la comunidad y le proporcionaremos ayuda.

## <a name="related-resources"></a>Recursos relacionados

- [Introducción a la puntuación segura de Microsoft](microsoft-secure-score.md)
- [Evaluar su postura de seguridad](microsoft-secure-score-improvement-actions.md)
- [Próximas novedades](microsoft-secure-score-whats-coming.md)
- [Novedades](microsoft-secure-score-whats-new.md)
