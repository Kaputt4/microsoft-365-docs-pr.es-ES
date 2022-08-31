---
title: Tabla DeviceNetworkEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de conexión de red que puede consultar en la tabla DeviceNetworkEvents del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernética, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, devicenetworkevents, NetworkCommunicationEvents, conexión de red, ip remota, ip local
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
ms.collection: m365-security-compliance
ms.topic: article
ms.openlocfilehash: cfd6fbd52aad3837ec6b330706215a4f9af745eb
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67472796"
---
# <a name="devicenetworkevents"></a>DeviceNetworkEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión



La `DeviceNetworkEvents` tabla del esquema [de búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre las conexiones de red y los eventos relacionados. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

>[!TIP]
> Para obtener información detallada sobre los tipos de eventos (`ActionType` valores) admitidos por una tabla, use la referencia de esquema integrada disponible en Defender for Cloud.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Fecha y hora en que se registró el evento. |
| `DeviceId` | `string` | Identificador único para el equipo en servicio |
| `DeviceName` | `string` | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo |
| `ActionType` | `string` | Tipo de actividad que desencadenó el evento. Consulte la [referencia de esquema en el portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obtener más información. |
| `RemoteIP` | `string` | Dirección IP a la que se ha conectado |
| `RemotePort` | `int` | Puerto TCP en el dispositivo remoto al que se estaba conectando |
| `RemoteUrl` | `string` | La dirección URL o el nombre de dominio completo (FQDN, según sus siglas en inglés) en el cual se ha estado conectado. |
| `LocalIP` | `string` | Dirección IP asignada a la máquina local utilizada durante la comunicación |
| `LocalPort` | `int` | Puerto TCP en la máquina local usada durante la comunicación |
| `Protocol` | `string` | Protocolo usado durante la comunicación |
| `LocalIPType` | `string` | Tipo de dirección IP, por ejemplo Public, Private, Reserved, Loopback, Teredo, FourToSixMapping y Broadcast |
| `RemoteIPType` | `string` | Tipo de dirección IP, por ejemplo Public, Private, Reserved, Loopback, Teredo, FourToSixMapping y Broadcast |
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
| `InitiatingProcessParentFileName` | `string` | Nombre del proceso primario que generó el proceso responsable del evento |
| `InitiatingProcessParentId` | `int` | Identificador de proceso (PID) del proceso primario que generó el proceso responsable del evento |
| `InitiatingProcessParentCreationTime` | `datetime` | Fecha y hora en que se inició el elemento primario del proceso responsable del evento |
| `InitiatingProcessAccountDomain` | `string` | Dominio de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountName` | `string` | Nombre de usuario de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountSid` | `string` | Identificador de seguridad (SID) de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountUpn` | `string` | Nombre principal de usuario (UPN) de la cuenta que ejecutó el proceso responsable del evento |
| `InitiatingProcessAccountObjectId` | `string` | Identificador de objeto de Azure AD de la cuenta de usuario que ejecutó el proceso responsable del evento |
| `InitiatingProcessIntegrityLevel` | `string` | Nivel de integridad del proceso que inició el evento. Windows asigna niveles de integridad a los procesos en función de ciertas características, como si se iniciaran desde una descarga de Internet. Estos niveles de integridad influyen en los permisos para los recursos |
| `InitiatingProcessTokenElevation` | `string` | Tipo de token que indica la presencia o ausencia de elevación de privilegios de Access Control de usuario (UAC) aplicada al proceso que inició el evento |
| `ReportId` | `long` | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp. |
| `AppGuardContainerId` | `string` | Identificador del contenedor virtualizado usado por Application Guard para aislar la actividad del explorador |
| `AdditionalFields` | `string` | Información adicional sobre el evento en formato de matriz JSON |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
