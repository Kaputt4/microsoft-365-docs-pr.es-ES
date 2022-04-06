---
title: Investigar incidentes en Microsoft Defender para punto de conexión
description: Ver alertas asociadas, administrar el incidente y ver metadatos de alerta para ayudarle a investigar un incidente
keywords: investigar, incidente, alertas, metadatos, riesgo, origen de detección, dispositivos afectados, patrones, correlación
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d66dde2c3f346449c7ecd03a7ef577e39cf98991
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64468807"
---
# <a name="investigate-incidents-in-microsoft-defender-for-endpoint"></a>Investigar incidentes en Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Investigar incidentes que afectan a la red, comprender lo que significan y recopilar evidencias para resolverlos.

Cuando investigues un incidente, verás lo siguiente:

- Detalles del incidente
- Comentarios y acciones de incidentes
- Pestañas (alertas, dispositivos, investigaciones, evidencias, gráfico)

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUV]

## <a name="analyze-incident-details"></a>Analizar detalles de incidentes

Haga clic en un incidente para ver el **panel Incidentes**. Seleccione **Abrir página de incidentes** para ver los detalles del incidente y la información relacionada (alertas, dispositivos, investigaciones, evidencias, gráfico).

:::image type="content" source="images/atp-incident-details.png" alt-text="Los detalles de un incidente" lightbox="images/atp-incident-details.png":::

### <a name="alerts"></a>Alertas

Puede investigar las alertas y ver cómo se vincularon en un incidente. Las alertas se agrupan en incidentes en función de los siguientes motivos:

- Investigación automatizada: la investigación automatizada desencadenó la alerta vinculada mientras se investigaba la alerta original.
- Características del archivo: los archivos asociados a la alerta tienen características similares
- Asociación manual: un usuario vinculó manualmente las alertas
- Tiempo próxima: las alertas se desencadenaron en el mismo dispositivo en un período de tiempo determinado
- Mismo archivo: los archivos asociados con la alerta son exactamente los mismos
- Misma dirección URL: la dirección URL que desencadenó la alerta es exactamente la misma

:::image type="content" source="images/atp-incidents-alerts-reason.png" alt-text="La pestaña Alertas con detalles de incidentes que muestra los motivos por los que se vincularon las alertas en ese incidente" lightbox="images/atp-incidents-alerts-reason.png":::

También puede administrar una alerta y ver metadatos de alerta junto con otra información. Para obtener más información, vea [Investigar alertas](investigate-alerts.md).

### <a name="devices"></a>Dispositivos

También puedes investigar los dispositivos que forman parte de un incidente determinado o están relacionados con ellos. Para obtener más información, consulta [Investigar dispositivos](investigate-machines.md).

:::image type="content" source="images/atp-incident-device-tab.png" alt-text="La pestaña Dispositivos en la página detalles de incidentes" lightbox="images/atp-incident-device-tab.png":::

### <a name="investigations"></a>Investigaciones

Seleccione **Investigaciones para** ver todas las investigaciones automáticas iniciadas por el sistema en respuesta a las alertas de incidentes.

:::image type="content" source="images/atp-incident-investigations-tab.png" alt-text="La pestaña investigaciones de la página de detalles del incidente" lightbox="images/atp-incident-investigations-tab.png":::

## <a name="going-through-the-evidence"></a>Pasar por la evidencia

Microsoft Defender para endpoint investiga automáticamente todos los eventos admitidos por los incidentes y las entidades sospechosas de las alertas, lo que le proporciona una respuesta automática e información sobre los archivos, procesos, servicios y mucho más importantes.

Cada una de las entidades analizadas se marcará como infectado, corregido o sospechoso.

:::image type="content" source="images/atp-incident-evidence-tab.png" alt-text="La pestaña Evidencia en la página detalles del incidente" lightbox="images/atp-incident-evidence-tab.png":::

## <a name="visualizing-associated-cybersecurity-threats"></a>Visualización de amenazas de ciberseguridad asociadas

Microsoft Defender para endpoint agrega la información de amenazas en un incidente para que pueda ver los patrones y correlaciones que vienen desde varios puntos de datos. Puede ver dicha correlación a través del gráfico de incidentes.

### <a name="incident-graph"></a>Gráfico de incidentes

El **Graph** cuenta la historia del ataque de ciberseguridad. Por ejemplo, muestra cuál era el punto de entrada, qué indicador de riesgo o actividad se observó en qué dispositivo. etc.

:::image type="content" source="images/atp-incident-graph-tab.png" alt-text="El gráfico de incidentes" lightbox="images/atp-incident-graph-tab.png":::

Puede hacer clic en los círculos del gráfico de incidentes para ver los detalles de los archivos malintencionados, las detecciones de archivos asociados, cuántas instancias ha habido en todo el mundo, si se ha observado en su organización, si es así, cuántas instancias.

:::image type="content" source="images/atp-incident-graph-details.png" alt-text="Página de detalles del incidente" lightbox="images/atp-incident-graph-details.png":::

## <a name="related-topics"></a>Temas relacionados

- [Cola de incidentes](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [Investigar incidentes en Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/investigate-incidents)
- [Administrar Microsoft Defender para incidentes de punto de conexión](/microsoft-365/security/defender-endpoint/manage-incidents)
