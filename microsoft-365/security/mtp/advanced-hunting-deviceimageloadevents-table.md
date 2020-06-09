---
title: Tabla DeviceImageLoadEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de carga de DLL en la tabla DeviceImageLoadEvents del esquema de búsqueda avanzada.
keywords: caza avanzado, cazar amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, imageloadevents, DeviceImageLoadEvents, carga de DLL, biblioteca, archivo de imagen
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
ms.openlocfilehash: 98aac3d231e2c8630cb4721ee8012054ab90feef
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617145"
---
# <a name="deviceimageloadevents"></a>DeviceImageLoadEvents

**Se aplica a:**
- Protección contra amenazas de Microsoft



La `DeviceImageLoadEvents` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre los eventos de carga de dll. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `DeviceId` | string | Identificador único para el equipo en servicio |
| `DeviceName` | string | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo |
| `ActionType` | string | Tipo de actividad que ha desencadenado el evento |
| `FileName` | string | Nombre del archivo donde se aplicó la acción registrada |
| `FolderPath` | string | Carpeta que contiene el archivo al que se aplicó la acción grabada |
| `SHA1` | string | SHA-1 del archivo donde fue aplicada la acción registrada |
| `SHA256` | cadena | SHA-256 del archivo donde se aplicó la acción registrada. Este campo no suele estar rellenado; use la columna SHA1 cuando se encuentre disponible. |
| `MD5` | cadena | Hash MD5 del archivo al que se aplicó la acción grabada |
| `InitiatingProcessAccountDomain` | string | Dominio de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountName` | string | Nombre de usuario de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountSid` | string | Identificador de seguridad (SID) de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessIntegrityLevel` | string | Nivel de integridad del proceso que inició el evento. Windows asigna niveles de integridad a los procesos en función de ciertas características, como si se iniciaron desde una descarga de Internet. Estos niveles de integridad influyen en los permisos para recursos |
| `InitiatingProcessTokenElevation` | string | Tipo de token que indica la presencia o ausencia de la elevación de privilegios de control de acceso de usuario (UAC) que se aplica al proceso que inició el evento |
| `InitiatingProcessSHA1` | string | SHA-1 del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessSHA256` | string | SHA-256 del proceso (archivo de imagen) que inició el evento. Este campo no suele estar rellenado; use la columna SHA1 cuando se encuentre disponible. |
| `InitiatingProcessMD5` | cadena | Hash MD5 del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessFileName` | string | Nombre del proceso que inició el evento |
| `InitiatingProcessId` | Entero | IDENTIFICADOR de proceso (PID) del proceso que inició el evento |
| `InitiatingProcessCommandLine` | string | Línea de comandos que se usa para ejecutar el proceso que inició el evento |
| `InitiatingProcessCreationTime` | datetime | Fecha y hora en que se inició el proceso que inició el evento |
| `InitiatingProcessFolderPath` | string | Carpeta que contiene el proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessParentId` | Entero | IDENTIFICADOR de proceso (PID) del proceso primario que generó el proceso responsable del evento |
| `InitiatingProcessParentFileName` | string | Nombre del proceso primario que generó el proceso responsable del evento |
| `InitiatingProcessParentCreationTime` | datetime | Fecha y hora en que se inició el primario del proceso responsable del evento |
| `ReportId` | largo | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y timestamp. |
| `AppGuardContainerId` | string | Identificador del contenedor virtualizado que usa la protección de aplicaciones para aislar la actividad del explorador |

## <a name="related-topics"></a>Temas relacionados
- [Búsqueda proactiva de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Búsqueda de amenazas en dispositivos y mensajes de correo electrónico](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
