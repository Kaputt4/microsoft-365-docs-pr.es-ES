---
title: Investigar y responder con Microsoft 365 Defender
description: Investigue y responda a incidentes con las funcionalidades de Microsoft 365 Defender.
keywords: incidentes, alertas, investigar, analizar, responder, correlación, ataque, máquinas, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, microsoft, m365, respuesta a incidentes, ciberataque
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
- M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: bb6189c92057b3c58a518bab3768011c4a1cffe4
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67480962"
---
# <a name="investigate-and-respond-with-microsoft-365-defender"></a>Investigar y responder con Microsoft 365 Defender

Estas son las tareas principales de investigación y respuesta para Microsoft 365 Defender:

- [Responder a los incidentes](#incident-response)
- [Revisión y aprobación de acciones de corrección automática](#automated-investigation-and-remediation)
- [Búsqueda de amenazas conocidas en los datos](#proactive-search-for-threats-with-advanced-hunting)
- [Descripción de los últimos ciberataques](#get-ahead-of-emerging-threats-with-threat-analytics)
- [Obtener ayuda](#collaborate-with-microsoft-experts)

## <a name="incident-response"></a>Respuesta a incidentes

Los servicios y aplicaciones de Microsoft 365 crean alertas cuando detectan un evento o actividad sospechosos o malintencionados. Las alertas individuales proporcionan pistas valiosas sobre un ataque completado o en curso. Sin embargo, los ataques suelen emplear varias técnicas en distintos tipos de entidades, como dispositivos, usuarios y buzones de entrada. El resultado son varias alertas para varias entidades del espacio empresarial. Dado que unir las alertas individuales para obtener información sobre un ataque puede ser un desafío y un consumo de tiempo, Microsoft 365 Defender agrega automáticamente las alertas y su información asociada a un incidente.

De forma continua, debe identificar los incidentes de mayor prioridad para el análisis y la resolución en la cola de incidentes y prepararlos para la respuesta. Esta es una combinación de:

- [Priorizar](incident-queue.md) para determinar los incidentes de mayor prioridad mediante el filtrado y la ordenación de la cola de incidentes. Esto también se conoce como triaging.
- [Administrar](manage-incidents.md) incidentes modificando su título, asignándolos a un analista, agregando etiquetas y comentarios, y cuando se resuelven, clasificándolos.

Para cada incidente, use el flujo de trabajo de respuesta a incidentes para analizar el incidente y sus alertas y datos para contener el ataque, erradicar la amenaza, recuperarse del ataque y aprender de él. Consulte [este ejemplo](incidents-overview.md#example-incident-response-workflow-for-microsoft-365-defender) para obtener Microsoft 365 Defender.

## <a name="automated-investigation-and-remediation"></a>Investigación y corrección automatizadas

Si su organización usa Microsoft 365 Defender, el equipo de operaciones de seguridad recibe una alerta en el portal de Microsoft 365 Defender cada vez que se detecta una actividad o artefacto malintencionado o sospechoso. Dado el flujo interminable de amenazas que pueden aparecer, los equipos de seguridad a menudo se enfrentan al desafío de abordar el alto volumen de alertas. Afortunadamente, Microsoft 365 Defender incluye funcionalidades de investigación y respuesta automatizadas (AIR) que pueden ayudar al equipo de operaciones de seguridad a abordar las amenazas de forma más eficaz y eficaz.

Cuando se completa una investigación automatizada, se llega a un veredicto por cada parte de evidencia de un incidente. En función del veredicto, se identifican las acciones de corrección. En algunos casos, las acciones de corrección se realizan automáticamente; en otros casos, las acciones de corrección esperan la aprobación a través del centro de Microsoft 365 Defender acción. 

Consulte [Investigación y respuesta automatizadas en Microsoft 365 Defender](m365d-autoir.md) para obtener más información.

## <a name="proactive-search-for-threats-with-advanced-hunting"></a>Búsqueda proactiva de amenazas con búsqueda avanzada

No es suficiente responder a los ataques a medida que se producen. Para ataques extendidos de varias fases, como ransomware, debe buscar proactivamente la evidencia de un ataque en curso y tomar medidas para detenerlo antes de que se complete.

La búsqueda avanzada es una herramienta de búsqueda de amenazas basada en consultas en Microsoft 365 Defender que le permite explorar hasta 30 días de datos sin procesar. Puede inspeccionar eventos de forma proactiva en su red para localizar entidades e indicadores de amenazas. Este acceso flexible a los datos de Microsoft 365 Defender permite la búsqueda sin restricciones de amenazas conocidas y potenciales.

Puede usar las mismas consultas de búsqueda de amenazas para crear reglas de detección personalizadas. Estas reglas se ejecutan automáticamente para buscar y, a continuación, responder a sospechas de actividad de infracción, máquinas mal configuradas y otros hallazgos.

Consulte [Búsqueda proactiva de amenazas con búsqueda avanzada en Microsoft 365 Defender](advanced-hunting-overview.md) para obtener más información.

## <a name="get-ahead-of-emerging-threats-with-threat-analytics"></a>Adelantarse a las amenazas emergentes con el análisis de amenazas

El análisis de amenazas es una funcionalidad de inteligencia sobre amenazas en Microsoft 365 Defender diseñada para ayudar al equipo de seguridad a ser lo más eficaz posible a la vez que se enfrenta a amenazas emergentes. Incluye análisis detallados e información sobre:

- Actores de amenazas activos y sus campañas
- Técnicas de ataque populares y nuevas
- Vulnerabilidades críticas
- Superficies de ataque comunes
- Malware frecuentes

El análisis de amenazas también incluye información sobre incidentes relacionados y recursos afectados dentro del inquilino de Microsoft 365 para cada amenaza identificada.

Cada amenaza identificada incluye un informe de analista, un análisis completo de la amenaza escrito por investigadores de seguridad de Microsoft que están a la vanguardia de la detección y el análisis de ciberseguridad. Estos informes también pueden proporcionar información sobre cómo aparecen los ataques en Microsoft 365 Defender.

Para obtener más información, consulte [Análisis de amenazas en Microsoft 365 Defender](threat-analytics.md).

## <a name="collaborate-with-microsoft-experts"></a>Colaboración con expertos de Microsoft

Expertos en amenazas de Microsoft: Las notificaciones de ataque dirigidas son un servicio de búsqueda de amenazas administrado. Una vez que se aplique y se acepte, recibirá notificaciones de ataque dirigidas de expertos en amenazas de Microsoft, por lo que no se perderá las amenazas críticas para su entorno. Estas notificaciones le ayudarán a proteger los puntos de conexión, el correo electrónico y las identidades de su organización. Expertos en amenazas de Microsoft: Expertos a petición le permite obtener consejos expertos sobre las amenazas a las que se enfrenta su organización y puede ponerse en contacto con usted para obtener ayuda sobre las amenazas a las que se enfrenta su organización. Está disponible como un servicio de suscripción adicional.

Para obtener más información, consulte [Expertos en amenazas de Microsoft en Información general de Microsoft 365](/microsoft-365/security/defender/microsoft-threat-experts).
