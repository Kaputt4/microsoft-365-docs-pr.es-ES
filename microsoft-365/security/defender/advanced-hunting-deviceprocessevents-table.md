---
title: Tabla DeviceProcessEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre el proceso de generación o creación de eventos en DeviceProcessEventstable del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernética, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, processcreationevents, DeviceProcessEvents, id. de proceso, línea de comandos, DeviceProcessEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.collection:
- m365-security
- tier3
ms.topic: article
ms.openlocfilehash: b28fb5b05ae0bfdb34d8793e1e0f63814c4dd597
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68089507"
---
# <a name="deviceprocessevents"></a>DeviceProcessEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión



La `DeviceProcessEvents` tabla del esquema [de búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre la creación de procesos y los eventos relacionados. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

>[!TIP]
> Para obtener información detallada sobre los tipos de eventos (`ActionType` valores) admitidos por una tabla, use la referencia de esquema integrada disponible en Defender for Cloud.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Fecha y hora en que se registró el evento. |
| `DeviceId` | `string` | Identificador único para el equipo en servicio |
| `DeviceName` | `string` | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo |
| `ActionType` | `string` | Tipo de actividad que desencadenó el evento. Consulte la [referencia de esquema en el portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obtener más información. |
| `FileName` | `string` | Nombre del archivo donde se aplicó la acción registrada |
| `FolderPath` | `string` | Carpeta que contiene el archivo al que se aplicó la acción registrada |
| `SHA1` | `string` | SHA-1 del archivo donde fue aplicada la acción registrada |
| `SHA256` | `string` | SHA-256 del archivo donde se aplicó la acción registrada. Este campo no suele estar rellenado; use la columna SHA1 cuando se encuentre disponible. |
| `MD5` | `string` | Hash MD5 del archivo al que se aplicó la acción registrada |
| `FileSize` | `long` | Tamaño del archivo en bytes |
| `ProcessVersionInfoCompanyName` | `string` | Nombre de la empresa de la información de versión del proceso recién creado |
| `ProcessVersionInfoProductName` | `string` | Nombre del producto de la información de versión del proceso recién creado |
| `ProcessVersionInfoProductVersion` | `string` | Versión del producto a partir de la información de versión del proceso recién creado |
| `ProcessVersionInfoInternalFileName` | `string` | Nombre de archivo interno de la información de versión del proceso recién creado |
| `ProcessVersionInfoOriginalFileName` | `string` | Nombre de archivo original de la información de versión del proceso recién creado |
| `ProcessVersionInfoFileDescription` | `string` | Descripción de la información de versión del proceso recién creado |
| `ProcessId` | `int` | Identificador de proceso (PID) del proceso recién creado |
| `ProcessCommandLine` | `string` | Línea de comandos usada para crear el nuevo proceso |
| `ProcessIntegrityLevel` | `string` | Nivel de integridad del proceso recién creado. Windows asigna niveles de integridad a los procesos en función de ciertas características, como si se iniciaran desde una descarga de Internet. Estos niveles de integridad influyen en los permisos para los recursos |
| `ProcessTokenElevation` | `string` | Indica el tipo de elevación de token aplicada al proceso recién creado. Valores posibles: TokenElevationTypeLimited (restringido), TokenElevationTypeDefault (estándar) y TokenElevationTypeFull (con privilegios elevados) |
| `ProcessCreationTime` | `datetime` | Fecha y hora en que se creó el proceso |
| `AccountDomain` | `string` | Dominio de la cuenta |
| `AccountName` | `string` | Nombre de usuario de la cuenta |
| `AccountSid` | `string` | Identificador de seguridad (SID) de la cuenta |
| `AccountUpn` | `string` | Nombre principal de usuario (UPN) de la cuenta |
| `AccountObjectId` | `string` | Identificador único de la cuenta en Azure AD |
| `LogonId` | `string` | Identificador de una sesión de inicio de sesión. Este identificador es único en la misma máquina solo entre reinicios |
| `InitiatingProcessAccountDomain` | `string` | Dominio de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountName` | `string` | Nombre de usuario de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountSid` | `string` | Identificador de seguridad (SID) de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountUpn` | `string` | Nombre principal de usuario (UPN) de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountObjectId` | `string` | Identificador de objeto de Azure AD de la cuenta de usuario que ejecutó el proceso responsable del evento |
| `InitiatingProcessLogonId` | `string` | Identificador de una sesión de inicio de sesión del proceso que inició el evento. Este identificador es único en la misma máquina solo entre reinicios. |
| `InitiatingProcessIntegrityLevel` | `string` | Nivel de integridad del proceso que inició el evento. Windows asigna niveles de integridad a los procesos en función de ciertas características, como si se iniciaran desde una descarga de Internet. Estos niveles de integridad influyen en los permisos para los recursos |
| `InitiatingProcessTokenElevation` | `string` | Tipo de token que indica la presencia o ausencia de elevación de privilegios de Access Control de usuario (UAC) aplicada al proceso que inició el evento |
| `InitiatingProcessSHA1` | `string` | SHA-1 del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessSHA256` | `string` | SHA-256 del proceso (archivo de imagen) que inició el evento. Este campo no suele estar rellenado; use la columna SHA1 cuando se encuentre disponible. |
| `InitiatingProcessMD5` | `string` | Hash MD5 del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessFileName` | `string` | Nombre del proceso que inició el evento |
| `InitiatingProcessFileSize` | `long` | Tamaño del archivo que ejecutó el proceso responsable del evento |
| `InitiatingProcessVersionInfoCompanyName` | `string` | Nombre de la empresa de la información de versión del proceso (archivo de imagen) responsable del evento |
| `InitiatingProcessVersionInfoProductName` | `string` | Nombre del producto de la información de versión del proceso (archivo de imagen) responsable del evento |
| `InitiatingProcessVersionInfoProductVersion` | `string` | Versión del producto a partir de la información de versión del proceso (archivo de imagen) responsable del evento |
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
| `InitiatingProcessSignerType` | `string` | Tipo de firmante de archivo del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessSignatureStatus` | `string` | Información sobre el estado de firma del proceso (archivo de imagen) que inició el evento |
| `ReportId` | `long` | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp. |
| `AppGuardContainerId` | `string` | Identificador del contenedor virtualizado usado por Protección de aplicaciones para aislar la actividad del explorador |
| `AdditionalFields` | `string` | Información adicional sobre el evento en formato de matriz JSON |


## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
