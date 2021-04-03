---
title: Tabla DeviceProcessEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de generación o creación de procesos en la tabla DeviceProcessEvents del esquema de búsqueda avanzado
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, deviceprocessevents, id. de proceso, línea de comandos, ProcessCreationEvents
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
ms.openlocfilehash: 4795809b7b24f09e52cb2c48a035dd7925fa136f
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500723"
---
# <a name="deviceprocessevents"></a>DeviceProcessEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

La `DeviceProcessEvents` tabla del esquema de [búsqueda](advanced-hunting-overview.md) avanzada contiene información sobre la creación de procesos y los eventos relacionados. Use esta referencia para crear consultas que devuelvan información de la tabla.

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
| `SHA256` | cadena | SHA-256 del archivo donde se aplicó la acción registrada. Este campo normalmente no se rellena: use la columna SHA1 cuando esté disponible. |
| `MD5` | cadena | Hash MD5 del archivo al que se aplicó la acción grabada |
| `ProcessId` | Entero | Identificador de proceso (PID) del proceso recién creado |
| `ProcessCommandLine` | cadena | Línea de comandos usada para crear el nuevo proceso |
| `ProcessIntegrityLevel` | cadena | Nivel de integridad del proceso recién creado. Windows asigna niveles de integridad a procesos basados en determinadas características, como si se iniciaron desde una descarga de Internet. Estos niveles de integridad influyen en los permisos de los recursos |
| `ProcessTokenElevation` | cadena | Tipo de token que indica la presencia o ausencia de elevación de privilegios del Control de acceso de usuario (UAC) aplicada al proceso recién creado |
| `ProcessCreationTime` | datetime | Fecha y hora en que se creó el proceso |
| `AccountDomain` | cadena | Dominio de la cuenta |
| `AccountName` | cadena | Nombre de usuario de la cuenta |
| `AccountSid` | cadena | Identificador de seguridad (SID) de la cuenta |
| `LogonId` | cadena | Identificador de una sesión de inicio de sesión. Este identificador es único en el mismo dispositivo solo entre reinicios |
| `InitiatingProcessAccountDomain` | cadena | Dominio de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountName` | cadena | Nombre de usuario de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountSid` | cadena | Identificador de seguridad (SID) de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessLogonId` | cadena | Identificador de una sesión de inicio de sesión del proceso que inició el evento. Este identificador es único en el mismo dispositivo solo entre reinicios. |
| `InitiatingProcessIntegrityLevel` | cadena | Nivel de integridad del proceso que inició el evento. Windows asigna niveles de integridad a procesos basados en determinadas características, como si se iniciaron desde una descarga de Internet. Estos niveles de integridad influyen en los permisos de los recursos |
| `InitiatingProcessTokenElevation` | cadena | Tipo de token que indica la presencia o ausencia de elevación de privilegios del Control de acceso de usuario (UAC) aplicada al proceso que inició el evento |
| `InitiatingProcessSHA1` | cadena | SHA-1 del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessSHA256` | cadena | SHA-256 del proceso (archivo de imagen) que inició el evento. Este campo normalmente no está rellenado: use la columna SHA1 cuando esté disponible |
| `InitiatingProcessMD5` | cadena | Hash MD5 del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessFileName` | cadena | Nombre del proceso que inició el evento |
| `InitiatingProcessId` | Entero | Identificador de proceso (PID) del proceso que inició el evento |
| `InitiatingProcessCommandLine` | cadena | Línea de comandos usada para ejecutar el proceso que inició el evento |
| `InitiatingProcessCreationTime` | datetime | Fecha y hora en que se inició el proceso que inició el evento |
| `InitiatingProcessFolderPath` | cadena | Carpeta que contiene el proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessParentId` | Entero | Identificador de proceso (PID) del proceso primario que generó el proceso responsable del evento |
| `InitiatingProcessParentFileName` | cadena | Nombre del proceso primario que generó el proceso responsable del evento |
| `InitiatingProcessParentCreationTime` | datetime | Fecha y hora en que se inició el elemento primario del proceso responsable del evento |
| `ReportId` | largo | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las `DeviceName` columnas y `Timestamp` |
| `AppGuardContainerId` | cadena | Identificador del contenedor virtualizado usado por Application Guard para aislar la actividad del explorador |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Entender el esquema](advanced-hunting-schema-reference.md)
