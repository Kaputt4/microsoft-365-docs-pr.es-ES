---
title: Paso 1. Triage and analyze your first incident
description: Cómo realizar una triaje e iniciar el análisis de su primer incidente en Microsoft 365 Defender.
keywords: incidentes, alertas, investigar, correlación, ataque, máquinas, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, microsoft, m365, respuesta a incidentes, ciberataque
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 299cb7847e19e625bbae3122e16c56bb54e05c89
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2022
ms.locfileid: "64499031"
---
# <a name="step-1-triage-and-analyze-your-first-incident"></a>Paso 1. Triage and analyze your first incident

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

A medida que pasa algún tiempo estableciendo, implementando y manteniendo medidas de seguridad de acuerdo con los estándares de la organización, puede configurar soluciones de seguridad para ayudarle a identificar rápidamente los riesgos y amenazas de seguridad. Microsoft 365 Defender permite detectar, realizar una triaje e investigar incidentes a través de su experiencia de un solo panel de cristal, donde puede encontrar la información que necesita para tomar decisiones a tiempo.

Una vez que se detecte un incidente de seguridad, Microsoft 365 Defender presenta detalles que necesitará para realizar una triaje o priorizar un incidente o incidentes sobre otros. Después de determinar la priorización, los analistas pueden centrar su energía en investigar los casos que se les han asignado.

## <a name="detection-by-microsoft-365-defender"></a>Detección por Microsoft 365 Defender

Microsoft 365 Defender recibe alertas y eventos de varias plataformas de seguridad de Microsoft como orígenes de detección para crear una imagen holística y un contexto de actividad malintencionada. Los posibles orígenes de detección son:

- [Microsoft Defender para endpoint](../defender-endpoint/microsoft-defender-endpoint.md) es una solución detección y respuesta de puntos de conexión (EDR) que usa antivirus de Microsoft Defender y protección contra amenazas avanzada habilitada en la nube con Microsoft Security Graph. Defender for Endpoint es una plataforma unificada para la protección preventiva, la detección posterior a la infracción, la investigación automatizada y la respuesta. Protege los puntos de conexión de ciberamenazas, detecta ataques avanzados e infracciones de datos, automatiza los incidentes de seguridad y mejora la posición de seguridad.
- [Microsoft Defender for Identity](/defender-for-identity/what-is) es una solución de seguridad basada en la nube que usa las señales locales de Servicios de dominio de Active Directory (AD DS) para identificar, detectar e investigar amenazas avanzadas, identidades comprometidas y acciones internas malintencionadas dirigidas a su organización.
- [Microsoft Defender para Aplicaciones](/cloud-app-security/) en la nube actúa como un guardián para el acceso de agente en tiempo real entre los usuarios de la empresa y los recursos en la nube que usan, independientemente del dispositivo que usen.
- [Microsoft Defender para Office 365](../office-365-security/overview.md) protege su organización contra amenazas malintencionadas en mensajes de correo electrónico, vínculos (URL) y herramientas de colaboración.
- [Azure Security Center](/azure/security-center/security-center-introduction) es un sistema de administración de seguridad de infraestructura unificada que refuerza la posición de seguridad de los centros de datos y proporciona protección contra amenazas avanzada en las cargas de trabajo híbridas en la nube y en las instalaciones.


En Microsoft 365 Defender, [los incidentes se](incidents-overview.md) identifican mediante la correlación de alertas de estos diferentes orígenes de detección. En lugar de gastar recursos en cadenas o distinguir varias alertas en sus respectivos incidentes, puede empezar con la cola de incidentes en Microsoft 365 Defender inmediato. Este enfoque le permite realizar una triaje de incidentes de forma eficaz en puntos de conexión, identidades, correo electrónico y aplicaciones, y reducir el daño causado por un ataque.

## <a name="triage-your-incidents"></a>Triage your incidents

La respuesta a incidentes Microsoft 365 Defender se inicia una vez que se hace una triage de la lista de incidentes mediante el método recomendado de priorización de la organización. Para triage significa asignar un nivel de importancia o urgencia a los incidentes, que luego determina el orden en que se investigarán.

Una guía de ejemplo útil para determinar qué incidente se debe priorizar en Microsoft 365 Defender puede resumirse mediante la fórmula: *Gravedad + Impacto = Prioridad*.

- **Gravedad es** el nivel designado por Microsoft 365 Defender y sus componentes de seguridad integrados.
- **El** impacto lo determina la organización y, por lo general, incluye, entre otros, un número umbral de usuarios, dispositivos, servicios afectados (o una combinación de los mismos) e incluso un tipo de alerta.

A continuación, los analistas inician investigaciones en función de los **criterios de** prioridad establecidos por la organización.

La priorización de incidentes puede variar según la organización. NIST también recomienda considerar el impacto funcional e informativo del incidente y la capacidad de recuperación.

A continuación se describe un enfoque de triaje:

1. Vaya a la [página incidentes](incidents-overview.md) para iniciar el triaje. Aquí puede ver una lista de incidentes que afectan a su organización. De forma predeterminada, se organizan desde el incidente más reciente hasta el más antiguo. Desde aquí, también puede ver diferentes columnas para cada incidente que muestran su gravedad, categoría, número de alertas activas y entidades afectadas, entre otras. Puede personalizar el conjunto de columnas y ordenar la cola de incidentes por algunas de estas columnas seleccionando el nombre de columna. También puede filtrar la cola de incidentes según sus necesidades. Para obtener una lista completa de los filtros disponibles, vea [Priorizar incidentes](incident-queue.md#available-filters).

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-queue.png" alt-text="Los incidentes en el portal de Microsoft 365 seguridad" lightbox="../../media/first-incident-analyze/first-incident-analyze-queue.png":::

    Un ejemplo de cómo puede realizar una triaje para este conjunto de incidentes es priorizar los incidentes que afectaron a más usuarios y dispositivos. En este ejemplo, puede priorizar el identificador de incidente 6769 porque afecta al mayor número de entidades: siete dispositivos, seis usuarios y dos buzones. Además, el incidente parece contener alertas de Microsoft Defender for Identity, que indican una alerta basada en identidad y un posible robo de credenciales.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-high-impact.png" alt-text="La página Incidentes** que muestra un ejemplo de un incidente de alto impacto en el portal de Microsoft 365 seguridad" lightbox="../../media/first-incident-analyze/first-incident-analyze-high-impact.png":::

2. Seleccione el círculo junto al nombre del incidente para revisar los detalles. Aparecerá un panel lateral en el lado derecho, que contiene información adicional que puede ayudar a su triage más.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout.png" alt-text="La página Incidentes que muestra un ejemplo de un panel lateral de incidentes en el portal Microsoft 365 seguridad" lightbox="../../media/first-incident-analyze/first-incident-analyze-incident-flyout.png":::

   Por ejemplo, al ver qué tácticas de [MITRE ATT&CK](https://attack.mitre.org/) usa el atacante en función de las categorías del incidente, puede priorizar este incidente porque el atacante usó credenciales robadas, estableció el comando y el control, realizó movimiento lateral y exfiltró algunos datos. Estas acciones sugieren que el atacante ya ha entrado en profundidad en la red y posiblemente ha robado información confidencial.

   Además, si su organización ha implementado el marco de confianza cero, consideraría el acceso a credenciales como una infracción de seguridad importante que vale la pena priorizar.

   Al desplazarse hacia abajo en el panel lateral, verá las entidades afectadas específicas, como usuarios, dispositivos y buzones. Puedes comprobar el nivel de exposición de cada dispositivo y los propietarios de los buzones afectados.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-details.png" alt-text="Detalles del panel lateral de incidentes" lightbox="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-details.png":::

3. Más abajo del panel lateral, puede encontrar las alertas asociadas. Microsoft 365 Defender ya ha realizado la correlación de estas alertas en un solo incidente, lo que le ahorra tiempo y recursos mejor invertidos en corregir el ataque. Las alertas son sospechosas y, por lo tanto, posiblemente eventos malintencionados del sistema que sugieren la presencia de un atacante en una red.

   En este ejemplo, se determinó que 87 alertas individuales formaban parte de un incidente de seguridad. Puedes ver todas las alertas para obtener una vista rápida de cómo se ha reproduciendo el ataque.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-alerts.png" alt-text="Las alertas de un panel lateral de incidentes en el portal Microsoft 365 seguridad" lightbox="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-alerts.png":::

## <a name="analyze-your-first-incident"></a>Analizar el primer incidente

Es igualmente importante comprender el contexto que rodea las alertas. A menudo, una alerta no es un solo evento independiente. Hay una cadena de procesos creados, comandos y acciones que podrían no haber ocurrido al mismo tiempo. Por lo tanto, un analista debe buscar la primera y la última actividad de la entidad sospechosa en las escalas de tiempo del dispositivo para comprender el contexto de las alertas.

Hay varias maneras de leer y analizar datos mediante Microsoft 365 Defender pero el objetivo final para los analistas es responder a incidentes lo antes posible. Aunque Microsoft 365 Defender reducir significativamente el tiempo medio de corrección [(MTTR)](https://www.microsoft.com/security/blog/2020/05/04/lessons-learned-microsoft-soc-part-3c/) a través de la característica de investigación y [](m365d-autoir.md) respuesta automatizada líder en el sector, siempre hay casos que requieren análisis manual.

Aquí le mostramos un ejemplo:

1. Una vez determinada la prioridad del triage, un analista comienza un análisis en profundidad seleccionando el nombre del incidente. En esta página se muestra el **resumen de incidentes** donde se muestran los datos en las pestañas para ayudar con el análisis. En la **pestaña** Alertas, se muestran los tipos de alertas. Los analistas pueden hacer clic en cada alerta para profundizar en el origen de detección correspondiente.

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-summary-tab.png" alt-text="Ficha Resumen de un incidente" lightbox="../../media/first-incident-analyze/first-incident-analyze-summary-tab.png":::

    Para obtener una guía rápida sobre qué dominio cubre cada origen de detección, revise la [sección Detectar](#detection-by-microsoft-365-defender) de este artículo.

2. Desde la **pestaña** Alertas, puede pivotar al origen de detección para llevar a cabo una investigación y un análisis más exhaustivos. Por ejemplo, al seleccionar Detección de malware con Microsoft Defender para aplicaciones en la nube como origen de detección, el analista se lleva a la página de alerta correspondiente.

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-select-alert.png" alt-text="Página Incidentes que muestra un ejemplo de selección de una alerta de un incidente." lightbox="../../media/first-incident-analyze/first-incident-analyze-select-alert.png":::

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-link-to-mcas.png" alt-text="Una página correspondiente en Microsoft Defender para aplicaciones en la nube" lightbox="../../media/first-incident-analyze/first-incident-analyze-link-to-mcas.png":::

3. Para investigar nuestro ejemplo más adelante, desplácese hasta la parte inferior de la página para ver los **usuarios afectados**. Para ver la actividad y el contexto que rodea la detección de malware, seleccione la página de usuario de Annette Hill.

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-page.png" alt-text="Una página de usuario" lightbox="../../media/first-incident-analyze/first-incident-analyze-user-page.png":::

4. La página de usuario enumera los eventos cronológicamente, empezando por un inicio de sesión arriesgado desde una alerta de dirección IP de red *TOR* . Aunque la desconfianza de una actividad depende de la naturaleza de la forma en que una organización lleva a cabo su negocio, en la mayoría de los casos el uso de The Onion Router (TOR), una red que permite a los usuarios navegar por la web de forma anónima, en un entorno empresarial puede considerarse altamente improbable e innecesario para operaciones en línea regulares.

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-event-list.png" alt-text="Lista cronológica de eventos para un usuario" lightbox="../../media/first-incident-analyze/first-incident-analyze-user-event-list.png":::

5. Cada alerta se puede seleccionar para obtener más información sobre la actividad. Por ejemplo, al seleccionar **Actividad desde una alerta de dirección IP de Tor** , se llega a la propia página de esa alerta. Annette es una administradora de Office 365, que indica privilegios elevados y que el incidente de origen podría haber llevado al acceso a información confidencial.

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-mcas-alert.png" alt-text="Detalles de alertas de Microsoft Defender para aplicaciones en la nube" lightbox="../../media/first-incident-analyze/first-incident-analyze-mcas-alert.png" :::

6. Al seleccionar otras alertas, puedes obtener una imagen completa del ataque.

## <a name="next-step"></a>Paso siguiente

:::image type="content" source="../../media/first-incident-overview/first-incident-path-step2.png" alt-text="La opción Corregir de la página Responder a su primer incidente" lightbox="../../media/first-incident-overview/first-incident-path-step2.png":::

Obtenga información sobre [cómo corregir incidentes](first-incident-remediate.md).

## <a name="see-also"></a>Vea también

- [Información general sobre incidentes](incidents-overview.md)
- [Investigar incidentes](investigate-incidents.md)
- [Administrar incidentes](manage-incidents.md)
