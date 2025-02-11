---
title: Novedades de Microsoft 365 Defender
description: Enumera las nuevas características y funcionalidades de Microsoft 365 Defender
keywords: novedades de Microsoft 365 Defender, ga, disponibilidad general, funcionalidades, disponibles, nuevas
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
ms.date: 07/27/2022
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- tier1
ms.topic: conceptual
ms.openlocfilehash: 77dd7dd7442e5e3bf585f9c6d52f194714a7d722
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68069565"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Novedades de Microsoft 365 Defender

Enumera las nuevas características y funciones de Microsoft 365 Defender. 

Fuente RSS: para recibir notificaciones cuando esta página se actualice, copie y pegue la dirección URL siguiente en el lector de fuentes: 

```http
https://learn.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+365+defender%22&locale=en-us
```

Para obtener más información sobre las novedades de otros productos de seguridad de Microsoft Defender, consulte:

- [Novedades de Microsoft Defender para Office 365](../office-365-security/whats-new-in-defender-for-office-365.md)
- [Novedades de Microsoft Defender para punto de conexión](../defender-endpoint/whats-new-in-microsoft-defender-endpoint.md)
- [Novedades de Microsoft Defender for Identity](/defender-for-identity/whats-new)
- [Novedades de Microsoft Defender for Cloud Apps](/cloud-app-security/release-notes)

También puede obtener actualizaciones de productos y notificaciones importantes a través del [centro de mensajes](https://admin.microsoft.com/Adminportal/Home#/MessageCenter).

## <a name="august-2022"></a>Agosto de 2022
- (GA) [Microsoft Defender Expertos en Caza](defender-experts-for-hunting.md) ya está disponible con carácter general. Si es un cliente Microsoft 365 Defender con un centro de operaciones de seguridad sólido, pero quiere que Microsoft le ayude a buscar amenazas de forma proactiva entre puntos de conexión, Office 365, aplicaciones en la nube e identidad mediante Microsoft Defender datos, obtenga más información sobre cómo aplicar, configurar y usar el servicio. Defender Experts for Hunting se vende por separado de otros productos Microsoft 365 Defender.
- (versión preliminar) [El modo guiado](advanced-hunting-modes.md#get-started-with-guided-hunting-mode) ya está disponible para la versión preliminar pública en la búsqueda avanzada. Los analistas ahora pueden empezar a consultar su base de datos en busca de puntos de conexión, identidades, correo electrónico & colaboración y datos de aplicaciones en la nube *sin conocer Lenguaje de consulta Kusto (KQL).*  El modo guiado cuenta con un estilo de bloque de creación sencillo y fácil de usar de construir consultas a través de menús desplegables que contienen filtros y condiciones disponibles. Consulte [Introducción al generador de consultas](advanced-hunting-query-builder.md).

## <a name="july-2022"></a>Julio de 2022
- (versión preliminar) Microsoft Defender expertos para la búsqueda de participantes en la versión preliminar pública ahora pueden esperar recibir informes mensuales para ayudarles a comprender las amenazas que el servicio de búsqueda anunció en su entorno, junto con las alertas generadas por sus productos de Microsoft 365 Defender. Para obtener más información, consulte [Descripción del informe de expertos de Defender para la búsqueda en Microsoft 365 Defender](defender-experts-report.md).

## <a name="june-2022"></a>Junio de 2022
- (versión preliminar) Las tablas [DeviceTvmInfoGathering](advanced-hunting-devicetvminfogathering-table.md) y [DeviceTvmInfoGatheringKB](advanced-hunting-devicetvminfogatheringkb-table.md) ya están disponibles en el esquema de búsqueda avanzada. Use estas tablas para buscar eventos de evaluación en Defender Vulnerability Management, incluido el estado de varias configuraciones y los estados de área expuesta a ataques de los dispositivos.

- La tarjeta de respuesta & investigación automatizada recién introducida en el portal de Microsoft 365 Defender proporciona información general sobre las acciones de corrección pendientes.
El equipo de operaciones de seguridad puede ver todas las acciones pendientes de aprobación y el tiempo estipulado para aprobar esas acciones en la propia tarjeta. El equipo de seguridad puede navegar rápidamente al Centro de acciones y tomar las medidas de corrección adecuadas. La tarjeta de respuesta & investigación automatizada también tiene un vínculo a la página Automatización completa. Esto permite al equipo de operaciones de seguridad administrar de forma eficaz las alertas y completar las acciones de corrección de forma oportuna.


## <a name="may-2022"></a>Mayo de 2022
- (versión preliminar) En consonancia con la expansión anunciada recientemente en una nueva categoría de servicio denominada [Microsoft Security Experts](https://aka.ms/MicrosoftSecurityExperts), presentamos la disponibilidad de [Microsoft Defender Experts for Hunting](defenderexpertsforhuntingprev.md) (Defender Experts for Hunting) para la versión preliminar pública. Expertos de Defender para la búsqueda es para clientes que tienen un sólido centro de operaciones de seguridad, pero quieren que Microsoft les ayude a buscar amenazas de forma proactiva en Microsoft Defender datos, incluidos puntos de conexión, Office 365, aplicaciones en la nube e identidad. 

## <a name="april-2022"></a>Abril de 2022
- (versión preliminar) [Ahora](advanced-hunting-take-action.md) se pueden realizar acciones en los mensajes de correo electrónico directamente desde los resultados de la consulta de búsqueda. Los correos electrónicos se pueden mover a otras carpetas o eliminarse de forma permanente. 
- (versión preliminar) La nueva [`UrlClickEvents` tabla](advanced-hunting-urlclickevents-table.md) de búsqueda avanzada se puede usar para buscar amenazas, como campañas de suplantación de identidad (phishing) y vínculos sospechosos basados en información procedente de clics de vínculos seguros en mensajes de correo electrónico, Microsoft Teams y aplicaciones Office 365.

## <a name="march-2022"></a>Marzo de 2022

- (versión preliminar) La cola de incidentes se ha mejorado con varias características diseñadas para ayudar a las investigaciones. Entre las mejoras se incluyen funcionalidades como la capacidad de buscar incidentes por identificador o nombre, especificar un intervalo de tiempo personalizado y otros.


## <a name="december-2021"></a>Diciembre de 2021

- (GA) La `DeviceTvmSoftwareEvidenceBeta` tabla se agregó a corto plazo en la búsqueda avanzada para permitir ver evidencias de dónde se detectó un software específico en un dispositivo.

## <a name="november-2021"></a>Noviembre de 2021

- (versión preliminar) La característica de complemento de gobernanza de aplicaciones para Defender for Cloud Apps ya está disponible en Microsoft 365 Defender. La gobernanza de aplicaciones proporciona una funcionalidad de administración de directivas y seguridad diseñada para aplicaciones habilitadas para OAuth que acceden a datos de Microsoft 365 a través de las API de Microsoft Graph. La gobernanza de aplicaciones ofrece visibilidad, corrección y gobernanza completas sobre cómo estas aplicaciones y sus usuarios acceden, usan y comparten sus datos confidenciales almacenados en Microsoft 365 a través de información útil, y alertas y acciones de directivas automatizadas. [Más información sobre la gobernanza de aplicaciones](/cloud-app-security/app-governance-manage-app-governance).
- (versión preliminar) La página [de búsqueda avanzada](advanced-hunting-overview.md) ahora tiene compatibilidad con multitab, desplazamiento inteligente, pestañas de esquema simplificadas, opciones de edición rápida para consultas, un indicador de uso de recursos de consulta y otras mejoras para que las consultas sean más fluidas y fáciles de ajustar.
- (versión preliminar) Ahora puede usar el [vínculo a la característica de incidente](advanced-hunting-link-to-incident.md) para incluir eventos o registros de los resultados de la consulta de búsqueda avanzada directamente en un incidente nuevo o existente que está investigando.

## <a name="october-2021"></a>Octubre de 2021

- (GA) En la búsqueda avanzada, se agregaron más columnas en la tabla [CloudAppEvents](advanced-hunting-cloudappevents-table.md) . Ahora puede incluir `AccountType`, `IsExternalUser`, `IsImpersonated`, `IPTags`, `IPCategory`y `UserAgentTags` en las consultas.

## <a name="september-2021"></a>Septiembre de 2021

- (GA) Microsoft Defender para Office 365 datos de eventos está disponible en la API de streaming de eventos de Microsoft 365 Defender. Puede ver la disponibilidad y el estado de los tipos de eventos en los [tipos de eventos Microsoft 365 Defender admitidos en la API de streaming](supported-event-types.md).
- (GA) Microsoft Defender para Office 365 datos disponibles en la búsqueda avanzada ahora están disponibles con carácter general.
- (GA) Asignación de incidentes y alertas a cuentas de usuario

  Puede asignar un incidente y todas las alertas asociadas a ella a una cuenta de usuario desde **Asignar a:** en el panel **Administrar incidente** de un incidente o en el panel **Administrar alerta** de una alerta.

## <a name="august-2021"></a>Agosto de 2021

- (versión preliminar) Microsoft Defender para Office 365 datos disponibles en la búsqueda avanzada

  Las nuevas columnas de las tablas de correo electrónico pueden proporcionar más información sobre las amenazas basadas en correo electrónico para realizar investigaciones más exhaustivas mediante la búsqueda avanzada. Ahora puede incluir la `AuthenticationDetails` columna en [EmailEvents](./advanced-hunting-emailevents-table.md), `FileSize` en [EmailAttachmentInfo](./advanced-hunting-emailattachmentinfo-table.md) y `ThreatTypes` `DetectionMethods` en las tablas [EmailPostDeliveryEvents](./advanced-hunting-emailpostdeliveryevents-table.md) .

- (versión preliminar) Gráfico de incidentes

  Una nueva pestaña **de Graph** en la pestaña **Resumen** de un incidente muestra el ámbito completo del ataque, cómo se extendió el ataque a través de la red a lo largo del tiempo, dónde se inició y hasta dónde llegó el atacante.

## <a name="july-2021"></a>Julio de 2021

- [Catálogo de servicios profesionales](https://sip.security.microsoft.com/interoperability/professional_services)

  Mejore las funcionalidades de detección, investigación e inteligencia sobre amenazas de la plataforma con conexiones de asociado compatibles.

## <a name="june-2021"></a>Junio de 2021

- (versión preliminar) [Visualización de informes por etiquetas de amenazas](threat-analytics.md#view-reports-per-threat-tags)

  Las etiquetas de amenazas le ayudan a centrarse en categorías de amenazas específicas y a revisar los informes más relevantes.

- (versión preliminar) [API de streaming](../defender-endpoint/raw-data-export.md)

  Microsoft 365 Defender admite el streaming de todos los eventos disponibles a través de búsqueda avanzada a una cuenta de Almacenamiento de Azure o Event Hubs.

- (versión preliminar) [Tomar medidas en la búsqueda avanzada](advanced-hunting-take-action.md)

  Contener rápidamente amenazas o abordar los recursos en peligro que se encuentran en la [búsqueda avanzada](advanced-hunting-overview.md).

- (versión preliminar) [Referencia de esquema en el portal](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)

  Obtenga información sobre las tablas de esquema de búsqueda avanzada directamente en el centro de seguridad. Además de las descripciones de tabla y columna, esta referencia incluye tipos de eventos admitidos (`ActionType` valores) y consultas de ejemplo.

- (versión preliminar) [Función DeviceFromIP()](advanced-hunting-devicefromip-function.md)

  Obtenga información sobre qué dispositivos se han asignado una dirección IP específica o direcciones en un intervalo de tiempo determinado.

## <a name="may-2021"></a>Mayo de 2021

- [Nueva página de alerta en el portal de Microsoft 365 Defender](https://techcommunity.microsoft.com/t5/microsoft-365-defender/easily-find-anomalies-in-incidents-and-alerts/ba-p/2339243)

  Proporciona información mejorada para el contexto en un ataque. Puede ver qué otra alerta desencadenada provocó la alerta actual y todas las entidades y actividades afectadas implicadas en el ataque, incluidos archivos, usuarios y buzones. Consulte [Investigar alertas](/microsoft-365/security/defender/investigate-alerts) para obtener más información.

- [Gráfico de tendencias de incidentes y alertas en el portal de Microsoft 365 Defender](https://techcommunity.microsoft.com/t5/microsoft-365-defender/new-alert-page-for-microsoft-365-defender-incident-detections/ba-p/2350425)

  Determine si hay varias alertas para un único incidente o si su organización está en ataque con varios incidentes diferentes. Consulte [Priorización de incidentes](/microsoft-365/security/defender/incident-queue) para obtener más información.

## <a name="april-2021"></a>Abril de 2021

- Microsoft 365 Defender

  El portal [de Microsoft 365 Defender](https://security.microsoft.com) mejorado ya está disponible. Esta nueva experiencia reúne Defender para punto de conexión, Defender para Office 365, Defender for Identity y mucho más en un único portal. Este es el nuevo hogar para administrar los controles de seguridad. [Ver las novedades](microsoft-365-defender-portal.md).

- [Microsoft 365 Defender informe de análisis de amenazas](threat-analytics.md)

  El análisis de amenazas le ayuda a responder y minimizar el impacto de los ataques activos. También puede obtener información sobre los intentos de ataque bloqueados por Microsoft 365 Defender soluciones y tomar medidas preventivas que mitigan el riesgo de una mayor exposición y aumentan la resistencia. Como parte de la experiencia de seguridad unificada, el análisis de amenazas ahora está disponible para Microsoft Defender para punto de conexión y Microsoft Defender para los titulares de licencias de Office E5.

## <a name="march-2021"></a>Marzo de 2021

- [Tabla CloudAppEvents](advanced-hunting-cloudappevents-table.md)

  Busque información sobre eventos en varias aplicaciones y servicios en la nube cubiertos por Microsoft Defender for Cloud Apps. Esta tabla también incluye información disponible anteriormente en la `AppFileEvents` tabla.
