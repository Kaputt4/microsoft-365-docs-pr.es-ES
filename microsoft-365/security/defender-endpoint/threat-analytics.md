---
title: Seguimiento y respuesta a amenazas emergentes con Microsoft Defender para punto de conexión análisis de amenazas
ms.reviewer: ''
description: Comprenda las amenazas emergentes y las técnicas de ataque y cómo detenerlas. Evalúe su impacto en la organización y evalúe la resistencia de la organización.
keywords: análisis de amenazas, evaluación de riesgos, mitigación del sistema operativo, mitigación de microcódigos, estado de mitigación
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: c043203c18e61a0a1c85b6bc15ab1a8944bb1a5b
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67576459"
---
# <a name="track-and-respond-to-emerging-threats-through-threat-analytics"></a>Seguimiento y respuesta a amenazas emergentes a través del análisis de amenazas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Con adversarios más sofisticados y nuevas amenazas emergentes con frecuencia y con frecuencia, es fundamental poder hacerlo rápidamente:

- Evaluación del impacto de las nuevas amenazas
- Revise la resistencia frente a las amenazas o su exposición a las amenazas.
- Identificar las acciones que puede realizar para detener o contener las amenazas

Análisis de amenazas es un conjunto de informes de expertos investigadores de seguridad de Microsoft que cubren las amenazas más relevantes, entre las que se incluyen:

- Actores de amenazas activos y sus campañas
- Técnicas de ataque populares y nuevas
- Vulnerabilidades críticas
- Superficies de ataque comunes
- Malware frecuentes

Cada informe proporciona un análisis detallado de una amenaza y una amplia guía sobre cómo defenderse contra esa amenaza. También incorpora datos de la red, lo que indica si la amenaza está activa y si tiene protecciones aplicables.

Vea este breve vídeo para obtener más información sobre cómo el análisis de amenazas puede ayudarle a realizar un seguimiento de las amenazas más recientes y detenerlas.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bw1f]

## <a name="required-roles-and-permissions"></a>Permisos y roles necesarios
En la tabla siguiente se describen los roles y permisos necesarios para acceder a Threat Analytics. Los roles definidos en la tabla siguiente hacen referencia a los roles personalizados en portales individuales y no están conectados a roles globales en Azure AD, aunque tenga un nombre similar.

| **Se requiere uno de los siguientes roles para Microsoft 365 Defender**  | **Se requiere uno de los siguientes roles para Defender para punto de conexión.**  | **Se requiere uno de los siguientes roles para Defender para Office 365** | **Se requiere uno de los siguientes roles para Defender for Cloud Apps.** | 
|---------|---------|---------|---------|
| Análisis de amenazas | Datos de alertas e incidentes: <ul><li>Ver operaciones de seguridad de datos</li></ul>Mitigaciones de Administración de vulnerabilidades de Defender:<ul><li>Visualización de datos: administración de amenazas y vulnerabilidades</li></ul> | Datos de alertas e incidentes:<ul> <li>Ver solo las alertas de administración</li> <li>Administrar alertas</li> <li>Configuración de la organización</li><li>Registros de auditoría</li> <li>Visualización de registros de auditoría de solo visualización</li><li>Lector de seguridad</li> <li>Administrador de seguridad</li><li>Destinatarios de solo visualización</li> </ul> Intentos de correo electrónico impedidos: <ul><li>Lector de seguridad</li> <li>Administrador de seguridad</li><li>Destinatarios de solo visualización</li> | No disponible para los usuarios de Defender for Cloud Apps o MDI |

## <a name="view-the-threat-analytics-dashboard"></a>Visualización del panel de análisis de amenazas

El panel de análisis de amenazas es un gran punto de partida para llegar a los informes que son más relevantes para su organización. Resume las amenazas en las secciones siguientes:

- **Amenazas más recientes**: enumera los informes de amenazas publicados más recientemente, junto con el número de dispositivos con alertas activas y resueltas.
- **Amenazas de alto impacto**: enumera las amenazas que han tenido el mayor impacto en la organización. En esta sección se clasifican las amenazas por el número de dispositivos que tienen alertas activas.
- **Resumen de amenazas**: muestra el impacto general de las amenazas de seguimiento mostrando el número de amenazas con alertas activas y resueltas.

Seleccione una amenaza en el panel para ver el informe de esa amenaza.

:::image type="content" source="images/ta_dashboard.png" alt-text="Panel de análisis de amenazas" lightbox="images/ta_dashboard.png":::

## <a name="view-a-threat-analytics-report"></a>Visualización de un informe de análisis de amenazas

Cada informe de análisis de amenazas proporciona información en tres secciones: **Información general**, **Informe de analistas** y **Mitigaciones**.

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a>Información general: Comprender rápidamente la amenaza, evaluar su impacto y revisar las defensas

**La sección Información general** proporciona una vista previa del informe detallado del analista. También proporciona gráficos que resaltan el impacto de la amenaza para su organización y su exposición a través de dispositivos mal configurados y no revisados.

:::image type="content" source="images/ta-overview.png" alt-text="La sección Información general de un informe de análisis de amenazas" lightbox="images/ta-overview.png":::
_Sección de información general de un informe de análisis de amenazas_

#### <a name="assess-the-impact-to-your-organization"></a>Evaluación del impacto en la organización

Cada informe incluye gráficos diseñados para proporcionar información sobre el impacto organizativo de una amenaza:

- **Dispositivos con alertas**: muestra el número actual de dispositivos distintos que se han visto afectados por la amenaza. Un dispositivo se clasifica como **Activo** si hay al menos una alerta asociada a esa amenaza y **Se resuelve** si se han resuelto *todas las* alertas asociadas a la amenaza en el dispositivo.
- **Dispositivos con alertas a lo largo del tiempo**: muestra el número de dispositivos distintos con alertas **activas** y **resueltas** a lo largo del tiempo. El número de alertas resueltas indica la rapidez con la que la organización responde a las alertas asociadas a una amenaza. Lo ideal es que el gráfico muestre alertas resueltas en unos días.

#### <a name="review-security-resilience-and-posture"></a>Revisión de la resistencia y la posición de la seguridad

Cada informe incluye gráficos que proporcionan información general sobre la resistencia de su organización frente a una amenaza determinada:

- **Estado de configuración de seguridad**: muestra el número de dispositivos que han aplicado la configuración de seguridad recomendada que puede ayudar a mitigar la amenaza. Los dispositivos se consideran **seguros** si han aplicado _toda_ la configuración de seguimiento.
- **Estado de aplicación de revisiones de** vulnerabilidades: muestra el número de dispositivos que han aplicado actualizaciones de seguridad o revisiones que solucionan las vulnerabilidades explotadas por la amenaza.

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a>Informe de analistas: Obtener información de expertos de investigadores de seguridad de Microsoft

Vaya a la sección **Informe de analistas** para leer la escritura detallada de expertos. La mayoría de los informes proporcionan descripciones detalladas de las cadenas de ataques, incluidas las tácticas y técnicas asignadas al marco de MITRE ATT&CK, listas exhaustivas de recomendaciones y potentes instrucciones para [la búsqueda de amenazas](advanced-hunting-overview.md) .

[Más información sobre el informe de analistas](threat-analytics-analyst-reports.md)

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a>Mitigaciones: revise la lista de mitigaciones y el estado de los dispositivos.

En la sección **Mitigaciones** , revise la lista de recomendaciones que requieren acción específicas que pueden ayudarle a aumentar la resistencia de la organización frente a la amenaza. La lista de mitigaciones de seguimiento incluye:

- **Actualizaciones de seguridad**: Implementación de actualizaciones de seguridad o revisiones para detectar vulnerabilidades
- **Configuración del Antivirus de Microsoft Defender**
  - Versión de inteligencia de seguridad
  - Protección entregada en la nube
  - Protección de aplicaciones potencialmente no deseadas (PUA)
  - Protección en tiempo real

La información de mitigación de esta sección incorpora datos de [Administración de vulnerabilidades de Microsoft Defender](next-gen-threat-and-vuln-mgt.md), que también proporciona información detallada de los distintos vínculos del informe.

:::image type="content" source="images/ta-mitigations.png" alt-text="La sección Mitigaciones de un informe de análisis de amenazas" lightbox="images/ta-mitigations.png":::


_Sección mitigaciones de un informe de análisis de amenazas_

## <a name="additional-report-details-and-limitations"></a>Detalles y limitaciones adicionales del informe

Al usar los informes, tenga en cuenta lo siguiente:

- El ámbito de los datos se basa en el ámbito del control de acceso basado en rol (RBAC). Verá el estado de los dispositivos en [grupos a los que puede acceder](machine-groups.md).
- Los gráficos solo reflejan las mitigaciones de las que se realiza el seguimiento. Compruebe la información general del informe para ver mitigaciones adicionales que no se muestran en los gráficos.
- Las mitigaciones no garantizan una resistencia completa. Las mitigaciones proporcionadas reflejan las mejores acciones posibles necesarias para mejorar la resistencia.
- Los dispositivos se cuentan como "no disponibles" si no han transmitido datos al servicio.
- Las estadísticas relacionadas con el antivirus se basan en la configuración del Antivirus de Microsoft Defender. Los dispositivos con soluciones antivirus de terceros pueden aparecer como "expuestos".

## <a name="related-topics"></a>Temas relacionados

- [Búsqueda proactiva de amenazas con la búsqueda avanzada](advanced-hunting-overview.md)
- [Descripción de la sección del informe de analistas](threat-analytics-analyst-reports.md)
- [Evaluación y resolución de debilidades y exposiciones de seguridad](next-gen-threat-and-vuln-mgt.md)
