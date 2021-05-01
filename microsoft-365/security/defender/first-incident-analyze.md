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
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
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
ms.openlocfilehash: 1890b4f9b4c71efebe833ebaee62debedbf0fb72
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114926"
---
# <a name="step-1-triage-and-analyze-your-first-incident"></a>Paso 1. Triage and analyze your first incident

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

A medida que pasa algún tiempo estableciendo, implementando y manteniendo medidas de seguridad de acuerdo con los estándares de la organización, puede configurar soluciones de seguridad para ayudarle a identificar rápidamente los riesgos y amenazas de seguridad. Microsoft 365 Defender te permite detectar, realizar una triaje e investigar incidentes a través de su experiencia de un solo panel de cristal donde puedes encontrar la información que necesitas para tomar decisiones a tiempo. 

Una vez detectado un incidente de seguridad, Microsoft 365 Defender presenta los detalles que necesitará para realizar una triaje o priorizar un incidente o incidentes sobre otros. Después de determinar la priorización, los analistas pueden centrar su energía en investigar los casos que se les han asignado.

## <a name="detection-by-microsoft-365-defender"></a>Detección por Microsoft 365 Defender

Microsoft 365 Defender recibe alertas y eventos de varias plataformas de seguridad de Microsoft como orígenes de detección para crear una imagen holística y un contexto de actividad malintencionada. Estos son los posibles orígenes de detección:

- [Microsoft Defender para endpoint](../defender-endpoint/microsoft-defender-endpoint.md) es una solución detección y respuesta de puntos de conexión (EDR) que usa antivirus de Microsoft Defender, así como protección contra amenazas avanzada habilitada en la nube con Microsoft Security Graph. Defender for Endpoint es una plataforma unificada para la protección preventiva, la detección posterior a la infracción, la investigación automatizada y la respuesta. Protege los puntos de conexión de ciberamenazas, detecta ataques avanzados e infracciones de datos, automatiza los incidentes de seguridad y mejora la posición de seguridad. 
- [Microsoft Defender for Identity](https://docs.microsoft.com/defender-for-identity/what-is) es una solución de seguridad basada en la nube que usa las señales locales de Servicios de dominio de Active Directory (AD DS) para identificar, detectar e investigar amenazas avanzadas, identidades comprometidas y acciones internas malintencionadas dirigidas a su organización. 
- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/) actúa como un guardián para el acceso de agente en tiempo real entre los usuarios de la empresa y los recursos en la nube que usan, independientemente del dispositivo que estén usando. 
- [Microsoft Defender para Office 365](../office-365-security/overview.md) protege su organización contra amenazas malintencionadas en mensajes de correo electrónico, vínculos (URL) y herramientas de colaboración. 
- [Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-introduction) es un sistema de administración de seguridad de infraestructura unificado que refuerza la posición de seguridad de los centros de datos y proporciona protección contra amenazas avanzada en las cargas de trabajo híbridas en la nube, así como en las instalaciones. 

En Microsoft 365 Defender, los incidentes se identifican mediante la correlación de [alertas](incidents-overview.md) de estos diferentes orígenes de detección. En lugar de gastar recursos en cadenas o distinguir varias alertas en sus respectivos incidentes, puedes empezar con la cola de incidentes en Microsoft 365 Defender inmediatamente. Esto le permite realizar triajes de incidentes de manera eficaz en puntos de conexión, identidades, correo electrónico y aplicaciones, y reducir los daños causados por un ataque.

## <a name="triage-your-incidents"></a>Triage your incidents

La respuesta a incidentes en Microsoft 365 Defender se inicia una vez que se triage la lista de incidentes mediante el método de priorización recomendado por la organización. Para triage significa asignar un nivel de importancia o urgencia a los incidentes, que luego determina el orden en que se investigarán. 

Una guía de ejemplo útil para determinar qué incidente se debe priorizar en Microsoft 365 Defender se puede resumir mediante la fórmula: *Gravedad + Impacto = Prioridad*. 

- **Gravedad es** el nivel designado por Microsoft 365 Defender y sus componentes de seguridad integrados. 
- **El** impacto lo determina la organización y, por lo general, incluye, entre otros, un número umbral de usuarios, dispositivos, servicios afectados (o una combinación de los mismos) e incluso un tipo de alerta. 

A continuación, los analistas inician investigaciones en función de los **criterios de** prioridad establecidos por la organización.

La priorización de incidentes puede variar según la organización. NIST recomienda también considerar el impacto funcional e informativo del incidente y la capacidad de recuperación.  

A continuación se muestra un solo enfoque para el triage: 

1. Vaya a la [página incidentes](incidents-overview.md) para iniciar el triaje. Aquí puede ver una lista de incidentes que afectan a su organización. De forma predeterminada, se organizan desde el incidente más reciente hasta el más antiguo. Desde aquí, también puede ver diferentes columnas para cada incidente que muestran su gravedad, categoría, número de alertas activas y entidades afectadas, entre otras. Puede personalizar el conjunto de columnas y ordenar la cola de incidentes por algunas de estas columnas seleccionando el nombre de columna. También puede filtrar la cola de incidentes según sus necesidades. Para obtener una lista completa de los filtros disponibles, vea [Priorizar incidentes](incident-queue.md#available-filters).
  
   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-queue.png" alt-text="Ejemplo de la cola de incidentes"::: 

    Un ejemplo de cómo puede realizar una triaje para este conjunto de incidentes es priorizar los incidentes que afectaron a más usuarios y dispositivos. En este ejemplo, puede priorizar el identificador de incidente 6769 porque afecta al mayor número de entidades: 7 dispositivos, 6 usuarios y 2 buzones. Además, el incidente parece contener alertas de Microsoft Defender for Identity que indican una alerta basada en identidad y un posible robo de credenciales.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-high-impact.png" alt-text="Ejemplo de un incidente de alto impacto":::
 
2. Seleccione el círculo junto al nombre del incidente para revisar los detalles. Aparecerá un panel lateral en el lado derecho, que contiene información adicional que puede ayudar a su triage más. 
 
   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout.png" alt-text="Ejemplo de un panel lateral de incidentes"::: 

   Por ejemplo, al ver qué tácticas de [MITRE ATT&CK](https://attack.mitre.org/) usó el atacante en función de las categorías del incidente, puede priorizar este incidente porque el atacante usó credenciales robadas, estableció el comando y el control, realizó movimiento lateral y exfiltró algunos datos. Esto sugiere que el atacante ya ha entrado en profundidad en la red y posiblemente ha robado información confidencial.

   Además, si su organización ha implementado el marco de confianza cero, consideraría el acceso a credenciales como una infracción de seguridad importante que vale la pena priorizar.
 
   Al desplazarse hacia abajo en el panel lateral, verá las entidades afectadas específicas, como usuarios, dispositivos y buzones. Puedes comprobar el nivel de exposición de cada dispositivo y los propietarios de los buzones afectados.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-details.png" alt-text="Ejemplo de detalles de un panel lateral de incidentes"::: 
 
3. Más abajo del panel lateral, puede encontrar las alertas asociadas. Microsoft 365 Defender ya ha realizado la correlación de estas alertas en un solo incidente, lo que le ahorra tiempo y recursos mejor invertidos en corregir el ataque. Las alertas son sospechosas y, por lo tanto, posiblemente eventos malintencionados del sistema que sugieren la presencia de un atacante en una red. 

   En este ejemplo, se determinó que 87 alertas individuales formaban parte de un incidente de seguridad. Puedes ver todas las alertas para obtener una vista rápida de cómo se ha reproduciendo el ataque.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-alerts.png" alt-text="Ejemplo de alertas en un panel lateral de incidentes"::: 
 
## <a name="analyze-your-first-incident"></a>Analizar el primer incidente

Es igualmente importante comprender el contexto que rodea las alertas. A menudo, una alerta no es un solo evento independiente. Hay una cadena de procesos creados, comandos y acciones que podrían no haber ocurrido al mismo tiempo. Por lo tanto, un analista debe buscar la primera y la última actividad de la entidad sospechosa en las escalas de tiempo del dispositivo para comprender el contexto de las alertas.

Hay varias maneras de leer y analizar datos con Microsoft 365 Defender, pero el objetivo final para los analistas es responder a incidentes lo antes posible. Aunque Microsoft 365 Defender puede reducir significativamente el tiempo medio de corrección [(MTTR)](https://www.microsoft.com/security/blog/2020/05/04/lessons-learned-microsoft-soc-part-3c/) a través de la característica de corrección automática líder del sector, siempre hay casos que requieren análisis manual. 

Aquí le mostramos un ejemplo:

1. Una vez determinada la prioridad del triage, un analista comienza un análisis en profundidad seleccionando el nombre del incidente. En esta página se muestra el **resumen de incidentes** donde se muestran los datos en las pestañas para ayudar con el análisis. En la **pestaña** Alertas se muestra el tipo de alertas. Los analistas pueden hacer clic en cada alerta para profundizar en el origen de detección correspondiente. 

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-summary-tab.png" alt-text="Ejemplo de la pestaña Resumen de un incidente"::: 
 
    Para obtener una guía rápida sobre qué dominio cubre cada origen de detección, revise la [sección Detectar](#detection-by-microsoft-365-defender) de este artículo.

2.  Desde la **pestaña Alertas,** un analista puede pivotar al origen de detección para llevar a cabo una investigación y un análisis más exhaustivos. Por ejemplo, al seleccionar Detección de malware Microsoft Cloud App Security como origen de detección, el analista se lleva a la página de alerta correspondiente.
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-select-alert.png" alt-text="Ejemplo de selección de una alerta de un incidente"::: 
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-link-to-mcas.png" alt-text="Ejemplo de una página correspondiente en Microsoft Cloud App Security"::: 
  
3.  Para investigar nuestro ejemplo más adelante, desplácese hasta la parte inferior de la página para ver los **usuarios afectados**. Para ver la actividad y el contexto que rodea la detección de malware, seleccione La página de usuario de Annette Hill . 
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-page.png" alt-text="Ejemplo de una página de usuario":::
  
4.  En la página de usuario hay una lista cronológica de eventos a partir de un inicio de sesión arriesgado desde una alerta de dirección IP de red *TOR.* Aunque la desconfianza de una actividad depende de la naturaleza de la forma en que una organización lleva a cabo su negocio, en la mayoría de los casos el uso de The Onion Router (TOR), una red que permite a los usuarios navegar por la web de forma anónima, en un entorno empresarial puede considerarse altamente improbable e innecesario para operaciones en línea regulares.
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-event-list.png" alt-text="Ejemplo de la lista cronológica de eventos para un usuario":::
  
5.  Cada alerta se puede seleccionar para obtener más información sobre la actividad. Por ejemplo, al seleccionar Actividad desde una alerta de **dirección IP de Tor,** se llega a la propia página de esa alerta. Annette es administradora de Office 365, lo que significa que tiene privilegios elevados y el incidente de origen podría haber llevado al acceso a información confidencial. 
  
    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-mcas-alert.png" alt-text="Ejemplo de detalles de alertas para Microsoft Cloud App Security"::: 
 
6.  Al seleccionar otras alertas, un analista puede obtener una imagen completa del ataque.

## <a name="next-step"></a>Paso siguiente

[![Paso 2: Información sobre cómo corregir incidentes](../../media/first-incident-overview/first-incident-path-step2.png)](first-incident-remediate.md)

Obtenga información sobre [cómo corregir incidentes](first-incident-remediate.md).

## <a name="see-also"></a>Vea también

- [Información general sobre incidentes](incidents-overview.md)
- [Analizar incidentes](investigate-incidents.md)
- [Administrar incidentes](manage-incidents.md)
