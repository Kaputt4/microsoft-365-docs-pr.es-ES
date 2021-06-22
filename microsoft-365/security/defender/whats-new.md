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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 582116047900fc5f28d5580398cf5c065e6a3e23
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2021
ms.locfileid: "53053028"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Novedades de Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> ¿Quiere experimentar Microsoft 365 Defender? Puede [evaluarlo en un entorno de pruebas](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) o bien [ejecutar el proyecto piloto en producción](m365d-pilot.md?ocid=cx-evalpilot).
>

Por lo general, las siguientes características están disponibles (GA) en la última versión de Microsoft 365 Defender.

Fuente RSS: recibe una notificación cuando se actualiza esta página copiando y pegando la siguiente dirección URL en el lector de fuentes:
```http
/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+365+defender%22&locale=en-us
```

## <a name="april-2021"></a>Abril de 2021
- Microsoft 365 Defender<br> El portal [de Microsoft 365 Defender](https://security.microsoft.com) mejorado ya está disponible. Esta nueva experiencia reúne Defender for Endpoint, Defender for Office 365, Defender for Identity y mucho más en un único portal. Este es el nuevo hogar para administrar los controles de seguridad. [Ver las novedades](./overview-security-center.md).

- [Microsoft 365 Defender análisis de amenazas](threat-analytics.md)<br>
 El análisis de amenazas te ayuda a responder y minimizar el impacto de los ataques activos. También puedes obtener información sobre los intentos de ataque bloqueados por Microsoft 365 Defender soluciones y realizar acciones preventivas que mitiguen el riesgo de exposición adicional y aumenten la resistencia. Como parte de la experiencia de seguridad unificada, el análisis de amenazas ahora está disponible para Microsoft Defender para Endpoint y Microsoft Defender para los Office de licencias de E5.

## <a name="march-2021"></a>Marzo 2021
- [Tabla CloudAppEvents](advanced-hunting-cloudappevents-table.md) <br>Encuentre información sobre eventos en varias aplicaciones y servicios en la nube cubiertos por Microsoft Cloud App Security. Esta tabla también incluye información disponible anteriormente en `AppFileEvents` .
## <a name="february-2021"></a>Febrero de 2021
- (Versión preliminar) El centro [de Microsoft 365 de https://security.microsoft.com) seguridad mejorada (](https://security.microsoft.com) ahora está disponible en versión preliminar pública. Esta nueva experiencia lleva a Defender for Endpoint and Defender para Office 365 al centro. [Más información sobre los cambios](./overview-security-center.md).

## <a name="september-2020"></a>Septiembre de 2020
- [Tabla IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) <br> Buscar eventos que impliquen un controlador de dominio local que ejecute Active Directory (AD). Esta [tabla de esquema](advanced-hunting-overview.md) de búsqueda avanzada abarca una serie de eventos relacionados con la identidad y eventos del sistema en el controlador de dominio.
- [Función AssignedIPAddresses()](advanced-hunting-assignedipaddresses-function.md) <br> Usa esta función en las consultas de búsqueda avanzadas para obtener rápidamente las direcciones IP más recientes asignadas a un dispositivo o las direcciones IP más recientes de un momento determinado.

## <a name="july-2020"></a>Julio de 2020
- [Función FileProfile()](advanced-hunting-fileprofile-function.md) <br> Use esta función en las consultas de búsqueda avanzadas para enriquecer los resultados con información completa del archivo.
- [Tablas de identidades y aplicaciones](advanced-hunting-schema-tables.md)<br> Obtenga visibilidad de eventos de autenticación, consultas de Active Directory y actividad relacionada con la aplicación con las tablas [IdentityLogonEvents,](advanced-hunting-identitylogonevents-table.md) [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)y [AppFileEvents](advanced-hunting-appfileevents-table.md) en el esquema de búsqueda avanzado.
- [Ir a la caza](advanced-hunting-go-hunt.md)<br> Pivote rápidamente desde investigar un incidente hasta inspeccionar un evento específico, un usuario, un dispositivo u otros tipos de entidad en la búsqueda avanzada.

## <a name="june-2020"></a>Junio de 2020
- Fuente de Twitter <br> Obtén las últimas investigaciones de seguridad, inteligencia de amenazas, noticias de productos y mucho más: directamente dentro del panel.
- [Tabla de esquema EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) <br> Incorpore información sobre las acciones posteriores a la entrega realizadas en los mensajes de correo electrónico en las consultas avanzadas de búsqueda.
- [Inspeccionar registros en búsqueda avanzada](advanced-hunting-query-results.md#drill-down-from-query-results) <br> Inspeccione rápidamente los registros de los resultados de la consulta con el nuevo panel de detalles.

## <a name="may-2020"></a>Mayo de 2020
- [Detecciones personalizadas](custom-detections-overview.md) <br> Use consultas de búsqueda avanzadas para crear reglas de detección personalizadas que supervisen y respondan automáticamente a los eventos de seguridad y los estados del sistema.

## <a name="february-2020"></a>Febrero de 2020
- [Incidentes](incidents-overview.md) <br> Sepa exactamente dónde se inició un ataque y otros detalles que le ayudarán a ver el alcance del ataque.
- [Investigación y respuesta automatizadas](m365d-autoir.md) <br> AIR permite al equipo de operaciones de seguridad aumentar drásticamente la capacidad de la organización para abordar las alertas de seguridad y las incidencias.
- [Mejoras avanzadas de la búsqueda](advanced-hunting-overview.md) <br> Busca de forma proactiva amenazas en todo el área de trabajo moderna con Kusto Query Language y un esquema optimizado para seguridad.

## <a name="march-2019"></a>Marzo de 2019
- Búsqueda avanzada <br> Página de aterrizaje a varias capacidades de búsqueda que le permiten encontrar proactivamente amenazas que afectan al correo electrónico y a los datos, los dispositivos y las identidades.
- [Puntuación de seguridad de Microsoft](microsoft-secure-score.md) <br> Medida de la posición de seguridad de una organización, con un número más alto que indica más acciones de mejora realizadas. Seguir las recomendaciones de la puntuación de seguridad puede proteger a su organización de amenazas. 
- [Informes](overview-security-center.md) <br>  Cuenta con un gran número de tarjetas que cubren una variedad de áreas que los administradores y analistas de seguridad rastrean como parte de sus operaciones diarias.
