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
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 49a0b608caa6d759f58889e6f831f84d2b4b90d3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072424"
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
| `DeviceName` | string | Nombre de dominio completo (FQDN) del dispositivo |
| `ActionType` | string | Tipo de actividad que desencadenó el evento |
| `FileName` | cadena | Nombre del archivo donde se aplicó la acción registrada |
| `FolderPath` | cadena | Carpeta que contiene el archivo al que se aplicó la acción grabada |
| `SHA1` | cadena | SHA-1 del archivo donde fue aplicada la acción registrada |
| `SHA256` | cadena | SHA-256 del archivo donde se aplicó la acción registrada. Este campo normalmente no está rellenado: use la columna SHA1 cuando esté disponible |
| `MD5` | string | Hash MD5 del archivo al que se aplicó la acción grabada |
| `AccountDomain` | string | Dominio de la cuenta |
| `AccountName` |string | Nombre de usuario de la cuenta |
| `AccountSid` | string | Identificador de seguridad (SID) de la cuenta |
| `RemoteUrl` | cadena | La dirección URL o el nombre de dominio completo (FQDN, según sus siglas en inglés) en el cual se ha estado conectado. |
| `RemoteDeviceName` | cadena | Nombre del dispositivo que realizó una operación remota en el dispositivo afectado. Según el evento notificado, este nombre podría ser un nombre de dominio completo (FQDN), un nombre NetBIOS o un nombre de host sin información de dominio |
| `ProcessId` | Entero | Identificador de proceso (PID) del proceso recién creado |
| `ProcessCommandLine` | string | Línea de comandos usada para crear el nuevo proceso |
| `ProcessCreationTime` | datetime | Fecha y hora en que se creó el proceso |
| `ProcessTokenElevation` | string | Tipo de token que indica la presencia o ausencia de elevación de privilegios del Control de acceso de usuario (UAC) aplicada al proceso recién creado |
| `LogonId` | string | Identificador de una sesión de inicio de sesión. Este identificador es único en el mismo dispositivo solo entre reinicios |
| `RegistryKey` | string | Clave del Registro a la que se aplicó la acción grabada |
| `RegistryValueName` | string | Nombre del valor del Registro al que se aplicó la acción grabada |
| `RegistryValueData` | string | Datos del valor del Registro al que se aplicó la acción grabada |
| `RemoteIP` | cadena | Dirección IP a la que se ha conectado |
| `RemotePort` | Entero | Puerto TCP en el dispositivo remoto al que se estaba conectando |
| `LocalIP` | string | Dirección IP asignada al dispositivo local usado durante la comunicación |
| `LocalPort` | Entero | Puerto TCP en el dispositivo local usado durante la comunicación |
| `FileOriginUrl` | string | DIRECCIÓN URL desde la que se descargó el archivo |
| `FileOriginIP` | string | Dirección IP desde la que se descargó el archivo |
| `AdditionalFields` | string | Información adicional sobre el evento en formato de matriz JSON |
| `InitiatingProcessSHA1` | string | SHA-1 del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessSHA256` | string | SHA-256 del proceso (archivo de imagen) que inició el evento. Este campo normalmente no está rellenado: use la columna SHA1 cuando esté disponible |
| `InitiatingProcessFileName` | string | Nombre del proceso que inició el evento |
| `InitiatingProcessFolderPath` | string | Carpeta que contiene el proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessId` | Entero | Identificador de proceso (PID) del proceso que inició el evento |
| `InitiatingProcessCommandLine` | string | Línea de comandos usada para ejecutar el proceso que inició el evento |
| `InitiatingProcessCreationTime` | datetime | Fecha y hora en que se inició el proceso que inició el evento |
| `InitiatingProcessParentId` | Entero | Identificador de proceso (PID) del proceso primario que generó el proceso responsable del evento |
| `InitiatingProcessParentFileName` | string | Nombre del proceso primario que generó el proceso responsable del evento |
| `InitiatingProcessParentCreationTime` | datetime | Fecha y hora en que se inició el elemento primario del proceso responsable del evento |
| `InitiatingProcessMD5` | string | Hash MD5 del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessAccountDomain` | string | Dominio de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountName` | string | Nombre de usuario de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountSid` | string | Identificador de seguridad (SID) de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessLogonId` | string | Identificador de una sesión de inicio de sesión del proceso que inició el evento. Este identificador es único en el mismo dispositivo solo entre reinicios |
| `ReportId` | largo | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las `DeviceName` columnas y `Timestamp` |
| `AppGuardContainerId` | string | Identificador del contenedor virtualizado usado por Application Guard para aislar la actividad del explorador |


## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Entender el esquema](advanced-hunting-schema-reference.md)
