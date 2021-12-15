---
title: Tabla DeviceLogonEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre la autenticación o los eventos de inicio de sesión en la tabla DeviceLogonEvents del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, logonevents, DeviceLogonEvents, autenticación, inicio de sesión, inicio de sesión, inicio de sesión
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: dbafb4c967bca09195277aa4c79c95dd1dc87afb
ms.sourcegitcommit: 6dcc3b039e0f0b9bae17c386f14ed2b577b453a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2021
ms.locfileid: "61530816"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión



La `DeviceLogonEvents` tabla del esquema de [búsqueda](advanced-hunting-overview.md) avanzada contiene información sobre los inicios de sesión del usuario y otros eventos de autenticación en dispositivos. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

>[!TIP]
> Para obtener información detallada acerca de los tipos de eventos ( valores) admitidos por una tabla, use la referencia de esquema integrada `ActionType` disponible en Defender para la nube.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Description |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Fecha y hora en que se registró el evento. |
| `DeviceId` | `string` | Identificador único para el equipo en servicio |
| `DeviceName` | `string` | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo |
| `ActionType` | `string` |Tipo de actividad que desencadenó el evento |
| `LogonType` | `string` | Tipo de sesión de inicio de sesión, específicamente:<br><br> - **Interactivo:** el usuario interactúa físicamente con la máquina con el teclado y la pantalla locales<br><br> - Inicios de sesión interactivos remotos **(RDP):** el usuario interactúa con el equipo de forma remota mediante Escritorio remoto, Terminal Services, Asistencia remota u otros clientes RDP<br><br> - **Red:** sesión iniciada cuando se tiene acceso al equipo mediante PsExec o cuando se tiene acceso a recursos compartidos en el equipo, como impresoras y carpetas compartidas.<br><br> - **Lote:** sesión iniciada por tareas programadas<br><br> - **Servicio:** sesión iniciada por los servicios cuando se inician<br> |
| `AccountDomain` | `string` | Dominio de la cuenta |
| `AccountName` | `string` | Nombre de usuario de la cuenta |
| `AccountSid` | `string` | Identificador de seguridad (SID) de la cuenta |
| `Protocol` | `string` | Protocolo usado durante la comunicación |
| `FailureReason` | `string` | Información que explica por qué falló la acción grabada |
| `IsLocalAdmin` | `boolean` | Indicador booleano de si el usuario es un administrador local en el equipo |
| `LogonId` | `string` | Identificador de una sesión de inicio de sesión. Este identificador es único en el mismo equipo solo entre reinicios |
| `RemoteDeviceName` | `string` | Nombre de la máquina que realizó una operación remota en la máquina afectada. Según el evento notificado, este nombre podría ser un nombre de dominio completo (FQDN), un nombre NetBIOS o un nombre de host sin información de dominio |
| `RemoteIP` | `string` | Dirección IP a la que se ha conectado |
| `RemoteIPType` | `string` | Tipo de dirección IP, por ejemplo Public, Private, Reserved, Loopback, Teredo, FourToSixMapping y Broadcast |
| `RemotePort` | `int` | Puerto TCP en el dispositivo remoto al que se estaba conectando |
| `InitiatingProcessAccountDomain` | `string` | Dominio de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountName` | `string` | Nombre de usuario de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountSid` | `string` | Identificador de seguridad (SID) de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountUpn` | `string` | Nombre principal de usuario (UPN) de la cuenta que ejecutó el proceso responsable del evento |
| ` InitiatingProcessAccountObjectId` | `string` | Azure AD de objeto de la cuenta de usuario que ejecutó el proceso responsable del evento |
| `InitiatingProcessIntegrityLevel` | `string` | Nivel de integridad del proceso que inició el evento. Windows asigna niveles de integridad a los procesos en función de determinadas características, como si se iniciaron desde una descarga de Internet. Estos niveles de integridad influyen en los permisos de los recursos |
| `InitiatingProcessTokenElevation` | `string` | Tipo de token que indica la presencia o ausencia de elevación de privilegios del Control de acceso de usuario (UAC) aplicada al proceso que inició el evento |
| `InitiatingProcessSHA1` | `string` | SHA-1 del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessSHA256` | `string` | SHA-256 del proceso (archivo de imagen) que inició el evento. Este campo normalmente no está rellenado: use la columna SHA1 cuando esté disponible |
| `InitiatingProcessMD5` | `string` | Hash MD5 del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessFileName` | `string` | Nombre del proceso que inició el evento |
| `InitiatingProcessFileSize` | `long` | Tamaño del archivo que ejecutó el proceso responsable del evento |
| `InitiatingProcessVersionInfoCompanyName` | `string` | Nombre de la compañía a partir de la información de versión del proceso (archivo de imagen) responsable del evento |
| `InitiatingProcessVersionInfoProductName` | `string` | Nombre del producto de la información de versión del proceso (archivo de imagen) responsable del evento |
| `InitiatingProcessVersionInfoProductVersion` | `string` | Versión del producto de la información de versión del proceso (archivo de imagen) responsable del evento |
| `InitiatingProcessVersionInfoInternalFileName` | `string` | Nombre de archivo interno de la información de versión del proceso (archivo de imagen) responsable del evento |
| `InitiatingProcessVersionInfoOriginalFileName` | `string` | Nombre de archivo original de la información de versión del proceso (archivo de imagen) responsable del evento |
| `InitiatingProcessVersionInfoFileDescription` | `string` | Descripción de la información de versión del proceso (archivo de imagen) responsable del evento |
| `InitiatingProcessId` | `int` | Identificador de proceso (PID) del proceso que inició el evento |
| `InitiatingProcessCommandLine` | `string` | Línea de comandos usada para ejecutar el proceso que inició el evento |
| `InitiatingProcessCreationTime` | `datetime` | Fecha y hora en que se inició el proceso que inició el evento |
| `InitiatingProcessFolderPath` | `string` | Carpeta que contiene el proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessParentId` | `int` | Identificador de proceso (PID) del proceso primario que generó el proceso responsable del evento |
| `InitiatingProcessParentFileName` | `string` | Nombre del proceso primario que generó el proceso responsable del evento |
| `InitiatingProcessParentCreationTime` | `datetime` | Fecha y hora en que se inició el elemento primario del proceso responsable del evento |
| `ReportId` | `long` | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp |
| `AppGuardContainerId` | `string` | Identificador del contenedor virtualizado usado por Application Guard para aislar la actividad del explorador |
| `AdditionalFields` | `string` | Información adicional sobre el evento en formato de matriz JSON |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
