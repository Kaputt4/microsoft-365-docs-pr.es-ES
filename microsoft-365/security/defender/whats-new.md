---
title: Novedades de Microsoft 365 Defender
description: Enumera las nuevas características y funcionalidades de Microsoft 365 Defender
keywords: novedades de Microsoft 365 Defender, ga, generalmente disponible, capacidades, disponible, nuevo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: f7c41ff83bffaa6c0e982f4dc0dd3c36e614c0fb
ms.sourcegitcommit: f8fbabf1ec7421cd7ad36aa52b8856fb863cf284
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/28/2021
ms.locfileid: "61620461"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Novedades de Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> ¿Quiere experimentar Microsoft 365 Defender? Puede [evaluarlo en un entorno de laboratorio](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) o [ejecutar el proyecto piloto en producción](m365d-pilot.md?ocid=cx-evalpilot).
>

Las siguientes características están en versión preliminar o generalmente disponibles (GA) en la última versión de Microsoft 365 Defender.

Fuente RSS: para recibir notificaciones cuando esta página se actualice, copie y pegue la dirección URL siguiente en el lector de fuentes: 
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+365+defender%22&locale=en-us
```

Para obtener más información sobre las novedades de otros productos de seguridad de Microsoft Defender, vea:

- [Novedades de Microsoft Defender para Office 365](../office-365-security/whats-new-in-defender-for-office-365.md)
- [Novedades de Microsoft Defender para punto de conexión](../defender-endpoint/whats-new-in-microsoft-defender-endpoint.md)
- [Novedades de Microsoft Defender for Identity](/defender-for-identity/whats-new)
- [Novedades de Microsoft Cloud App Security](/cloud-app-security/release-notes)

## <a name="december-2021"></a>Diciembre de 2021
- (Versión preliminar) `DeviceTvmSoftwareEvidentBeta` tabla se agregó en búsqueda avanzada para permitir ver evidencias de dónde se detectó un software específico en un dispositivo. 
 
## <a name="november-2021"></a>Noviembre de 2021

- (Versión preliminar) La característica de complemento de gobierno de aplicaciones para Defender para Aplicaciones en la nube ya está disponible en Microsoft 365 Defender. El gobierno de aplicaciones proporciona una funcionalidad de administración de directivas y seguridad diseñada para aplicaciones habilitadas para OAuth que tienen acceso a Microsoft 365 a través de las API Graph Microsoft. La gobernanza de aplicaciones ofrece visibilidad, corrección y gobernanza completas sobre cómo estas aplicaciones y sus usuarios acceden, usan y comparten sus datos confidenciales almacenados en Microsoft 365 a través de información útil, y alertas y acciones de directivas automatizadas. [Obtenga más información sobre el gobierno de aplicaciones](/cloud-app-security/app-governance-manage-app-governance).
- (Versión preliminar) La [](advanced-hunting-overview.md) página de búsqueda avanzada ahora tiene compatibilidad con varias fichas, desplazamiento inteligente, pestañas de esquema optimizadas, opciones de edición rápida para consultas, un indicador de uso de recursos de consulta y otras mejoras para que las consultas sean más sencillas y fáciles de ajustar.
- (Versión preliminar) Ahora puede usar el vínculo a la característica [de](advanced-hunting-link-to-incident.md) incidente para incluir eventos o registros de los resultados avanzados de la consulta de búsqueda directamente en un incidente nuevo o existente que está investigando. 
## <a name="october-2021"></a>Octubre de 2021
- (GA) En la búsqueda avanzada, se agregaron más columnas en la [tabla CloudAppEvents.](advanced-hunting-cloudappevents-table.md) Ahora puede incluir `AccountType` , , , , y a sus `IsExternalUser` `IsImpersonated` `IPTags` `IPCategory` `UserAgentTags` consultas. 

## <a name="september-2021"></a>Septiembre de 2021
- (GA) Microsoft Defender para Office 365 datos de eventos está disponible en la API Microsoft 365 Defender streaming de eventos. Puede ver la disponibilidad y el estado de los tipos de eventos en el archivo Microsoft 365 Defender tipos de eventos [en la API de streaming.](supported-event-types.md)
- (GA) Microsoft Defender para los Office 365 disponibles en la búsqueda avanzada ya está disponible en general.
- (Versión preliminar) Asignar incidentes y alertas a cuentas de usuario <br> Puede asignar un incidente y todas las alertas asociadas a él  a una cuenta de  usuario desde **Asignar a:** en el panel Administrar incidente de un incidente o en el panel Administrar alerta de una alerta.


## <a name="august-2021"></a>Agosto de 2021
- (Versión preliminar) Microsoft Defender para obtener Office 365 disponibles en la búsqueda avanzada
<br>Las nuevas columnas de las tablas de correo electrónico pueden proporcionar más información sobre las amenazas basadas en correo electrónico para realizar investigaciones más exhaustivas mediante la búsqueda avanzada. Ahora puede incluir la `AuthenticationDetails` columna en [EmailEvents](./advanced-hunting-emailevents-table.md), `FileSize` en [EmailAttachmentInfo](./advanced-hunting-emailattachmentinfo-table.md)y en las tablas `ThreatTypes` `DetectionMethods` [EmailPostDeliveryEvents.](./advanced-hunting-emailpostdeliveryevents-table.md) 

- (Versión preliminar) Gráfico de incidentes <br>  Una nueva **pestaña Graph** en  la pestaña Resumen de un incidente muestra el ámbito completo del ataque, cómo se extendió el ataque a través de la red con el tiempo, dónde se inició y hasta dónde llegó el atacante.

## <a name="july-2021"></a>Julio de 2021
- [Professional de servicios](https://sip.security.microsoft.com/interoperability/professional_services)<br>Mejore las capacidades de detección, investigación e inteligencia de amenazas de la plataforma con conexiones de partners compatibles.

## <a name="june-2021"></a>Junio de 2021
- (Versión preliminar) [Ver informes por etiquetas de amenazas](threat-analytics.md#view-reports-per-threat-tags)<br> Las etiquetas de amenazas le ayudan a centrarse en categorías de amenazas específicas y revisar los informes más relevantes.
- (Versión preliminar) [API de streaming](../defender-endpoint/raw-data-export.md)<br> Microsoft 365 Defender permite transmitir todos los eventos disponibles a través de la búsqueda avanzada a un centro de eventos o una cuenta de Azure Storage.
- (Versión preliminar) [Tomar medidas en la búsqueda avanzada](advanced-hunting-take-action.md)<br> Contienen rápidamente amenazas o abordan activos en peligro que se encuentran en la [búsqueda avanzada.](advanced-hunting-overview.md)
- (Versión preliminar) [Referencia de esquema en el portal](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)<br> Obtenga información sobre tablas de esquema de búsqueda avanzada directamente en el centro de seguridad. Además de las descripciones de tabla y columna, esta referencia incluye tipos de eventos admitidos `ActionType` (valores) y consultas de ejemplo.
- (Versión preliminar) [Función DeviceFromIP()](advanced-hunting-devicefromip-function.md)<br> Obtenga información sobre los dispositivos a los que se ha asignado una dirección IP específica o direcciones en un intervalo de tiempo determinado.
    

## <a name="may-2021"></a>Mayo de 2021

- [Nueva página de alerta en el Microsoft 365 Defender de alertas](https://techcommunity.microsoft.com/t5/microsoft-365-defender/easily-find-anomalies-in-incidents-and-alerts/ba-p/2339243) <br> Proporciona información mejorada para el contexto en un ataque. Puede ver qué otra alerta desencadenada causó la alerta actual y todas las entidades y actividades afectadas implicadas en el ataque, incluidos los archivos, los usuarios y los buzones. Consulte [Investigar alertas](/microsoft-365/security/defender/investigate-alerts) para obtener más información.
- [Gráfico de tendencias para incidentes y alertas en el portal Microsoft 365 Defender web](https://techcommunity.microsoft.com/t5/microsoft-365-defender/new-alert-page-for-microsoft-365-defender-incident-detections/ba-p/2350425) <br> Determine si hay varias alertas para un solo incidente o si su organización está siendo atacada con varios incidentes diferentes. Consulte [Priorizar incidentes](/microsoft-365/security/defender/incident-queue) para obtener más información.


## <a name="april-2021"></a>Abril de 2021
- Microsoft 365 Defender<br> El portal [de Microsoft 365 Defender](https://security.microsoft.com) mejorado ya está disponible. Esta nueva experiencia reúne Defender for Endpoint, Defender for Office 365, Defender for Identity y mucho más en un único portal. Este es el nuevo hogar para administrar los controles de seguridad. [Ver las novedades](./microsoft-365-defender.md#the-microsoft-365-defender-portal).

- [Microsoft 365 Defender análisis de amenazas](threat-analytics.md)<br>
 El análisis de amenazas te ayuda a responder y minimizar el impacto de los ataques activos. También puedes obtener información sobre los intentos de ataque bloqueados por Microsoft 365 Defender soluciones y realizar acciones preventivas que mitiguen el riesgo de exposición adicional y aumenten la resistencia. Como parte de la experiencia de seguridad unificada, el análisis de amenazas ahora está disponible para Microsoft Defender para Endpoint y Microsoft Defender para los Office de licencias de E5.

## <a name="march-2021"></a>Marzo 2021
- [Tabla CloudAppEvents](advanced-hunting-cloudappevents-table.md) <br>Encuentre información sobre eventos en varias aplicaciones y servicios en la nube cubiertos por Microsoft Cloud App Security. Esta tabla también incluye información disponible anteriormente en la `AppFileEvents` tabla.
## <a name="february-2021"></a>Febrero de 2021
- (Versión preliminar) El portal [de Microsoft 365 Defender https://security.microsoft.com) mejorado (](https://security.microsoft.com) ahora está disponible en versión preliminar pública. Esta nueva experiencia lleva a Defender for Endpoint and Defender para Office 365 al centro. [Más información sobre los cambios](microsoft-365-defender.md#the-microsoft-365-defender-portal).
- **[(Versión preliminar) Microsoft 365 Defender](api-overview.md)** API: las API de Microsoft 365 Defender de nivel superior le permitirán automatizar los flujos de trabajo en función de las tablas de búsqueda avanzada y de incidentes compartidos. 
