---
title: 'Información del panel: administración de amenazas y vulnerabilidades'
description: El panel de administración de amenazas y vulnerabilidades puede ayudar a SecOps y a los administradores de seguridad a abordar las amenazas de ciberseguridad y a crear la resistencia de seguridad de su organización.
keywords: Microsoft Defender para Endpoint-tvm, panel de Microsoft Defender para Endpoint-tvm, administración de vulnerabilidades de & amenazas, administración de amenazas y vulnerabilidades, administración de vulnerabilidades basada en riesgos &, configuración de seguridad, Puntuación segura de Microsoft para dispositivos, puntuación de exposición
search.appverid: met150
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 82b6123a99eb406918708c6bf23b870ef3bc3d79
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934146"
---
# <a name="dashboard-insights---threat-and-vulnerability-management"></a>Información del panel: administración de amenazas y vulnerabilidades

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Administración de amenazas y vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

La administración de amenazas y vulnerabilidades es un componente de Defender for Endpoint y proporciona a los administradores de seguridad y a los equipos de operaciones de seguridad un valor único, incluidos:


- Información de detección y respuesta de puntos de conexión (EDR) en tiempo real correlacionada con las vulnerabilidades de los puntos de conexión.
- Contexto de vulnerabilidad de dispositivos inestimable durante las investigaciones de incidentes
- Procesos de corrección integrados a través de Microsoft Intune y Microsoft Endpoint Configuration Manager  
  
Puede usar la funcionalidad de administración de amenazas y vulnerabilidades en el Centro de seguridad [de Microsoft Defender](https://securitycenter.windows.com/) para:

- Ver la puntuación de exposición y puntuación segura de Microsoft para dispositivos, junto con las recomendaciones de seguridad más importantes, vulnerabilidad de software, actividades de corrección y dispositivos expuestos
- Correlacionar los conocimientos de EDR con las vulnerabilidades de los puntos de conexión y procesarlos
- Seleccionar opciones de corrección para realizar un triage y realizar un seguimiento de las tareas de corrección
- Seleccionar opciones de excepción y realizar un seguimiento de excepciones activas

> [!NOTE]
> Los dispositivos que no están activos en los últimos 30 días no se tienen en cuenta en los datos que reflejan la puntuación de exposición a la administración de amenazas y vulnerabilidades de su organización y la puntuación de Microsoft Secure Score para dispositivos.

Vea este vídeo para obtener una introducción rápida a lo que se encuentra en el panel de administración de amenazas y vulnerabilidades.

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r1nv]

## <a name="threat-and-vulnerability-management-dashboard"></a>Panel de administración de amenazas y vulnerabilidades

 ![Portal de Microsoft Defender para puntos de conexión](images/tvm-dashboard-devices.png)

Área | Descripción
:---|:---
**Grupos de dispositivos seleccionados (#/#)**   | Filtra los datos de administración de amenazas y vulnerabilidades que quieres ver en el panel y las tarjetas por grupos de dispositivos. Lo que seleccione en el filtro se aplica a lo largo de las páginas de administración de amenazas y vulnerabilidades.
[**Puntuación de exposición**](tvm-exposure-score.md)   | Consulta el estado actual de la exposición del dispositivo de tu organización a amenazas y vulnerabilidades. Varios factores afectan a la puntuación de exposición de la organización: debilidades detectadas en los dispositivos, probabilidad de que los dispositivos se incumplen, valor de los dispositivos para la organización y alertas relevantes detectadas con los dispositivos. El objetivo es reducir la puntuación de exposición de la organización para que sea más segura. Para reducir la puntuación, debe corregir los problemas de configuración de seguridad relacionados enumerados en las recomendaciones de seguridad.
[**Puntuación de seguridad de Microsoft para dispositivos**](tvm-microsoft-secure-score-devices.md) | Consulta la posición de seguridad del sistema operativo, las aplicaciones, la red, las cuentas y los controles de seguridad de la organización. El objetivo es corregir los problemas de configuración de seguridad relacionados para aumentar la puntuación de los dispositivos. Seleccionar las barras le llevará a la **página Recomendación de** seguridad.
**Distribución de exposición a dispositivos** | Consulta cuántos dispositivos se exponen en función de su nivel de exposición. Seleccione una sección en el gráfico de  anillos para ir a la página de lista Dispositivos y ver los nombres de dispositivos afectados, el nivel de exposición, el nivel de riesgo y otros detalles como dominio, plataforma del sistema operativo, su estado de mantenimiento, cuándo se vio por última vez y sus etiquetas.
**Recomendaciones de seguridad principales** | Vea las recomendaciones de seguridad intercaladas que se ordenan y priorizan en función de la exposición a riesgos de su organización y de la urgencia que requiere. Seleccione **Mostrar más** para ver el resto de las recomendaciones de seguridad de la lista. Seleccione **Mostrar excepciones para** la lista de recomendaciones que tienen una excepción.
**Software vulnerable superior** | Obtenga visibilidad en tiempo real del inventario de software de su organización con una lista clasificada en pila de software vulnerable instalado en los dispositivos de la red y cómo afectan a la puntuación de exposición de la organización. Seleccione un elemento para obtener más información o **Mostrar más** para ver el resto de la lista de software vulnerable en la página **Inventario de** software.
**Principales actividades de corrección** | Realice un seguimiento de las actividades de corrección generadas a partir de las recomendaciones de seguridad. Puede seleccionar cada elemento de la lista  para ver los detalles de la página Corrección o seleccionar **Mostrar** más para ver el resto de las actividades de corrección y las excepciones activas.
**Dispositivos expuestos superiores** | Ver los nombres de dispositivo expuestos y su nivel de exposición. Selecciona un nombre de dispositivo de la lista para ir a la página del dispositivo donde puedes ver las alertas, riesgos, incidentes, recomendaciones de seguridad, software instalado y vulnerabilidades detectadas asociadas con los dispositivos expuestos. Selecciona **Mostrar más** para ver el resto de la lista de dispositivos expuestos. Desde la lista de dispositivos, puedes administrar etiquetas, iniciar investigaciones automatizadas, iniciar una sesión de respuesta en directo, recopilar un paquete de investigación, ejecutar el examen antivirus, restringir la ejecución de aplicaciones y aislar el dispositivo.

Para obtener más información sobre los iconos usados en todo el portal, vea [Iconos de Microsoft Defender para puntos de conexión](portal-overview.md#microsoft-defender-for-endpoint-icons).


## <a name="related-topics"></a>Temas relacionados

- [Introducción a la administración de amenazas y vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Puntuación de exposición](tvm-exposure-score.md)
- [Puntuación de seguridad de Microsoft para dispositivos](tvm-microsoft-secure-score-devices.md)
- [Recomendaciones de seguridad](tvm-security-recommendation.md)
- [Inventario de software](tvm-software-inventory.md)
- [Línea de tiempo de eventos](threat-and-vuln-mgt-event-timeline.md)

