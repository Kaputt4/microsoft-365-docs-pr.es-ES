---
title: Tabla DeviceEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre antivirus, firewall y otros tipos de eventos en la tabla eventos de dispositivos varios (DeviceEvents) del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, eventos de seguridad, antivirus, firewall, protección contra vulnerabilidades de seguridad, MiscEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1e67da3a5d93c5e8c86afd755c882f3f0459aab0
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499197"
---
# <a name="deviceevents"></a>DeviceEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)


> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

La tabla o eventos de dispositivos varios del esquema de búsqueda avanzada contiene información sobre varios tipos de eventos, incluidos los eventos desencadenados por controles de seguridad, como Antivirus de Microsoft Defender y `DeviceEvents` protección contra vulnerabilidades de seguridad. [](advanced-hunting-overview.md) Use esta referencia para crear consultas que devuelvan información de la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea la referencia de esquema [de búsqueda avanzada](advanced-hunting-schema-reference.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `DeviceId` | cadena | Identificador único del dispositivo en el servicio |
| `DeviceName` | cadena | Nombre de dominio completo (FQDN) del dispositivo |
| `ActionType` | cadena | Tipo de actividad que desencadenó el evento |
| `FileName` | cadena | Nombre del archivo donde se aplicó la acción registrada |
| `FolderPath` | cadena | Carpeta que contiene el archivo al que se aplicó la acción grabada |
| `SHA1` | cadena | SHA-1 del archivo donde fue aplicada la acción registrada |
| `SHA256` | cadena | SHA-256 del archivo donde se aplicó la acción registrada. Este campo normalmente no está rellenado: use la columna SHA1 cuando esté disponible |
| `MD5` | cadena | Hash MD5 del archivo al que se aplicó la acción grabada |
| `AccountDomain` | cadena | Dominio de la cuenta |
| `AccountName` |cadena | Nombre de usuario de la cuenta |
| `AccountSid` | cadena | Identificador de seguridad (SID) de la cuenta |
| `RemoteUrl` | cadena | La dirección URL o el nombre de dominio completo (FQDN, según sus siglas en inglés) en el cual se ha estado conectado. |
| `RemoteDeviceName` | cadena | Nombre del dispositivo que realizó una operación remota en el dispositivo afectado. Según el evento notificado, este nombre podría ser un nombre de dominio completo (FQDN), un nombre NetBIOS o un nombre de host sin información de dominio |
| `ProcessId` | Entero | Identificador de proceso (PID) del proceso recién creado |
| `ProcessCommandLine` | cadena | Línea de comandos usada para crear el nuevo proceso |
| `ProcessCreationTime` | datetime | Fecha y hora en que se creó el proceso |
| `ProcessTokenElevation` | cadena | Tipo de token que indica la presencia o ausencia de elevación de privilegios del Control de acceso de usuario (UAC) aplicada al proceso recién creado |
| `LogonId` | cadena | Identificador de una sesión de inicio de sesión. Este identificador es único en el mismo dispositivo solo entre reinicios |
| `RegistryKey` | cadena | Clave del Registro a la que se aplicó la acción grabada |
| `RegistryValueName` | cadena | Nombre del valor del Registro al que se aplicó la acción grabada |
| `RegistryValueData` | cadena | Datos del valor del Registro al que se aplicó la acción grabada |
| `RemoteIP` | cadena | Dirección IP a la que se ha conectado |
| `RemotePort` | Entero | Puerto TCP en el dispositivo remoto al que se estaba conectando |
| `LocalIP` | cadena | Dirección IP asignada al dispositivo local usado durante la comunicación |
| `LocalPort` | Entero | Puerto TCP en el dispositivo local usado durante la comunicación |
| `FileOriginUrl` | cadena | DIRECCIÓN URL desde la que se descargó el archivo |
| `FileOriginIP` | cadena | Dirección IP desde la que se descargó el archivo |
| `AdditionalFields` | cadena | Información adicional sobre el evento en formato de matriz JSON |
| `InitiatingProcessSHA1` | cadena | SHA-1 del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessSHA256` | cadena | SHA-256 del proceso (archivo de imagen) que inició el evento. Este campo normalmente no está rellenado: use la columna SHA1 cuando esté disponible |
| `InitiatingProcessFileName` | cadena | Nombre del proceso que inició el evento |
| `InitiatingProcessFolderPath` | cadena | Carpeta que contiene el proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessId` | Entero | Identificador de proceso (PID) del proceso que inició el evento |
| `InitiatingProcessCommandLine` | cadena | Línea de comandos usada para ejecutar el proceso que inició el evento |
| `InitiatingProcessCreationTime` | datetime | Fecha y hora en que se inició el proceso que inició el evento |
| `InitiatingProcessParentId` | Entero | Identificador de proceso (PID) del proceso primario que generó el proceso responsable del evento |
| `InitiatingProcessParentFileName` | cadena | Nombre del proceso primario que generó el proceso responsable del evento |
| `InitiatingProcessParentCreationTime` | datetime | Fecha y hora en que se inició el elemento primario del proceso responsable del evento |
| `InitiatingProcessMD5` | cadena | Hash MD5 del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessAccountDomain` | cadena | Dominio de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountName` | cadena | Nombre de usuario de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountSid` | cadena | Identificador de seguridad (SID) de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessLogonId` | cadena | Identificador de una sesión de inicio de sesión del proceso que inició el evento. Este identificador es único en el mismo dispositivo solo entre reinicios |
| `ReportId` | largo | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las `DeviceName` columnas y `Timestamp` |
| `AppGuardContainerId` | cadena | Identificador del contenedor virtualizado usado por Application Guard para aislar la actividad del explorador |


## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Entender el esquema](advanced-hunting-schema-reference.md)
