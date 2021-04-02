---
title: Tabla DeviceFileEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos relacionados con archivos en la tabla DeviceFileEvents del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, filecreationevents, DeviceFileEvents, archivos, ruta de acceso, hash, sha1, sha256, md5
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 6528d25b385a2b4eafc408cbfb6609372a6688de
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498583"
---
# <a name="devicefileevents"></a>DeviceFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La `DeviceFileEvents` tabla del esquema de [búsqueda](advanced-hunting-overview.md) avanzada contiene información sobre la creación, modificación y otros eventos del sistema de archivos. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

>[!TIP]
> Para obtener información detallada acerca de los tipos de eventos ( valores) admitidos por una tabla, use la referencia de esquema integrada `ActionType` disponible en el centro de seguridad.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `DeviceId` | cadena | Identificador único para el equipo en servicio |
| `DeviceName` | cadena | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo |
| `ActionType` | cadena | Tipo de actividad que desencadenó el evento. Vea la [referencia de esquema en el portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obtener más información |
| `FileName` | cadena | Nombre del archivo donde se aplicó la acción registrada |
| `FolderPath` | cadena | Carpeta que contiene el archivo al que se aplicó la acción grabada |
| `SHA1` | cadena | SHA-1 del archivo donde fue aplicada la acción registrada |
| `SHA256` | cadena | SHA-256 del archivo donde se aplicó la acción registrada. Este campo no suele estar rellenado; use la columna SHA1 cuando se encuentre disponible. |
| `MD5` | cadena | Hash MD5 del archivo al que se aplicó la acción grabada |
| `FileOriginUrl` | cadena | DIRECCIÓN URL desde la que se descargó el archivo |
| `FileOriginReferrerUrl` | cadena | Dirección URL de la página web que vincula al archivo descargado |
| `FileOriginIP` | cadena | Dirección IP desde la que se descargó el archivo |
| `PreviousFolderPath` | cadena | Carpeta original que contiene el archivo antes de aplicar la acción grabada |
| `PreviousFileName` | cadena | Nombre original del archivo cuyo nombre se cambió como resultado de la acción |
| `FileSize` | largo | Tamaño del archivo en bytes |
| `InitiatingProcessAccountDomain` | cadena | Dominio de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountName` | cadena | Nombre de usuario de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountSid` | cadena | Identificador de seguridad (SID) de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountUpn` | cadena | Nombre principal de usuario (UPN) de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountObjectId` | cadena | Identificador de objeto de Azure AD de la cuenta de usuario que ejecutó el proceso responsable del evento |
| `InitiatingProcessMD5` | cadena | Hash MD5 del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessSHA1` | cadena | SHA-1 del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessSHA256` | cadena | SHA-256 del proceso (archivo de imagen) que inició el evento. Este campo no suele estar rellenado; use la columna SHA1 cuando se encuentre disponible. |
| `InitiatingProcessFolderPath` | cadena | Carpeta que contiene el proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessFileName` | cadena | Nombre del proceso que inició el evento |
| `InitiatingProcessFileSize` | largo | Tamaño del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessVersionInfoCompanyName` | cadena | Nombre de la compañía a partir de la información de versión del proceso (archivo de imagen) responsable del evento |
| `InitiatingProcessVersionInfoProductName` | cadena | Nombre del producto de la información de versión del proceso (archivo de imagen) responsable del evento |
|` InitiatingProcessVersionInfoProductVersion` | cadena | Versión del producto de la información de versión del proceso (archivo de imagen) responsable del evento |
|` InitiatingProcessVersionInfoInternalFileName` | cadena | Nombre de archivo interno de la información de versión del proceso (archivo de imagen) responsable del evento |
| `InitiatingProcessVersionInfoOriginalFileName` | cadena | Nombre de archivo original de la información de versión del proceso (archivo de imagen) responsable del evento |
| `InitiatingProcessVersionInfoFileDescription` | cadena | Descripción de la información de versión del proceso (archivo de imagen) responsable del evento |
| `InitiatingProcessId` | Entero | Identificador de proceso (PID) del proceso que inició el evento |
| `InitiatingProcessCommandLine` | cadena | Línea de comandos usada para ejecutar el proceso que inició el evento |
| `InitiatingProcessCreationTime` | datetime | Fecha y hora en que se inició el proceso que inició el evento |
| `InitiatingProcessIntegrityLevel` | cadena | Nivel de integridad del proceso que inició el evento. Windows asigna niveles de integridad a procesos basados en determinadas características, como si se iniciaron desde una descarga de Internet. Estos niveles de integridad influyen en los permisos de los recursos |
| `InitiatingProcessTokenElevation` | cadena | Tipo de token que indica la presencia o ausencia de elevación de privilegios del Control de acceso de usuario (UAC) aplicada al proceso que inició el evento |
| `InitiatingProcessParentId` | Entero | Identificador de proceso (PID) del proceso primario que generó el proceso responsable del evento |
| `InitiatingProcessParentFileName` | cadena | Nombre del proceso primario que generó el proceso responsable del evento |
| `InitiatingProcessParentCreationTime` | datetime | Fecha y hora en que se inició el elemento primario del proceso responsable del evento |
| `RequestProtocol` | cadena | Protocolo de red, si procede, usado para iniciar la actividad: Desconocido, Local, SMB o NFS |
| `RequestSourceIP` | cadena | Dirección IPv4 o IPv6 del dispositivo remoto que inició la actividad |
| `RequestSourcePort` | cadena | Puerto de origen en el dispositivo remoto que inició la actividad |
| `RequestAccountName` | cadena | Nombre de usuario de la cuenta usada para iniciar la actividad de forma remota |
| `RequestAccountDomain` | cadena | Dominio de la cuenta usada para iniciar la actividad de forma remota |
| `RequestAccountSid` | cadena | Identificador de seguridad (SID) de la cuenta usada para iniciar la actividad de forma remota |
| `ShareName` | cadena | Nombre de la carpeta compartida que contiene el archivo |
| `InitiatingProcessFileSize` | largo | Tamaño del archivo que ejecutó el proceso responsable del evento |
| `SensitivityLabel` | cadena | Etiqueta aplicada a un correo electrónico, archivo u otro contenido para clasificarlo para la protección de la información |
| `SensitivitySubLabel` | cadena | Sublabel applied to an email, file, or other content to classify it for information protection; las subetiquetas de confidencialidad se agrupan bajo etiquetas de confidencialidad, pero se tratan de forma independiente |
| `IsAzureInfoProtectionApplied` | boolean | Indica si azure Information Protection cifra el archivo |
| `ReportId` | largo | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp. |
| `AppGuardContainerId` | cadena | Identificador del contenedor virtualizado usado por Application Guard para aislar la actividad del explorador |
| `AdditionalFields` | cadena | Información adicional sobre la entidad o el evento |
>[!NOTE]
> La información de hash de archivo siempre se mostrará cuando esté disponible. Sin embargo, hay varias razones posibles por las que no se puede calcular un SHA1, SHA256 o MD5. Por ejemplo, el archivo puede estar ubicado en almacenamiento remoto, bloqueado por otro proceso, comprimido o marcado como virtual. En estos escenarios, la información de hash del archivo aparece vacía.

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
