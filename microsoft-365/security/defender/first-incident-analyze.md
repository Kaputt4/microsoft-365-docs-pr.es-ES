---
title: Paso 1. Evaluación y análisis del primer incidente
description: Cómo evaluar e iniciar el análisis del primer incidente en Microsoft 365 Defender.
keywords: incidentes, alertas, investigación, correlación, ataque, máquinas, dispositivos, usuarios, identidades, identidad, buzón de correo electrónico, 365, microsoft, m365, respuesta a incidentes, ciberataque
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
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
- m365-security
- m365solution-firstincident
- highpri
- tier1
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: b2e10cd5e3d615495a688484dd8351cecb1564f4
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68080049"
---
# <a name="step-1-triage-and-analyze-your-first-incident"></a>Paso 1. Evaluación y análisis del primer incidente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

A medida que dedica algún tiempo a establecer, implementar y mantener medidas de seguridad de acuerdo con los estándares de la organización, puede configurar soluciones de seguridad para ayudarle a identificar rápidamente los riesgos y amenazas de seguridad. Microsoft 365 Defender permite detectar, evaluar e investigar incidentes a través de su experiencia de panel único de cristal, donde puede encontrar la información que necesita para tomar decisiones oportunas.

Una vez detectado un incidente de seguridad, Microsoft 365 Defender presenta detalles que deberá evaluar o priorizar un incidente o incidente sobre otros. Después de determinar la priorización, los analistas pueden centrar su energía en investigar los casos asignados a ellos.

## <a name="detection-by-microsoft-365-defender"></a>Detección por Microsoft 365 Defender

Microsoft 365 Defender recibe alertas y eventos de varias plataformas de seguridad de Microsoft como orígenes de detección para crear una imagen holística y un contexto de actividad malintencionada. Los posibles orígenes de detección son:

- [Microsoft Defender para punto de conexión](../defender-endpoint/microsoft-defender-endpoint.md) es una solución de detección y respuesta de puntos de conexión (EDR) que usa Microsoft Defender antivirus y protección contra amenazas avanzada habilitada para la nube mediante Microsoft Security Graph. Defender for Endpoint es una plataforma unificada para la protección preventiva, la detección posterior a la vulneración, la investigación automatizada y la respuesta. Protege los puntos de conexión frente a ciberamenazas, detecta ataques avanzados e infracciones de datos, automatiza incidentes de seguridad y mejora la posición de seguridad.
- [Microsoft Defender for Identity](/defender-for-identity/what-is) es una solución de seguridad basada en la nube que usa las señales de Active Directory local Domain Services (AD DS) para identificar, detectar e investigar amenazas avanzadas, identidades en peligro y acciones internas malintencionadas dirigidas a su organización.
- [Microsoft Defender for Cloud Apps](/cloud-app-security/) actúa como portero para brokerar el acceso en tiempo real entre los usuarios empresariales y los recursos en la nube que usan, dondequiera que se encuentren los usuarios e independientemente del dispositivo que usen.
- [Microsoft Defender para Office 365](/microsoft-365/office-365-security/overview) protege a su organización frente a amenazas malintencionadas en mensajes de correo electrónico, vínculos (direcciones URL) y herramientas de colaboración.
- [Azure Security Center](/azure/security-center/security-center-introduction) es un sistema unificado de administración de seguridad de la infraestructura que refuerza la posición de seguridad de los centros de datos y proporciona protección contra amenazas avanzada en las cargas de trabajo híbridas en la nube y en el entorno local.


En Microsoft 365 Defender, los incidentes se identifican mediante la correlación de [alertas](incidents-overview.md) de estos orígenes de detección diferentes. En lugar de gastar recursos encadenándose juntos o distinguir varias alertas en sus incidentes respectivos, puede empezar con la cola de incidentes en Microsoft 365 Defender inmediatamente. Este enfoque le permite evaluar los incidentes de forma eficaz entre puntos de conexión, identidades, correo electrónico y aplicaciones, y reducir el daño de un ataque.

## <a name="triage-your-incidents"></a>Evaluación de los incidentes

La respuesta a incidentes en Microsoft 365 Defender se inicia una vez que se evalúa la lista de incidentes mediante el método recomendado de priorización de la organización. Evaluar significa asignar un nivel de importancia o urgencia a los incidentes, que luego determina el orden en el que se investigarán.

Una guía de ejemplo útil para determinar qué incidente debe priorizar en Microsoft 365 Defender se puede resumir mediante la fórmula: *Gravedad + Impacto = Prioridad*.

- **Gravedad** es el nivel designado por Microsoft 365 Defender y sus componentes de seguridad integrados.
- **El impacto** lo determina la organización y, por lo general, incluye, entre otros, un número de umbral de usuarios, dispositivos, servicios afectados (o una combinación de ellos) e incluso el tipo de alerta.

A continuación, los analistas inician investigaciones basadas en los criterios de **prioridad** establecidos por la organización.

La priorización de incidentes puede variar en función de la organización. NIST también recomienda tener en cuenta el impacto funcional e informativo del incidente y la capacidad de recuperación.

A continuación se describe un enfoque de evaluación de prioridades:

1. Vaya a la página [incidentes](incidents-overview.md) para iniciar la evaluación de prioridades. Aquí puede ver una lista de incidentes que afectan a su organización. De forma predeterminada, se organizan del incidente más reciente al más antiguo. Desde aquí, también puede ver columnas diferentes para cada incidente que muestran su gravedad, categoría, número de alertas activas y entidades afectadas, entre otras. Puede personalizar el conjunto de columnas y ordenar la cola de incidentes por algunas de estas columnas seleccionando el nombre de columna. También puede filtrar la cola de incidentes según sus necesidades. Para obtener una lista completa de los filtros disponibles, consulte [Priorización de incidentes](incident-queue.md#available-filters).

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-queue.png" alt-text="Los incidentes en el portal de seguridad de Microsoft 365" lightbox="../../media/first-incident-analyze/first-incident-analyze-queue.png":::

    Un ejemplo de cómo puede realizar la evaluación de prioridades para este conjunto de incidentes es priorizar los incidentes que afectaron a más usuarios y dispositivos. En este ejemplo, podría priorizar el identificador de incidente 6769 porque afectaba al mayor número de entidades: siete dispositivos, seis usuarios y dos buzones de correo. Además, el incidente parece contener alertas de Microsoft Defender for Identity, que indican una alerta basada en identidad y un posible robo de credenciales.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-high-impact.png" alt-text="La página Incidentes** muestra el ejemplo de un incidente de alto impacto en el portal de seguridad de Microsoft 365" lightbox="../../media/first-incident-analyze/first-incident-analyze-high-impact.png":::

2. Seleccione el círculo situado junto al nombre del incidente para revisar los detalles. Aparecerá un panel lateral en el lado derecho, que contiene información adicional que puede ayudar más a la evaluación de la evaluación.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout.png" alt-text="Página Incidentes que muestra el ejemplo de un panel lateral de incidentes en el portal de seguridad de Microsoft 365" lightbox="../../media/first-incident-analyze/first-incident-analyze-incident-flyout.png":::

   Por ejemplo, al examinar qué [tácticas de MITRE ATT&CK](https://attack.mitre.org/) usaba el atacante en función de las categorías del incidente, podría priorizar este incidente porque el atacante usó credenciales robadas, estableció comando y control, realizó movimiento lateral y exfiltró algunos datos. Estas acciones sugieren que el atacante ya ha profundizado en la red y posiblemente ha robado información confidencial.

   Además, si su organización ha implementado el marco de Confianza cero, consideraría el acceso a credenciales como una infracción de seguridad importante que merece la pena priorizar.

   Al desplazarse por el panel lateral, verá las entidades afectadas específicas, como usuarios, dispositivos y buzones de correo. Puede comprobar el nivel de exposición de cada dispositivo y los propietarios de los buzones afectados.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-details.png" alt-text="Detalles del panel lateral del incidente" lightbox="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-details.png":::

3. Más abajo en el panel lateral, puede encontrar las alertas asociadas. Microsoft 365 Defender ya ha realizado la correlación de dichas alertas en un único incidente, lo que le ahorra tiempo y recursos que se dedican mejor a corregir el ataque. Las alertas son sospechosas y, por lo tanto, posiblemente eventos malintencionados del sistema que sugieren la presencia de un atacante en una red.

   En este ejemplo, se determinó que 87 alertas individuales formaban parte de un incidente de seguridad. Puede ver todas las alertas para obtener una vista rápida de cómo se ha realizado el ataque.

   :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-alerts.png" alt-text="Las alertas de un panel lateral de incidentes en el portal de seguridad de Microsoft 365" lightbox="../../media/first-incident-analyze/first-incident-analyze-incident-flyout-alerts.png":::

## <a name="analyze-your-first-incident"></a>Análisis del primer incidente

Comprender el contexto que rodea las alertas es igual de importante. A menudo, una alerta no es un evento independiente. Hay una cadena de procesos creados, comandos y acciones que podrían no haberse producido al mismo tiempo. Por lo tanto, un analista debe buscar la primera y la última actividad de la entidad sospechosa en las escalas de tiempo del dispositivo para comprender el contexto de las alertas.

Hay varias maneras de leer y analizar datos mediante Microsoft 365 Defender, pero el objetivo final para los analistas es responder a los incidentes lo más rápido posible. Aunque Microsoft 365 Defender pueden reducir significativamente el [tiempo medio de corrección (MTTR)](https://www.microsoft.com/security/blog/2020/05/04/lessons-learned-microsoft-soc-part-3c/) a través de la característica de [investigación y respuesta automatizada](m365d-autoir.md) líder del sector, siempre hay casos que requieren análisis manuales.

Aquí le mostramos un ejemplo:

1. Una vez que se ha determinado la prioridad de evaluación de prioridades, un analista comienza un análisis detallado seleccionando el nombre del incidente. En esta página se muestra el **resumen de incidentes** , donde los datos se muestran en pestañas para ayudar con el análisis. En la pestaña **Alertas** , se muestran los tipos de alertas. Los analistas pueden hacer clic en cada alerta para explorar en profundidad el origen de detección correspondiente.

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-summary-tab.png" alt-text="Pestaña Resumen de un incidente" lightbox="../../media/first-incident-analyze/first-incident-analyze-summary-tab.png":::

    Para obtener una guía rápida sobre qué dominio abarca cada origen de detección, revise la sección [Detectar](#detection-by-microsoft-365-defender) de este artículo.

2. En la pestaña **Alertas** , puede pasar al origen de detección para realizar una investigación y un análisis más detallados. Por ejemplo, al seleccionar Detección de malware con Microsoft Defender for Cloud Apps como origen de detección, el analista se lleva a su página de alerta correspondiente.

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-select-alert.png" alt-text="La página Incidentes que muestra un ejemplo de selección de una alerta de un incidente." lightbox="../../media/first-incident-analyze/first-incident-analyze-select-alert.png":::

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-link-to-mcas.png" alt-text="Página correspondiente en el Microsoft Defender for Cloud Apps" lightbox="../../media/first-incident-analyze/first-incident-analyze-link-to-mcas.png":::

3. Para investigar aún más nuestro ejemplo, desplácese hasta la parte inferior de la página para ver los **usuarios afectados**. Para ver la actividad y el contexto que rodean la detección de malware, seleccione la página de usuario de Annette Hill.

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-page.png" alt-text="Una página de usuario" lightbox="../../media/first-incident-analyze/first-incident-analyze-user-page.png":::

4. En la página de usuario se enumeran los eventos cronológicamente, empezando por un *inicio de sesión de riesgo desde una alerta de dirección IP de red TOR* . Aunque la sospecha de una actividad depende de la naturaleza de cómo una organización lleva a cabo su negocio, en la mayoría de los casos el uso de The Onion Router (TOR), una red que permite a los usuarios navegar por la web de forma anónima, en un entorno empresarial podría considerarse altamente improbable e innecesario para las operaciones en línea normales.

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-user-event-list.png" alt-text="Lista cronológica de eventos para un usuario" lightbox="../../media/first-incident-analyze/first-incident-analyze-user-event-list.png":::

5. Cada alerta se puede seleccionar para obtener más información sobre la actividad. Por ejemplo, al seleccionar **Actividad en una alerta de dirección IP de Tor** , se le dirigirá a la propia página de esa alerta. Annette es administrador de Office 365, lo que indica privilegios elevados y que el incidente de origen podría haber llevado al acceso a información confidencial.

    :::image type="content" source="../../media/first-incident-analyze/first-incident-analyze-mcas-alert.png" alt-text="Los detalles de alertas de la Microsoft Defender for Cloud Apps" lightbox="../../media/first-incident-analyze/first-incident-analyze-mcas-alert.png" :::

6. Al seleccionar otras alertas, puede obtener una imagen completa del ataque.

## <a name="next-step"></a>Paso siguiente

:::image type="content" source="../../media/first-incident-overview/first-incident-path-step2.png" alt-text="La opción Corregir en la página Responder a su primer incidente" lightbox="../../media/first-incident-overview/first-incident-path-step2.png":::

Obtenga información sobre cómo [corregir incidentes](first-incident-remediate.md).

## <a name="see-also"></a>Vea también

- [Información general sobre incidentes](incidents-overview.md)
- [Investigar incidentes](investigate-incidents.md)
- [Administrar incidentes](manage-incidents.md)
