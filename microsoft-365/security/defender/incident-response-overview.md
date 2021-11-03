---
title: Investigar y responder con Microsoft 365 Defender
description: Investigar y responder a incidentes con las capacidades de Microsoft 365 Defender.
keywords: incidentes, alertas, investigar, analizar, respuesta, correlación, ataque, máquinas, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, microsoft, m365, respuesta a incidentes, ciberataque
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: abd075ae76eefc4a86d3e99471f092b3f4f03b34
ms.sourcegitcommit: cfcdb11cc5d39c6c71a34e09c03e8859cd6708d3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2021
ms.locfileid: "60724823"
---
# <a name="investigate-and-respond-with-microsoft-365-defender"></a>Investigar y responder con Microsoft 365 Defender

Estas son las tareas principales de investigar y responder para Microsoft 365 Defender:

- [Responder a los incidentes](#incident-response)
- [Revisar y aprobar acciones de corrección automática](#automated-investigation-and-remediation)
- [Buscar amenazas conocidas en los datos](#proactive-search-for-threats-with-advanced-hunting)
- [Comprender los últimos ciberataques](#get-ahead-of-emerging-threats-with-threat-analytics)
- [Obtener ayuda](#collaborate-with-microsoft-experts)

## <a name="incident-response"></a>Respuesta a incidentes

Los servicios y aplicaciones de Microsoft 365 crean alertas cuando detectan un evento o actividad sospechosos o malintencionados. Las alertas individuales proporcionan pistas valiosas sobre un ataque completado o en curso. Sin embargo, los ataques suelen emplear varias técnicas en distintos tipos de entidades, como dispositivos, usuarios y buzones de entrada. El resultado son varias alertas para varias entidades del espacio empresarial. Dado que unir las alertas individuales para obtener información sobre un ataque puede ser un desafío y un consumo de tiempo, Microsoft 365 Defender agrega automáticamente las alertas y su información asociada a un incidente.

De forma continua, identifique los incidentes más prioritarios para su análisis y resolución en la cola de incidentes y prepárelos para su respuesta. Esta es una combinación de:

- [Triaging](incident-queue.md) to determining the highest priority incidents through filtering and sorting of the incident queue.
- [Administrar](manage-incidents.md) incidentes modificando su título, asignándolos a un analista y agregando etiquetas y comentarios.

Para cada incidente, use el flujo de trabajo de respuesta a incidentes para analizar el incidente y sus alertas y datos para contener el ataque, eliminar la amenaza, recuperarse del ataque y aprender de él. Vea [este ejemplo](incidents-overview.md#example-incident-response-workflow-for-microsoft-365-defender) para obtener Microsoft 365 Defender.

## <a name="automated-investigation-and-remediation"></a>Investigación y corrección automatizadas

Si su organización usa Microsoft 365 Defender, el equipo de operaciones de seguridad recibe una alerta en el portal de Microsoft 365 Defender siempre que se detecte una actividad o artefacto malintencionados o sospechosos. Dado el flujo interminable de amenazas que pueden llegar, los equipos de seguridad a menudo se enfrentan al desafío de abordar el alto volumen de alertas. Afortunadamente, Microsoft 365 Defender capacidades de investigación y respuesta automatizadas (AIR) que pueden ayudar a su equipo de operaciones de seguridad a abordar las amenazas de forma más eficaz y eficaz.

Cuando se completa una investigación automatizada, se llega a un veredicto para cada parte de evidencia de un incidente implicado. Según el veredicto, se identifican las acciones de corrección. En algunos casos, las acciones de corrección se toman automáticamente; en otros casos, las acciones de corrección esperan la aprobación a través del centro Microsoft 365 Defender acción. 

Vea [Investigación automatizada y respuesta en Microsoft 365 Defender](m365d-autoir.md) para obtener más información.

## <a name="proactive-search-for-threats-with-advanced-hunting"></a>Búsqueda proactiva de amenazas con búsqueda avanzada

No basta con responder a los ataques a medida que se producen. Para ataques multifase extendidos, como ransomware, debes buscar proactivamente la evidencia de un ataque en curso y tomar medidas para detenerlo antes de que se complete.

La búsqueda avanzada es una herramienta de búsqueda de amenazas basada en consultas Microsoft 365 Defender que te permite explorar hasta 30 días de datos sin procesar. Puede inspeccionar eventos de forma proactiva en su red para localizar entidades e indicadores de amenazas. Este acceso flexible a los Microsoft 365 Defender permite la búsqueda sin restricciones de amenazas conocidas y potenciales.

Puede usar las mismas consultas de búsqueda de amenazas para crear reglas de detección personalizadas. Estas reglas se ejecutan automáticamente para buscar y responder a una actividad de infracción sospechosa, máquinas mal configuradas y otras conclusiones.

Consulta [Búsqueda proactiva de amenazas con búsqueda avanzada en Microsoft 365 Defender](advanced-hunting-overview.md) para obtener más información.

## <a name="get-ahead-of-emerging-threats-with-threat-analytics"></a>Anticiparse a las amenazas emergentes con análisis de amenazas

El análisis de amenazas es una funcionalidad de inteligencia de amenazas Microsoft 365 Defender diseñada para ayudar a su equipo de seguridad a ser lo más eficiente posible mientras enfrenta amenazas emergentes. Incluye análisis detallado e información sobre:

- Actores de amenazas activas y sus campañas
- Técnicas de ataque populares y nuevas
- Vulnerabilidades críticas
- Superficies de ataque comunes
- Malware frecuentes

El análisis de amenazas también incluye información sobre incidentes relacionados y activos afectados dentro de Microsoft 365 inquilino para cada amenaza identificada.

Cada amenaza identificada incluye un informe de analista, un análisis completo de la amenaza escrita por investigadores de seguridad de Microsoft que están a la vanguardia de la detección y el análisis de ciberseguridad y pueden proporcionar información sobre cómo aparecen los ataques en Microsoft 365 Defender.

Para obtener más información, vea [Análisis de amenazas en Microsoft 365 Defender](threat-analytics.md).

## <a name="collaborate-with-microsoft-experts"></a>Colaborar con expertos de Microsoft

Expertos en amenazas de Microsoft: las notificaciones de ataque dirigidos son un servicio de búsqueda de amenazas administrado. Una vez que apliques y te acepten, recibirás notificaciones de ataques dirigidos de expertos en amenazas de Microsoft, para que no te pierdas las amenazas críticas a tu entorno. Estas notificaciones le ayudarán a proteger los puntos de conexión, el correo electrónico y las identidades de su organización. Expertos en amenazas de Microsoft: expertos a petición te permiten obtener consejos de expertos sobre las amenazas a las que se enfrenta la organización y puedes obtener ayuda sobre las amenazas a las que se enfrenta la organización. Está disponible como servicio de suscripción adicional.

Para obtener más información, [vea Expertos en amenazas de Microsoft en Microsoft 365 overview](/security/mtp/microsoft-threat-experts.md).
