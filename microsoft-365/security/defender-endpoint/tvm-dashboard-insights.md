---
title: 'Información del panel: Administración de amenazas y vulnerabilidades'
description: El Administración de amenazas y vulnerabilidades puede ayudar a SecOps y a los administradores de seguridad a abordar las amenazas de ciberseguridad y a crear la resistencia de seguridad de su organización.
keywords: Panel de Microsoft Defender para Endpoint-tvm, Microsoft Defender para Endpoint-tvm, & administración de vulnerabilidades amenazas, Administración de amenazas y vulnerabilidades, amenazas basadas en & administración de vulnerabilidades , configuración de seguridad, Puntuación segura de Microsoft para dispositivos, puntuación de exposición
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 76eedd78e6bc6a95450a50c04d4f85b0de46db8e
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64472493"
---
# <a name="dashboard-insights---threat-and-vulnerability-management"></a>Información del panel: Administración de amenazas y vulnerabilidades

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Amenaza y administración de vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

Threat and administración de vulnerabilidades is a component of Defender for Endpoint, and provides both security administrators and security operations teams with unique value, including:

- Información de detección y respuesta de puntos de conexión (EDR) en tiempo real correlacionada con las vulnerabilidades de los puntos de conexión.
- Contexto de vulnerabilidad de dispositivos inestimable durante las investigaciones de incidentes
- Procesos de corrección integrados a Microsoft Intune y Microsoft Endpoint Configuration Manager

Puede usar la funcionalidad Administración de amenazas y vulnerabilidades en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender para</a>:

- Ver la puntuación de exposición y la puntuación segura de Microsoft para dispositivos, junto con las recomendaciones de seguridad más importantes, la vulnerabilidad del software, las actividades de corrección y los dispositivos expuestos
- Correlacionar EDR información con vulnerabilidades de punto de conexión y procesarlas
- Seleccionar opciones de corrección para realizar un triage y realizar un seguimiento de las tareas de corrección
- Seleccionar opciones de excepción y realizar un seguimiento de excepciones activas

> [!NOTE]
> Los dispositivos que no están activos en los últimos 30 días no se tienen en cuenta en los datos que reflejan la puntuación de exposición de Administración de amenazas y vulnerabilidades de la organización y la puntuación segura de Microsoft para dispositivos.

Vea este vídeo para obtener una introducción rápida de lo que se encuentra en el Administración de amenazas y vulnerabilidades panel.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4r1nv]

## <a name="threat-and-vulnerability-management-dashboard"></a>Panel de administración de vulnerabilidades amenazas

:::image type="content" source="../../media/tvmdashboard.png" alt-text="Panel de administración de amenazas y vulnerabilidades para dispositivos" lightbox="../../media/tvmdashboard.png":::

<br>

****

|Área|Descripción|
|---|---|
|**Grupos de dispositivos seleccionados (#/#)**|Filtra los Administración de amenazas y vulnerabilidades datos que quieres ver en el panel y las tarjetas por grupos de dispositivos. Lo que seleccione en el filtro se aplica en todas Administración de amenazas y vulnerabilidades páginas.|
|[**Puntuación de exposición**](tvm-exposure-score.md)|Consulta el estado actual de la exposición del dispositivo de tu organización a amenazas y vulnerabilidades. Varios factores afectan a la puntuación de exposición de la organización: debilidades detectadas en los dispositivos, probabilidad de que los dispositivos se incumplen, valor de los dispositivos para la organización y alertas relevantes detectadas con los dispositivos. El objetivo es reducir la puntuación de exposición de la organización para que sea más segura. Para reducir la puntuación, debe corregir los problemas de configuración de seguridad relacionados enumerados en las recomendaciones de seguridad.|
|[**Puntuación de seguridad de Microsoft para dispositivos**](tvm-microsoft-secure-score-devices.md)|Consulta la posición de seguridad del sistema operativo, las aplicaciones, la red, las cuentas y los controles de seguridad de la organización. El objetivo es corregir los problemas de configuración de seguridad relacionados para aumentar la puntuación de los dispositivos. Seleccionar las barras le llevará a la **página Recomendación de** seguridad.|
|**Distribución de exposición a dispositivos**|Consulta cuántos dispositivos se exponen en función de su nivel de exposición. Seleccione una sección en el gráfico de anillos para ir a la  página de lista Dispositivos y ver los nombres de dispositivos afectados, el nivel de exposición, el nivel de riesgo y otros detalles como dominio, plataforma del sistema operativo, su estado de mantenimiento, cuándo se vio por última vez y sus etiquetas.|
|**Recomendaciones de seguridad principales**|Vea las recomendaciones de seguridad intercaladas que se ordenan y priorizan en función de la exposición a riesgos de su organización y de la urgencia que requiere. Seleccione **Mostrar más** para ver el resto de las recomendaciones de seguridad de la lista. Seleccione **Mostrar excepciones para** la lista de recomendaciones que tienen una excepción.|
|**Software vulnerable superior**|Obtenga visibilidad en tiempo real del inventario de software de su organización con una lista clasificada en pila de software vulnerable instalado en los dispositivos de la red y cómo afectan a la puntuación de exposición de la organización. Seleccione un elemento para obtener más información o **Mostrar más** para ver el resto de la lista de software vulnerable en la **página Inventario de** software.|
|**Principales actividades de corrección**|Realice un seguimiento de las actividades de corrección generadas a partir de las recomendaciones de seguridad. Puede seleccionar cada elemento de la lista para ver los detalles de la página  Corrección o seleccionar **Mostrar** más para ver el resto de las actividades de corrección y las excepciones activas.|
|**Dispositivos expuestos superiores**|Ver los nombres de dispositivo expuestos y su nivel de exposición. Selecciona un nombre de dispositivo de la lista para ir a la página del dispositivo donde puedes ver las alertas, riesgos, incidentes, recomendaciones de seguridad, software instalado y vulnerabilidades detectadas asociadas con los dispositivos expuestos. Selecciona **Mostrar más** para ver el resto de la lista de dispositivos expuestos. Desde la lista de dispositivos, puedes administrar etiquetas, iniciar investigaciones automatizadas, iniciar una sesión de respuesta en directo, recopilar un paquete de investigación, ejecutar el examen antivirus, restringir la ejecución de aplicaciones y aislar el dispositivo.|
|

Para obtener más información sobre los iconos usados en todo el portal, consulta [Iconos de Microsoft Defender para puntos de conexión](portal-overview.md#microsoft-defender-for-endpoint-icons).

## <a name="related-topics"></a>Temas relacionados

- [Información general sobre amenazas administración de vulnerabilidades amenazas](next-gen-threat-and-vuln-mgt.md)
- [Puntuación de exposición](tvm-exposure-score.md)
- [Puntuación de seguridad de Microsoft para dispositivos](tvm-microsoft-secure-score-devices.md)
- [Recomendaciones de seguridad](tvm-security-recommendation.md)
- [Inventario de software](tvm-software-inventory.md)
- [Línea de tiempo de eventos](threat-and-vuln-mgt-event-timeline.md)
