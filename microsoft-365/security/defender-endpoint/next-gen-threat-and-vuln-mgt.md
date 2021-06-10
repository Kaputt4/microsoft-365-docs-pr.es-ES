---
title: Administración de amenazas y vulnerabilidades
description: Esta nueva funcionalidad usa un enfoque basado en riesgos que cambia el juego para la detección, priorización y corrección de vulnerabilidades y configuraciones erróneas de puntos de conexión.
keywords: threat & administración de vulnerabilidades, Administración de amenazas y vulnerabilidades, Microsoft Defender for Endpoint TVM, Microsoft Defender for Endpoint-TVM, administración de vulnerabilidades, vulnerability assessment, threat and vulnerability scanning, secure configuration assessment, Microsoft Defender for Endpoint, endpoint vulnerabilities, next generation
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: overview
ms.technology: mde
ms.openlocfilehash: 474b8f032d32668eaea3a477da013c2b8e74019b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934170"
---
# <a name="threat-and-vulnerability-management"></a>Administración de amenazas y vulnerabilidades

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Identificar, evaluar y corregir eficazmente las debilidades de los puntos de conexión es fundamental para ejecutar un programa de seguridad correcto y reducir los riesgos de la organización. La administración de amenazas y vulnerabilidades funciona a modo de infraestructura para reducir la exposición en la organización, fortalecer la superficie de los puntos de conexión y aumentar la resistencia de la organización.

Descubra vulnerabilidades y configuraciones erróneas en tiempo real con sensores y sin necesidad de agentes ni exámenes periódicos. Prioriza las vulnerabilidades en función del panorama de amenazas, las detecciones de la organización, la información confidencial en dispositivos vulnerables y el contexto empresarial.

Vea este vídeo para obtener una introducción rápida a Administración de amenazas y vulnerabilidades.

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4mLsn]

## <a name="bridging-the-workflow-gaps"></a>Puentear las diferencias de flujo de trabajo

La amenaza administración de vulnerabilidades está integrada, en tiempo real y con tecnología de nube. Está totalmente integrado con la pila de seguridad de puntos de conexión de Microsoft, la base de Graph seguridad inteligente de Microsoft y la base de conocimientos de análisis de aplicaciones.  

La administración de vulnerabilidades es la primera solución del sector que ha puenteado la brecha entre la administración de seguridad y la administración de IT durante el proceso de corrección. Cree una tarea o vale de seguridad integrándose con Microsoft Intune y Microsoft Endpoint Configuration Manager.

### <a name="real-time-discovery"></a>Detección en tiempo real

Para detectar vulnerabilidades de puntos de conexión y configuración incorrecta, Administración de amenazas y vulnerabilidades usa los mismos sensores integrados de Defender for Endpoint sin agente para reducir los engorrosos exámenes de red y la sobrecarga de TI.

También proporciona:

- **Inventario de dispositivos** en tiempo real: los dispositivos incorporados a Defender for Endpoint informan e insertan automáticamente datos de configuración de seguridad y vulnerabilidad en el panel.
- **Visibilidad del software y las vulnerabilidades:** ópticas en el inventario de software de la organización y cambios de software como instalaciones, desinstalaciones y revisiones. Las vulnerabilidades detectadas recientemente se notifican con recomendaciones de mitigación que se pueden aplicar para aplicaciones de 1ª y 3ª parte.
- **Contexto de tiempo de ejecución** de la aplicación: visibilidad de los patrones de uso de la aplicación para una mejor priorización y toma de decisiones.
- **Posición de configuración:** visibilidad de la configuración de seguridad de la organización o de las configuraciones erróneas. Los problemas se notifican en el panel con recomendaciones de seguridad que se pueden usar.

### <a name="intelligence-driven-prioritization"></a>Priorización basada en inteligencia

Amenaza y administración de vulnerabilidades ayuda a los clientes a priorizar y centrarse en las debilidades que representan el riesgo más urgente y más alto para la organización. Combina recomendaciones de seguridad con amenazas dinámicas y contexto empresarial:

- **Exponer los ataques emergentes de forma natural:** alinea dinámicamente la priorización de las recomendaciones de seguridad. La amenaza administración de vulnerabilidades se centra en las vulnerabilidades que se están explotando actualmente en las amenazas emergentes y silvestres que representan el mayor riesgo.
- **Localización de infracciones activas:** correlaciona Administración de amenazas y vulnerabilidades y EDR información para priorizar las vulnerabilidades que se explotan en una infracción activa dentro de la organización.
- **Protección de activos de alto** valor: identifique los dispositivos expuestos con aplicaciones críticas para la empresa, datos confidenciales o usuarios de alto valor.

### <a name="seamless-remediation"></a>Corrección sin problemas

Las amenazas y administración de vulnerabilidades permiten a los administradores de seguridad y a los administradores de TI colaborar sin problemas para solucionar problemas.

- **Solicitudes de corrección enviadas** a IT: cree una tarea de corrección en Microsoft Intune desde una recomendación de seguridad específica. Planeamos expandir esta funcionalidad a otras plataformas de administración de seguridad de IT.
- **Mitigaciones alternativas:** obtenga información sobre mitigaciones adicionales, como cambios de configuración que pueden reducir el riesgo asociado con vulnerabilidades de software.
- **Estado de corrección** en tiempo real: supervisión en tiempo real del estado y el progreso de las actividades de corrección en toda la organización.

## <a name="threat-and-vulnerability-management-walk-through"></a>Amenazas y administración de vulnerabilidades paso a través

Vea este vídeo para ver un recorrido completo de Administración de amenazas y vulnerabilidades.

>[!VIDEO https://aka.ms/MDATP-TVM-Interactive-Guide]

## <a name="navigation-pane"></a>Panel de navegación 

Área | Descripción
:---|:---
**Panel**   | Obtenga una vista de alto nivel de la puntuación de exposición de la organización, puntuación segura de Microsoft para dispositivos, distribución de exposición de dispositivos, recomendaciones de seguridad principales, software vulnerable superior, actividades de corrección superior y datos de dispositivos expuestos superiores.
[**Recomendaciones de seguridad**](tvm-security-recommendation.md) | Consulta la lista de recomendaciones de seguridad e información de amenazas relacionada. Al seleccionar un elemento de la lista, se abre un panel desplegable con detalles de vulnerabilidad, un vínculo para abrir la página de software y opciones de corrección y excepción. También puedes abrir un vale en Intune si los dispositivos están unidos a través de Azure Active Directory y has habilitado las conexiones de Intune en Defender para endpoint.
[**Corrección**](tvm-remediation.md) | Vea las actividades de corrección que ha creado y las excepciones de recomendación.
[**Inventario de software**](tvm-software-inventory.md) | Consulta la lista de software vulnerable de tu organización, junto con información de debilidad y amenazas.
[**Debilidades**](tvm-weaknesses.md) | Consulta la lista de vulnerabilidades y exposiciones comunes (CVE) en tu organización.
[**Línea de tiempo de eventos**](threat-and-vuln-mgt-event-timeline.md) | Ver eventos que pueden afectar el riesgo de su organización.

## <a name="apis"></a>API

Ejecute Administración de amenazas y vulnerabilidades de API relacionadas para automatizar administración de vulnerabilidades de trabajo. Obtenga más información en esta [entrada Community blog de Microsoft Tech](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/threat-amp-vulnerability-management-apis-are-now-generally/ba-p/1304615).

Vea los siguientes artículos para obtener las API relacionadas:

- [API compatibles de Microsoft Defender para punto de conexión](exposed-apis-list.md)
- [API de máquina](machine.md)
- [API de recomendación](vulnerability.md)
- [API de puntuación](score.md)
- [API de software](software.md)
- [API de vulnerabilidad](vulnerability.md)
- [Enumerar vulnerabilidades por máquina y software](get-all-vulnerabilities-by-machines.md)

## <a name="see-also"></a>Consulte también

- [Plataformas y sistemas operativos compatibles](tvm-supported-os.md)
- [Panel de administración de vulnerabilidades amenazas](tvm-dashboard-insights.md)
- [BLOG: La administración de vulnerabilidades de & amenazas de Microsoft ahora ayuda a miles de clientes a detectar, priorizar y corregir vulnerabilidades en tiempo real](https://www.microsoft.com/security/blog/2019/07/02/microsofts-threat-vulnerability-management-now-helps-thousands-of-customers-to-discover-prioritize-and-remediate-vulnerabilities-in-real-time/)
