---
title: Tabla DeviceLogonEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre la autenticación o los eventos de inicio de sesión en la tabla DeviceLogonEvents del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, devicelogonevents, autenticación, inicio de sesión, inicio de sesión, LogonEvents
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
ms.openlocfilehash: c270f54c856c1ed504533c826ca884786c784549
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499151"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

La `DeviceLogonEvents` tabla del esquema de [búsqueda](advanced-hunting-overview.md) avanzada contiene información sobre los inicios de sesión del usuario y otros eventos de autenticación. Use esta referencia para crear consultas que devuelvan información de la tabla.

> [!NOTE]
> La colección de DeviceLogonEvents no se admite en Windows 7 o Windows Server 2008 R2.
> Se recomienda actualizar a Windows 10 o Windows Server 2019 para obtener una visibilidad óptima de la actividad de inicio de sesión del usuario.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea la referencia de esquema [de búsqueda avanzada](advanced-hunting-schema-reference.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `DeviceId` | cadena | Identificador único del dispositivo en el servicio |
| `DeviceName` | cadena | Nombre de dominio completo (FQDN) del dispositivo |
| `ActionType` | cadena |Tipo de actividad que desencadenó el evento |
| `AccountDomain` | cadena | Dominio de la cuenta |
| `AccountName` | cadena | Nombre de usuario de la cuenta |
| `AccountSid` | cadena | Identificador de seguridad (SID) de la cuenta |
| `LogonType` | cadena | Tipo de sesión de inicio de sesión, específicamente:<br><br> - **Interactivo:** el usuario interactúa físicamente con el dispositivo con el teclado y la pantalla locales<br><br> - Inicios de sesión interactivos remotos **(RDP):** el usuario interactúa con el dispositivo de forma remota mediante Escritorio remoto, Terminal Services, Asistencia remota u otros clientes RDP<br><br> - **Red:** sesión iniciada cuando se accede al dispositivo mediante PsExec o cuando se accede a recursos compartidos en el dispositivo, como impresoras y carpetas compartidas.<br><br> - **Lote:** sesión iniciada por tareas programadas<br><br> - **Servicio:** sesión iniciada por los servicios cuando se inician<br> |
| `LogonId` | cadena | Identificador de una sesión de inicio de sesión. Este identificador es único en el mismo dispositivo solo entre reinicios |
| `RemoteDeviceName` | cadena | Nombre del dispositivo que realizó una operación remota en el dispositivo afectado. Según el evento notificado, este nombre podría ser un nombre de dominio completo (FQDN), un nombre NetBIOS o un nombre de host sin información de dominio |
| `RemoteIP` | cadena | Dirección IP a la que se ha conectado |
| `RemoteIPType` | cadena | Tipo de dirección IP, por ejemplo Public, Private, Reserved, Loopback, Teredo, FourToSixMapping y Broadcast |
| `RemotePort` | Entero | Puerto TCP en el dispositivo remoto al que se estaba conectando |
| `AdditionalFields` | cadena | Información adicional sobre el evento en formato de matriz JSON |
| `InitiatingProcessAccountDomain` | cadena | Dominio de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountName` | cadena | Nombre de usuario de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountSid` | cadena | Identificador de seguridad (SID) de la cuenta que ejecutó el proceso responsable del evento |
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
| `IsLocalAdmin` | boolean | Indicador booleano de si el usuario es un administrador local en el dispositivo |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Entender el esquema](advanced-hunting-schema-reference.md)
