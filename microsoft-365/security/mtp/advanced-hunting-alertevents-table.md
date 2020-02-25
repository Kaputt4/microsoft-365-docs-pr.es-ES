---
title: Tabla EmailEvents en el esquema de búsqueda avanzada
description: Obtenga más información sobre los eventos de generación de alertas en la tabla AlertEvents en el esquema de búsqueda avanzada
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, alertevents, alerta, gravedad, categoría
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 9f341705d8247183b7e8a5271231c82faf8b386a
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235099"
---
# <a name="alertevents"></a>AlertEvents

**Se aplica a:**
- Protección contra amenazas de Microsoft



El esquema en la `AlertEvents`tabla de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre las alertas procesadas por la ATP de Microsoft Defender. Use esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener información sobre otras tablas en el esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `AlertId` | string | Identificador único de alerta. |
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `DeviceId` | cadena | Identificador único para la máquina del servicio |
| `DeviceName` | cadena | Nombre de dominio completo (FQDN, por sus siglas en inglés) de la máquina |
| `Severity` | cadena | El indicador de amenazas indica el posible impacto (alto, medio o bajo) de las actividades de vulneración identificadas por la alerta. |
| `Category` | cadena | Tipo de indicador de amenazas o actividad de vulneración identificada por la alerta |
| `Title` | cadena | Título de la alerta. |
| `FileName` | cadena | Nombre del archivo donde se aplicó la acción registrada |
| `SHA1` | cadena | SHA-1 del archivo donde fue aplicada la acción registrada |
| `RemoteUrl` | cadena | La dirección URL o el nombre de dominio completo (FQDN, según sus siglas en inglés) en el cual se ha estado conectado. |
| `RemoteIP` | cadena | Dirección IP a la que se ha conectado |
| `ReportId` | largo | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y timestamp. |
| `Table` | cadena | Tabla con el contenido detallado del evento |

## <a name="related-topics"></a>Temas relacionados
- [Búsqueda proactiva de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Búsqueda de amenazas en dispositivos y mensajes de correo electrónico](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
