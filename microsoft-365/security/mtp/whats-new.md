---
title: Novedades de Microsoft 365 Defender
description: Enumera las nuevas características y funcionalidades de Microsoft 365 Defender
keywords: novedades de microsoft threat protection, ga, generally available, capabilities, available, new
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
ms.openlocfilehash: 72c6ec814c5f3317f582cb4bfb21858677fbb7e1
ms.sourcegitcommit: a6b998fef5bdb35ec6726c743a24fea721535fcd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "50509127"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Novedades de Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> ¿Desea experimentar Microsoft 365 Defender? Puede [evaluarlo en un entorno de laboratorio o](https://aka.ms/mtp-trial-lab) ejecutar el proyecto piloto en [producción.](https://aka.ms/m365d-pilotplaybook)
>

Por lo general, las siguientes características están disponibles (GA) en la versión más reciente de Microsoft 365 Defender.

Fuente RSS: recibe una notificación cuando se actualiza esta página copiando y pegando la siguiente dirección URL en el lector de fuentes:
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+365+defender%22&locale=en-us
```

## <a name="february-2021"></a>Febrero de 2021
- (Versión preliminar) El centro [de seguridad mejorado https://security.microsoft.com) de Microsoft 365 (](https://security.microsoft.com) ya está disponible en versión preliminar pública. Esta nueva experiencia lleva a Defender para Endpoint y Defender para Office 365 al centro. [Obtenga más información sobre lo que ha cambiado](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center).

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
- [Investigación y respuesta automatizadas](mtp-autoir.md) <br> AIR permite al equipo de operaciones de seguridad aumentar drásticamente la capacidad de la organización para abordar las alertas de seguridad y las incidencias.
- [Mejoras avanzadas de la búsqueda](advanced-hunting-overview.md) <br> Busca de forma proactiva amenazas en todo el área de trabajo moderna con Kusto Query Language y un esquema optimizado para seguridad.

## <a name="march-2019"></a>Marzo de 2019
- Búsqueda avanzada <br> Página de aterrizaje a varias capacidades de búsqueda que le permiten encontrar proactivamente amenazas que afectan al correo electrónico y a los datos, los dispositivos y las identidades.
- [Puntuación de seguridad de Microsoft](microsoft-secure-score.md) <br> Medida de la posición de seguridad de una organización, con un número más alto que indica más acciones de mejora realizadas. Seguir las recomendaciones de puntuación de seguridad puede proteger su organización de amenazas. 
- [Informes](monitoring-and-reporting.md) <br>  Cuenta con un gran número de tarjetas que cubren una variedad de áreas que los administradores y analistas de seguridad rastrean como parte de sus operaciones diarias.
