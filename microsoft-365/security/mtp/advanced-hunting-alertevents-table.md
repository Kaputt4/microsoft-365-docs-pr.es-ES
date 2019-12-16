---
title: Tabla EmailEvents en el esquema de búsqueda avanzada
description: Obtenga más información sobre los eventos de generación de alertas en la tabla AlertEvents en el esquema de búsqueda avanzada
keywords: Búsqueda, búsqueda avanzada, de amenazas, de ciberamenazas, consulta, telemetría, referencia del esquema, kusto, tabla, columna, tipo de datos, descripción, alertas, alerta, gravedad, categoría
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 4d83b659a98c56cc59e88f9777aa73ca2e25b745
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911642"
---
# <a name="alertevents"></a>AlertEvents

**Se aplica a:**
- Protección contra amenazas de Microsoft

[!include[Prerelease information](prerelease.md)]

El esquema en la `AlertEvents`tabla de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre las alertas procesadas por la ATP de Microsoft Defender. Use esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener información sobre otras tablas en el esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `AlertId` | string | Identificador único de alerta. |
| `EventTime` | datetime | Fecha y hora en que se registró el evento. |
| `MachineId` | cadena | Identificador único para la máquina del servicio |
| `ComputerName` | cadena | Nombre de dominio completo (FQDN, por sus siglas en inglés) de la máquina |
| `Severity` | cadena | El indicador de amenazas indica el posible impacto (alto, medio o bajo) de las actividades de vulneración identificadas por la alerta. |
| `Category` | cadena | Tipo de indicador de amenazas o actividad de vulneración identificada por la alerta |
| `Title` | cadena | Título de la alerta. |
| `FileName` | cadena | Nombre del archivo donde se aplicó la acción registrada |
| `SHA1` | cadena | SHA-1 del archivo donde fue aplicada la acción registrada |
| `RemoteUrl` | cadena | La dirección URL o el nombre de dominio completo (FQDN, según sus siglas en inglés) en el cual se ha estado conectado. |
| `RemoteIP` | cadena | Dirección IP a la que se ha conectado |
| `ReportId` | largo | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe utilizarse conjuntamente con las columnas ComputerName y EventTime. |
| `Table` | cadena | Tabla con el contenido detallado del evento |

## <a name="related-topics"></a>Temas relacionados
- [Búsqueda proactiva de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Búsqueda de amenazas en dispositivos y mensajes de correo electrónico](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
