---
title: Tabla AlertEvidence en el esquema de búsqueda avanzada
description: Obtenga información sobre la información asociada a las alertas en la tabla AlertEvidence del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, AlertInfo, alerta, entidades, evidencia, archivo, dirección IP, dispositivo, máquina, usuario, cuenta
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
ms.openlocfilehash: 731d72ff5e42b85a5ddc68ed58e8914e142cea9f
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68636988"
---
# <a name="alertevidence"></a>AlertEvidence

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La `AlertEvidence` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre varias entidades (archivos, direcciones IP, direcciones URL, usuarios o dispositivos) asociada a alertas de Microsoft Defender para punto de conexión, Microsoft Defender para Office 365, Microsoft Defender for Cloud Apps y Microsoft Defender for Identity. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Fecha y hora en que se registró el evento. |
| `AlertId` | `string` | Identificador único de alerta. |
| `ServiceSource` | `string` | Producto o servicio que proporcionó la información de alerta |
| `EntityType` | `string` | Tipo de objeto, como un archivo, un proceso, un dispositivo o un usuario |
| `EvidenceRole` | `string` | Cómo participa la entidad en una alerta, que indica si se ve afectada o simplemente está relacionada |
| `EvidenceDirection` | `string` | Indica si la entidad es el origen o el destino de una conexión de red. |
| `FileName` | `string` | Nombre del archivo donde se aplicó la acción registrada |
| `FolderPath` | `string` | Carpeta que contiene el archivo al que se aplicó la acción registrada |
| `SHA1` | `string` | SHA-1 del archivo donde fue aplicada la acción registrada |
| `SHA256` | `string` | SHA-256 del archivo donde se aplicó la acción registrada. Este campo normalmente no se rellena: use la columna SHA1 cuando esté disponible. |
| `FileSize` | `int` | Tamaño del archivo en bytes |
| `ThreatFamily` | `string` | Familia de malware en la que se ha clasificado el archivo o proceso sospechoso o malintencionado en |
| `RemoteIP` | `string` | Dirección IP a la que se ha conectado |
| `RemoteUrl` | `string` | La dirección URL o el nombre de dominio completo (FQDN, según sus siglas en inglés) en el cual se ha estado conectado. |
| `AccountName` | `string` | Nombre de usuario de la cuenta |
| `AccountDomain` | `string` | Dominio de la cuenta |
| `AccountSid` | `string` | Identificador de seguridad (SID) de la cuenta |
| `AccountObjectId` | `string` | Identificador único de la cuenta en Azure Active Directory |
| `AccountUpn` | `string` | Nombre principal de usuario (UPN) de la cuenta |
| `DeviceId` | `string` | Identificador único del dispositivo en el servicio |
| `DeviceName` | `string` | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo |
| `LocalIP` | `string` | Dirección IP asignada al dispositivo local usado durante la comunicación |
| `NetworkMessageId` | `string` | Identificador único de correo electrónico, generado por Office 365 |
| `EmailSubject` | `string` | Asunto del correo electrónico. |
| `ApplicationId` | `string` | Identificador único de la aplicación |
| `Application` | `string` | Aplicación que realizó la acción registrada |
| `ProcessCommandLine` | `string` | Línea de comandos usada para crear el nuevo proceso |
| `AdditionalFields` | `string` | Información adicional sobre el evento en formato de matriz JSON |
| `RegistryKey` |`string` | Clave del Registro a la que se aplicó la acción registrada |
| `RegistryValueName` |`string` | Nombre del valor del Registro al que se aplicó la acción registrada |
| `RegistryValueData` |`string` | Datos del valor del Registro al que se aplicó la acción registrada |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
