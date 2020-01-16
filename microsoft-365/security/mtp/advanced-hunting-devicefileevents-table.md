---
title: Tabla DeviceFileEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre eventos relacionados con archivos en la tabla DeviceFileEvents del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, filecreationevents, DeviceFileEvents, archivos, ruta de acceso Hash, SHA1, SHA256, MD5
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
ms.openlocfilehash: b772f1adccfcab52709fbedd872cb48b1c15f4e2
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210492"
---
# <a name="devicefileevents"></a>DeviceFileEvents

**Se aplica a:**
- Protección contra amenazas de Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

La `DeviceFileEvents` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre la creación, modificación y otros eventos del sistema de archivos. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `DeviceId` | string | Identificador único para el equipo en servicio |
| `DeviceName` | string | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo |
| `ActionType` | string | Tipo de actividad que ha desencadenado el evento |
| `FileName` | string | Nombre del archivo donde se aplicó la acción registrada |
| `FolderPath` | string | Carpeta que contiene el archivo al que se aplicó la acción grabada |
| `SHA1` | string | SHA-1 del archivo donde fue aplicada la acción registrada |
| `SHA256` | cadena | SHA-256 del archivo donde se aplicó la acción registrada. Este campo no suele rellenarse; use la columna SHA1 cuando esté disponible |
| `MD5` | string | Hash MD5 del archivo al que se aplicó la acción grabada |
| `FileOriginUrl` | string | Dirección URL desde la que se descargó el archivo |
| `FileOriginReferrerUrl` | string | Dirección URL de la página web que vincula al archivo descargado |
| `FileOriginIP` | string | Dirección IP desde la que se descargó el archivo |
| `InitiatingProcessAccountDomain` | string | Dominio de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountName` | string | Nombre de usuario de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountSid` | string | Identificador de seguridad (SID) de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessMD5` | string | Hash MD5 del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessSHA1` | string | SHA-1 del proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessFolderPath` | string | Carpeta que contiene el proceso (archivo de imagen) que inició el evento |
| `InitiatingProcessFileName` | string | Nombre del proceso que inició el evento |
| `InitiatingProcessId` | entero | IDENTIFICADOR de proceso (PID) del proceso que inició el evento |
| `InitiatingProcessCommandLine` | string | Línea de comandos que se usa para ejecutar el proceso que inició el evento |
| `InitiatingProcessCreationTime` | datetime | Fecha y hora en que se inició el proceso que inició el evento |
| `InitiatingProcessIntegrityLevel` | string | Nivel de integridad del proceso que inició el evento. Windows asigna niveles de integridad a los procesos en función de ciertas características, como si se iniciaron desde una descarga de Internet. Estos niveles de integridad influyen en los permisos para recursos |
| `InitiatingProcessTokenElevation` | string | Tipo de token que indica la presencia o ausencia de la elevación de privilegios de control de acceso de usuario (UAC) que se aplica al proceso que inició el evento |
| `InitiatingProcessParentId` | entero | IDENTIFICADOR de proceso (PID) del proceso primario que generó el proceso responsable del evento |
| `InitiatingProcessParentFileName` | string | Nombre del proceso primario que generó el proceso responsable del evento |
| `InitiatingProcessParentCreationTime` | datetime | Fecha y hora en que se inició el primario del proceso responsable del evento |
| `ReportId` | largo | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y timestamp. |
| `AppGuardContainerId` | string | Identificador del contenedor virtualizado que usa la protección de aplicaciones para aislar la actividad del explorador |
| `SensitivityLabel` | string | Etiqueta aplicada a un correo electrónico, archivo u otro contenido para clasificarlo para la protección de la información |
| `SensitivitySubLabel` | string | Subetiqueta aplicada a un correo electrónico, un archivo u otro contenido para clasificarlo para la protección de la información; las subetiquetas de confidencialidad se agrupan en las etiquetas de confidencialidad, pero se tratan de manera independiente |
| `IsAzureInfoProtectionApplied` | booleano | Indica si Azure Information Protection ha cifrado el archivo |

## <a name="related-topics"></a>Temas relacionados
- [Búsqueda proactiva de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Búsqueda de amenazas en dispositivos y mensajes de correo electrónico](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
