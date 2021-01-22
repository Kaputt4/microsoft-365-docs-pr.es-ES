---
title: Tabla DeviceFileEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre eventos relacionados con archivos en la tabla DeviceFileEvents del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, filecreationevents, DeviceFileEvents, archivos, ruta de acceso, hash, sha1, sha256, md5
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: cb51d9b94cc500361f836f7ba8bc4fc290436805
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931331"
---
# <a name="devicefileevents"></a>DeviceFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La `DeviceFileEvents` tabla del esquema de [búsqueda](advanced-hunting-overview.md) avanzada contiene información sobre la creación, modificación y otros eventos del sistema de archivos. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

>[!TIP]
> Para obtener información detallada acerca de los tipos de eventos (valores) admitidos por una tabla, use la referencia de esquema integrada `ActionType` disponible en el centro de seguridad. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `DeviceId` | cadena | Identificador único para el equipo en servicio |
| `DeviceName` | cadena | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo |
| `ActionType` | cadena | Tipo de actividad que desencadenó el evento. Consulta la [referencia del esquema del portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obtener más información |
| `FileName` | cadena | Nombre del archivo donde se aplicó la acción registrada |
| `FolderPath` | cadena | Carpeta que contiene el archivo al que se aplicó la acción grabada |
| `SHA1` | cadena | SHA-1 del archivo donde fue aplicada la acción registrada |
| `SHA256` | cadena | SHA-256 del archivo donde se aplicó la acción registrada. Este campo no suele estar rellenado; use la columna SHA1 cuando se encuentre disponible. |
| `MD5` | cadena | Hash MD5 del archivo al que se aplicó la acción grabada |
| `FileOriginUrl` | string | Dirección URL desde la que se descargó el archivo |
| `FileOriginReferrerUrl` | string | Dirección URL de la página web que vincula al archivo descargado |
| `FileOriginIP` | string | Dirección IP desde la que se descargó el archivo |
| `InitiatingProcessAccountDomain` | string | Dominio de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountName` | string | Nombre de usuario de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountSid` | string | Identificador de seguridad (SID) de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessMD5` | string | Hash MD5 del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessSHA1` | string | SHA-1 del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessSHA256` | string | SHA-256 del proceso (archivo de imagen) que inició el evento. Este campo no suele estar rellenado; use la columna SHA1 cuando se encuentre disponible. |
| `InitiatingProcessFolderPath` | cadena | Carpeta que contiene el proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessFileName` | string | Nombre del proceso que inició el evento |
| `InitiatingProcessId` | entero | Identificador de proceso (PID) del proceso que inició el evento |
| `InitiatingProcessCommandLine` | string | Línea de comandos usada para ejecutar el proceso que inició el evento |
| `InitiatingProcessCreationTime` | datetime | Fecha y hora en que se inició el proceso que inició el evento |
| `InitiatingProcessIntegrityLevel` | string | Nivel de integridad del proceso que inició el evento. Windows asigna niveles de integridad a los procesos en función de determinadas características, como si se iniciaron desde una descarga de Internet. Estos niveles de integridad influyen en los permisos para los recursos |
| `InitiatingProcessTokenElevation` | string | Tipo de token que indica la presencia o ausencia de elevación de privilegios del Control de acceso de usuario (UAC) aplicada al proceso que inició el evento |
| `InitiatingProcessParentId` | entero | Identificador de proceso (PID) del proceso primario que generó el proceso responsable del evento |
| `InitiatingProcessParentFileName` | string | Nombre del proceso primario que generó el proceso responsable del evento |
| `InitiatingProcessParentCreationTime` | datetime | Fecha y hora en que se inició el elemento principal del proceso responsable del evento |
| `RequestProtocol` | string | Protocolo de red, si procede, usado para iniciar la actividad: Desconocido, Local, SMB o NFS |
| `ShareName` | string | Nombre de la carpeta compartida que contiene el archivo |
| `RequestSourceIP` | string | Dirección IPv4 o IPv6 del dispositivo remoto que inició la actividad |
| `RequestSourcePort` | string | Puerto de origen en el dispositivo remoto que inició la actividad |
| `RequestAccountName` | string | Nombre de usuario de la cuenta usada para iniciar la actividad de forma remota |
| `RequestAccountDomain` | string | Dominio de la cuenta usada para iniciar la actividad de forma remota |
| `RequestAccountSid` | string | Identificador de seguridad (SID) de la cuenta usada para iniciar la actividad de forma remota |
| `ReportId` | largo | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp |
| `AppGuardContainerId` | string | Identificador del contenedor virtualizado usado por la Protección de aplicaciones para aislar la actividad del explorador |
| `SensitivityLabel` | string | Etiqueta aplicada a un correo electrónico, archivo u otro contenido para clasificarla para la protección de la información |
| `SensitivitySubLabel` | string | Subetiqueta aplicada a un correo electrónico, archivo u otro contenido para clasificarlo para la protección de la información; las subetiquetas de confidencialidad se agrupan en etiquetas de confidencialidad, pero se tratan de forma independiente |
| `IsAzureInfoProtectionApplied` | boolean | Indica si Azure Information Protection cifra el archivo. |

>[!NOTE]
> La información de hash de archivo siempre se mostrará cuando esté disponible. Sin embargo, hay varias razones posibles por las que no se puede calcular un SHA1, SHA256 o MD5. Por ejemplo, el archivo puede estar ubicado en el almacenamiento remoto, bloqueado por otro proceso, comprimido o marcado como virtual. En estos escenarios, la información de hash del archivo aparece vacía.

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
