---
title: Tabla DeviceEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre antivirus, Firewall y otros tipos de eventos en la tabla eventos de dispositivos diversos (DeviceEvents) del esquema de búsqueda avanzada.
keywords: caza avanzado, cazar amenazas, búsqueda de amenazas en el ciberespacio, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, eventos de seguridad, antivirus, firewall, protección contra ataques, DeviceEvents
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
ms.openlocfilehash: aec5751cf400f94abaf259aaa5fe2238b4b91311
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2019
ms.locfileid: "40809406"
---
# <a name="deviceevents"></a>DeviceEvents

**Se aplica a:**
- Protección contra amenazas de Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

La tabla o `DeviceEvents` los eventos de dispositivos variados del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contienen información sobre varios tipos de eventos, incluidos los eventos desencadenados por controles de seguridad, como antivirus de Windows Defender y protección contra la vulnerabilidad. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).


| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `DeviceId` | string | Identificador único para el equipo en servicio |
| `DeviceName` | cadena | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo |
| `ActionType` | cadena | Tipo de actividad que ha desencadenado el evento |
| `FileName` | cadena | Nombre del archivo donde se aplicó la acción registrada |
| `FolderPath` | cadena | Carpeta que contiene el archivo al que se aplicó la acción grabada |
| `SHA1` | cadena | SHA-1 del archivo donde fue aplicada la acción registrada |
| `SHA256` | cadena | SHA-256 del archivo donde se aplicó la acción registrada. Este campo no suele rellenarse; use la columna SHA1 cuando esté disponible |
| `MD5` | cadena | Hash MD5 del archivo al que se aplicó la acción grabada |
| `AccountDomain` | cadena | Dominio de la cuenta |
| `AccountName` | cadena | Nombre de usuario de la cuenta |
| `AccountSid` | cadena | Identificador de seguridad (SID) de la cuenta |
| `RemoteUrl` | cadena | La dirección URL o el nombre de dominio completo (FQDN, según sus siglas en inglés) en el cual se ha estado conectado. |
| `RemoteDeviceName` | cadena | Nombre del equipo que llevó a cabo una operación remota en el equipo afectado. Según el evento del que se informa, este nombre puede ser un nombre de dominio completo (FQDN), un nombre NetBIOS o un nombre de host sin información del dominio |
| `ProcessId` | entero | IDENTIFICADOR de proceso (PID) del proceso recién creado |
| `ProcessCommandLine` | cadena | Línea de comandos usada para crear el nuevo proceso |
| `ProcessCreationTime` | datetime | Fecha y hora de creación del proceso |
| `ProcessTokenElevation` | cadena | Tipo de token que indica la presencia o ausencia de la elevación de privilegios de control de acceso de usuario (UAC) que se aplica al proceso recién creado. |
| `LogonId` | cadena | Identificador de una sesión de inicio de sesión. Este identificador es único en el mismo equipo solo entre reinicios |
| `RegistryKey` | cadena | Clave del registro a la que se aplicó la acción grabada |
| `RegistryValueName` | cadena | Nombre del valor del registro al que se aplicó la acción grabada |
| `RegistryValueData` | cadena | Datos del valor del registro al que se aplicó la acción grabada |
| `RemoteIP` | cadena | Dirección IP a la que se ha conectado |
| `RemotePort` | entero | Puerto TCP del dispositivo remoto al que se estaba conectando |
| `LocalIP` | cadena | Dirección IP asignada al equipo local usada durante la comunicación |
| `LocalPort` | entero | Puerto TCP del equipo local usado durante la comunicación |
| `FileOriginUrl` | cadena | Dirección URL desde la que se descargó el archivo |
| `FileOriginIP` | cadena | Dirección IP desde la que se descargó el archivo |
| `AdditionalFields` | cadena | Información adicional sobre el evento en el formato de matriz JSON |
| `InitiatingProcessSHA1` | cadena | SHA-1 del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessSHA256` | cadena | SHA-256 del proceso (archivo de imagen) que inició el evento. Este campo no suele rellenarse; use la columna SHA1 cuando esté disponible |
| `InitiatingProcessFileName` | cadena | Nombre del proceso que inició el evento |
| `InitiatingProcessFolderPath` | cadena | Carpeta que contiene el proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessId` | entero | IDENTIFICADOR de proceso (PID) del proceso que inició el evento |
| `InitiatingProcessCommandLine` | cadena | Línea de comandos que se usa para ejecutar el proceso que inició el evento |
| `InitiatingProcessCreationTime` | datetime | Fecha y hora en que se inició el proceso que inició el evento |
| `InitiatingProcessParentId` | entero | IDENTIFICADOR de proceso (PID) del proceso primario que generó el proceso responsable del evento |
| `InitiatingProcessParentFileName` | cadena | Nombre del proceso primario que generó el proceso responsable del evento |
| `InitiatingProcessParentCreationTime` | datetime | Fecha y hora en que se inició el primario del proceso responsable del evento |
| `InitiatingProcessMD5` | cadena | Hash MD5 del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessAccountDomain` | cadena | Dominio de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountName` | cadena | Nombre de usuario de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountSid` | cadena | Identificador de seguridad (SID) de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessLogonId` | cadena | Identificador de una sesión de inicio del proceso que inició el evento. Este identificador es único en el mismo equipo solo entre reinicios |
| `ReportId` | largo | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y timestamp. |
| `AppGuardContainerId` | cadena | Identificador del contenedor virtualizado que usa la protección de aplicaciones para aislar la actividad del explorador |

## <a name="related-topics"></a>Temas relacionados
- [Búsqueda proactiva de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Búsqueda de amenazas en dispositivos y mensajes de correo electrónico](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
