---
title: Tabla DeviceFileEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos relacionados con archivos en la tabla DeviceFileEvents del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernética, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, filecreationevents, DeviceFileEvents, files, path, hash, sha1, sha256, md5
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
ms.topic: conceptual
ms.openlocfilehash: 3b056054f9e24b3b1a5520ec8acb6da750bbbb67
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68646031"
---
# <a name="devicefileevents"></a>DeviceFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión

La `DeviceFileEvents` tabla del esquema [de búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre la creación, modificación y otros eventos del sistema de archivos. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

>[!TIP]
> Para obtener información detallada sobre los tipos de eventos (`ActionType` valores) admitidos por una tabla, use la referencia de esquema integrada disponible en Defender for Cloud.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Fecha y hora en que se registró el evento. |
| `DeviceId` | `string` | Identificador único para el equipo en servicio |
| `DeviceName` | `string` | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo |
| `ActionType` | `string` | Tipo de actividad que desencadenó el evento. Consulte la [referencia de esquema en el portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obtener más información. |
| `FileName` | `string`| Nombre del archivo donde se aplicó la acción registrada |
| `FolderPath` | `string` | Carpeta que contiene el archivo al que se aplicó la acción registrada |
| `SHA1` | `string` | SHA-1 del archivo donde fue aplicada la acción registrada |
| `SHA256` | `string` | SHA-256 del archivo donde se aplicó la acción registrada. Este campo no suele estar rellenado; use la columna SHA1 cuando se encuentre disponible. |
| `MD5` | `string` | Hash MD5 del archivo al que se aplicó la acción registrada |
| `FileOriginUrl` | `string` | Dirección URL desde la que se descargó el archivo |
| `FileOriginReferrerUrl` | `string` | Dirección URL de la página web que vincula al archivo descargado |
| `FileOriginIP` | `string` | Dirección IP desde la que se descargó el archivo |
| `PreviousFolderPath` | `string` | Carpeta original que contiene el archivo antes de aplicar la acción registrada |
| `PreviousFileName` | `string` | Nombre original del archivo al que se cambió el nombre como resultado de la acción |
| `FileSize` | `long` | Tamaño del archivo en bytes |
| `InitiatingProcessAccountDomain` | `string` | Dominio de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountName` | string | Nombre de usuario de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountSid` | `string` | Identificador de seguridad (SID) de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountUpn` | `string` | Nombre principal de usuario (UPN) de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountObjectId` | `string` | Identificador de objeto de Azure AD de la cuenta de usuario que ejecutó el proceso responsable del evento |
| `InitiatingProcessMD5` | `string` | Hash MD5 del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessSHA1` | `string` | SHA-1 del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessSHA256` | `string` | SHA-256 del proceso (archivo de imagen) que inició el evento. Este campo no suele estar rellenado; use la columna SHA1 cuando se encuentre disponible. |
| `InitiatingProcessFolderPath` | `string` | Carpeta que contiene el proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessFileName` | `string` | Nombre del proceso que inició el evento |
| `InitiatingProcessFileSize` | `long` | Tamaño del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessVersionInfoCompanyName` | `string` | Nombre de la empresa de la información de versión del proceso (archivo de imagen) responsable del evento |
| `InitiatingProcessVersionInfoProductName` | `string` | Nombre del producto de la información de versión del proceso (archivo de imagen) responsable del evento |
|` InitiatingProcessVersionInfoProductVersion` | `string` | Versión del producto a partir de la información de versión del proceso (archivo de imagen) responsable del evento |
|` InitiatingProcessVersionInfoInternalFileName` | `string` | Nombre de archivo interno de la información de versión del proceso (archivo de imagen) responsable del evento |
| `InitiatingProcessVersionInfoOriginalFileName` | `string` | Nombre de archivo original de la información de versión del proceso (archivo de imagen) responsable del evento |
| `InitiatingProcessVersionInfoFileDescription` | `string` | Descripción de la información de versión del proceso (archivo de imagen) responsable del evento |
| `InitiatingProcessId` | `int` | Identificador de proceso (PID) del proceso que inició el evento |
| `InitiatingProcessCommandLine` | `string` | Línea de comandos usada para ejecutar el proceso que inició el evento |
| `InitiatingProcessCreationTime` | `datetime` | Fecha y hora en que se inició el proceso que inició el evento |
| `InitiatingProcessIntegrityLevel` | `string` | Nivel de integridad del proceso que inició el evento. Windows asigna niveles de integridad a los procesos en función de ciertas características, como si se iniciaran desde una descarga de Internet. Estos niveles de integridad influyen en los permisos para los recursos |
| `InitiatingProcessTokenElevation` | `string` | Tipo de token que indica la presencia o ausencia de elevación de privilegios del Control de acceso de usuario (UAC) aplicada al proceso que inició el evento |
| `InitiatingProcessParentId` | `int` | Identificador de proceso (PID) del proceso primario que generó el proceso responsable del evento |
| `InitiatingProcessParentFileName` | `string` | Nombre del proceso primario que generó el proceso responsable del evento |
| `InitiatingProcessParentCreationTime` | `datetime` | Fecha y hora en que se inició el elemento primario del proceso responsable del evento |
| `RequestProtocol` | `string` | Protocolo de red, si procede, que se usa para iniciar la actividad: Desconocido, Local, SMB o NFS |
| `RequestSourceIP` | `string` | Dirección IPv4 o IPv6 del dispositivo remoto que inició la actividad |
| `RequestSourcePort` | `string` | Puerto de origen en el dispositivo remoto que inició la actividad |
| `RequestAccountName` | `string` | Nombre de usuario de la cuenta que se usa para iniciar la actividad de forma remota |
| `RequestAccountDomain` | `string` | Dominio de la cuenta usada para iniciar la actividad de forma remota |
| `RequestAccountSid` | `string` | Identificador de seguridad (SID) de la cuenta usada para iniciar la actividad de forma remota |
| `ShareName` | `string` | Nombre de la carpeta compartida que contiene el archivo |
| `InitiatingProcessFileSize` | `long` | Tamaño del archivo que ejecutó el proceso responsable del evento |
| `SensitivityLabel` | `string` | Etiqueta aplicada a un correo electrónico, archivo u otro contenido para clasificarlo para la protección de la información |
| `SensitivitySubLabel` | `string` | Subetiqueta aplicada a un correo electrónico, archivo u otro contenido para clasificarlo para la protección de la información; subetiquetas de confidencialidad se agrupan en etiquetas de confidencialidad, pero se tratan de forma independiente |
| `IsAzureInfoProtectionApplied` | `boolean` | Indica si Azure Information Protection cifra el archivo |
| `ReportId` | `long` | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp. |
| `AppGuardContainerId` | `string` | Identificador del contenedor virtualizado usado por Protección de aplicaciones para aislar la actividad del explorador |
| `AdditionalFields` | `string` | Información adicional sobre la entidad o el evento |
>[!NOTE]
> La información de hash de archivo siempre se mostrará cuando esté disponible. Sin embargo, hay varias razones posibles por las que un SHA1, SHA256 o MD5 no se puede calcular. Por ejemplo, el archivo puede encontrarse en el almacenamiento remoto, bloqueado por otro proceso, comprimido o marcado como virtual. En estos escenarios, la información de hash de archivo aparece vacía.

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
