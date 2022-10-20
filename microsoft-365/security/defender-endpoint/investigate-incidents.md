---
title: Investigar incidentes en Microsoft Defender para punto de conexión
description: Consulte las alertas asociadas, administre el incidente y consulte los metadatos de alerta para ayudarle a investigar un incidente.
keywords: investigar, incidente, alertas, metadatos, riesgo, origen de detección, dispositivos afectados, patrones, correlación
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier1
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 0fed7977e9ce9c348831c03f693f0d507215c5af
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68636484"
---
# <a name="investigate-incidents-in-microsoft-defender-for-endpoint"></a>Investigar incidentes en Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Investigue los incidentes que afectan a la red, comprenda lo que significan y cotee las pruebas para resolverlos.

Cuando investigue un incidente, verá lo siguiente:

- Detalles del incidente
- Comentarios y acciones de incidentes
- Pestañas (alertas, dispositivos, investigaciones, pruebas, gráficos)

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUV]

## <a name="analyze-incident-details"></a>Análisis de los detalles del incidente

Haga clic en un incidente para ver el **panel Incidente**. Seleccione **Abrir página de incidentes** para ver los detalles del incidente y la información relacionada (alertas, dispositivos, investigaciones, pruebas, gráficos).

:::image type="content" source="images/atp-incident-details.png" alt-text="Detalles de un incidente" lightbox="images/atp-incident-details.png":::

### <a name="alerts"></a>Alertas

Puede investigar las alertas y ver cómo se vincularon en un incidente. Las alertas se agrupan en incidentes por los siguientes motivos:

- Investigación automatizada: la investigación automatizada desencadenó la alerta vinculada mientras investigaba la alerta original.
- Características de archivo: los archivos asociados a la alerta tienen características similares
- Asociación manual: un usuario vinculó manualmente las alertas
- Hora próxima: las alertas se desencadenaron en el mismo dispositivo dentro de un período de tiempo determinado.
- Mismo archivo: los archivos asociados a la alerta son exactamente los mismos
- Misma dirección URL: la dirección URL que desencadenó la alerta es exactamente la misma.

:::image type="content" source="images/atp-incidents-alerts-reason.png" alt-text="La pestaña Alertas con la página de detalles del incidente muestra los motivos por los que las alertas se vincularon en ese incidente." lightbox="images/atp-incidents-alerts-reason.png":::

También puede administrar una alerta y ver los metadatos de la alerta junto con otra información. Para obtener más información, vea [Investigar alertas](investigate-alerts.md).

### <a name="devices"></a>Dispositivos

También puede investigar los dispositivos que forman parte o están relacionados con un incidente determinado. Para obtener más información, consulte [Investigación de dispositivos](investigate-machines.md).

:::image type="content" source="images/atp-incident-device-tab.png" alt-text="Pestaña Dispositivos en la página de detalles del incidente" lightbox="images/atp-incident-device-tab.png":::

### <a name="investigations"></a>Investigaciones

Seleccione **Investigaciones** para ver todas las investigaciones automáticas iniciadas por el sistema en respuesta a las alertas de incidentes.

:::image type="content" source="images/atp-incident-investigations-tab.png" alt-text="Pestaña Investigaciones de la página de detalles del incidente" lightbox="images/atp-incident-investigations-tab.png":::

## <a name="going-through-the-evidence"></a>Pasar por las pruebas

Microsoft Defender para punto de conexión investiga automáticamente todos los eventos admitidos por los incidentes y las entidades sospechosas de las alertas, lo que le proporciona autorespuesta e información sobre los archivos, procesos, servicios, etc. importantes.

Cada una de las entidades analizadas se marcará como infectada, corregida o sospechosa.

:::image type="content" source="images/atp-incident-evidence-tab.png" alt-text="Pestaña Evidencia en la página de detalles del incidente" lightbox="images/atp-incident-evidence-tab.png":::

## <a name="visualizing-associated-cybersecurity-threats"></a>Visualización de las amenazas de ciberseguridad asociadas

Microsoft Defender para punto de conexión agrega la información de amenazas a un incidente para que pueda ver los patrones y las correlaciones procedentes de varios puntos de datos. Puede ver dicha correlación a través del gráfico de incidentes.

### <a name="incident-graph"></a>Gráfico de incidentes

**Graph cuenta** la historia del ataque de ciberseguridad. Por ejemplo, muestra cuál era el punto de entrada, qué indicador de riesgo o actividad se observó en qué dispositivo. Etc.

:::image type="content" source="images/atp-incident-graph-tab.png" alt-text="Gráfico de incidentes" lightbox="images/atp-incident-graph-tab.png":::

Puede hacer clic en los círculos del gráfico de incidentes para ver los detalles de los archivos malintencionados, las detecciones de archivos asociadas, cuántas instancias se han producido en todo el mundo, si se han observado en su organización, si es así, cuántas instancias.

:::image type="content" source="images/atp-incident-graph-details.png" alt-text="Página de detalles del incidente" lightbox="images/atp-incident-graph-details.png":::

## <a name="related-topics"></a>Temas relacionados

- [Cola de incidentes](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [Investigar incidentes en Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/investigate-incidents)
- [Administración de incidentes Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/manage-incidents)
