---
title: Novedades de Protección contra amenazas de Microsoft
description: Enumera las nuevas características y funciones de la protección contra amenazas de Microsoft
keywords: Novedades en protección contra amenazas de Microsoft, GA, disponibilidad general, capacidades disponibles, nueva
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 8b9176fea67583fbdce647b2a3c37cf1d6fde7ed
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2020
ms.locfileid: "48304863"
---
# <a name="whats-new-in-microsoft-threat-protection"></a>Novedades de Protección contra amenazas de Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Las siguientes características están generalmente disponibles (GA) en la última versión de la protección contra amenazas de Microsoft.

Fuente RSS: obtener una notificación cuando se actualice esta página copiando y pegando la siguiente dirección URL en el lector de fuentes:
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+Threat+Protection%22&locale=en-us
```
## <a name="september-2020"></a>Septiembre de 2020
- [Tabla IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) <br> Buscar eventos relacionados con un controlador de dominio local que ejecuta Active Directory (AD). Esta tabla de esquema de [caza avanzado](advanced-hunting-overview.md) cubre una amplia variedad de eventos relacionados con la identidad y del sistema en el controlador de dominio.
- [Función AssignedIPAddresses ()](advanced-hunting-assignedipaddresses-function.md) <br> Use esta función en sus consultas de búsqueda avanzada para obtener rápidamente las direcciones IP más recientes asignadas a un dispositivo o las direcciones IP más recientes de una hora específica.

## <a name="july-2020"></a>Julio de 2020
- [Función FileProfile ()](advanced-hunting-fileprofile-function.md) <br> Use esta función en sus consultas de búsqueda avanzada para enriquecer los resultados con información completa del archivo.
- [Tablas de identidad y aplicación](advanced-hunting-schema-tables.md)<br> Obtenga visibilidad de los eventos de autenticación, las consultas de Active Directory y la actividad relacionada con las aplicaciones con las tablas [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)y [AppFileEvents](advanced-hunting-appfileevents-table.md) en el esquema de búsqueda avanzada.
- [Ir a la caza](advanced-hunting-go-hunt.md)<br> Dinamiza rápidamente desde la investigación de un incidente para inspeccionar un evento específico, un usuario, un dispositivo u otros tipos de entidad en la búsqueda avanzada.

## <a name="june-2020"></a>Junio de 2020
- Fuente de Twitter <br> Obtenga la última investigación sobre seguridad, la inteligencia de amenazas, las noticias de productos y más información en el panel.
- [Tabla de esquema EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) <br> Incorporar información sobre las acciones posteriores a la entrega realizadas en los mensajes de correo electrónico en las consultas de búsqueda avanzada.
- [Inspeccionar registros en la búsqueda avanzada](advanced-hunting-query-results.md#drill-down-from-query-results) <br> Inspeccione rápidamente los registros de los resultados de la consulta con el nuevo panel de detalles.

## <a name="may-2020"></a>Mayo de 2020
- [Detecciones personalizadas](custom-detections-overview.md) <br> Usar consultas de búsqueda avanzada para crear reglas de detección personalizadas que supervisen automáticamente los eventos de seguridad y los Estados del sistema y respondan a ellos.

## <a name="february-2020"></a>Febrero de 2020
- [Incidentes](incidents-overview.md) <br> Sepa exactamente dónde empezó un ataque y otros detalles que le ayudarán a ver el alcance del ataque.
- [Investigación y respuesta automatizadas](mtp-autoir.md) <br> AIR permite al equipo de operaciones de seguridad aumentar drásticamente la capacidad de la organización para abordar las alertas de seguridad y las incidencias.
- [Mejoras avanzadas de búsqueda](advanced-hunting-overview.md) <br> Búsqueda proactiva de amenazas en el área de trabajo moderna con el lenguaje de consulta Kusto y un esquema optimizado para la seguridad.

## <a name="march-2019"></a>Marzo de 2019
- Búsqueda avanzada <br> Página de aterrizaje a varias funcionalidades de búsqueda que le permiten buscar de forma proactiva las amenazas que afectan el correo electrónico y los datos, los dispositivos y las identidades.
- [Puntuación de seguridad de Microsoft](microsoft-secure-score.md) <br> Medida de la postura de seguridad de una organización con un número más alto que indica que se han realizado más acciones de mejora. Seguir las recomendaciones de puntuación de seguridad puede proteger a su organización de las amenazas. 
- [Informes](monitoring-and-reporting.md) <br>  Incluye un host de tarjetas que abarcan una amplia variedad de áreas que los analistas de seguridad y los administradores realizan un seguimiento como parte de sus operaciones cotidianas.
